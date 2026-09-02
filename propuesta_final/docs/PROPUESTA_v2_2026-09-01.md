# La elasticidad de la demanda de trabajo en los mercados laborales locales de México
### Propuesta de tesis de maestría — versión 2, 2026-09-01

> **Este documento supersede el encuadre de** `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md` (que aún describe la ruta estructural-primero) **y consolida** la ruta empírica (2026-07-23), el proceso de estimación (2026-08-07), la guía de lectura v3 (2026-08-07), el plan de maestría (2026-08-09) y el inventario de datos (2026-09-01). Es el único documento que hay que leer para entender la tesis.
>
> **Compañeros:** `CUADERNO_EXPLORACION_2026-09-01.md` (el mapa de datos y el catálogo descriptivo) · `inventario_datos_EconLab_LLM_2026-09-01.md` (el detalle técnico de la base).

---

## §0. Lo que cambió en esta versión

Tres cosas, y las tres importan.

1. **Los datos están en la máquina.** 21 GB en `data/`: los 29 agregados de mercado-año, el microdato de personas de las cinco olas y el de vivienda. Varias preguntas que estaban abiertas ya se contestaron contra los `.dta` reales, no contra el diccionario (§3).
2. **El mensaje de política sube al centro.** La tesis deja de ser "estimo un parámetro que nadie ha estimado" y pasa a ser "entrego la mitad faltante de un par de elasticidades con la que se puede predecir la incidencia de una política". Hay además una prueba de consistencia que sale gratis (§5).
3. **⚠️ El claim de "casilla vacía" se corrige.** La búsqueda de esta sesión encontró dos antecedentes mexicanos directos —Mishra (2007) y Hanson (2005)— y, más grave, encontró que **Hanson rechaza explícitamente el instrumento de enclaves para México**. Eso no mata la tesis, pero cambia cómo hay que escribirla y obliga a una respuesta frontal en §4.3. Es el cambio más importante de esta versión.

---

## §1. La idea, en una página

### El objeto

Se estima la **pendiente de la curva de demanda de trabajo en un mercado laboral local**:

$$\varepsilon_D \equiv -\frac{\partial \ln L_l}{\partial \ln w_l}\bigg|_{\text{demanda}}$$

mediante 2SLS sobre diferencias largas entre los **777 mercados laborales locales** de México (Aldeco, Calderón, Chiquiar, Hanson, Pérez Pérez y Velázquez, 2024), 1990–2020:

$$\Delta \ln w_{lt} = \beta \,\Delta \ln L_{lt} + \gamma' X_{lt} + \delta_t + \epsilon_{lt}, \qquad \beta = -1/\varepsilon_D$$

instrumentando $\Delta \ln L_{lt}$ con un **shift-share de enclaves de migración interna** al estilo Card (2001): la exposición del mercado $l$ al empuje migratorio nacional de cada estado de origen $o$, pesada por dónde vivían históricamente los nacidos en $o$.

$$Z_{lt} = \sum_{o \neq o(l)} s_{ol,1990}\; g_{ot}^{(-l)}$$

### Por qué hace falta un instrumento de **oferta**

Una regresión de salario contra empleo local no identifica nada: ambos son de equilibrio. Para trazar la **demanda** hay que mover la **oferta**. Ése es todo el diseño, y es la razón por la que este trabajo es el complemento —no el sustituto— de lo que ya existe.

### El posicionamiento, y su límite honesto

La base publicada por Banxico trae **choques Bartik de demanda** ya construidos. Un desplazador de demanda identifica la **elasticidad de oferta**, y eso es exactamente lo que hace el mimeo companion (Aldeco, Chiquiar, Pérez Pérez y Salcedo, *Estimación de la elasticidad de la oferta de trabajo en México*). La propia nota metodológica lo dice textual: los Bartik permiten estimar *"the elasticity of labor supply"*. **El lado de la demanda queda vacío en esa base.**

Pero "vacío en esa base" no es "vacío en la literatura". Existen antecedentes mexicanos:

| Trabajo | Qué estima | Unidad | Periodo | Resultado |
|---|---|---|---|---|
| **Mishra (2007, JDE 82(1))** | Elasticidad del salario respecto al flujo de emigrantes | **Celdas nacionales** educación×experiencia (estilo Borjas 2003) | 1970–2000 | **0.4** ⇒ implica $\lvert\varepsilon_D\rvert \approx 2.5$ |
| **Hanson (2005/2007)** | Efecto de la exposición a la emigración sobre la distribución salarial | **32 estados** de nacimiento | 1990–2000 | Salarios +6–9% en estados de alta migración |

Ambos usan **emigración a Estados Unidos** como el choque de oferta. Lo que no está hecho, y es lo que esta tesis hace:

1. al nivel de **mercado laboral local** (777 unidades, no 32 estados ni celdas nacionales);
2. con **migración interna** como desplazador, no emigración;
3. sobre **1990–2020**, no solo los noventa;
4. con el **aparato moderno de shift-share** (pesos de Rotemberg, número efectivo de shocks, balance a nivel shock, inferencia AKM), que no existía cuando se escribieron;
5. y con la **descomposición transable / no transable** que convierte la amenaza del canal consumidor en un resultado.

> **La contribución, en una frase.** Estimar la pendiente de la demanda de trabajo local en México con un diseño cuasi-experimental de migración interna, y usarla junto con la elasticidad de oferta ya estimada para predecir la incidencia —salario contra empleo— de una política laboral.

