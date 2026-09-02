# Inventario y lectura crítica de los diccionarios EconLab — Local Labor Markets in Mexico
**Sesión 2026-09-01 · insumo: carpeta `LLM/` (74 archivos)**
**Estado: análisis de diccionarios COMPLETO. Bases `.dta` aún no revisadas.**

Este documento cierra el segmento **S0 (verificar el diccionario)** del `PLAN_ensayo1_maestria_2026-08-09.md`, con dos salvedades: hay tres preguntas que el diccionario **no puede** contestar y que quedan listadas en §8 para el momento en que lleguen los `.dta`.

---

## 1. Qué llegó y qué es redundante

| Archivo | Contenido | Estado |
|---|---|---|
| `Codebook Local-Labor-Market Level Data.xlsx` | 33 hojas. Diccionario de las 29 bases agregadas + equivalencia IPUMS | **NUEVO — núcleo del análisis** |
| `Codebook Individual-Level Data.xlsx` | 40 hojas. 66 variables + tablas de compatibilidad por ola censal | **NUEVO — núcleo del análisis** |
| `Codebook Housing-Unit Level Data.xlsx` | 33 hojas. 42 variables de vivienda + crosswalk de nombres por ola | **NUEVO — periférico** |
| `Individual-Level Catalogs/` (39 CSV) | Catálogos individuales | **NUEVO — FYI, §6** |
| `Housing-Unit Level Catalogs/` (29 CSV) | Catálogos de vivienda | **NUEVO — FYI, §6** |
| `Local-Labor-Market Level Catalogs/Local Labour Markets.csv` | **El crosswalk municipio → mercado** | **NUEVO — pieza crítica** |
| `{2BB5ECD9-…}.pdf` | Nota Aldeco et al. (2024) | **DUPLICADO EXACTO** (md5 `2f10120…`) de `papers/00_nucleo_tema/` |
| `{FD95C036-…}.pdf` | Nota metodológica abril 2024 | **DUPLICADO EXACTO** (md5 `bd907f4…`) de `propuesta_final/datos/` |

> **Acción de acervo sugerida:** borrar los dos PDF de `LLM/` (ya existen en el repo con nombres legibles). Es la segunda vez que llega el mismo par duplicado.

---

## 2. Arquitectura de la base — el mapa mental

Tres niveles, unidos por un **modelo estrella** (archivos de hechos + catálogos numéricos, sin texto en los archivos grandes; todos los "no especificado" están codificados, **no hay nulos** en campos con catálogo).

```
                    Local Labour Markets.csv
   MUNICIPIO  ────────────────────────────────►  MERCADO_TRABAJO_LOCAL (777)
      ▲                                                     ▲
      │                                                     │
 microdato INDIVIDUAL (66 vars, 5 olas)  ──agregación──►  29 bases agregadas
      │                                                    (código Stata incluido)
 microdato VIVIENDA (42 vars, 5 olas)
```

**Olas:** 1990, 2000, 2010 (censos, cuestionario ampliado), **2015 (Encuesta Intercensal)**, 2020 (censo ampliado, levantado 2–27 de marzo de 2020 ⇒ **pre-COVID**). No hay 1995 ni 2005: INEGI no midió características económicas con suficiente detalle.

### 2.1 El crosswalk, analizado
`Local Labour Markets.csv` = **2,469 municipios → 777 mercados**, con `LLAVE_ENTIDAD`, `CLAVE_ENTIDAD_INEGI (AGEE)`, `LLAVE_MUNICIPIO`, `CLAVE_MUNICIPIO_INEGI (AGEM)`, nombre y `MERCADO_TRABAJO_LOCAL`.

Distribución del tamaño de los mercados (municipios por mercado):

| # municipios | 1 | 2 | 3 | 4 | 5 | 6 | 7–10 | 11–20 | 21–30 |
|---|---|---|---|---|---|---|---|---|---|
| # mercados | **279** | 155 | 113 | 72 | 55 | 33 | 45 | 20 | 5 |

- **279 de 777 mercados (36%) son un solo municipio.** Rurales, muestra delgada. Consecuencia directa: ponderar por empleo y reportar como robustez el recorte de los mercados más chicos.
- **50 mercados cruzan fronteras estatales.** Relevante para el instrumento de enclaves (§9.1).
- Mercado más grande: 30 municipios.

---

## 3. Nivel MERCADO LOCAL — qué hay y, sobre todo, qué NO hay

29 archivos: 4 "bases intermedias" y 25 "bases finales". Reordenados por utilidad para la tesis:

### 3.1 Lo que se usa directamente

| Archivo | Nivel | Variables clave | Olas |
|---|---|---|---|
| `Demograficos_Nivel.dta` / `Demograficos_Log.dta` | MTL×año | `PoblacionT/M/F`, `ActivaT/M/F`, **`Empleada_T/M/F`**, `Edad_TrabajoT/M/F`, todo partido por calificado/no calificado (`_Sup1/_Sup0`), + 24 razones. La versión `_Log` es la misma en logaritmos | **5** |
| `SalResMTL_N/_0/_1.dta` (N=todos, 0=mujeres, 1=hombres) | MTL×año | **`LogSalario`** (promedio ponderado de log ingreso real), **`ResIngresoE`** (residual controlando edad), **`ResIngresoEE`** (residual controlando edad × educación), `Empleada` | **5** |
| `LongBartikNacional.dta` | MTL×año | `EmpleoTot_CZ`, `LogEmpleoCZ`, **`DLogEmpleoCZ`**, **`BartikQ`** (choque de empleo), **`BartikP`** (choque de salario), `DifQ` | **2000+** |
| `LongBartikNacional_Trade0/_Trade1/_Manuf.dta` | MTL×año | Idem, restringido a no transables / transables / manufactura | 2000+ |
| `WideBartikNacional.dta` | MTL×año | `BartikQ_T`, `BartikP_T`, **`Prop1990_T_k` = el share `s_{lk,1990}` de cada industria**, `DEmpN_T_k`, `DSalN_T_k`, agregados por sector primario/secundario/terciario | 2000+ |
| `Tasa_Crecimiento_Industria_Nacional.dta` | **industria×año** | `Ind3D`, `EmpN1`, `SalRN1`, **`DEmpN1`**, `DSalRN1` — **los shifts `g_kt`** | 2000+ |
| `Informalidad.dta` | MTL×año | `Informal_T/M/F`, `Informalidad_TasaT/M/F` | **2000+, NO 1990** |
| `Vulnerabilidad.dta` | MTL×año | 62 variables: pobreza y pobreza extrema (líneas CONEVAL, ingreso del hogar vs. línea ajustada por tamaño), trabajo infantil 12–18, ninis (4 definiciones), hogares monoparentales | 5 |
| `Ingresos_Pob15.dta`, `SalariosResiduales.dta` | **individuo×año** | Bases intermedias: `Real_Ingreso`, `LogIngreso`, `ResIngresoEdad`, `ResIngresoEdadEduc`, con `MTL` e `Identmun_1990` ⇒ **se puede reagregar como uno quiera** | 5 |
| `ConvergenciaNivelMTL_*.dta` | **año** | sd y percentiles p10/p50/p90 y razones *entre* mercados. Nivel nacional, no sirve como panel | 5 |

