# Cuaderno de exploración — datos EconLab de mercados laborales locales
### Mapa operativo y catálogo descriptivo · 2026-09-01

> **Regla de este documento: cero código.** Es un mapa y un documento de intuición. La Parte I dice **qué hay, cómo se pega y en qué orden**; la Parte II dice **qué queremos ver y qué esperamos encontrar**, con el signo escrito **antes** de mirar. Así la exploración es falsable y no una pesca.
>
> Compañero: `PROPUESTA_v2_2026-09-01.md` (el argumento). Detalle técnico: `inventario_datos_EconLab_LLM_2026-09-01.md`.

---

# PARTE I — Mapa operativo

## 1. Qué hay realmente en `data/` (verificado)

**21 GB, 52 archivos `.dta`, ~67.9 millones de registros de persona.**

### 1.1 Agregados — `data/PUG_Agregados_Stata/` (~2.4 GB, casi todo en dos archivos)

Éstos son chicos y se cargan sin ceremonia. Es donde vive el 80% de la tesis.

| Carpeta / archivo | Obs | Contenido |
|---|---:|---|
| `Demograficos/Demograficos_Nivel.dta` | **3,885** = 5×777 | Empleo, PEA, edad de trabajar, todo × sexo × calificación, + 24 razones |
| `Demograficos/Demograficos_Log.dta` | 3,885 | Lo mismo en logaritmos |
| `SalariosResiduales/SalResMTL_N.dta` (y `_0` mujeres, `_1` hombres) | **3,882** | `LogSalario`, `ResIngresoE`, `ResIngresoEE`, `Empleada` |
| `ChoquesBartik/LongBartikNacional.dta` | 3,885 | `EmpleoTot_MTL`, `DLogEmpleoMTL`, `BartikQ`, `BartikP` |
| `ChoquesBartik/LongBartikNacional_Trade1.dta` | **3,882** | ★ **Empleo TRANSABLE** por mercado-año |
| `ChoquesBartik/LongBartikNacional_Trade0.dta` | **3,873** | ★ **Empleo NO TRANSABLE** por mercado-año |
| `ChoquesBartik/LongBartikNacional_Manuf.dta` | ~3,87x | Manufactura |
| `ChoquesBartik/WideBartikNacional.dta` | **3,108** × 321 vars | ★ Los **104 shares industriales 1990** (`Prop1990_T_k`) + 104 `DEmpN_T_k` + 104 `DSalN_T_k` |
| `ChoquesBartik/Tasa_Crecimiento_Industria_Nacional.dta` | **520** = 104×5 | ★ Los **shifts** `g_kt` a nivel industria-año |
| `Informalidad/Informalidad.dta` | **3,105** = 4×777 | Tasa de informalidad. **Sin 1990** |
| `Vulnerabilidad/Vulnerabilidad.dta` | 3,885 | Pobreza CONEVAL, trabajo infantil, ninis, monoparentales |
| `Ingresos_Pob15/Ingresos_Pob15.dta` | — | **1.2 GB, nivel individuo.** Base intermedia de ingresos |
| `SalariosResiduales/SalariosResiduales.dta` | — | **1.1 GB, nivel individuo.** Ingresos residualizados |
| `SalariosResiduales/ConvergenciaNivelMTL_*.dta` | 5 | Nivel **año nacional**, no es panel. Poco útil aquí |

Las tres versiones por sexo (`Nacional` / `Hombre0` = mujeres / `Hombre1` = hombres) × tres cortes sectoriales dan los **9 archivos Bartik largos**.

### 1.2 Personas — `data/PUG_Personas_Stata/` (~13 GB)

Los archivos vienen **partidos con tope duro de 8,499,999 observaciones**; hay que apilarlos.

| Ola | Archivos | Total personas |
|---|---|---:|
| 1990 | `1990_0` | **8,118,242** |
| 2000 | `2000_0` + `2000_1` | **10,099,182** |
| 2010 | `2010_0` + `2010_1` | **11,938,402** |
| **2015** | `2015_0` + `2015_1` + `2015_2` | **22,692,265** ← la más grande |
| 2020 | `2020_0` + `2020_1` | **15,015,683** |