### La respuesta a Monte-Redding-Rossi-Hansberg, que va en la página 1

MRRH (2018, AER) reportan la **elasticidad de empleo local de equilibrio**, que mezcla oferta, demanda y conmutación. No es un sustituto de lo que se estima aquí: es una función de ello. La pendiente de la demanda es un **insumo** de su modelo. Presentar ambos números como si compitieran sería un error de categoría, y hay que decirlo antes de que alguien lo pregunte.

### Un ancla numérica, corregida

⚠️ El rango clásico $\lvert\varepsilon_D\rvert \approx 0.25\text{–}0.7$ (Lichter, Peichl y Siegloch, 2015, *EER*) **no aplica a este número**: mide la elasticidad propia a nivel industria o empresa, con capital fijo. Aquí se estima una elasticidad **local y de largo plazo**, donde ajustan el capital, la entrada de empresas y la composición industrial. La literatura de mercados locales implica $\lvert\varepsilon_D\rvert$ de **3 a 10**, y el 2.5 implícito en Mishra (2007) cae justo debajo de esa banda — un contraste externo tranquilizador.

**Si $\varepsilon_D$ sale en 0.4, hay que desconfiar, no celebrar.**

---

## §2. La literatura, ordenada

Seis bloques. Cada uno responde a **una** pregunta; no es un catálogo. La columna final dice si el PDF está en el repo.

### Bloque 1 — ¿Cómo se identifica un desplazamiento de oferta laboral?

Es *el* bloque: define el diseño.

| Lectura | Qué aporta a esta tesis | ¿En repo? |
|---|---|---|
| **Card (2001, JOLE)** | El instrumento de enclaves en su forma canónica: shares de asentamiento previo × empuje nacional por origen. La plantilla literal. También la respuesta de nativos ("native outflows"). | ❌ |
| **Altonji & Card (1991)** | El original del diseño de áreas; el marco de oferta/demanda que hace que el 2SLS signifique algo. | ❌ |
| **★ Dustmann, Schönberg & Stuhler (2017, QJE)** | **El pick #1.** No es "un paper de migración y salarios": es el diseño más limpio que existe para aislar un desplazador **puro** de oferta. Los conmutantes checos trabajan en Alemania y **gastan en Chequia** ⇒ oferta sin consumo. Es la respuesta al canal consumidor, hecha por diseño y no por supuesto. Además: (i) el outflow de nativos contamina el denominador, lo que justifica IV sobre $\Delta\ln L$ en vez de forma reducida sobre el flujo migratorio; (ii) efectos muy distintos a lo largo de la distribución salarial. | ❌ |
| **Boustan, Fishback & Kantor (2010, JOLE)** | Migración **interna** como choque de oferta — la plantilla de que esto se puede hacer sin cruzar fronteras. | ❌ |

### Bloque 2 — ¿Cuándo es creíble un shift-share?

| Lectura | Qué aporta | ¿En repo? |
|---|---|---|
| **Goldsmith-Pinkham, Sorkin & Swift (2020, AER)** | El régimen "los exógenos son los **shares**". Da los **pesos de Rotemberg**, que aquí son obligatorios porque el número de orígenes es chico. **Es el marco principal de esta tesis.** | ❌ |
| **Borusyak, Hull & Jaravel (2022, REStud)** | El régimen "los exógenos son los **shifts**, condicionales a los shares". Aquí entra como diagnóstico y como fuente de errores estándar agrupados por origen, no como el argumento. | ❌ |
| **★ Borusyak, Hull & Jaravel (2025, JEP 39(1), 181-204)** | La guía práctica. Su ejemplo corrido es el espejo de esta regresión, y recomienda reportar **ambos** juegos de diagnósticos. La lectura más rentable por página. | ❌ |
| **Jaeger, Ruist & Stuhler (2018, NBER WP 24285)** | La crítica: los shares de enclave son persistentes, así que el instrumento mezcla el efecto de corto y largo plazo. **Es la versión moderna de la objeción de Hanson (§4.3).** | ❌ |
| **Adão, Kolesár & Morales (2019, QJE)** | Los shift-share están **mecánicamente** correlacionados en el espacio ⇒ los errores estándar convencionales sobre-rechazan. La corrección de inferencia. | ❌ |
| Borusyak & Hull (2023, Ecma 91(6)) | Instrumentos construidos con exposición no aleatoria; recentrado. Solo si el balance falla. | ❌ |

### Bloque 3 — ¿Qué objeto es $\varepsilon_D$ y cuánto debería valer?

| Lectura | Qué aporta | ¿En repo? |
|---|---|---|
| **Hamermesh (1993)**, *Labor Demand* | La taxonomía: propia vs. cruzada, corto vs. largo plazo, constante-producto vs. escala. Fija **qué** se está estimando. | ❌ |
| **Lichter, Peichl & Siegloch (2015, EER)** | El meta-análisis con el rango 0.25–0.7 — **y por qué NO es el ancla de este número** (§1). Se reserva para la capa de discusión de $\sigma$. | ❌ |
| **★ Monte, Redding & Rossi-Hansberg (2018, AER)** | **El rival.** Elasticidad de empleo local de equilibrio con conmutación. La respuesta está en §1. | ❌ |
| **Borjas (2003, QJE 118(4))** | *"The Labor Demand Curve Is Downward Sloping"* — el título es el programa. Choque de oferta ⇒ curva de demanda ⇒ parámetro CES. Es la familia a la que pertenece esta tesis. | ❌ |
| Ottaviano & Peri (2012, JEEA); Card (2012, JEEA); Llull (2018, REStud) | La discusión sobre qué elasticidad de sustitución se recupera y con qué agregación. Nivel 3. | ❌ |