Todas las variables de empleo/salario vienen en **tres versiones: total, hombres (`_1`/`Hombre1`), mujeres (`_0`/`Hombre0`)**. Cada versión de Bartik cruza además con transable/no transable/manufactura ⇒ **9 archivos de Bartik en formato largo**.

### 3.2 Lo que la base NO tiene (y hay que construir del microdato)

Esto es lo que más ajusta el alcance:

1. **NO hay empleo por industria a nivel mercado, salvo los shares de 1990** (`WideBartik`). El panel agregado tiene empleo total, por sexo y por calificación — nada más.
2. **⚠️ Por lo tanto, la columna "empleo transable" del diseño de tres columnas NO está garantizada.** Los archivos `LongBartikNacional_Trade1.dta` traen `EmpleoTot_CZ`, cuya definición en el diccionario dice literalmente *"Total employment: sum of employment within a local labor market"*, sin aclarar si está restringida al sector. **Es la verificación #1 cuando lleguen los `.dta`** (§8).
3. **NO hay salario por industria ni por sector a nivel mercado.** Tampoco salario por calificación (sí hay *empleo* por calificación). La prima de calificación de la §4 de la nota se calculó del microdato.
4. **NO hay deflactor espacial.** `Real_Ingreso` = ingreso / INPC **nacional**. Todos los "salarios reales" del panel son nominales deflactados por un índice nacional.
5. **NO hay nada de migración a nivel mercado.** La nota lo dice explícitamente (fn. 18, p. 11): los módulos de migración *"are within project's scope in the next stage"*. **Todo el instrumento de enclaves se construye desde cero del microdato.**
6. **NO hay matriz de conmutación publicada.** Se puede reconstruir del microdato 2010 (`LLAVE_MUNICIPIO` × `LLAVE_MUNICIPIO_TRABAJO`).
7. **NO hay capital, producto ni establecimientos.** Si el mapeo ε_D → σ pasara de discusión a estimación, harían falta Censos Económicos (§10).

---

## 4. Nivel INDIVIDUAL — 66 variables y la disponibilidad por ola

### 4.1 Las variables que importan

| Variable | Qué es | Uso en la tesis |
|---|---|---|
| `MERCADO_TRABAJO_LOCAL` | id del mercado (777) | unidad de análisis |
| `LLAVE_MUNICIPIO`, `CLAVE_MUNICIPIO_INEGI` | municipio de residencia | crosswalk, nivel alterno de agregación |
| **`LLAVE_ENTIDAD_NAC`** | **entidad de nacimiento** | **shares del instrumento de enclaves** |
| **`LLAVE_ENTIDAD_RES5A`, `LLAVE_MUNICIPIO_RES5A`, `LLAVE_PAIS_RES5A`** | **residencia hace 5 años** | **shifts (flujo de migración)** |
| `LLAVE_CAUSAMIGRACION` | motivo de migración | ⚠️ **solo 2000 y 2020** |
| **`LLAVE_MUNICIPIO_TRABAJO`, `LLAVE_ENTIDAD_TRABAJO`, `LLAVE_PAIS_TRABAJO`** | **lugar de trabajo** | **matriz de conmutación, diseño DSS** |
| `LLAVE_TIETRASLADO_TRABAJO`, `LLAVE_MEDTRASLADO_TRABAJO` | tiempo y medio de traslado | ⚠️ **solo 2015 y 2020** |
| `LLAVE_ACTPRIMARIA` | condición de actividad | definición de empleado; **5 olas** |
| `LLAVE_SITTRA` | posición en el trabajo | proxy de informalidad; **5 olas** |
| `LLAVE_ACTECONOMICA` | industria armonizada (SCIAN 3 díg.) | shares industriales; **5 olas** |
| `ACTIVIDAD_ECONOMICA_INEGI` | clave INEGI original (SCIAN 2000, 523 valores) | detalle fino |
| `INGRESO` | ingreso mensual del trabajo | salario |
| `HORAS_TRABAJADAS` | horas la semana pasada | **salario por hora — no está en el agregado** |
| `ESCOLARIDAD`, `ESCOLARIDAD_ACUMULADA`, `LLAVE_NIVACAD` | educación | residualización, celdas de calificación |
| `EDAD`, `LLAVE_SEXO` | demografía | celdas |
| `FACTOR_EXP`, `ESTRATO`, `UPM` | diseño muestral | **ponderación y errores estándar** |
| `LLAVE_DHSERSAL` (tabla aparte) | derechohabiencia | informalidad; ⚠️ **2000+, NO 1990** |
| `LLAVE_PRESTACION` (tabla aparte) | prestaciones laborales | informalidad fina; ⚠️ **2000+, NO 1990** |
| `LLAVE_INGRESO` (tabla aparte) | **tipo de ingreso, incluye remesas** | ver §7.4 |

Cinco variables son *multivaluadas* y viven en tablas satélite unidas por `ANIO` + `ID_PERSONA`: discapacidad, causa de discapacidad, **prestaciones**, **tipo de ingreso**, **derechohabiencia**.

### 4.2 Tabla de disponibilidad por ola — lo que el codebook SÍ documenta

Las hojas de catálogo del codebook individual traen una **tabla de compatibilidad** que mapea cada valor armonizado al valor original de cada censo. Donde falta una ola, la variable **no existe** en esa ola:

| Variable | 1990 | 2000 | 2010 | 2015 | 2020 |
|---|:--:|:--:|:--:|:--:|:--:|
| `SEXO`, `EDAD`, `ESCOLARIDAD` | ✅ | ✅ | ✅ | ✅ | ✅ |
| **`ACTPRIMARIA`** (condición de actividad) | ✅ | ✅ | ✅ | ✅ | ✅ |
| **`SITTRA`** (posición en el trabajo) | ✅ | ✅ | ✅ | ✅ | ✅ |
| **`ACTECONOMICA`** (industria SCIAN 3d) | ✅ (223 mapeos) | ✅ | ✅ | ✅ | ✅ |
| `NIVACAD` (nivel académico) | ✅ parcial (5 mapeos) | ✅ | ✅ | ✅ | ✅ |
| `OCUPACION` | ❌ | ❌ | ❌ | ✅ | ✅ |
| **`DHSERSAL`** (derechohabiencia) | ❌ | ✅ | ✅ | ✅ | ✅ |
| **`PRESTACIONES`** | ❌ | ✅ | ✅ | ✅ | ✅ |
| **`CAUSAMIGRACION`** | ❌ | ✅ | ❌ | ❌ | ✅ |
| **`TIETRASLADO_TRABAJO`** | ❌ | ❌ | ❌ | ✅ | ✅ |
| `COBERTURA` (censado / muestreado) | ❌ | ❌ | ❌ | ✅ | ✅ |

**Tres lecturas de esta tabla:**

- **`ACTECONOMICA` armonizada existe en 1990.** Valida que el share base 1990 del Bartik es legítimo y, más importante, que **puedes construir shares industriales 1990 propios** con cualquier corte de industria.
- **Las tres variables de informalidad se comportan distinto.** `DHSERSAL` (la que usa `Informalidad.dta`) empieza en 2000 — por eso la base tira 1990. Pero **`SITTRA` sí está en 1990**: un proxy por posición en el trabajo (cuenta propia + no remunerado + jornalero) cubre las cinco olas. Y `PRESTACIONES` (2000+) da una medida de formalidad mucho mejor que derechohabiencia: servicio médico *por el trabajo*, AFORE/SAR, crédito de vivienda, aguinaldo, vacaciones pagadas.
- **`CAUSAMIGRACION` es inservible como filtro consistente** (solo 2000 y 2020). No construyas el diseño sobre "migrantes por motivos laborales".

### 4.3 Lo que el codebook NO documenta
Las variables geográficas (`ENTIDAD_NAC`, `ENTIDAD_RES5A`, `MUNICIPIO_RES5A`, `MUNICIPIO_TRABAJO`) usan catálogos **compartidos** (`CAT_ENTIDADES`, `CAT_MUNICIPIOS`, `CAT_PAISES`) que no traen tabla de compatibilidad por ola. **Su disponibilidad por año es la laguna principal del diccionario**, y es exactamente donde vive la decisión de diseño pendiente. Va a §8.

### 4.4 Notas de comparabilidad para la sección de datos
- **1990, ingreso:** el valor `999998` **no** es tope de censura en 1990 (sí lo es en 2000+, donde significa "≥999,999 pesos/mes"); se recodificó a `99999999`. Además, en 1990 el ingreso se dividió entre mil por el cambio a nuevos pesos.
- **2015 y 2020, ingresos no laborales:** el detalle de tipo de ingreso se asignó **al jefe de hogar**, porque el cuestionario dejó de identificar a qué persona corresponde. No uses `LLAVE_INGRESO` a nivel individuo en esas olas; úsalo a nivel hogar o mercado.
- **`ID_PERSONA`** es un consecutivo asignado en 1990/2000/2010 (el original no era único a nivel nacional) y el original en 2015/2020. Los 4 primeros dígitos son el año. **No hay panel de personas.**
- **1990 y 2000:** cada hogar era una observación aunque compartiera vivienda; `ID_VIVIENDA` no era único nacional. De 2010 en adelante vivienda = hogar.
- **1990:** el archivo fuente no separaba persona de vivienda; Banxico repartió las variables por descripción.
- **2015 (Intercensal):** `CAT_COBERTURA` distingue municipio *censado*, *muestreado* y **"municipio con muestra insuficiente"**. Con 279 mercados unimunicipales, esto es un problema real de medición, no un tecnicismo.
- **Inconsistencia del nombre del identificador de mercado entre documentos:** la nota metodológica Tabla 1 dice `MERCADO_TRABAJO_LABORAL`; la Tabla 6 y el codebook individual dicen `MERCADO_TRABAJO_LOCAL`; el codebook de vivienda dice `TRABAJO_MERCADO_LOCAL`. Tres nombres para lo mismo. Verificar en el `.dta`.

---

## 5. Nivel VIVIENDA — FYI

42 variables: materiales de muros/techos/pisos, cocina, sanitario, agua (dotación, abasto, potable/no potable), drenaje, electricidad, combustible, tenencia y forma de adquisición, tipo de hogar, eliminación y separación de basura, antigüedad de construcción, focos y focos ahorradores, cuartos y dormitorios, personas y familias por vivienda; más tres tablas satélite (bienes, equipamiento, separación de basura). Trae identificador de mercado.

La hoja ` Descriptions` del codebook de vivienda es la **única** que da un crosswalk explícito de nombres de variable por ola (1990/2000/2005/2010/2015/2020) — útil si alguna vez hay que bajar al dato crudo de INEGI.

**Uso plausible en la tesis, uno solo:** un índice de activos del hogar como control de nivel de vida / proxy de costo de vida local, o como variable de balance en las pruebas de exogeneidad de los shares (GPSS pide justo eso: mostrar que los shares de enclave altos no predicen características de nivel). No forma parte del núcleo.

---

## 6. Catálogos — documentación agregada (FYI; consultar cuando se use uno)

69 CSV, todos con la forma `LLAVE_X, "DESCRIPCION_X"`. Los que importan:

**Geografía** — `CAT_ENTIDADES` (32 estados + código 0 "no identificado"), `CAT_MUNICIPIOS` (2,470), `CAT_LOCALIDADES` (300,876; solo localidades ≥50,000 hab. tienen llave propia), `CAT_PAISES` (300).

**Economía y trabajo** — **`CAT_ACTECONOMICA` (104 industrias SCIAN 3 dígitos + bandera `LLAVE_EXPORTADORA` 0/1 — ver §7.2)**, `CAT_ACT_ECONOMICA_INEGI` (523 claves originales), `CAT_OCUPACION` (989, jerárquico: división → grupo principal → subgrupo → ocupación), `CAT_SITTRA` (8), `CAT_ACTPRIMARIA` (11), `CAT_PRESTACIONES` (9), `CAT_DHSERSAL` (12), **`CAT_INGRESOS` (7 — ver §7.4)**.