66 variables en 1990 y 2000; **65 en 2010, 2015 y 2020** (desaparece `ID_HOGAR`, consistente con que de 2010 en adelante vivienda = hogar).

**Tablas satélite** (llave `anio` + `ID_PERSONA`, formato largo — una fila por valor):

| Archivo | Obs | Para qué |
|---|---:|---|
| `Informacion Ingresos.dta` | **78,352,723** | ★ **Remesas** (`LLAVE_INGRESO` = 4 internacionales, 5 internas) |
| `Informacion Derechohabiencia.dta` | 42,294,246 | Informalidad (2000+) |
| `Informacion Prestaciones.dta` | 29,527,669 | Formalidad fina: servicio médico por el trabajo, AFORE/SAR, crédito de vivienda (2000+) |
| `Informacion Discapacidades.dta` | 5,574,468 | No se usa |

### 1.3 Vivienda — `data/PUG_Vivienda_Stata/` (~5.6 GB)

1990: 1.63M · 2000: 2.31M · 2010: 2.90M · 2015: 5.85M · 2020: 4.02M viviendas. Más satélites de bienes (77.1M), equipamiento (30.4M) y separación de basura (11.0M).

**Uso previsto: uno solo.** Un índice de activos del hogar como control de nivel de vida y como variable de balance en las pruebas de exogeneidad (F10). No forma parte del núcleo.

### 1.4 Lo que falta descargar

- ⚠️ **La carpeta `Códigos` de SIDIE** — el código Stata con el que Banxico construyó los agregados. No está en `data/`. **Léelo antes de replicar nada**: contesta solo cómo se definió cada variable y evita reinventar decisiones.
- El **mimeo de la elasticidad de oferta** (Aldeco, Chiquiar, Pérez Pérez y Salcedo). No indexado; pedirlo a econlab@banxico.org.mx.

---

## 2. Llaves, uniones y las trampas de nombres

```
   crosswalk_municipio_MTL_777.csv          (propuesta_final/datos/, 2,469 filas)
   LLAVE_MUNICIPIO ─────────────────► MERCADO_TRABAJO_LOCAL  (1..777)
            ▲                                    ▲
            │                                    │  MTL + Año
   PERSONAS (66/65 vars, 5 olas)          AGREGADOS (29 archivos)
   MERCADO_TRABAJO_LOCAL ya viene incluido
            │
            │  anio + ID_PERSONA
            ▼
   SATÉLITES: Ingresos · Derechohabiencia · Prestaciones · Discapacidades
```

### ⚠️ Trampas verificadas — cuestan una tarde si se descubren tarde

| Dónde | Trampa |
|---|---|
| Agregados | La variable se llama **`EmpleoTot_MTL` / `LogEmpleoMTL` / `DLogEmpleoMTL`** — el codebook decía `_CZ`. |
| Agregados | El año es **`Año`**, con tilde y mayúscula inicial. |
| Personas | El año es **`anio`**, y `edad`, `escolaridad`, `ingreso`, `estrato`, `upm`, `numpersona` van **en minúsculas**. El resto en mayúsculas. |
| Personas | `CLAVE_MUNICIPIO_INEGI_CLAVE_DE_A` — **truncado a 32 caracteres** por el límite de Stata. |
| Todos | El identificador de mercado es **`MERCADO_TRABAJO_LOCAL`**. Queda descartado `MERCADO_TRABAJO_LABORAL` de la nota metodológica. |
| Catálogos | **No hay nulos** en campos con catálogo: "sin valor" y "no especificado" son **categorías codificadas**. Un `missing()` no detecta ausencia de información. |

Esa última trampa es la más peligrosa, y es la que define la verificación S0.

---

## 3. Secuencia revisada de exploración

### Lo que ya NO hay que hacer

- ~~Averiguar si el empleo sectorial existe~~ → **resuelto**: `EmpleoTot_MTL` en los archivos `_Trade0/_Trade1` es sectorial (mercado 1 en 1990: total 200,320 · transable 91,310 · no transable 105,620).
- ~~Averiguar si el id de mercado cambia entre olas~~ → **no cambia**, la partición se definió una vez con conmutación de 2010.
- ~~Averiguar si la industria existe en 1990~~ → **existe**, 104 industrias SCIAN 3 dígitos armonizadas en las cinco olas.
- ~~Construir un crosswalk municipio→mercado~~ → **viene hecho** y ya está trackeado en el repo.