### Bloque 4 — ¿Cómo se ve esto en México?

| Lectura | Qué aporta | ¿En repo? |
|---|---|---|
| **★ Aldeco, Calderón, Chiquiar, Hanson, Pérez Pérez & Velázquez (2024)** | La definición de los 777 mercados y la base. Relectura quirúrgica: §2.1 (el algoritmo), ec. (2) y fn. 20 p. 11 (el Bartik es **leave-one-out**, disponible 2000+), fn. 18 p. 11 (los módulos de migración están *"within project's scope in the next stage"* — el aviso de scooping). | ✅ |
| **★ Mishra (2007, JDE 82(1), 180-199)** | El antecedente numérico: elasticidad del salario al flujo migratorio = **0.4** en celdas nacionales, 1970–2000. El contraste externo del resultado. | ❌ |
| **★ Hanson (2005 WP; en Borjas ed., 2007)** | El antecedente de diseño **y la objeción principal**. Ver §4.3. ⚠️ Verificar la referencia publicada exacta antes de citar. | ⬇️ descargado a `tool-results/` |
| **Monras (2020, JPE)** | La crisis del peso como *push* nacional mexicano. La plantilla de "de dónde sale el shift". | ❌ |
| Caballero, Cadena & Kovak (2018) | Construcción de redes migratorias mexicanas. Reserva para la robustez con red estadounidense. ⚠️ Año/revista por verificar. | ❌ |
| Aldeco, Chiquiar, Pérez Pérez & Salcedo (mimeo) | **El otro lado del par.** No indexado; hay que pedirlo a econlab@banxico.org.mx. | ❌ |

### Bloque 5 — ¿Cómo se pasa de una elasticidad estimada a una pregunta estructural?

Éste es el molde del argumento, y era el bloque que faltaba hasta la guía v3.

| Lectura | Qué aporta | ¿En repo? |
|---|---|---|
| **★ Suárez Serrato & Zidar (2016, AER 106(9), 2582-2624)** | **Lo más cercano a la arquitectura de esta tesis**: elasticidades *design-based* → modelo de equilibrio espacial → contrafáctico de incidencia. Tiene Comment+Reply en AER; leer los tres. | ❌ |
| **Kline & Moretti (2014, QJE 129(1), 275-331)** | Evaluación de una política de desarrollo local con elasticidades locales. ⚠️ **No** confundir con el Kline-Moretti del *Annual Review* del mismo año. | ❌ |
| **Notowidigdo (2020, JOLE 38(3))** | Incidencia asimétrica de choques locales. El puente entre elasticidades y quién gana o pierde. | ❌ |
| Diamond (2016, AER 106(3)) | Equilibrio espacial con amenidades endógenas. Nivel 3. | ❌ |
| Raval (2019); Oberfield & Raval (2021, Ecma 89(2)) | El mapeo $\varepsilon_D \to \sigma$ y el teorema de agregación micro→macro. **Aquí es discusión, no estimación** (§6, §2 del alcance). | ❌ |

### Bloque 6 — Qué NO se hace, y por qué

Decir esto explícitamente en la tesis vale más que hacerlo mal.

- **Econometría espacial (SAR/SDM) fuera del núcleo.** Los shift-share están mecánicamente correlacionados en el espacio; **AKM (2019) trata eso como estorbo y el SAR como parámetro, y son respuestas incompatibles al mismo hecho**. Además, separar $\rho$ de $\beta$ exige que la estructura espacial del instrumento difiera de $W$, y aquí $W$ (la conmutación) **define** los mercados. Sustituto: dos niveles de agregación y exposición de vecinos estilo **Helm (2020, REStud 87(3))**.
- **$\sigma$ estructural: discusión, no estimación.** El mapeo $\varepsilon_D \to \sigma$ son dos páginas de interpretación. Ahí vive la brecha local-largo-plazo vs. agregado-ciclo (V10) y no se resuelve con datos censales.
- **Informalidad: trabajo futuro.** La descomposición formal/informal exige una elasticidad de sustitución entre sectores que el censo no identifica (V5).
- **El diseño de dos instrumentos de JRS: se menciona, no se estima.** Con dos periodos no hay potencia.

### Estado del acervo — el problema operativo

**De las lecturas marcadas ★, solo una está en el repo.** `papers/06_shift_share_migracion/` y `papers/07_arquitectura_elasticidad_estructural/` están **vacías** desde que se crearon el 2026-08-09. Es un pendiente de tres sesiones y ahora bloquea la redacción de §4, porque el diseño se defiende citando a DSS, GPSS y BHJ, no parafraseándolos.

**Ruta mínima, seis lecturas, en este orden:** DSS 2017 → Card 2001 → BHJ 2025 (JEP) → GPSS 2020 → JRS 2018 → MRRH 2018.

---

## §3. Los datos: qué hay, qué habilitan y qué obligan

### 3.1 La base

**Banco de México / EconLab, *Local Labor Markets in Mexico*** (SIDIE Datasets), descarga directa. Tres niveles unidos por un modelo estrella:

- **777 mercados laborales locales** = agrupación de **2,469 municipios** por intensidad de conmutación, con el algoritmo de Fowler-Jensen / Tolbert-Sizer usado por el ERS de Estados Unidos.
- **Microdato individual** (66 variables) y de vivienda (42), armonizado entre olas.
- **29 bases agregadas** de mercado-año: demografía y empleo, salarios residualizados, informalidad, vulnerabilidad y **choques Bartik pre-construidos**.