**Educación** — `CAT_NIVACAD` (20 niveles), `CAT_CARRERAS` (1,362), `CAT_ALFABETISMO`, `CAT_ASISESCOLAR`.

**Movilidad** — `CAT_MEDTRASLADO` (11 medios), `CAT_TIETRASLADO` / `CAT_TIETRASLADOTRAB` (8 rangos), `CAT_CAUSAMIGRACION` (12).

**Demografía y hogar** — `CAT_SEXO`, `CAT_PARENTESCO` (77), `CAT_SITUACONYUGAL` (10), `CAT_TAMLOC` (4 rangos: <2.5k / 2.5–15k / 15–100k / ≥100k), `CAT_COBERTURA` (4), `CAT_NACIONALIDAD`, `CAT_RELIGION` (300), `CAT_LENGUAMAT` (118), `CAT_PERTEINDIGENA`, `CAT_AFRODES`, `CAT_DISCAPACIDAD`, `CAT_CAUSADISC`, `CAT_REGISNAC`, `CAT_IDENTIDAD`, `CAT_SERSALUD`, `CAT_CLASEVIVIENDA`.

**Vivienda (29)** — materiales, servicios, equipamiento, bienes, tenencia. Todos chicos (5–18 filas) salvo localidades y municipios.

---

## 7. Los siete hallazgos que cambian el diseño

### 7.1 ✅ El id de los 777 mercados **es constante entre olas, por construcción**
La nota (p. 3): *"a measure of the intensity of commuting between each pair of municipalities is constructed using data on the workers' municipalities of residence and work from the **2010 Census**"*, sobre el marco geoestadístico municipal **de 2010**. El crosswalk es **una sola tabla municipio→mercado**, aplicada a las cinco olas.

**Esto cierra la pregunta S0 #2 del plan: sí, el id es constante.** El precio es una hipótesis fuerte que hay que declarar: los patrones de conmutación de 1990 se aproximan con los de 2010. Para diferencias largas 1990→2020 eso es un supuesto, no un hecho.

**Corolario aprovechable:** el número 777 es **arbitrario** — se eligió para igualar a Blyde et al. (2020). El umbral de disimilitud de Tolbert-Sizer (0.98) aplicado a México da **925 mercados** (fn. 9). Como tienes el microdato 2010 con `MUNICIPIO_TRABAJO`, **puedes reconstruir la partición a otra granularidad**. Eso convierte la "robustez de dos niveles de agregación" estilo Helm de un gesto vago en un ejercicio concreto y barato.

*(Detalle metodológico para citar: `D_ij = 1 − (f_ij + f_ji)/min(Σ_l f_il, Σ_l f_jl)`, con clustering jerárquico divisivo; índices negativos truncados a cero; municipios a más de 150 km se fijan en D=1.)*

### 7.2 ⚠️ La bandera "transable" de la base **no es la que el diseño necesita**
`CAT_ACTECONOMICA` trae `LLAVE_EXPORTADORA` ∈ {0,1}: **53 transables, 50 no transables, 1 sin clasificar** (999). Es la definición que alimenta todos los archivos `_Trade0`/`_Trade1`. Y contiene esto:

> **Clasificadas como TRANSABLES:** agricultura (11x), minería (21x), manufactura (31–33x) — **y además** comercio al por mayor (43x), **todo transporte, incluido 485 "transporte terrestre de pasajeros excepto por ferrocarril"** (= camión urbano, colectivo, taxi), 523 (bolsa e inversión financiera), 532–533 (renta de autos, maquinaria, marcas y patentes).
>
> **Clasificadas como NO TRANSABLES:** electricidad y agua, construcción, comercio al por menor, correo y almacenamiento, medios, servicios financieros al menudeo, inmobiliaria, servicios profesionales, educación, salud, **hotelería y restaurantes (721/722)**, servicios personales, gobierno.

El nombre lo delata: `EXPORTADORA`. Es una clasificación de **sectores exportables / que mueven mercancía**, no de *"precio determinado nacionalmente"*.

**Por qué importa:** en el plan, la columna transable/no transable **es la prueba del canal consumidor**, y su validez descansa en el argumento de Hong & McLaren (el precio del producto transable no responde a la población local). Meter transporte urbano de pasajeros del lado transable, y sacar turismo del lado transable, rompe ese argumento en las dos direcciones.

**Decisión recomendada:** usar `LLAVE_EXPORTADORA` como la definición *de la casa* (comparabilidad con el mimeo y con Banxico) **y construir una segunda bandera propia** — agricultura + minería + manufactura, quizá + turismo — desde `LLAVE_ACTECONOMICA` en el microdato. Reportar ambas. Que la definición de transable sea una decisión declarada de la tesis y no una herencia silenciosa.

### 7.3 ⚠️ El origen del instrumento son **32 estados**, no más
Existe `LLAVE_ENTIDAD_NAC` (entidad de nacimiento) pero **no existe `LLAVE_MUNICIPIO_NAC`**: el censo no pregunta municipio de nacimiento. Entonces:

- **Shares por lugar de nacimiento ⇒ máximo 32 orígenes.**
- El municipio de origen solo es observable vía `LLAVE_MUNICIPIO_RES5A` (residencia hace 5 años), en las olas donde exista.

Con K=32 shocks, el marco de **muchos shocks de Borusyak-Hull-Jaravel se tambalea**: el número efectivo de shocks (1/Σ de los pesos de exposición al cuadrado) va a estar dominado por media docena de estados expulsores (Oaxaca, Guerrero, Chiapas, Veracruz, Michoacán, Zacatecas, Estado de México). Hay que **calcularlo y reportarlo**, no suponerlo.

**Dos salidas, no excluyentes:** (i) **expandir la dimensión de origen a celdas** estado × sexo × grupo de educación (32×2×3 = 192), que es literalmente lo que hace Card (2001) con origen × ocupación; (ii) si `MUNICIPIO_RES5A` existe en 1990, construir shares base 1985–1990 a nivel municipio de origen (2,469) — mucho más rico y **más fiel a Card**, que usa localización previa, no lugar de nacimiento.

### 7.4 ★ La base **mide remesas directamente** — la amenaza V3 se vuelve medible
`CAT_INGRESOS` (tabla satélite `LLAVE_INGRESO`):