### S0 — La verificación que queda **(bloquea todo · medio día)**

**El problema, dicho con precisión.** Las columnas `LLAVE_ENTIDAD_RES5A`, `LLAVE_MUNICIPIO_RES5A`, `LLAVE_ENTIDAD_NAC` y `LLAVE_MUNICIPIO_TRABAJO` **existen en los cinco archivos de personas** — pero eso es un artefacto de la armonización: Banxico impone el mismo esquema a todas las olas. Como "sin valor" es una categoría del catálogo y no un nulo, la columna puede estar completa de códigos que significan "esta pregunta no se hizo ese año".

**Lo que hay que producir:** una tabla de **cinco filas × cuatro columnas** con el porcentaje de la población en la categoría "sin valor"/"no especificado" de cada variable, por ola.

**Cómo se lee el resultado:**

| Si… | Entonces |
|---|---|
| `ENTIDAD_RES5A` poblada en 1990 | Hay shift para la primera diferencia ⇒ el placebo 1990→2000 es real |
| `ENTIDAD_RES5A` vacía en 1990 | El instrumento arranca en 2000 ⇒ se pierde una diferencia y el placebo hay que rediseñarlo |
| `MUNICIPIO_RES5A` poblada en 1990 | ★ Shares a nivel **municipio de origen** (2,469) ⇒ diseño mucho más fuerte, más fiel a Card, y el problema del número efectivo de shocks se disuelve |
| `MUNICIPIO_RES5A` vacía en 1990 | Shares atados a 32 estados de nacimiento ⇒ **obligatorio** expandir a celdas origen × sexo × educación |
| `MUNICIPIO_TRABAJO` poblada en 2000 | Dos periodos para el diseño de conmutantes |
| `MUNICIPIO_TRABAJO` solo 2010+ | El diseño de conmutantes vive en diferencias de 5 años |

**Verificación cruzada obligatoria:** la fracción de "no nacidos en la entidad de residencia" por ola debería moverse de forma plausible y coincidir con las cifras publicadas de migración interna de INEGI. Si no coincide, hay un problema de armonización antes que de diseño.

### S1 a S6 — el resto

| Segmento | Qué produce | Criterio de salida |
|---|---|---|
| **S1 · Panel de mercado-año** (1–2 días) | Un panel único de 777×5 pegando demográficos, salarios residuales, Bartik (total y sectorial), informalidad y vulnerabilidad | **Validación obligatoria**: reproducir una descriptiva publicada de Aldeco et al. §4 (la razón empleo/población, o la prima de calificación) antes de construir nada nuevo |
| **S2 · Shares de enclave** (2–3 días) | $s_{ol,1990}$ desde el microdato 1990, con el estado propio excluido; y la versión por celdas | Los shares suman 1 por mercado; la distribución tiene dispersión (F5) |
| **S3 · Push nacional** (2 días) | $g_{ot}$ leave-one-out desde `RES5A` | El push replica los grandes movimientos conocidos (crisis del peso, violencia 2007+) |
| **S4 · Instrumento y primera etapa** (2 días) | $Z_{lt}$ y la primera etapa | ★ **PUNTO DE DECISIÓN: F ≥ 10** sin controles finos. Si no, replantear antes de seguir |
| **S5 · Forma reducida y 2SLS** (1 semana) | El número | — |
| **S6 · Conmutantes** (3 días, paralelo) | Matriz municipal de conmutación 2010 y factibilidad del diseño DSS | Hay masa suficiente de gente que trabaja fuera de su municipio de residencia |

**Nuevo, y va antes que S4:** calcular el **número efectivo de shocks** $1/\sum_o \hat{s}_o^2$ en cuanto existan los shares (fin de S2). Es más barato que la primera etapa y puede obligar a rehacer S2 con celdas. **No tiene sentido llegar a S4 con una construcción que ya se sabe insuficiente.**

---

## 4. Los do-files, especificados (no escritos)