**Olas:** 1990, 2000, 2010, **2015 (Intercensal)**, 2020. El censo 2020 se levantó del 2 al 27 de marzo de 2020 ⇒ **es pre-COVID**.

### 3.2 Lo verificado contra los `.dta` (no contra el diccionario)

| Verificación | Resultado |
|---|---|
| ¿`EmpleoTot_MTL` en los archivos `_Trade1` es sectorial o total? | **✅ SECTORIAL.** Mercado 1, 1990: total 200,320 · transable 91,310 · no transable 105,620. **El diseño de tres columnas cuesta un día, no dos semanas.** |
| ¿El id de los 777 es constante entre olas? | **✅ Sí, por construcción.** La partición se definió **una** vez con conmutación del Censo 2010 sobre el marco geoestadístico 2010. Precio: para 1990 es un supuesto que hay que declarar. |
| ¿La industria está armonizada en 1990? | **✅ Sí.** SCIAN 3 dígitos, **104 industrias**, 223 mapeos para 1990 ⇒ los shares base 1990 son legítimos y se pueden reconstruir con cualquier corte. |
| ¿El Bartik es leave-one-out? | **✅ Sí** (fn. 20 de la nota, textual), disponible 2000+ ⇒ cubre las cuatro diferencias. |
| Dimensiones | `Demograficos_Nivel` 3,885 = 5×777 · `WideBartikNacional` 3,108×321 con 104 `Prop1990_T_k` · `Tasa_Crecimiento_Industria_Nacional` 520 = 104×5 · `Informalidad` 3,105 (2000+) · `SalResMTL_N` 3,882 |
| ¿`RES5A` y `MUNICIPIO_TRABAJO` existen en 1990? | **⚠️ Las columnas existen en las cinco olas.** Falta ver si están **pobladas** — el codebook codifica "sin valor" como categoría del catálogo, no como nulo. **Es la verificación S0 pendiente y es la única que sigue bloqueando.** |

### 3.3 Los cuatro hechos que obligan a decisiones de diseño

**(a) La bandera "transable" de la base no sirve para el argumento que se le quiere dar.**
`CAT_ACTECONOMICA` trae `LLAVE_EXPORTADORA` (53 transables / 50 no / 1 sin clasificar), que alimenta todos los archivos `_Trade0`/`_Trade1`. Del lado **transable** mete comercio al por mayor, **todo el transporte —incluido el 485, transporte urbano de pasajeros (camión, colectivo, taxi)—**, bolsa y renta de autos; y deja hotelería y restaurantes del lado no transable. El nombre lo delata: es una clasificación de **sectores exportables**, no de *"precio determinado nacionalmente"*.
⇒ **Decisión:** usar `LLAVE_EXPORTADORA` como la definición de la casa (comparabilidad con el mimeo) **y construir una bandera propia** (agricultura + minería + manufactura, quizá + turismo) desde `LLAVE_ACTECONOMICA` en el microdato. Reportar ambas. Es una decisión declarada de la tesis, no una herencia silenciosa.

**(b) El origen del instrumento son 32 estados y no hay más.**
Existe `LLAVE_ENTIDAD_NAC` pero **no existe `LLAVE_MUNICIPIO_NAC`**: el censo no pregunta municipio de nacimiento. Con $K=32$, el marco de "muchos shocks" de BHJ se tambalea y el número efectivo de shocks va a estar dominado por media docena de estados expulsores.
⇒ **Decisión:** (i) calcular y reportar el número efectivo de shocks **antes** de escribir §4; (ii) expandir el origen a **celdas** estado × sexo × grupo de educación (192), que es lo que hace Card (2001) con origen × ocupación; (iii) si `MUNICIPIO_RES5A` resulta poblado en 1990, construir shares a nivel municipio de origen (2,469) — más rico y más fiel a Card.

**(c) La base mide remesas, y eso convierte una amenaza en una variable.**
`CAT_INGRESOS` clave **4** = *"ayuda de personas que viven en otro país"* y clave **5** = *"ayuda de personas que viven dentro del país"*. Las remesas eran la amenaza V3 de la crítica de julio; ahora son observables. Tres usos: control del desplazador de demanda que no viene del trabajo; validación de que las remesas internas fluyen al **origen** y no al destino; y como resultado propio.
⚠️ En 2015 y 2020 el detalle se asignó al jefe de hogar ⇒ usar a nivel hogar o mercado, nunca individuo.

**(d) El diseño de conmutantes tiene que bajar de nivel.**
Los 777 mercados se construyeron **precisamente** para internalizar la conmutación: el índice de disimilitud agrupa municipios con flujo denso y separa los de flujo escaso. Por lo tanto **el flujo entre mercados es mecánicamente mínimo** — es el criterio de construcción. Un diseño DSS a nivel mercado se queda sin variación por definición.
⇒ **Decisión:** el diseño de conmutantes vive a nivel **municipio dentro de mercado** (unidad = municipio, cluster = mercado), donde la conmutación es densa por construcción. Requiere `LLAVE_MUNICIPIO_TRABAJO`, que existe al menos en 2010 porque es el insumo con el que se definieron los mercados.

### 3.4 Las cuatro cosas que la base NO tiene