| clave | descripción |
|---|---|
| 1 | Ingreso principal |
| 2 | Uno o más programas de gobierno |
| 3 | Jubilación o pensión |
| **4** | **Ayuda de personas que viven en otro país** ← remesas internacionales |
| **5** | **Ayuda de personas que viven dentro del país** ← remesas internas |
| 6 | Procampo o Progresa |
| 7 | Otras fuentes |

Esto no estaba en el radar. Tres usos, en orden de valor:
1. **Medir el desplazador de demanda local que no viene del trabajo.** Un mercado con muchas remesas tiene demanda de no transables inflada por una vía que nada tiene que ver con la oferta laboral local ⇒ control natural y prueba de heterogeneidad.
2. **Validar el argumento de migración interna.** Las remesas internas fluyen hacia el **origen**, no hacia el destino. Es una prueba directa del supuesto fijado en Q2 de la nota de ruta.
3. **Como resultado, no como control:** si el instrumento de enclaves predice remesas internas hacia los mercados de origen, tienes evidencia del canal completo.

⚠️ Límite: en 2015 y 2020 el detalle se asignó al jefe de hogar. Úsese a nivel hogar/mercado, no individuo.

### 7.5 ⚠️ El diseño de *commuters* estilo DSS choca con la definición de los mercados
Es el "diferenciador" que entró al núcleo el 2026-08-09. Hay que corregirlo antes de invertir en él.

Los 777 mercados están construidos **precisamente** para internalizar la conmutación: la métrica de disimilitud agrupa municipios con flujo denso entre sí y separa los de flujo escaso. Por lo tanto **la conmutación *entre* mercados es mecánicamente pequeña** — es el criterio de construcción. Un diseño DSS a nivel mercado ("trabaja en *l*, no reside en *l*") se queda casi sin variación por definición.

**La corrección, y es buena noticia:** el diseño DSS pertenece al **nivel municipal, dentro de mercado**, donde la conmutación es densa por construcción. Unidad = municipio; cluster = mercado. Para cada municipio se observa el flujo de gente que **trabaja ahí sin vivir ahí**: oferta laboral sin demanda de consumo. Contrastar la respuesta salarial a (i) choques de oferta por residentes vs. (ii) choques de oferta por conmutantes **es el canal consumidor medido, no supuesto**. Requiere `LLAVE_MUNICIPIO_TRABAJO`, que existe al menos en 2010 (es el insumo con el que se definieron los mercados).

### 7.6 ✅ El Bartik **sí es leave-one-out**, y arranca en 2000
Nota, ec. (2) p. 11 y **fn. 20**: `B^G_lt ≡ Σ_k s_{kl,1990} · g^G_kt`, donde `g^G_kt` es el crecimiento nacional del empleo de la industria *k* *"calculated excluding the local labor market l"*, y *"only data on demand shocks from 2000 and afterward are included"* porque hacen falta dos periodos consecutivos.

Confirma el movimiento fijado en `proceso_estimacion_epsilonD_2026-08-07.md`: **el Bartik industrial entra como CONTROL** (purga demanda local), disponible para las cuatro diferencias (2000, 2010, 2015, 2020). La nota además dice, textual, que estos choques permiten estimar *"the elasticity of labor supply"* — sigue confirmando que la casilla de demanda está vacía.

### 7.7 ⚠️ Los mercados chicos y la ola 2015
279 mercados unimunicipales + la bandera "muestra insuficiente" en 2015 = ruido de medición concentrado justo donde la muestra es delgada. Con `DLogEmpleoCZ` y `LogSalario` construidos de muestras chicas, el error de medición en el regresor endógeno es un problema real (atenúa MCO y en 2SLS interactúa con la fuerza del instrumento). **Ponderar por empleo; reportar sin el cuartil más chico; considerar excluir 2015 del núcleo** y dejarla como ola de robustez.

---

## 8. Preguntas que el diccionario no contesta — checklist para los `.dta`

Ordenadas por cuánto bloquean. Las tres primeras **cambian el diseño**, no solo lo confirman.

1. **¿`EmpleoTot_CZ` en `LongBartikNacional_Trade1.dta` es empleo *transable* o empleo *total*?** Comparar contra `LongBartikNacional.dta` para el mismo MTL-año. Si difiere ⇒ tienes la variable dependiente sectorial gratis. Si es idéntica ⇒ hay que construirla del microdato con `LLAVE_ACTECONOMICA` + crosswalk. **Determina si el diseño de tres columnas cuesta un día o dos semanas.**
2. **¿`LLAVE_ENTIDAD_RES5A` y `LLAVE_MUNICIPIO_RES5A` existen en 1990?** (`tab ANIO if !missing(...)`). Si municipio existe en 1990 ⇒ shares de enclave a nivel municipio de origen (2,469): diseño mucho más fuerte y más fiel a Card. Si no ⇒ estás atado a 32 estados de nacimiento y hay que expandir por celdas demográficas (§7.3).
3. **¿En qué olas existe `LLAVE_MUNICIPIO_TRABAJO`?** Se sabe que en 2010. Si existe en 2000 ⇒ dos periodos para el diseño DSS municipal. Si solo 2010/2015/2020 ⇒ el diseño DSS vive en diferencias de 5 años.
4. **¿Cómo se llama de verdad el identificador de mercado?** (`MERCADO_TRABAJO_LOCAL` / `_LABORAL` / `TRABAJO_MERCADO_LOCAL`).
5. **¿Los agregados cubren las cinco olas sin huecos?** `tab AÑO` en `Demograficos_Nivel.dta` y `SalResMTL_N.dta`. Esperado: 5 × 777 = 3,885 obs. Confirmar que no faltan mercados en 1990.
6. **¿Cuántos mercados tienen `Empleada_T` por debajo de un umbral usable?** Distribución de empleo por mercado y año — insumo del cálculo de potencia, que sigue pendiente.
7. **¿`Prop1990_T_k` está para las 104 industrias o para un subconjunto?** Determina el K real del análisis de pesos de Rotemberg.
8. **¿`FACTOR_EXP` de 2015 reproduce los totales publicados de la Intercensal?** Validación obligatoria de S1 (reproducir una descriptiva de la nota antes de construir nada).
9. **¿`LLAVE_INGRESO` = 4 y 5 tienen cobertura razonable por ola?** Determina si el ejercicio de remesas de §7.4 es viable.

Y una **pregunta de forma**, no de dato: la nota metodológica dice que el código Stata de construcción de los agregados viene incluido. **Léelo antes de replicar nada** — resuelve de un golpe las preguntas 1, 5 y 7.