Nombre → insumo → producto → **qué decide**.

| Do-file | Insumo | Producto | Decide |
|---|---|---|---|
| `00_setup.do` | — | Rutas, globals, `version` | — |
| `01_s0_cobertura_variables.do` | 5 archivos de personas | Tabla ola × variable de % "sin valor" | **Si el diseño arranca en 1990 o en 2000; si los shares son estatales o municipales** |
| `02_panel_agregado.do` | 29 agregados + crosswalk | `panel_mtl.dta` (777×5) | — |
| `03_validacion_descriptivas.do` | `panel_mtl.dta` | Réplica de una figura de Aldeco et al. §4 | **Si confiamos en nuestra construcción** |
| `04_shares_enclave.do` | Personas 1990 | $s_{ol,1990}$, versión estatal y por celdas | — |
| `05_diagnostico_shares.do` | shares | Número efectivo de shocks, HHI, pesos de Rotemberg | **Si hay que ir a celdas** |
| `06_push_nacional.do` | Personas todas las olas | $g_{ot}$ leave-one-out | — |
| `07_instrumento.do` | 04 + 06 | $Z_{lt}$, con el estado propio excluido | — |
| `08_primera_etapa.do` | 02 + 07 | F, primera etapa | ★ **go / no-go** |
| `09_bandera_transable.do` | Personas + `CAT_ACTECONOMICA` | Bandera propia de transable; empleo sectorial alterno | **Si el corte sectorial sirve como prueba del canal consumidor** |
| `10_remesas.do` | `Informacion Ingresos.dta` + personas | Exposición a remesas por mercado-año | — |
| `11_conmutacion_2010.do` | Personas 2010 | Matriz municipal origen-destino | **Si el diseño DSS es viable** |
| `12_resultados.do` | todo | 2SLS, tres columnas, batería de pruebas | — |

---

## 5. Nota de manejo — cómo no perder un día por memoria

- **Stata 18 MP** (`C:\Program Files\Stata18\StataMP-64.exe`) es la vía. Python con `pandas`+`pyreadstat` sirve para metadatos y lecturas por trozos, pero **no** tiene `linearmodels` instalado; no hay R.
- **El patrón correcto es colapsar temprano.** Cargar personas con `keep` de 8–10 variables → `collapse` a mercado-año → guardar el agregado chico → cerrar. **Nunca** cargar un archivo de personas completo en memoria de Python.
- Los archivos grandes de verdad son `Informacion Ingresos.dta` (2.5 GB, 78M filas), `Informacion Bienes.dta` (2.7 GB, 77M) y las personas de 2015 (3 archivos, 22.7M personas).
- Para S0 basta leer **una columna a la vez** de cada archivo de personas. Es barato.
- **Ponderar siempre con `FACTOR_EXP`.** Los conteos crudos no son poblacionales. Para errores estándar, `estrato` y `upm` están disponibles.

---
---

# PARTE II — Catálogo descriptivo: qué querríamos ver

Cada entrada trae cuatro campos fijos: **qué muestra · qué la alimenta · qué esperamos y por qué · qué sería mala noticia**. No hay números inventados: el signo esperado se escribe ahora, y se contrasta después.

---

## Bloque A — Describir los datos (§2 de la tesis)

### F1 · Distribución del tamaño de los mercados
- **Qué muestra:** histograma de municipios por mercado y de empleo por mercado, por ola.
- **Qué la alimenta:** crosswalk (2,469 municipios → 777) · `Empleada_T` de `Demograficos_Nivel`.
- **Qué esperamos:** una distribución muy sesgada. **279 mercados (36%) tienen un solo municipio** — ya verificado. En empleo, la cola derecha son Valle de México, Guadalajara y Monterrey; la izquierda, mercados rurales con unos miles de trabajadores.
- **Mala noticia:** que un número apreciable de mercados tenga tan poco empleo que `LogSalario` sea puro ruido. Eso obligaría a un umbral mínimo, con la pérdida de representatividad nacional que implica.

