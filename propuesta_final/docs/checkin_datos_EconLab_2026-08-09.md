# Check-in de datos — base de mercados laborales locales (Banxico/EconLab)

**Fecha:** 2026-08-09
**Fuente:** `propuesta_final/datos/Banxico_EconLab_LLM_nota_metodologica_2024-04.pdf` — *Database on local labor markets in Mexico: Methodological note*, Banco de México, actualizada abril 2024.
**Contrasta con:** `proceso_estimacion_epsilonD_2026-08-07.md` (el diseño de estimación).

> **Nota de acervo.** El otro PDF subido (`LLM_1`) resultó ser el mismo documento Aldeco et al. (2024) que ya estaba en `papers/00_nucleo_tema/{2BB5ECD9-…}.pdf` — texto idéntico página por página. Se eliminó el duplicado. El nombre críptico se conserva porque está referenciado en cuatro documentos del repo.

---

## 0. Veredicto: **Q3 queda resuelto, y a favor de EconLab por más margen del que suponía el esbozo**

La recomendación era "INEGI/EconLab como espina + IPUMS como plantilla de armonización". La nota metodológica confirma la primera mitad y **vuelve casi redundante la segunda**: Banxico ya armonizó las variables entre olas censales y documenta cada decisión de armonización en el diccionario de datos. No necesitas IPUMS como plantilla; baja a *cross-check* opcional y a insumo solo si activas la robustez de la red EE.UU.

Tres razones concretas, todas nuevas respecto de lo que asumía el esbozo:

1. **El identificador de mercado laboral es nativo del microdato** (`MERCADO_TRABAJO_LABORAL`, variable #66 en personas y #42 en hogares). El paso 2 del §8 —"crosswalk municipio→777"— deja de existir como tarea.
2. **Los salarios residualizados por composición ya están construidos.** El §3.1 los pedía como "deseable"; existen como `SalResMTL_N/0/1.dta`, "residual average income after controlling for education and age", y además separados por sexo.
3. **La clasificación transable / no transable ya existe** dentro de los archivos Bartik. Esto cierra el pendiente #3 del §9.

---

## 1. Lo que ya está construido (no lo hagas tú)

| Ingrediente del diseño | Dónde está | Comentario |
|---|---|---|
| ID de los 777 mercados | `MERCADO_TRABAJO_LABORAL` (micro, individual y hogar) | Nativo. Elimina el paso de crosswalk |
| Δln L, Δln w a nivel mercado | `Demograficos_Nivel.dta` y **`DemograficosLogs.dta`** | El segundo ya viene en logaritmos |
| Salario residualizado (educación + edad) | `SalResMTL_N.dta` (total), `_0` (mujeres), `_1` (hombres) | Lo "deseable" de §3.1, hecho y por sexo |
| Ingreso individual residualizado | `SalariosResiduales.dta`, `Ingresos_Pob15s.dta` | Nivel individuo-año, por si quieres rehacer la residualización |
| **Bartik industrial como control** (§3.2 #3) | `LongBartikNacional.dta` (+ `Hombre0`/`Hombre1`) | En dos formas: usando cambios nacionales de empleo y de salarios |
| **Transables / no transables / manufactura** (§3.3) | `LongBartikNacional_Trade1` (transables), `_Trade0` (no transables), `_Manuf` | Adoptas la definición de Banxico ⇒ tu tabla queda comparable renglón a renglón con la del mimeo |
| Shares industriales 1990 por mercado | `WideBartikNacional.dta` — trae "share of employment in 1990 in the local labor market" por industria | Es el `s_lk,1990` de la eq. (2) de Aldeco et al., ya calculado |
| Crecimiento nacional por industria | `Tasa_Crecimiento_Industria_Nacional.dta` | El `g^G_kt` de la misma ecuación |
| Proxy de informalidad | `Informalidad.dta` (agregado); en micro: `LLAVE_DHSERSAL`, `LLAVE_SERSALUD`, `LLAVE_PRESTACION`, `LLAVE_SITTRA` | Cuatro proxies distintos, no uno |
| Pobreza / vulnerabilidad | `Vulnerabilidad.dta` (líneas Coneval) | Para controles o heterogeneidad |
| Convergencia / desigualdad entre mercados | `Convergencia_Nivel_MTL_*.dta` | Contexto descriptivo |
| Código de construcción | Carpeta `Códigos` — **Stata**, genera los agregados desde el microdato | Puedes auditar y extender su código en vez de reinventarlo |

---

## 2. Lo que tienes que construir tú — el instrumento

La base **no trae ningún instrumento de oferta**. Eso sigue siendo tuyo, y es justo la contribución. Las materias primas están todas en el microdato individual:

| Pieza | Variable | Nota |
|---|---|---|
| Shares de enclave `s_ol,1990` | `LLAVE_ENTIDAD_NAC` (estado de nacimiento) × `MERCADO_TRABAJO_LABORAL`, ola 1990, ponderado por `FACTOR_EXP` | Exactamente los 32 orígenes que fija §2.1 |
| Origen más fino (la "alternativa a evaluar" de §2.1) | `LLAVE_MUNICIPIO_RES5A` (municipio de residencia hace 5 años) | Habilita la desagregación para el marco BHJ |
| Push `g_ot` | `LLAVE_ENTIDAD_RES5A` / `LLAVE_MUNICIPIO_RES5A` | Ver la advertencia de §3.1 abajo |
| Motivo de migración | `LLAVE_CAUSAMIGRACION` | Permite separar push de pull *dentro de los datos*, no solo por narrativa. No estaba contemplado en el esbozo |
| Red EE.UU. (robustez en reserva) | `LLAVE_PAIS_NAC`, `LLAVE_PAIS_RES5A` | Parte de la robustez transfronteriza se puede hacer aquí mismo |

---

## 3. Los tres hallazgos que cambian el diseño

### 3.1 ⚠️ La migración se mide a **5 años**, el diseño corre en diferencias de **10**

`LLAVE_ENTIDAD_RES5A` y `LLAVE_MUNICIPIO_RES5A` capturan residencia *cinco* años antes del censo. Tu diseño usa diferencias largas decenales (§1). Desajuste real, no cosmético:

- El flujo observado cubre la **segunda mitad** de cada década. Quien migró en el año 1 y se quedó no se cuenta como migrante; quien migró y regresó tampoco.
- Consecuencia: el shift `g_ot` construido con `RES5A` mide media década y **subestima** el flujo de la década completa, probablemente con error de medida no clásico (peor en orígenes con migración de retorno).

Dos salidas, y hay que elegir una explícitamente:

- **(a) Asimétrica (recomendada):** shares desde `ENTIDAD_NAC` —el stock de nacidos cubre toda la historia migratoria y es el objeto que Card (2001) usa— y shift desde `RES5A`, reconociendo que es un flujo de media década y reescalando o dejándolo en unidades declaradas.
- **(b) Cambiar de stock:** construir tanto shares como shift desde diferencias del *stock* por `ENTIDAD_NAC` entre olas. Coherente en horizonte, pero mete migración de retorno y mortalidad diferencial en el shift.

**Esto es una decisión de diseño nueva. El esbozo del 2026-08-07 no la contempla y hay que agregarla al §2.2.**

### 3.2 ★ Existe municipio de **trabajo**, no solo de residencia — y eso desbloquea el diseño de Dustmann-Schönberg-Stuhler

`LLAVE_ENTIDAD_TRABAJO`, `LLAVE_MUNICIPIO_TRABAJO`, `LLAVE_TIETRASLADO_TRABAJO` (tiempo de traslado) y `LLAVE_MEDTRASLADO_TRABAJO` están en el microdato individual. Dos consecuencias:

1. **Puedes construir la matriz de commuting tú mismo** — la `W` del Bloque 6 de la guía, sin depender de que te la den.
2. **Puedes identificar a quien trabaja en el mercado `l` pero reside fuera de `l`.** Ese es *literalmente* el diseño de Dustmann-Schönberg-Stuhler (2017 QJE), el pick #1 de tu Guía v3: gente que aporta oferta laboral al destino sin aportar demanda de consumo. Hasta ahora tu respuesta al canal "migrantes = consumidores" era **aproximarlo** con la restricción al sector transable (§3.3, §6.4). Ahora puedes hacerlo **directo**.

Es la mejora más grande que sale de esta lectura: §6.4 pasa de argumento defensivo a diseño de identificación.

### 3.3 La ola **2015** (Encuesta Intercensal) está incluida

Las olas son 1990, 2000, 2010, **2015**, 2020. No cambia el diseño principal (decenal, dos periodos), pero da un punto intermedio para verificar tendencias entre 2010 y 2020, y una muestra extra si el poder estadístico aprieta — que es justo el pendiente #4 del §9.

---

## 4. Detalles técnicos que hay que respetar

- **Top-coding del ingreso.** En 2000, 2010, 2015 y 2020 el valor `999998` significa "999,999 pesos mensuales o más". En **1990 no**: ahí `999998` es un nivel real medido, y el tope se recodificó como `99999999`. Afecta medias y percentiles altos, no la mediana. Confirma que la elección de mediana en §3.1 era la correcta; si reportas p75 como robustez, trátalo con cuidado y de forma distinta en 1990.
- **Clasificación industrial = SCIAN 2000** (`ACTIVIDAD_ECONOMICA_INEGI`, campo de texto; `LLAVE_ACTECONOMICA` es la versión catalogada). La definición operativa de "transable" tiene que anclarse a SCIAN 2000.
- **Ingreso 2015 y 2020**: por un cambio de metodología, el detalle de ingreso se asignó **al jefe de hogar**. Si usas ingreso individual en esas olas, verifica que no estés arrastrando ingreso de hogar disfrazado de individual.
- **1990 no separa variables de persona y de vivienda**; Banxico las emparejó usando las descripciones de los cuestionarios de otras olas. El año base de tus shares es justo 1990 — vale la pena leer la hoja de armonización antes de confiar.
- **Identificadores no son estables por construcción**: `ID_PERSONA` e `ID_VIVIENDA` fueron reasignados secuencialmente en varias olas. No sirven para seguir gente entre censos (no es panel), cosa que el diseño de diferencias largas no necesita, pero conviene tenerlo claro.
- **Sin valores nulos**: todas las variables con catálogo tienen categoría "No especificado". Ojo: eso significa que los faltantes vienen **codificados**, no vacíos. Hay que tratarlos explícitamente.

---

## 5. Lo que falta verificar (en el diccionario de datos, no en esta nota)

1. **¿`RES5A` existe en las cinco olas, incluida 1990?** El censo de 1990 preguntó residencia en 1985, pero la cobertura por variable está en la hoja "Cobertura" del Excel del diccionario, no en la nota metodológica. **Es lo primero que hay que abrir.**
2. **¿El id de los 777 mercados es constante entre olas** o se redefine por ola? Todo el diseño de diferencias largas depende de que sea el mismo.
3. **¿Los agregados cubren todas las olas o solo 2000+?** El Bartik de Aldeco et al. está disponible de 2000 en adelante; si los demás agregados heredan esa restricción, el placebo 1990→2000 del §6.1 hay que armarlo desde microdato.
4. **Acceso.** La nota dice que los datos se piden a `econlab@banxico.org.mx`, y una de las figuras del catálogo lleva la marca **"INTERNA – USO LIMITADO"**. Es posible que haya proceso de solicitud y no descarga abierta. **Esto es lo que hay que resolver esta semana**, porque marca el calendario de todo lo demás — y conviene mandar en el mismo correo la petición del mimeo de oferta.

---

## 6. Efecto sobre el plan de ejecución (§8 del esbozo)

| Paso original | Estado nuevo |
|---|---|
| 1. Confirmar Q3 y bajar base | **Q3 resuelto.** Queda solo el acceso — ver §5.4 |
| 2. Crosswalk municipio→777 + shares | **El crosswalk desaparece.** Solo quedan los shares |
| 3. Push + instrumento | Sin cambio, **pero antes hay que decidir §3.1 (5 vs 10 años)** |
| 4–5. Primera etapa, 2SLS, tres columnas | Más rápido: transables/no transables ya vienen definidos |
| 6. Inferencia AKM + Rotemberg | Sin cambio |
| 7. Placebo + desplazamiento de nativos | Sin cambio |
| 8. Dos niveles de agregación + vecinos | **Más fácil**: la matriz de commuting es construible con `MUNICIPIO_TRABAJO` |
| — | **Paso nuevo:** diseño de *commuters* estilo DSS (§3.2). Debería subir a prioridad alta: ataca la amenaza principal con el diseño canónico |

---

*Ver [[project-tesis-elasticidad-demanda-local]].*