1. **Empleo y salario por industria a nivel mercado** — solo los shares de 1990. (El empleo *sectorial* transable/no transable sí está, §3.2.)
2. **Deflactor espacial.** `Real_Ingreso` = ingreso / INPC **nacional**. Todos los salarios reales son nominales deflactados por un índice nacional. Caveat obligatorio: un choque de oferta que baja el salario nominal local también baja el costo local de la vivienda.
3. **Migración agregada a nivel mercado.** La nota lo dice (fn. 18): está fuera del alcance de esta etapa del proyecto. **Todo el instrumento se construye desde cero.**
4. **Capital, producto y establecimientos.** Si el mapeo $\varepsilon_D \to \sigma$ pasara de discusión a estimación, harían falta Censos Económicos.

### 3.5 Dos problemas de medición que hay que administrar

- **279 de 777 mercados (36%) son un solo municipio.** Rurales, muestra delgada. Con `DLogEmpleoMTL` y `LogSalario` construidos de muestras chicas, el error de medición en el regresor endógeno atenúa MCO e interactúa con la fuerza del instrumento. ⇒ **Ponderar por empleo; robustez sin el cuartil más chico.**
- **La ola 2015 es una encuesta, no un censo**, y `CAT_COBERTURA` marca municipios con *"muestra insuficiente"*. ⇒ Considerar 2015 fuera del núcleo y usarla como ola de robustez.

### 3.6 Comparabilidad — la letra chica que va en la sección de datos

En 1990 el ingreso **no** está top-coded en 999998 (se recodificó a 99999999) y está dividido entre mil por el cambio a nuevos pesos · en 2015/2020 el detalle de tipo de ingreso se asigna al jefe de hogar · no hay panel de personas (`ID_PERSONA` es un consecutivo en 1990/2000/2010) · en 1990–2000 hogar ≠ vivienda · **la derechohabiencia (`DHSERSAL`) y las prestaciones no existen en 1990**, por eso `Informalidad.dta` empieza en 2000 — pero `SITTRA` sí está en las cinco olas y da un proxy alterno · `CAUSAMIGRACION` solo existe en 2000 y 2020, así que **no se puede filtrar por "migró por motivos laborales"**.

---

## §4. Metodología

### 4.1 Construcción

**Shares (exposición).** Para cada mercado $l$ y origen $o$, la participación de los nacidos en $o$ dentro de la población del mercado en el año base 1990:
$$s_{ol,1990} = \frac{\text{Pob}_{ol,1990}}{\text{Pob}_{l,1990}}$$
Construidos del microdato con `LLAVE_ENTIDAD_NAC` + el crosswalk municipio→mercado. **Se excluye el estado propio del mercado** (§4.3).

**Shifts (empuje).** El crecimiento nacional del flujo de salida del estado $o$ entre $t-1$ y $t$, **leave-one-out** (excluyendo el mercado $l$), construido con `LLAVE_ENTIDAD_RES5A`.

**⚠️ La asimetría temporal, y por qué se acepta.** Los shares se miden con lugar de **nacimiento** (stock, sin ventana) y los shifts con residencia hace **5 años** (flujo, ventana de 5). El resultado corre en diferencias de 10. La vía asimétrica es la recomendada y hay que justificarla: el share solo necesita capturar *dónde está la red*, que es persistente; el shift necesita capturar *cuándo se movió la gente*, que no lo es.

### 4.2 Especificación

| # | Especificación | Signo esperado |
|---|---|---|
| 1 | Primera etapa: $\Delta \ln L_l$ sobre $Z_l$ | $\pi > 0$, **F ≥ 10 es el go/no-go** |
| 2 | Forma reducida: $\Delta \ln w_l$ sobre $Z_l$ | $< 0$ |
| 3 | MCO: $\Delta \ln w_l$ sobre $\Delta \ln L_l$ | menos negativo que IV (sesgo de demanda) |
| 4 | **2SLS** | $\beta \in [-0.3, -0.1]$ ⇒ $\lvert\varepsilon_D\rvert \in [3,10]$ |
| 5 | 2SLS, empleo **transable** | la estimación limpia del canal consumidor |
| 6 | 2SLS, empleo **no transable** | **debe salir MÁS elástico que transable** |
| 7 | Placebo de pre-tendencia (shares 1990 vs. $\Delta$ 1990→2000) | $\approx 0$ |
| 8 | Desplazamiento de nativos: salida de nativos sobre $Z_l$ | $> 0$ ⇒ el 2SLS es necesario |

**Controles, en columnas acumulativas:** efectos fijos de periodo → **el Bartik industrial de la base** (purga la demanda local; posiciona la tesis frente al mimeo, que lo usa como instrumento) → composición demográfica y educativa inicial → participación industrial inicial → exposición a remesas.

**Ventana.** Núcleo en **diferencias de 10 años** (2000→2010, 2010→2020; N = 1,554), con 1990→2000 reservado como placebo. Alterna: el **panel de 4 diferencias** (N = 3,108), que además **alinea la ventana del resultado con la de `RES5A`** en 2010→2015 y 2015→2020 — resolviendo de paso la asimetría de §4.1, al costo de mezclar ventanas y de meter la ola 2015.

### 4.3 ⚠️ La objeción de Hanson, y la respuesta

**Ésta es la costura más delgada de la tesis y hay que atacarla de frente, no en un pie de página.**

Hanson (2005), coautor de la propia base que se usa aquí, **rechaza explícitamente el instrumento de enclaves para México**. Textual:

> *"historical state emigration rates are unlikely to be a valid instrument for current migration rates. Emigration opportunities in an individual's birth state may have affected an individual's accumulation of human capital, either by influencing the individual's early employment prospects (if local emigration rates affect local wage levels) or the quality of education the individual received as a youth."*

Es la misma objeción que Jaeger, Ruist y Stuhler (2018) formalizan: **los shares de enclave son persistentes, así que correlacionan con todo lo que sea persistente** — incluida la formación de capital humano y las tendencias locales de largo plazo.

**Cuatro respuestas, y ninguna es completa por sí sola:**

1. **El objeto no es el mismo.** Hanson analiza el **origen**: cómo le fue a la gente nacida en estados de alta emigración. Esta tesis analiza el **destino**: cómo le fue a un mercado según la composición por origen de *quienes ya vivían ahí*. Su mecanismo de contaminación —la emigración moldea el capital humano de quien nace ahí— opera sobre el individuo en su estado natal, no sobre el mercado receptor. **No lo mata, pero cambia la dirección del sesgo y hay que argumentarlo, no asumirlo.**
2. **Es migración interna, no emigración.** El canal de Hanson pasa por la *opción* de emigrar a Estados Unidos y su efecto sobre el retorno esperado a la educación. La migración interna no tiene ese premio salarial y ese canal se debilita.
3. **El salario está residualizado por edad y educación** (`ResIngresoEE`, ya construido en la base). Si el mecanismo es composición de capital humano, residualizar absorbe buena parte.
4. **Y sobre todo: es una hipótesis testeable, no una condena.** Es exactamente lo que miden las pruebas de balance de GPSS. Si los shares de peso alto predicen niveles pre-periodo de escolaridad, salario o pobreza, Hanson tiene razón y hay que recentrar (Borusyak-Hull 2023) o cambiar de diseño.

⇒ **En la tesis, esto no es una amenaza escondida: es una sección.** Se cita a Hanson, se corre el balance, y se reporta el resultado sea cual sea.

### 4.4 Pruebas de exogeneidad — los dos regímenes

**Marco principal: GPSS** (con 32 orígenes, la identificación honestamente viene de la variación transversal de los shares).
- Tabla de **pesos de Rotemberg** por origen — va a salir concentrada, y eso se reporta, no se esconde.
- **Balance** de los shares de peso alto contra niveles pre-periodo: población, composición industrial, escolaridad, pobreza, índice de activos del hogar. **Es la prueba de la objeción de Hanson.**
- Placebo de pre-tendencia.
- Heterogeneidad de las $K$ estimaciones apenas identificadas.

**Diagnóstico e inferencia: BHJ.**
- **Número efectivo de shocks** $= 1/\sum_o \hat{s}_o^2$. **Se calcula antes de escribir la sección.** Si sale < 10, el régimen BHJ no es defendible con orígenes-estado y hay que ir a celdas.
- Balance a nivel shock; pre-tendencia a nivel shock.
- **Errores estándar agrupados por origen**, más la corrección de Adão-Kolesár-Morales.

### 4.5 Lo que resuelve el canal consumidor

Los migrantes hacen cuatro cosas y solo dos son amenazas:

| Mecanismo | ¿Sesgo? | Tratamiento |
|---|---|---|
| (a) **Consumen localmente** ⇒ sube la demanda de no transables | **Sí.** $\lvert\beta\rvert$ hacia cero ⇒ $\varepsilon_D$ demasiado elástica | Corte sectorial como **prueba**; diseño de conmutantes; exposición a remesas |
| (b) Son complementos en producción | No. Redefine el objeto: es la demanda de trabajo **total** | Se declara en la definición |
| (c) Inducen entrada de capital y de empresas | **No.** *Es* la definición de la elasticidad local de largo plazo | Se declara; es por qué el ancla es 3–10 y no 0.25–0.7 |
| (d) Se derraman a otros mercados | **Sí.** SUTVA | Desplazamiento de nativos (espec. 8); exposición de vecinos estilo Helm |

El corte sectorial deja de ser robustez y pasa a ser **la prueba**: si el canal consumidor importa, no transables debe salir más elástico que transables. Con la advertencia de §3.3(a): primero hay que arreglar la definición de transable.

---

## §5. La política: dos ramas, presentadas por separado

**Este apartado no elige.** Son dos enfoques de tesis distintos, con alcance y riesgo distintos, para decidir con el asesor.

### La aritmética que ambas comparten

Con demanda $\Delta \ln L^d = -\varepsilon_D \Delta \ln w + D$ y oferta $\Delta \ln L^s = \varepsilon_S \Delta \ln w + S$:

| Choque | Salario | Empleo |
|---|---|---|
| Demanda $D$ (Bartik) | $\Delta \ln w = \dfrac{D}{\varepsilon_D+\varepsilon_S}$ | $\Delta \ln L = \dfrac{\varepsilon_S D}{\varepsilon_D+\varepsilon_S}$ |
| Oferta $S$ (migración) | $\Delta \ln w = \dfrac{-S}{\varepsilon_D+\varepsilon_S}$ | $\Delta \ln L = \dfrac{\varepsilon_D S}{\varepsilon_D+\varepsilon_S}$ |

Con $\varepsilon_D$ sola no se predice nada. **Con el par se predice la incidencia de cualquier choque.** Ése es el argumento de relevancia: la tesis entrega la mitad faltante de un par que el mimeo de Banxico ya empezó, sobre los mismos 777 mercados, las mismas olas y las mismas variables.