### F2 · Cobertura por ola
- **Qué muestra:** para cada ola, cuántos mercados tienen dato en cada variable núcleo, y qué fracción de la población vive en municipios marcados como "muestra insuficiente" en 2015.
- **Qué la alimenta:** `Demograficos_Nivel`, `SalResMTL_N`, `LongBartik*` · `LLAVE_COBERTURA`.
- **Qué esperamos:** cobertura casi completa (ya se sabe: 3,885 de 3,885 en demográficos; 3,882 en salarios; 3,873 en no transables). **2015 debe verse peor**, y concentrada en los mercados chicos.
- **Mala noticia:** que los mercados faltantes no sean aleatorios sino los más chicos y pobres — sería selección, no ruido, y contamina toda comparación entre olas.

### F3 · Distribución del salario, por ola
- **Qué muestra:** densidades de `LogSalario` y de `ResIngresoEE` entre mercados, superpuestas por ola.
- **Qué la alimenta:** `SalResMTL_N/_0/_1`.
- **Qué esperamos:** una **caída real fuerte de 1990 a 2000** (la nota documenta −20.3% para no calificados; la crisis del 94-95 está dentro de la ventana) y recuperación parcial después. La dispersión **entre** mercados debería estrecharse en la versión residualizada respecto de la bruta: es la definición de residualizar.
- **Mala noticia:** que residualizar por edad y educación no reduzca la dispersión. Significaría que la variación entre mercados no es de composición y que hay un problema de comparabilidad del ingreso entre olas (el top-coding de 1990 es el sospechoso).

### F4 · Concentración de los shares industriales de 1990
- **Qué muestra:** para cada mercado, el HHI de los 104 `Prop1990_T_k`; y el mapa de qué industrias dominan.
- **Qué la alimenta:** `WideBartikNacional.dta`.
- **Qué esperamos:** mercados rurales muy concentrados (agricultura por encima de 0.5 del empleo) y metropolitanos diversificados. Es la variación que hace funcionar al Bartik **como control**.
- **Mala noticia:** concentración uniforme. Sin heterogeneidad de exposición industrial, el Bartik no purga nada y el control es decorativo.

---

## Bloque B — Justificar el diseño: el observable (§4)

Éste es el bloque que decide si hay tesis.

### F5 · Dispersión de la exposición de enclaves — **la figura que decide todo**
- **Qué muestra:** distribución de $s_{ol,1990}$ entre mercados para los orígenes principales; y la distribución del instrumento $Z_{lt}$.
- **Qué la alimenta:** `LLAVE_ENTIDAD_NAC` del microdato 1990 + crosswalk.
- **Qué esperamos:** **dispersión sustancial una vez excluido el estado propio.** Debe verse el patrón conocido: Oaxaca, Guerrero, Chiapas, Veracruz, Michoacán y Zacatecas como expulsores; y destinos concentrados en la frontera norte, el Valle de México y los polos turísticos.
- **Mala noticia, y es la peor de todas:** que al quitar el estado propio, la exposición residual sea casi cero para la mayoría de los mercados. **Sin dispersión no hay diseño**, y hay que saberlo en S2, no en S4.

### F6 · Esperanza condicional de $\Delta \ln L$ dado el instrumento — la primera etapa, dibujada
- **Qué muestra:** binscatter de $\Delta \ln L_l$ contra $Z_{lt}$, ponderado por empleo.
- **Qué la alimenta:** `DLogEmpleoMTL` + el instrumento de S4.
- **Qué esperamos:** **pendiente positiva y visiblemente lineal.** Es la primera etapa antes de que salga un número: si la nube no tiene pendiente a ojo, la F no la va a rescatar.
- **Mala noticia:** relación plana, o arreada por un puñado de mercados en la cola. Lo segundo es peor que lo primero, porque una F alta impulsada por cinco observaciones es una F falsa.

### F7 · Esperanza condicional de $\Delta \ln w$ dado el instrumento — la forma reducida
- **Qué muestra:** binscatter de $\Delta \ln w_l$ contra $Z_{lt}$.
- **Qué la alimenta:** $\Delta$`ResIngresoEE` + el instrumento.
- **Qué esperamos:** **pendiente negativa.** Más oferta, menor salario. La curva de demanda tiene pendiente negativa — eso es lo que se está mirando, literalmente.
- **Mala noticia:** pendiente positiva o nula. Positiva significa que el instrumento está captando demanda, no oferta, y manda de vuelta a S3.