---

## 9. Las tres preguntas conceptuales de la sesión

### 9.1 Exogeneidad del shift-share: shares vs. shifts, y qué pruebas van en la tesis

Hay **dos regímenes de identificación**, no uno, y no compiten: piden supuestos distintos y se diagnostican distinto. La guía de Borusyak-Hull-Jaravel (2025, JEP) recomienda reportar **ambos** juegos de diagnósticos.

**Régimen GPSS (Goldsmith-Pinkham, Sorkin & Swift 2020) — "los exógenos son los shares".**
El estimador shift-share es *numéricamente idéntico* a un GMM que combina K instrumentos apenas identificados —uno por share— con **pesos de Rotemberg** α_k. La identificación exige `E[s_lo · ε_l] = 0` para los orígenes con peso alto. Diagnósticos:
- **Tabla de pesos de Rotemberg**: qué orígenes concentran la identificación. Con K=32 va a salir brutalmente concentrada (§7.3) — y eso es un resultado que se reporta, no se esconde.
- **Balance de los shares de peso alto** contra niveles pre-periodo: población, composición industrial, escolaridad, pobreza, índice de activos del hogar (§5).
- **Placebo de pre-tendencia**: los mismos shares contra el cambio del resultado en el periodo *previo* (ya está en el plan, con 1990→2000).
- **Heterogeneidad de las K estimaciones apenas identificadas**: si los β_o difieren sistemáticamente, o el instrumento agregado no es exógeno o el efecto es heterogéneo.

**Régimen BHJ (Borusyak, Hull & Jaravel 2022) — "los exógenos son los shifts, condicionales a los shares".**
Los shares pueden ser endógenos; lo que se necesita es que los `g_o` sean casi aleatorios entre orígenes, **muchos**, mutuamente poco correlacionados y sin ninguno dominante. Diagnósticos:
- **Número efectivo de shocks** = 1/Σ_o ŝ_o², con ŝ_o los pesos de exposición agregados. **Con 32 estados, calcúlalo antes de escribir la sección.** Si sale <10, el régimen BHJ no es defendible con orígenes-estado y hay que ir a celdas.
- **Balance a nivel shock**: regresar `g_o` contra promedios de covariables ponderados por exposición.
- **Pre-tendencia a nivel shock.**
- **La regresión equivalente a nivel shock** (la transformación BHJ) y **errores estándar agrupados a nivel origen**, no a nivel mercado.

**Recomendación para esta tesis:** el marco **principal es GPSS** — con 32 orígenes, la identificación honestamente viene de la variación transversal en los shares, no de un experimento entre muchos shocks. BHJ entra como **diagnóstico y como fuente de errores estándar**, no como el argumento. Y hay dos ajustes específicos de este diseño:

- ⚠️ **Hay que eliminar el estado propio del shift-share.** Cada mercado está dentro de algún estado, y 50 cruzan fronteras estatales. El share de residentes nacidos en el estado propio es enorme (típicamente 70–90%). Si lo incluyes, el instrumento se vuelve esencialmente "el empuje nacional del propio estado del mercado", que no es exógeno a nada. **Excluir origen = estado propio, y probablemente también los contiguos**, y decirlo en la ecuación, no en un pie de página.
- **El Bartik industrial como control** (ya decidido) es exactamente la "exogeneidad condicional" que BHJ formalizan: purga el componente de la demanda local que podría correlacionar con los enclaves.

### 9.2 Spillovers por aumento de la demanda de bienes — el nudo

Creo que este punto se te atora porque están mezclados **cuatro mecanismos distintos** bajo un mismo nombre. Separados, cada uno tiene su respuesta.

La ecuación es `Δln w_l = β Δln L_l + X + ε`, instrumentando `Δln L_l` con el empuje de enclaves; `β = −1/ε_D`. Para que β sea la pendiente de la demanda, el instrumento tiene que mover la **oferta** sin mover la **demanda**. Los migrantes hacen cuatro cosas:

**(a) Consumen localmente.** Suben la demanda de no transables ⇒ la curva de demanda de trabajo se desplaza a la derecha ⇒ el salario cae *menos* de lo que el desplazamiento puro de oferta implicaría ⇒ |β| sesgado hacia cero ⇒ **ε_D estimada demasiado elástica**. Éste es el sesgo que te preocupa, y es real.

**(b) Son complementos en producción.** Si traen una mezcla de habilidades distinta, la demanda por trabajadores incumbentes se desplaza. A nivel *agregado* esto no es sesgo — es parte de la curva de demanda agregada de trabajo. Pero significa que el objeto estimado es la elasticidad de demanda del **trabajo total**, no de un tipo de trabajador. Hay que decirlo en la definición del objeto.

**(c) Inducen entrada de capital y de empresas.** Tampoco es sesgo: **es la definición de la elasticidad de demanda local de largo plazo.** Es la razón por la que |ε_D| local es 3–10 y no 0.25–0.7 (la corrección del ancla LPS que ya está en el proyecto). Se declara, no se corrige.

**(d) Se derraman a otros mercados** — violación de SUTVA. Dos vías: desplazamiento de nativos hacia los mercados de control; y derrame de demanda de producto vía comercio entre mercados.

Sólo **(a)** y **(d)** son amenazas. Cuatro respuestas, en orden de fuerza:

1. **Convertir el corte transable/no transable en la prueba, no en la robustez** (ya está en el plan). La lógica: el canal de consumo opera casi enteramente por no transables (vivienda, comercio al menudeo, restaurantes, servicios personales); la demanda del producto transable es nacional, así que la población local casi no mueve su precio. Predicción falsable: **si el canal consumidor importa, |ε_D| en no transables > |ε_D| en transables**, y la estimación transable es la limpia. Es el argumento de Hong & McLaren. **Con la advertencia de §7.2: hay que arreglar primero la definición de transable, porque la de la casa mete el transporte urbano de pasajeros del lado transable.**
   *Matiz que hay que declarar:* un sector transable perfectamente abierto tendría demanda de trabajo **infinitamente elástica** (insensibilidad de precios de factores / Rybczynski). Que la ε_D transable salga finita es información sobre el grado de especialización local, no un fracaso del diseño.

2. **El diseño de conmutantes — y aquí está el vínculo con Dustmann et al. (§9.3).** Un choque de oferta laboral que llega **sin** el choque de consumo.

3. **Medir el canal directamente con `LLAVE_INGRESO` 4 y 5** (§7.4). El canal consumidor deja de ser un supuesto y pasa a ser una variable.