---

### Rama A — Incidencia ex-ante (simulación)

**Qué es.** $\varepsilon_D$ (tuya) + $\varepsilon_S$ (mimeo) → predecir el reparto salario/empleo de una política. Aplicación recomendada: **incidencia de un impuesto a la nómina** o de un cambio en las cuotas de seguridad social.

**Alcance:** 3–5 páginas · **Identificación propia:** ninguna · **Cabe en el recorte congelado:** sí, entero.

**Y trae una prueba de sobreidentificación que sale gratis.** Las regresiones de Bartik —las del mimeo, reproducibles desde `LongBartikNacional.dta` + `SalResMTL_N.dta`, que ya están en `data/`— dan las respuestas de **equilibrio**:

- $\Delta \ln L$ sobre Bartik $\;\Rightarrow\; \varepsilon_S/(\varepsilon_D+\varepsilon_S)$
- $\Delta \ln w$ sobre Bartik $\;\Rightarrow\; 1/(\varepsilon_D+\varepsilon_S)$
- El cociente $\;\Rightarrow\;$ **una estimación de $\varepsilon_S$**
- La segunda, con **tu** $\varepsilon_D$ $\;\Rightarrow\;$ **una segunda estimación de $\varepsilon_S$**

Que coincidan es una **restricción testeable de todo el marco**, y todos los insumos ya están publicados. Es también la respuesta más contundente a MRRH.

**Ventajas:** recupera el hilo fiscal que buscaba el Ensayo 2 congelado sin tocar a Correia ni las vulnerabilidades V10/V12/V13; la extensión natural es informalidad —el impuesto aplica solo al sector formal, genera una cuña— sin tener que identificar $\sigma_{FI}$; y la heterogeneidad espacial es el punto, que es lo que un panel de 777 mercados puede decir y una estimación nacional no.

**Riesgos:** $\varepsilon_S$ es ajena ⇒ hay que presentar un **rango**, no un punto. Y en mercados locales de largo plazo $\varepsilon_S$ es una elasticidad de **migración**, potencialmente enorme (Blanchard-Katz), así que puede aplastar a $\varepsilon_D$ y casi toda la incidencia caer en cantidades. **Eso, en sí mismo, es el mensaje de política**, no una falla del ejercicio.

---

### Rama B — Evaluación ex-post de una política real

**Qué es.** Estimar el efecto causal de una política ocurrida entre olas censales. **Requiere una estrategia de identificación propia además del shift-share** ⇒ agranda la tesis fuera del alcance congelado.

**Menú, fechado contra las ventanas censales:**

| Política | Ventana | Variación local | Riesgo |
|---|---|---|---|
| **★ Salario mínimo 2016–2020 (mordida por mercado)** | 2015→2020 | La mordida varía con la distribución salarial de cada mercado | El censo 2020 es de marzo 2020: ventana corta |
| **Zona Libre de la Frontera Norte, ene-2019** | 2015→2020 | 43 municipios fronterizos + **todo Baja California**; salario mínimo **×2** | Solo 14 meses post; **tratamiento empaquetado**: sube el mínimo 100%, baja el IVA a la mitad y baja el ISR |
| China / OMC 2001 | 2000→2010 | Exposición industrial (la base se construyó para replicar ADH) | Muy transitado; y ya hay trabajo con zonas de conmutación mexicanas |
| Seguro Popular 2004–2010 | 2000→2010 | Despliegue escalonado | **Contamina la propia medida de informalidad** (`DHSERSAL`) |
| Apertura / TLCAN 1994 | 1990→2000 | Exposición regional | Muy transitado; ya hay un paper del BID con zonas de conmutación |
| RIF, reforma fiscal 2014 | 2010→2015 | Incentivo a formalizarse | Efecto chico, difícil de aislar |

**Contexto verificado de la política del salario mínimo:** los incrementos reales fueron de 2–3% entre 2016 y 2018 y de ~11% en 2019, con un aumento acumulado ponderado por fuerza laboral de ~37%. La fracción de trabajadores por debajo del mínimo en 2019-II iba de **6.9% en Nuevo León a 41.1% en Chiapas** — es decir, hay una dispersión enorme de la mordida, y a nivel de los 777 mercados será todavía más rica. La literatura existente (varios estudios con ENOE y diferencias-en-diferencias) encuentra **efectos de empleo pequeños o nulos**.

**⚠️ El hueco, y es real:** las evaluaciones existentes usan **ENOE** —trimestral pero con geografía parcial— o comparan estados. **Nadie lo ha hecho al nivel de los 777 mercados con datos censales.**

**★ Y la observación que puede decidir el asunto:** el salario mínimo es la **única** política del menú donde $\varepsilon_D$ no es un insumo sino el parámetro de interés:
$$\Delta \ln L_l \approx -\varepsilon_D \times \text{mordida}_l$$
Eso permite una **validación fuera de muestra**: estimar $\varepsilon_D$ con choques migratorios 1990–2010, predecir la respuesta del empleo al salario mínimo 2015→2020, y contrastar contra lo observado. Es la única del menú que conecta las dos ramas de forma no decorativa, y es la versión más convincente de "las dos juntas".

**Riesgos de la Rama B, sin adornos:** duplica la carga empírica; obliga a defender **dos** identificaciones; la ventana post es de un año; y si la validación fuera de muestra falla, hay que reportarlo — con el riesgo de que el lector concluya que $\varepsilon_D$ está mal, cuando podría ser que el salario mínimo no fuera binding.