### F8 · El sesgo que el IV debe corregir
- **Qué muestra:** el mismo binscatter de $\Delta \ln w$ contra $\Delta \ln L$, dos veces: crudo (MCO) y con ambas variables residualizadas contra el instrumento (IV).
- **Qué esperamos:** **MCO menos negativo que IV.** Los mercados con demanda pujante crecen en empleo *y* en salario, lo que sesga MCO hacia arriba. Ver esa brecha *es* el argumento de por qué hace falta un instrumento.
- **Mala noticia:** que MCO e IV coincidan. Implicaría que no había endogeneidad que corregir y que el aparato entero es innecesario — un resultado publicable, pero otra tesis.

---

## Bloque C — Validez del instrumento (§5)

### F9 · Pesos de Rotemberg y número efectivo de shocks
- **Qué muestra:** los pesos $\alpha_o$ ordenados; y el número efectivo de shocks $1/\sum_o \hat{s}_o^2$.
- **Qué esperamos:** **concentración alta.** Con 32 orígenes, cinco o seis estados expulsores van a llevarse la mayor parte del peso. Se reporta tal cual — GPSS pide exactamente esto.
- **Mala noticia:** número efectivo **por debajo de 5**. Ahí el marco de "muchos shocks" de BHJ es indefendible y hay que ir a celdas origen × sexo × educación. **Es la razón por la que esta figura va antes de S4.**

### F10 · Balance de los shares de peso alto — **la prueba de la objeción de Hanson**
- **Qué muestra:** correlación de los shares de mayor peso contra características **pre-periodo** del mercado: escolaridad promedio, salario en nivel, tasa de pobreza, participación industrial, índice de activos del hogar.
- **Qué la alimenta:** shares de S2 · `Demograficos_Nivel`, `Vulnerabilidad`, y los satélites de vivienda.
- **Qué esperamos:** **correlaciones chicas y sin patrón.** Alguna va a salir significativa por puro múltiple testing; lo que importa es que no haya un patrón sistemático de que los mercados de alta exposición sean sistemáticamente más pobres o menos educados.
- **Mala noticia, y hay que decirlo con nombre y apellido:** que sí haya patrón. **Hanson (2005) predice exactamente eso** — que las redes migratorias históricas correlacionan con la acumulación de capital humano. Si aparece, hay que recentrar el instrumento (Borusyak-Hull 2023) o admitir que el diseño no identifica.

### F11 · Placebo de pre-tendencia
- **Qué muestra:** los shares de 1990 contra el cambio de salario y empleo en el periodo **previo**.
- **Qué esperamos:** **cero.** Que la exposición no prediga lo que pasó antes de que llegara el choque.
- **Mala noticia:** pre-tendencia significativa ⇒ los shares captan trayectorias locales de largo plazo, no exposición a un choque. Es la crítica de Jaeger-Ruist-Stuhler hecha carne.
- ⚠️ **Depende de S0:** si `RES5A` no está poblado en 1990, este placebo hay que rediseñarlo.

### T1–T4 · Las tablas que acompañan
- **T1** Estadística descriptiva del panel: media, sd, p10/p50/p90 de cada variable núcleo, por ola.
- **T2** Construcción del instrumento: los 10 orígenes principales, su share promedio y su push por periodo.
- **T3** Pesos de Rotemberg: origen, peso, estimación apenas identificada, y su error estándar.
- **T4** Balance: la matriz de F10 en formato de regresión, con el número efectivo de shocks al pie.

---

## Bloque D — El canal consumidor (§6)