4. **Control de exposición de vecinos estilo Helm (2020)**: incluir el promedio ponderado por conmutación del instrumento de los mercados vecinos. Ataca (d). Se queda como robustez corta, según el alcance congelado. La otra mitad de (d) —desplazamiento de nativos— ya está como una de las 8 especificaciones.

**Lo que NO hay que hacer:** meter un rezago espacial (SAR/SDM). Ya está resuelto en la guía v3 y sigue siendo correcto: los shift-share están *mecánicamente* correlacionados en el espacio; AKM (2019) trata eso como estorbo y SAR como parámetro, y son respuestas incompatibles. Además, separar ρ de β exige que la estructura espacial del instrumento difiera de W, y aquí W (conmutación) *define* los mercados.

### 9.3 Dustmann, Schönberg & Stuhler (2017): cuál es exactamente el vínculo

**No es "un paper simpático sobre migración y salarios". Es el diseño más limpio que existe para aislar un desplazador *puro* de oferta laboral — que es literalmente el requisito de identificación de ε_D.**

DSS estudian una política en la frontera checo-alemana que permitió a trabajadores checos **conmutar** a municipios alemanes fronterizos: **trabajan en el destino pero viven, y gastan, en el origen**. Eso separa el choque de oferta de trabajo del choque de demanda de bienes. Es exactamente el mecanismo (a) de §9.2, neutralizado **por diseño** en lugar de por supuesto.

Tres cosas más de DSS que se mapean uno a uno con las especificaciones del plan:
- **El outflow de nativos contamina el denominador.** El cambio en la oferta laboral local **no** es la entrada de migrantes: los nativos responden saliendo. Por eso hace falta IV sobre `Δln L`, no forma reducida sobre el flujo migratorio. Justifica el 2SLS frente a la forma reducida.
- **Efectos muy distintos a lo largo de la distribución salarial** y por tipo de trabajador; el desplazamiento se concentra abajo. Motiva las especificaciones por calificación (la base permite el corte en *empleo*; en *salario* hay que construirlo del microdato, §3.2).
- **Descomposición empleo vs. salario**: la misma perturbación reparte su incidencia entre precio y cantidad. Es exactamente el objeto de §9.4.

**Cómo se implementa en México, con la corrección de §7.5:** a nivel **municipio dentro de mercado**, con `LLAVE_MUNICIPIO_TRABAJO` vs. `LLAVE_MUNICIPIO`. Factible al menos con 2010, y probablemente 2015 y 2020. A nivel de los 777 mercados no funciona, porque la definición de los mercados se comió esa variación.

### 9.4 Las dos elasticidades juntas: el mensaje de política

Tu intuición es correcta y, en mi lectura, **mejora el encuadre actual**. Vale la pena subirlo de "implicaciones cuantitativas, 2–3 pp." a **el argumento de por qué la tesis importa**.

**La aritmética.** En un mercado local, con demanda `Δln L^d = −ε_D Δln w + D` y oferta `Δln L^s = ε_S Δln w + S`:

| Choque | Efecto en salario | Efecto en empleo |
|---|---|---|
| Demanda `D` (p. ej. Bartik) | `Δln w = D/(ε_D+ε_S)` | `Δln L = ε_S·D/(ε_D+ε_S)` |
| Oferta `S` (p. ej. migración) | `Δln w = −S/(ε_D+ε_S)` | `Δln L = ε_D·S/(ε_D+ε_S)` |

Con ε_D sola no puedes predecir nada. Con **el par**, predices la incidencia de *cualquier* choque o política. Ése es el mensaje: **la tesis entrega la mitad faltante de un par que el mimeo de Banxico ya empezó**, sobre los mismos 777 mercados, las mismas olas y las mismas variables de salario y empleo. Los dos números están *diseñados* para combinarse.

**Y hay una prueba de sobreidentificación que puedes correr con la base publicada, sin datos extra.** De las regresiones de Bartik —que son las del mimeo y son reproducibles desde `LongBartikNacional.dta` + `SalResMTL_N.dta`— obtienes las respuestas de **equilibrio**:

- `Δln L` sobre Bartik ⇒ estima `ε_S/(ε_D+ε_S)`
- `Δln w` sobre Bartik ⇒ estima `1/(ε_D+ε_S)`
- El cociente de ambas ⇒ **una estimación de ε_S**
- La segunda, junto con **tu** ε_D ⇒ **una segunda estimación de ε_S**

Que las dos coincidan es una **restricción testeable de todo el marco**, y sale casi gratis porque todos los insumos ya están publicados. Es, además, la respuesta más contundente a V1 (MRRH): la elasticidad de empleo local de MRRH **es** esa mezcla de equilibrio; tu ε_D es el **insumo estructural** de la que ellos reportan.

**Qué política elegir para el contrafactual.** Una sola, y recomiendo ésta:

> **Incidencia de un impuesto a la nómina (o de una reforma de contribuciones a la seguridad social).** Un impuesto τ sobre el trabajo formal se reparte entre salario y empleo como función de ε_D y ε_S — derivación de una página, nivel Economía I, pero con elasticidades estimadas creíblemente para México y a nivel local.

Por qué ésta y no otra: (i) usa **ambas** elasticidades de manera esencial, no decorativa; (ii) **recupera el hilo fiscal** que buscaba el Ensayo 2 congelado, sin tocar a Correia ni las vulnerabilidades V10/V12/V13 que el crítico demolió; (iii) la extensión natural es informalidad —el impuesto aplica solo al sector formal, genera una cuña, reasigna— lo que reconecta con Ulyssea **sin** tener que identificar σ_FI; (iv) la heterogeneidad espacial es el punto: la incidencia difiere entre mercados con distinta ε_D, y eso es exactamente lo que un panel de 777 mercados puede decir y una estimación nacional no.

Alternativas si ésa no camina: **salario mínimo de la Zona Libre de la Frontera Norte 2019** (duplicación, discontinuidad espacial nítida, pero solo una ola posterior y es 2020); **choque comercial estilo ADH** (la base se construyó explícitamente para replicar ADH en México); **retorno migratorio de EE.UU. 2008–2012**.

