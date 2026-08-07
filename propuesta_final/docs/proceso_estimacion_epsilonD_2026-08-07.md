# Proceso de estimación de ε_D — shift-share de enclaves migratorios internos (MX)

**Fecha:** 2026-08-07 · Para: Carlos Ramírez (ITAM)
**Ejecuta el paso 2 de** `ruta_empirica_shift_share_migracion_2026-07-23.md` §7.
**Lecturas de apoyo:** `GUIA_LECTURA_top_v3_2026-08-07.md` (Bloque 1 = el diseño; Bloque 6 = amenazas espaciales).

> **Supuesto declarado (Q3 sin confirmar).** Este esbozo asume la recomendación de §6 de la nota de ruta: **INEGI/EconLab como espina** (municipio completo + id nativo de los 777 mercados + mismo *source* que el mimeo de oferta), con **IPUMS International solo como plantilla de armonización** de las variables de migración entre olas censales. Los dos únicos puntos donde la alternativa cambiaría algo están marcados con **[Q3]**. Si eliges IPUMS-primaria, se reescriben §2.1 y §3.1; el resto del diseño no se mueve.

---

## 0. El objeto y la ecuación

Curva de demanda de trabajo local, en diferencias largas:

$$\Delta \ln L_{lt} = \alpha_t - |\varepsilon_D| \, \Delta \ln w_{lt} + \eta_{lt}$$

Como el instrumento mueve la **oferta**, se estima la **relación inversa** y se invierte al final:

$$\boxed{\;\Delta \ln w_{lt} = \beta \, \Delta \ln L_{lt} + X_{lt}'\gamma + \delta_t + \epsilon_{lt}, \qquad |\varepsilon_D| = 1/|\beta| \;}$$

**Signo esperado: β < 0.** Un empujón exógeno de oferta baja el salario a lo largo de la curva de demanda. Reportar siempre β y $|\varepsilon_D|$ juntos: el referee quiere ver la transformación explícita, y el error de reportar β como si fuera la elasticidad es común.

### Advertencia de magnitud (leer antes de calibrar expectativas)

La guía v3, Bloque 2, ancla $|\varepsilon_D| \approx 0.25\text{–}0.7$ (Lichter-Peichl-Siegloch 2015). **Ese ancla no aplica directamente a tu número, y conviene tenerlo claro desde antes de correr nada.**

- LPS mide la elasticidad **propia, a nivel firma/industria**, típicamente con producto (cuasi-)constante.
- Tú vas a medir una elasticidad **local, de largo plazo, en equilibrio parcial espacial**. Ahí el ajuste no ocurre solo vía salario: entra capital, cambia la composición industrial (absorción tipo Rybczynski) y salen nativos.
- Consecuencia mecánica: la literatura de inmigración en mercados locales encuentra respuestas salariales **pequeñas** ($|\beta|$ del orden de 0.1–0.3), lo que implica $|\varepsilon_D|$ de **3 a 10** — un orden de magnitud arriba del ancla LPS.

**Esto no es un bug, es el resultado.** Pero obliga a dos cosas: (i) nombrar explícitamente en la propuesta que $\varepsilon_D^{\text{local}} \neq \varepsilon_D^{\text{industria}}$, y (ii) reservar el ancla LPS para la **capa de modelo** (el σ que recuperas à la Raval), no para el número reducido. Es exactamente la brecha que MRRH (V1) formaliza y que Oberfield-Raval (2021) enseña a cruzar. Si tu $|\varepsilon_D|$ sale en 0.4 deberías desconfiar, no celebrar.

---

## 1. Unidad, periodos y muestra

| Elemento | Decisión | Nota |
|---|---|---|
| **Unidad** | 777 mercados laborales locales (Aldeco et al. 2024) | id nativo en la base EconLab |
| **Frecuencia** | Censal decenal: 1990, 2000, 2010, 2020 | ⇒ **diferencias largas**, no panel anual |
| **Año base de shares** | **1990** (el más lejano disponible) | Jaeger-Ruist-Stuhler exige distancia máxima |
| **Periodos estimados** | **2000→2010** y **2010→2020** | 2 periodos × 777 = **1,554 obs** |
| **Periodo 1990→2000** | **NO** entra en la principal | Se usa como **pre-tendencia/placebo** (§6.1): los shares de 1990 vienen del mismo *stock* cuyo cambio se mediría — solapamiento mecánico |

**Consecuencia de interpretación:** el diseño decenal entrega una elasticidad de **largo plazo**. Es la respuesta correcta a Jaeger-Ruist-Stuhler solo a medias: ellos advierten que el estimador *mezcla* corto y largo plazo. Con dos periodos de 10 años no puedes separarlos limpiamente — hay que decirlo, y compensarlo con el diseño de dos instrumentos (§6.2).

---

## 2. Construcción del instrumento

### 2.1 Shares de enclave (los pesos) **[Q3]**

Para cada origen $o$ y mercado destino $l$:

$$s_{ol,1990} = \frac{\text{personas nacidas en } o \text{ que residen en } l \text{ en 1990}}{\text{total de personas nacidas en } o \text{ que residen fuera de } o \text{ en 1990}}, \qquad \sum_l s_{ol,1990} = 1$$

- **Origen $o$ = entidad federativa de nacimiento** (32 orígenes). Es lo que el censo capta de forma consistente en las cuatro olas.
  - *Alternativa a evaluar:* origen a nivel municipio o zona de origen (más orígenes ⇒ mejor para el marco BHJ, que quiere *muchos* shifts cuasi-aleatorios). Costo: shares mucho más ruidosos y celdas vacías. **Recomendación: empezar con 32 estados, y probar la desagregación como robustez**, reportando cómo cambian los pesos de Rotemberg.
- **[Q3]** Con espina INEGI: se construye del microdato censal 1990 usando `entidad de nacimiento` + municipio de residencia → colapsar a los 777 vía el crosswalk público. Con IPUMS-primaria: `BPLMX` + geografía IPUMS, con la pérdida de municipios agregados por confidencialidad.
- **Cross-check obligatorio:** replicar los shares en ambas fuentes para una ola y comparar la distribución. Si divergen más de lo tolerable en mercados chicos, eso decide Q3 de facto.

### 2.2 El shift (push nacional del origen)

$$g_{ot} = \frac{\text{emigrantes netos que salen de } o \text{ entre } t \text{ y } t{+}10}{\text{población de } o \text{ en } t}$$

- Construir **leave-one-out**: al calcular $g_{ot}$ para predecir el flujo hacia $l$, excluir a los migrantes cuyo destino fue $l$. Sin esto el instrumento contiene mecánicamente el resultado de $l$. Es la misma convención que usa Aldeco et al. en su Bartik industrial (eq. 2, p. 11).
- **Fuente de identificación del push:** condiciones de expulsión en el origen, no atracción del destino. Reportar la correlación de $g_{ot}$ con shocks de origen (sequía/precipitación, colapso de precios agrícolas, violencia) como evidencia narrativa de que el push es exógeno al destino. Monras (2020) es la plantilla de cómo se argumenta esto con datos mexicanos.

### 2.3 El instrumento

$$Z_{lt} = \frac{1}{L_{l,t}}\sum_{o} s_{ol,1990}\; \cdot\; g_{ot}^{(-l)} \cdot P_{ot}$$

Es decir: flujo migratorio **predicho** hacia $l$, normalizado por el empleo (o población en edad de trabajar) de base del mercado. La normalización importa para la interpretación —$Z$ queda en unidades de "puntos porcentuales de la fuerza laboral local"— y para que β sea comparable con la literatura.

---

## 3. Especificación y controles

### 3.1 Variables dependientes **[Q3]**

- $\Delta \ln w_{lt}$: log del salario **mediano** (robusto a colas) y, en robustez, el promedio y percentiles 25/50/75. Deseable: **residualizado por composición** (educación, edad, sexo) — regresión individual de primera etapa, luego promediar residuos por mercado. Es lo que evita que el efecto composicional del propio flujo migratorio se lea como efecto de precio.
- $\Delta \ln L_{lt}$: empleo total del mercado.
- **[Q3]** Ambas salen directas de la base agregada de EconLab; con IPUMS habría que reconstruirlas y perder la comparabilidad con el mimeo de oferta.

### 3.2 Controles $X_{lt}$

1. **Efectos fijos de periodo** $\delta_t$ — obligatorios.
2. **Efectos fijos de región** (o estado) — absorben tendencias regionales persistentes; reportar con y sin, porque comen mucha de tu variación.
3. **★ El Bartik industrial de Aldeco et al. (eq. 2, p. 11) como control.** Este es el movimiento más elegante del diseño: incluir el *shifter de demanda* ya pre-construido en la base purga los shocks de demanda local, que son justo la amenaza a la restricción de exclusión del *shifter de oferta*. Además te posiciona explícitamente frente al mimeo companion: ellos usan ese Bartik como instrumento, tú lo usas como control.
4. **Composición industrial base (1990)** y **composición educativa base** — la crítica JRS es que los enclaves correlacionan con estructura económica persistente.
5. **Crecimiento salarial y de empleo del pre-periodo** — control directo de tendencias previas.
6. **Urbanización / tamaño de mercado** base.

### 3.3 La restricción al sector transable (decisión Q2, §5 de la nota de ruta)

**Especificación principal: transables.** Manufactura + agricultura de exportación. Razón: la demanda de trabajo transable depende de precios nacionales/mundiales, no del consumo local ⇒ el canal "migrantes = consumidores" (que sesga $|\varepsilon_D|$ al alza) casi desaparece.

Reportar **tres columnas siempre juntas**: (a) total, (b) transable, (c) no transable. La comparación *es* el test del canal consumidor: si (c) da una demanda sistemáticamente más elástica que (b), el mecanismo está ahí y tu restricción está justificada empíricamente, no solo por argumento. Esto convierte una amenaza en un resultado.

---

## 4. Estimación

**Primera etapa**
$$\Delta \ln L_{lt} = \pi Z_{lt} + X_{lt}'\gamma_1 + \delta_t + u_{lt}$$

**Segunda etapa**
$$\Delta \ln w_{lt} = \beta \,\widehat{\Delta \ln L}_{lt} + X_{lt}'\gamma_2 + \delta_t + \epsilon_{lt}$$

- Reportar F de primera etapa (y el efectivo de Montiel Olea-Pflueger si F es marginal).
- Reportar **forma reducida** ($\Delta\ln w$ sobre $Z$) además del 2SLS. Con instrumento débil la forma reducida es lo único creíble, y el referee la va a pedir.
- MCO junto al 2SLS: el contraste MCO vs IV muestra la dirección del sesgo de endogeneidad y es un chequeo de sanidad del diseño.

---

## 5. Inferencia

1. **Adão-Kolesár-Morales (2019)** — la principal. Los residuos están correlacionados entre mercados con shares de enclave parecidos, aunque estén lejos geográficamente; el clustering por mercado o por estado **no** lo captura. Sin esto la tabla principal no pasa referee.
2. **Inferencia a nivel de shift (BHJ 2022)** como robustez — colapsa a nivel origen. Si las dos coinciden, tienes un argumento fuerte; si no, hay que explicar cuál marco aplica.
3. Clustering convencional por estado, solo como referencia comparativa (para mostrar cuánto subestima).

---

## 6. Amenazas y diagnósticos

### 6.1 Validez de los shares (GPSS)

- **Pesos de Rotemberg** (GPSS 2020): calcular qué orígenes cargan la identificación. Si 2–3 estados explican la mayoría, el diseño se vuelve un estudio de caso de esos estados y hay que decirlo.
- **Placebo de pre-tendencia:** ¿predicen los shares de 1990 el crecimiento salarial 1990→2000? Debe dar nulo. Éste es el uso del periodo excluido en §1.
- **Balance:** correlacionar $Z_{lt}$ con características base observables.

### 6.2 Jaeger-Ruist-Stuhler: corto vs largo plazo

Diseño de **dos instrumentos**: incluir simultáneamente el shock contemporáneo $Z_{lt}$ y el rezagado $Z_{l,t-1}$, instrumentando el cambio contemporáneo y el pasado. Separa la respuesta de impacto de la de ajuste. Con solo dos periodos esto es apretado —hay que ser honesto sobre la potencia— pero es la respuesta esperada y omitirla es una invitación a que te la exijan.

### 6.3 Amenazas espaciales (Bloque 6 de la guía v3)

**(a) Desplazamiento de nativos / SUTVA.** Si el flujo hacia $l$ expulsa nativos hacia $l'$, los controles están tratados y $\Delta \ln L$ subestima el shock de oferta ⇒ $|\beta|$ sesgado. Tres respuestas:
- Estimar el efecto de $Z_{lt}$ sobre **población nativa** del mercado (el ejercicio literal de Card 2001 y Boustan-Fishback-Kantor 2010). Si es cero, la amenaza no muerde; si es negativo, cuantifica la atenuación.
- **Estimar a dos niveles de agregación** — mercado local y agrupaciones gruesas construidas de la matriz de commuting. Si $|\varepsilon_D|$ cae al agregar, eso *es* la evidencia del desplazamiento, y es limpia.
- **Exposición del vecino estilo Helm (2020):** incluir la exposición *leave-own-out* de los mercados conectados por commuting como regresor adicional. Da efecto directo e indirecto sin imponer estructura ρW.

**(b) NO usar spatial lag/SAR aquí.** Ver la advertencia técnica del Bloque 6: la correlación espacial de los residuos viene en parte del propio diseño del instrumento (la razón de existir de AKM), y separar ρ de β exige que la estructura espacial del instrumento difiera de W — condición al filo de fallar cuando W (commuting) es lo que define los mercados y correlaciona con la red de enclaves.

### 6.4 "Migrantes = consumidores"

Ya cubierto por §3.3 (contraste transable/no transable). Complemento: Dustmann-Schönberg-Stuhler (2017) es el precedente de cómo se aísla el canal empleo del canal consumo — su diseño de *commuters* que trabajan sin consumir en el destino es el ideal que tú aproximas con la restricción sectorial.

---

## 7. Del ε_D reducido al σ estructural

El número design-based no es el final: es el **momento que disciplina la capa de modelo**.

1. Con el bloque CES del EG estático, $\varepsilon_D = f(\sigma, \text{participaciones factoriales}, \text{elast. demanda de producto})$.
2. Se recupera σ à la **Raval (2019)**, usando la misma variación de salarios locales de los 777 mercados.
3. **Oberfield-Raval (2021)** da el teorema de agregación para pasar del σ micro al agregado — y es lo que justifica que un número estimado a nivel mercado hable de tecnología.
4. **Ulyssea (2010)** habilita la descomposición formal/informal usando el proxy de seguridad social que ya trae la base.

El chequeo de consistencia de toda la tesis: **¿el σ implicado por tu $\varepsilon_D$ local cae en el rango 0.3–0.5 de Raval?** Si sí, la traducción funcionó. Si no, el gap mismo es el resultado interesante y hay que interpretarlo (fuga espacial, movilidad de capital, o composición industrial endógena).

---

## 8. Orden de ejecución

| # | Entregable | Depende de | Bloquea |
|---|---|---|---|
| 1 | Confirmar Q3 y bajar base EconLab | — | todo |
| 2 | Crosswalk municipio→777 + tabla de shares $s_{ol,1990}$ | 1 | 3 |
| 3 | Push $g_{ot}$ leave-one-out + instrumento $Z_{lt}$ | 2 | 4 |
| 4 | Primera etapa + forma reducida (sin controles finos) | 3 | — |
| 5 | 2SLS principal + tres columnas sectoriales | 4 | — |
| 6 | Inferencia AKM + pesos de Rotemberg | 5 | — |
| 7 | Placebo pre-tendencia + desplazamiento de nativos | 5 | — |
| 8 | Dos niveles de agregación + exposición de vecinos | 7 | — |
| 9 | Mapeo $\varepsilon_D \rightarrow \sigma$ | 5 | — |

**Los pasos 4 y 5 son el mínimo publicable de una propuesta.** 6–8 son lo que la vuelve defendible en seminario. 9 es la capa de modelo.

---

## 9. Pendientes que este documento deja abiertos

1. **Q3 sin confirmar** — todo §2.1 y §3.1 está escrito bajo supuesto.
2. **Mimeo de oferta (Aldeco-Chiquiar-Pérez Pérez-Salcedo) no obtenido.** Es el paper-espejo: define qué controles usaron y qué normalización, y tu tabla debería ser legible al lado de la suya. Pedir a econlab@banxico.org.mx.
3. **Definición operativa de "transable"** — falta fijar el criterio (¿clasificación por rama SCIAN? ¿umbral de intensidad exportadora?). Hong-McLaren es la referencia para justificarlo.
4. **Potencia con 1,554 observaciones y dos periodos** — no está evaluada. Conviene un cálculo de potencia mínimo antes de comprometerse con el diseño de dos instrumentos de §6.2.

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]].*