---

### Cómo se ven las dos, lado a lado

| | Rama A | Rama B |
|---|---|---|
| Semanas adicionales | ~1 | ~4–6 |
| Identificación propia | No | **Sí** |
| ¿Cabe en el alcance congelado? | Sí | No |
| Riesgo de que falle | Bajo | Medio-alto |
| Qué agrega si sale | Relevancia + prueba de sobreidentificación | Validación externa del parámetro central |
| Peor escenario | El rango de $\varepsilon_S$ es tan ancho que el ejercicio no discrimina | La ventana es tan corta que no se ve nada, y no se sabe si es el diseño o la política |

**Recomendación de secuencia, no de elección:** la Rama A es un piso barato que conviene tener escrito de cualquier forma. La decisión real es si se agrega la Rama B, y **esa decisión no debería tomarse hasta después del punto de control S4** (la F de primera etapa). Si el instrumento no tiene fuerza, la Rama B es irrelevante porque no hay $\varepsilon_D$ que validar.

---

## §6. Estructura de la tesis

| § | Argumenta | Se sostiene en | Extensión |
|---|---|---|---|
| **1. Introducción** | El objeto, el hueco, la contribución; la respuesta a MRRH; el antecedente Mishra/Hanson | — | 4–5 pp |
| **2. Contexto y datos** | Qué son los 777 mercados; qué mide la base; sus límites | F1–F4, T1 | 6–8 pp |
| **3. Marco conceptual** | Por qué hace falta un desplazador de oferta; qué elasticidad es y qué no | — | 4–5 pp |
| **4. Estrategia empírica** | Construcción, ecuación, supuestos; **la objeción de Hanson y la respuesta** | F5, T2 | 8–10 pp |
| **5. Validez del instrumento** | Rotemberg, número efectivo de shocks, balance, pre-tendencia | F9–F11, T3–T4 | 6–8 pp |
| **6. Resultados** | Primera etapa, forma reducida, 2SLS; tres columnas sectoriales | F6–F8, F12, T5–T6 | 8–10 pp |
| **7. Interpretación y política** | Qué significa el número; incidencia con ambas elasticidades; sobreidentificación | T7–T8 | 5–6 pp |
| **8. Conclusión** | Qué se aprendió; qué queda (informalidad, $\sigma$, espacial) | — | 2 pp |

Total ≈ 45–55 páginas. Las etiquetas F#/T# remiten al `CUADERNO_EXPLORACION_2026-09-01.md`.

---

## §7. Riesgos vivos

| # | Riesgo | Estado | Qué lo mata |
|---|---|---|---|
| **R1** | **Instrumento débil.** 32 orígenes, número efectivo de shocks chico | Abierto — **es el go/no-go** | S4: F de primera etapa. Si F<10, celdas origen×demografía |
| **R2** | **La objeción de Hanson** (§4.3): los shares de enclave correlacionan con capital humano | Abierto | El balance de GPSS. Es testeable |
| **R3** | El corte transable no separa el canal consumidor porque la bandera de la casa está mal armada | Identificado, con solución | Bandera propia desde `LLAVE_ACTECONOMICA` |
| **R4** | Error de medición en 279 mercados unimunicipales y en la ola 2015 | Identificado | Ponderar por empleo; robustez sin el cuartil chico |
| **R5** | `RES5A` no poblado en 1990 ⇒ no hay shift para la primera diferencia | **Abierto — verificación S0** | Tabular la categoría "sin valor" por ola |
| **R6** | Scooping: la nota anuncia que los módulos de migración entran *"in the next stage"* | Abierto | Correo a EconLab. **Decisión previa: preguntar puede prevenir o invitar el scooping** |
| **R7** | Sin deflactor espacial, el salario real está mal medido entre mercados | Identificado | Caveat + robustez con INPC por ciudad (46 ciudades) |
| V1 | MRRH estiman otra cosa | **Cerrado** | §1, va en la página 1 |
| V3 | Remesas contaminan el destino | **Cerrado** | Ahora son medibles (§3.3c) |
| V5, V10, V12, V13 | Informalidad, brecha local-agregado, ruteo de parámetros a Correia | **Cerrados por alcance** | Ensayo 2 congelado |

---

## §8. Siguientes pasos

1. **S0 — la única verificación que sigue bloqueando:** tabular si `ENTIDAD_RES5A`, `MUNICIPIO_RES5A` y `MUNICIPIO_TRABAJO` están **pobladas** por ola (las columnas existen; falta el contenido).
2. **Descargar la carpeta `Códigos` de SIDIE** — el código Stata de construcción de los agregados. Resuelve solo varias preguntas de replicación y es el primer insumo de S1.
3. **Descargar las seis lecturas del Nivel 1.** Pendiente de tres sesiones, y ahora bloquea la redacción de §4: DSS 2017 → Card 2001 → BHJ 2025 JEP → GPSS 2020 → JRS 2018 → MRRH 2018.
4. **Verificar la referencia publicada de Hanson (2005)** antes de citarla — el PDF localizado es un working paper de abril de 2005 para una conferencia del NBER.
5. **Correo a econlab@banxico.org.mx:** pedir el mimeo de oferta y decidir antes si preguntar por el lado de demanda previene o invita el scooping (R6).
6. **Someter este documento al agente `critic`**, con foco en R1, R2 y en si la Rama B es alcance de maestría.
7. **Calcular el número efectivo de shocks** — es el primer número que hay que ver, antes que la primera etapa.