⚠️ **Dos advertencias que el ejercicio tiene que llevar impresas:** (1) ε_S viene de *otra* estimación — presenta un **rango**, no un punto, y muestra cómo se mueve el contrafactual; (2) en mercados locales y en el largo plazo, ε_S es la elasticidad de **migración**, potencialmente enorme (Blanchard-Katz), así que ε_S puede aplastar a ε_D y casi toda la incidencia caer en cantidades y no en salarios. **Eso, en sí mismo, es el mensaje de política**, no un problema del ejercicio.

---

## 10. Fuentes externas: qué sí conviene sumar

**El núcleo no necesita nada.** La base + el microdato son autosuficientes para ε_D. Ésa es la noticia más importante de la sesión. Lo demás, ordenado por razón beneficio/costo:

| Fuente | Para qué | Costo | Veredicto |
|---|---|---|---|
| **Censos Económicos** (1989, 94, 99, 04, 09, 14, 19), municipal | Capital, VA, producción, **número de establecimientos**. Disciplina la discusión ε_D→σ y **mide el mecanismo** detrás de una demanda plana en el largo plazo (entrada de empresas) | Bajo, público | **Sí, como S6 opcional** |
| **INPC por ciudad** (Banxico/INEGI, 46 ciudades) | Deflactor espacial parcial (§3.2 punto 4) | Bajo | **Sí, como robustez** |
| **SESNSP, homicidios municipales** | Confusor mayor de la migración interna 2007–2020; además, candidato a *push* nacional estilo Monras | Bajo | Sí como control; **cuidado** como instrumento (la violencia también afecta al destino) |
| **CONAPO: marginación e índices de migración municipal** | Controles de nivel y validación externa de los flujos construidos | Bajo | Sí, para las pruebas de balance |
| **IPUMS International (México)** | ⚠️ La hoja de equivalencia del codebook cubre **solo 12 variables** (PERWT, SCHOOL, YRSCHOOL, SEX, AGE, MARST, RELATE, INCEARN, CLASSWK, EMPSTAT, LABFORCE, HLTHCOV, INDGEN) y **no incluye ninguna variable de migración**. Su valor real ahora es la muestra de EE.UU. para la robustez de red estadounidense (Caballero-Cadena-Kovak) | Medio | **Reserva** |
| **IMSS** (empleo formal mensual, municipal) | Sería el mejor complemento posible | 2–4 meses de acceso | **Fuera del alcance congelado** |
| ENOE | Informalidad bien medida, pero geografía parcial | Medio | No, para este ensayo |

*(Corrección al codebook: la hoja de equivalencia mapea `INDGEN` —que en IPUMS es industria— contra `LLAVE_OCUPACION` —ocupación—. Es un error del documento. No lo uses como crosswalk de industria.)*

---

## 11. Qué cambia en el alcance congelado

El alcance del 2026-08-09 **se sostiene**. No hay nada aquí que obligue a replantear la tesis. Los ajustes son de ejecución:

**Se confirma y se puede tachar de la lista:**
- El id de los 777 es constante entre olas (§7.1). ✅ S0 #2 cerrado.
- Los agregados y el microdato cubren 1990 para empleo, salario, industria y posición en el trabajo (§4.2). ✅ S0 #3 cerrado en lo esencial.
- El Bartik es leave-one-out y está disponible para las cuatro diferencias (§7.6). ✅
- La informalidad pierde 1990, pero la informalidad **no está en el núcleo** — y de todos modos `SITTRA` da un proxy para las cinco olas (§4.2).

**Se agrega al núcleo (costo bajo, valor alto):**
- Construir una **bandera propia de transable** además de la de la casa (§7.2). Es la prueba central del canal consumidor; no puede descansar en una clasificación heredada que mete el camión urbano del lado transable.
- Calcular y reportar el **número efectivo de shocks** y los **pesos de Rotemberg** antes de escribir la sección de identificación (§9.1). Con 32 orígenes, esto puede forzar el paso a celdas origen × demografía.
- **Excluir el estado propio** (y probablemente los contiguos) del shift-share, explícitamente en la ecuación (§9.1).

**Se corrige:**
- El **diseño DSS baja del nivel mercado al nivel municipio-dentro-de-mercado** (§7.5). Sigue siendo el diferenciador; cambia la unidad.
- La **robustez de dos niveles de agregación** deja de ser vaga: es 777 vs. ~925 mercados, reconstruible desde el microdato 2010 (§7.1).

**Se promueve:**
- El **ejercicio de incidencia con ambas elasticidades** sube de "implicaciones cuantitativas" a **el argumento de relevancia de la tesis**, con la prueba de sobreidentificación de §9.4 como pieza propia. Sigue siendo corto de escribir; cambia de lugar en la narrativa.

**Se abre (nuevo, no estaba):**
- El **panel de 4 diferencias** en vez de 2. Con las cinco olas hay 1990→2000, 2000→2010, 2010→2015, 2015→2020 ⇒ **3,108 observaciones** en vez de 1,554, al costo de mezclar ventanas de 10 y 5 años. Y con una ventaja que no es menor: **2010→2015 y 2015→2020 alinean la ventana del resultado con la ventana de `RES5A`**, que era justo el desajuste de la decisión pendiente §6.1 del plan. En contra: 2015 es Intercensal, con muestra insuficiente en algunos municipios (§7.7). **Recomendación: núcleo en diferencias de 10 años (2000→2010, 2010→2020), y el panel de 4 diferencias como especificación alterna que sirve para dos cosas a la vez — potencia y alineación temporal de la migración.**
- El **ejercicio de remesas** (§7.4), que convierte V3 de amenaza en medición.

---

## 12. Siguientes pasos

1. **Cuando lleguen los `.dta`:** correr el checklist de §8 en orden. Empezar por leer el **código Stata de construcción** que viene con la base — resuelve solo las preguntas 1, 5 y 7.
2. **Decidir migración 5 vs. 10 años** (§6.1 del plan) — hoy hay un argumento nuevo a favor del panel de 4 diferencias (§11).
3. **Descargar los 6 papers del Nivel 1** a `papers/06_shift_share_migracion/` — pendiente de tres sesiones. **DSS 2017 primero**: después de §9.3 es el paper que carga el diferenciador.
4. **Correo a econlab@banxico.org.mx**: mimeo de oferta + la pregunta sobre el lado de demanda (decisión de scooping V4; es una de las 3 preguntas para el asesor).
5. **Agregar la amenaza de desplazamiento de nativos a §5 de `ruta_empirica_shift_share_migracion_2026-07-23.md`** — pendiente documental de cuatro sesiones.
6. **Cálculo de potencia** — ahora con dos escenarios de N (1,554 y 3,108).