### F12 · Las tres columnas, lado a lado — **con la predicción escrita antes**
- **Qué muestra:** $\varepsilon_D$ estimada tres veces, sobre empleo total, transable y no transable, con sus intervalos de confianza en la misma escala. Y por partida doble: con la bandera `LLAVE_EXPORTADORA` de la casa y con la bandera propia.
- **Qué la alimenta:** `LongBartikNacional_Trade0/_Trade1` (ya verificado que traen empleo sectorial) y la reconstrucción propia desde `LLAVE_ACTECONOMICA`.
- **★ Qué esperamos, y esto es una predicción, no una esperanza:** **no transables debe salir MÁS elástico que transables.** Si los migrantes desplazan la demanda de trabajo vía consumo, el efecto está en los bienes que se consumen donde se producen. La estimación transable es la limpia.
- **Mala noticia — y hay dos, distintas:**
  1. **Que salgan iguales.** Entonces o el canal consumidor no opera, o la clasificación sectorial no lo separa. La segunda es más probable **con la bandera de la casa**, que mete el transporte urbano de pasajeros del lado transable. Por eso van las dos banderas.
  2. **Que transables salga infinitamente elástico** (coeficiente estadísticamente nulo). No es un fracaso: es insensibilidad de precios de factores, y significa que el mercado no está especializado. Pero hay que anticiparlo para no leerlo como instrumento débil.

### T5 · Exposición a remesas
- **Qué muestra:** por mercado-año, la fracción de hogares que reportan `LLAVE_INGRESO` = 4 (internacionales) y = 5 (internas).
- **Qué esperamos:** las **internacionales** concentradas en el occidente tradicional (Zacatecas, Michoacán, Guanajuato, Jalisco) y creciendo fuerte de 2000 a 2010. Las **internas** concentradas en los mercados de **origen**, no de destino — que es exactamente el supuesto que sostiene el diseño de migración interna.
- **Mala noticia:** que las remesas internas se concentren en los destinos. Rompería el argumento de que el canal consumidor de la migración interna es de una sola vía.
- ⚠️ En 2015 y 2020 esto se mide a nivel jefe de hogar; usar a nivel mercado.

### T6 · $\varepsilon_D$ por corte demográfico
- **Qué muestra:** la estimación por sexo y por calificación.
- **Qué esperamos:** más elástica para trabajadores no calificados, siguiendo a DSS 2017 (el desplazamiento se concentra abajo).
- **Mala noticia:** que no se pueda estimar, porque el salario por calificación a nivel mercado **no está en los agregados** y hay que construirlo del microdato.

---

## Bloque E — Interpretación y política (§7)

### T7 · La mordida del salario mínimo por mercado
- **Qué muestra:** para cada mercado, la fracción de trabajadores por debajo del nuevo mínimo antes de cada incremento, 2015→2020; y el corte de la Zona Libre de la Frontera Norte.
- **Qué la alimenta:** `SalariosResiduales.dta` a nivel individuo + el calendario de salarios mínimos.
- **Qué esperamos:** una dispersión enorme. Ya se sabe que a nivel estatal la fracción por debajo del mínimo iba de **6.9% en Nuevo León a 41.1% en Chiapas** en 2019; a nivel de mercado será más ancha aún. La ZLFN debe destacarse como discontinuidad espacial nítida.
- **Mala noticia:** que la mordida sea trivial en casi todos los mercados. Entonces la Rama B del §5 de la propuesta no tiene nada que evaluar.

### T8 · Incidencia implícita bajo un rango de $\varepsilon_S$
- **Qué muestra:** una tabla de dos entradas — $\varepsilon_D$ estimada × un rango de $\varepsilon_S$ — con el reparto salario/empleo de un choque unitario en cada celda.
- **Qué esperamos:** que **la mayor parte de la incidencia caiga en cantidades**, porque en mercados locales de largo plazo $\varepsilon_S$ es una elasticidad de migración y es grande (Blanchard-Katz).
- **Mala noticia:** que la tabla sea tan sensible al rango de $\varepsilon_S$ que no discrimine entre escenarios. Sería el argumento más fuerte para conseguir el mimeo y usar su número, en vez de un rango.

---

## 6. Cómo se usa este cuaderno

1. **Antes de correr nada**, leer la entrada correspondiente y quedarse con el signo esperado.
2. **Correr.**
3. **Comparar contra lo escrito**, no contra lo que uno hubiera querido.
4. Si el resultado contradice la expectativa, **escribir por qué** en la entrada — el cuaderno es un registro, no un plan.

Las figuras que no tienen "mala noticia" definida sobran: significa que no se sabe qué se está probando.
