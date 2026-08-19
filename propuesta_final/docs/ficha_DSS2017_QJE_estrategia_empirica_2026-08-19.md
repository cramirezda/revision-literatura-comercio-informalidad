# Ficha de lectura — Dustmann, Schönberg & Stuhler (2017), QJE 132(1), 435–483

*Labor Supply Shocks, Native Wages, and the Adjustment of Local Employment*

**Fecha:** 2026-08-19 · Para: Carlos Ramírez (ITAM)
**Es el pick #1** de `LECTURAS_ensayo1_2026-08-09.md` (Nivel 1) y de `GUIA_LECTURA_top_v3_2026-08-07.md` (Bloque 1).
**Foco de esta ficha:** Sección IV (estrategia empírica) en adelante, y **cómo se conecta con el modelo de la Sección II**.
**Documentos relacionados:** `proceso_estimacion_epsilonD_2026-08-07.md` (§0, §6) · `PLAN_ensayo1_maestria_2026-08-09.md` (§6.3, diseño de commuters).

---

## 0. La pregunta que motiva esta ficha

> *"No comprendo en qué momento se une el modelo con lo empírico; siento que son dos cosas completamente distintas."*

Es una lectura legítima y hay que resolverla de entrada, porque el paper **no estima el modelo**. No hay calibración, no hay GMM, no se recuperan σ ni β por máxima verosimilitud. Lo que hacen es construir el modelo de modo que **sus estáticas comparativas tengan exactamente la forma de un coeficiente de regresión**. Literalmente.

Las secciones 1 a 3 de esta ficha desarrollan esa costura; las 4 a 7, la estrategia y los resultados.

---

## 1. La costura: el modelo no se estima, se usa como lente

### 1.1 Correspondencia término a término

Está en el párrafo bisagra de la p. 452 (§IV.A). Es la tabla que resuelve la duda:

| Modelo (Sección II) | Empírico (Sección IV) |
|---|---|
| $dI = \dfrac{dL^I}{L^N}$ — shock de oferta relativo al empleo base | $\Delta C_j^{92-90} = \dfrac{L^{Czech}_{j92}-L^{Czech}_{j90}}{L^N_{j90}+L^{for}_{j90}}$ — **el regresor** |
| $d\log w_g$ | $\Delta \ln w_{gs,j}$ — variable dependiente (ec. 7) |
| $d\log L^N_g$ | $\Delta L^N_{gs,j}$ — variable dependiente (ec. 8) |
| $\dfrac{d\log w_g}{dI}$ (ecs. 4 y 5) | $\beta_{gs}$ — **el coeficiente estimado** |
| $\dfrac{d\log L^N_g}{dI}$ (ecs. 2 y 5) | $\delta_{gs}$ — **el coeficiente estimado** |

Es decir: **β y δ *son* las derivadas del modelo.** Las ecuaciones (7) y (8) son la versión muestral de las derivadas teóricas: el regresor es $dI$, el regresando es $d\log w$ o $d\log L^N$, y el coeficiente es el cociente. No hay más traducción que hacer.

Las ecuaciones empíricas, completas:

$$\Delta \ln w_{gs,j} = \alpha_{gs} + \beta_{gs}\,\Delta C_j^{92-90} + u_{gs,j} \qquad (7)$$
$$\Delta L^N_{gs,j} = \gamma_{gs} + \delta_{gs}\,\Delta C_j^{92-90} + v_{gs,j} \qquad (8)$$

Escritas en **primeras diferencias** para eliminar efectos fijos de área, habilidad y edad constantes en el tiempo, permitiendo tasas de crecimiento específicas por grupo ($\alpha_{gs}$, $\gamma_{gs}$).

### 1.2 El detalle fino: qué ecuación teórica corresponde a cada coeficiente

Esto es lo que casi todo lector se salta y es donde el modelo gana su valor:

- **Salarios flexibles:** el sistema está en equilibrio y *tanto* $\beta_{gs}$ *como* $\delta_{gs}$ corresponden a las **ecuaciones (4) y (5)** — la intersección de oferta y demanda. Ambos son objetos de equilibrio, determinados conjuntamente.
- **Salarios parcialmente rígidos a la baja:** la caída salarial ya no la determina el equilibrio sino la restricción institucional $\underline{d\log w_g}$. Entonces $\beta_{gs}$ está determinado **exógenamente** por el grado de rigidez, y $\delta_{gs}$ se lee directamente sobre la **curva de demanda, ecuación (2)**: la economía está restringida por el lado de la demanda y hay nativos que querrían trabajar a ese salario sin encontrar empleo.

> ⚠️ **Consecuencia:** el par $(\hat\beta,\hat\delta)$ **no se puede interpretar sin decidir en qué régimen estás**. El paper es honesto en que no puede distinguir empíricamente entre "oferta muy elástica" y "salario rígido" — generan el mismo patrón observable (pp. 463 y 470).

### 1.3 Por qué el regresor es el shock *total* y no el específico del grupo

Segunda pieza de la costura, y también genera confusión.

En la ecuación (2) del modelo el shock entra como $dI$ (total), y la heterogeneidad por grupo entra por el **término de intensidad relativa** $\pi^I_g/\pi^N_g$ — densidad de inmigrantes respecto de nativos *dentro* del grupo $g$. El modelo está escrito así a propósito.

Consecuencia empírica (p. 453): en (7)-(8) el regresor es **siempre el mismo** $\Delta C_j^{92-90}$, y lo que cambia entre regresiones es la **variable dependiente**. Nunca asignan checos a celdas de habilidad. Dos razones, ambas del propio diseño:

1. **Solo el influjo total es cuasi-aleatorio.** La composición por habilidad de los checos en cada municipio *no* es exógena — depende de la estructura productiva local. Usar el influjo específico por grupo reintroduce endogeneidad.
2. **Evita el error de clasificación por *downgrading*.** Los inmigrantes suelen trabajar por debajo de su nivel educativo formal (Dustmann–Preston 2012). Si asignas checos a "no calificados" por educación observada, mides mal contra quién compiten. Aquí el grado de competencia con cada grupo nativo **es parte del parámetro estimado**, no un supuesto previo (n. 9, p. 439).

> **Corolario para citar:** por eso $\beta_{gs}$ y $\delta_{gs}$ son **efectos totales** (incluyen complementariedades entre grupos y entre capital y trabajo) y **no son comparables** con los efectos parciales directos del enfoque de celdas nacionales de Borjas (2003) ni con Card (2001). Responden a *"¿cuál es el efecto global del influjo sobre este grupo?"*, no a *"¿cuál es el efecto del influjo de ese mismo tipo de trabajador?"*.

### 1.4 La normalización que hace legible a δ

Escalan el shock por el empleo **total** (nativo + extranjero) de 1990 justamente para que **δ = −1 signifique desplazamiento pleno**: cada checo empleado desplaza exactamente a un residente (n. 21). Por eso el −0.926 estimado se lee de inmediato como *desplazamiento casi total*.

---

## 2. El modelo en 15 líneas (solo lo que hace falta para leer lo empírico)

- **Producción:** Cobb-Douglas $Q = AK^\alpha L^{1-\alpha}$, con $L$ un agregado CES de calificados y no calificados, elasticidad de sustitución $\sigma = 1/(1-\beta)$.
- **Nativos e inmigrantes son sustitutos perfectos** dentro de cada grupo de habilidad.
- **Capital con oferta local imperfectamente elástica:** $K = h(r, r')$, con $\lambda$ el inverso de la elasticidad. De ahí sale $\phi = -\frac{\alpha\lambda}{1-\alpha+\lambda}$, **la pendiente de la curva de demanda agregada de trabajo**.
- **Oferta laboral local de nativos con elasticidad $\eta_g$ que puede variar por grupo.** Ojo: **no** es la elasticidad de la literatura de oferta laboral (MaCurdy, Chetty). Es una elasticidad *local* que resume varios márgenes: migración interna entre áreas, entradas y salidas de la fuerza laboral, transiciones a no empleo. Por eso puede ser grande.
- **Inmigrantes ofrecen trabajo inelásticamente** (como en Borjas 2013).
- **Rigidez salarial parcial y heterogénea por grupo** (§II.B).

**Las dos innovaciones respecto de la literatura previa son exactamente esas dos últimas:** $\eta_g$ heterogénea y rigidez heterogénea. Todo el pago del modelo está ahí (§5.3 de esta ficha).

**Predicción central bajo homogeneidad (ec. 5):** el grupo con mayor intensidad relativa de inmigración ($\pi^I_g/\pi^N_g > \Pi$, donde $\Pi$ es el promedio ponderado) debe ver caer **tanto** su salario **como** su empleo respecto del otro grupo.

**Predicción bajo heterogeneidad (ec. 6):** si $\eta_g$ difiere, los efectos relativos de salario y empleo pueden tener **signos cruzados** respecto a la exposición. El paper los llama **"efectos perversos"**.

---

## 3. El experimento

**Política:** la *Grenzgängerregelung*, anunciada en septiembre de 1990 e implementada el 1 de enero de 1991, parte de un esquema mayor para reclutar extranjeros tras la reunificación (cubría no discriminadamente todos los distritos con frontera checa o polaca → exogeneidad respecto de condiciones locales).

**El rasgo que hace el diseño:** los checos podían **trabajar** en los distritos fronterizos pero **no residir**. Estaban obligados a conmutar diariamente. Aplicado vía la *Grenzgängerkarte* y el requisito de doble registro (inquilino y arrendador), que hacía imposible rentar legalmente.

**De ahí sale la variación:** como conmutar es costoso, **la distancia a la frontera determina la exposición**. Municipios pegados a la frontera recibieron ~10% de su empleo en checos; a más de 50 km, casi nada.

> **Esto es lo que distingue al paper de un Mariel:** no hay una sola unidad tratada, hay **variación continua de intensidad de tratamiento a nivel municipal**, generada por geografía — plausiblemente ortogonal a las tendencias laborales locales.

**Muestra y exclusiones.** La región elegible son 21 distritos en una banda de ~80 km. Excluyen los que están a menos de ~80 km de la antigua frontera interalemana, para evitar contaminación con conmutantes de Alemania Oriental tras la reunificación. Quedan **13 distritos / 291 municipios**.

**Ventana temporal:** hasta 1993. El share checo sube de ~0 a ~3% regional (10% en los municipios más cercanos) para junio de 1992, se estabiliza 1992–93 y **cae desde 1994** por una interpretación más estricta del esquema. Ese "experimento inverso" es potencialmente **endógeno** a las condiciones laborales locales (fue reacción política a las quejas), así que lo descartan. Decisión correcta y explícita.

**Composición de los checos (Tabla II)** — la retienes porque es el insumo de todas las predicciones:

| | No checos (1989) | Checos (1992) |
|---|---|---|
| No calificados | 0.276 | **0.505** |
| Menores de 30 | 0.435 | 0.344 |
| 30–49 | 0.408 | **0.619** |
| 50 y más | 0.157 | **0.037** |

Sobrerrepresentados en construcción y hotelería; predominantemente hombres.

---

## 4. Estrategia empírica (§IV.B) — el detalle operativo

### 4.1 Las tres estrategias posibles, y cuál eligen

El paper es explícito en que hay tres formas de estimar (7)-(8), y **reporta las tres**:

| Estrategia | Variación usada | Dónde |
|---|---|---|
| (a) Región fronteriza completa vs. controles emparejados | Solo entre región y control | Control sintético (§V.C.3) |
| (b) Solo dentro de la región fronteriza, IV con distancia | Solo intra-frontera | Tabla V, col. (3) |
| **(c) Baseline: pool de ambas** | Intra-frontera **+** frontera vs. interior | Tablas IV y V col. (1) |

Baseline: **291 municipios fronterizos + 1,259 de control = 1,550**.

### 4.2 La implementación IV en dos etapas

Está en la **nota al pie 26** — es donde vive el detalle operativo, fácil de perderse.

**Primera etapa** (nivel municipal, ponderada por empleo total de 1990):

$$\Delta C_j^{92-90} = \pi_0 + \pi_1 Z_j + \pi_2 Z_j^2 + \varepsilon_j$$

con $Z_j$ = distancia aérea del centroide del municipio al cruce fronterizo más cercano.

**Tabla III:**

| | Solo frontera | Con controles |
|---|---|---|
| Distancia (×100) | −0.338 (0.095) | −0.338 (0.092) |
| Distancia² (×100) | 0.268 (0.113) | 0.268 (0.110) |
| Constante (frontera) | 0.115 (0.017) | 0.114 (0.016) |
| Constante (interior) | — | 0.0011 (0.0003) |
| N municipios | 291 | 1,550 |
| **R²** | **0.387** | **0.544** |
| **F** | **42.58** | **52.70** |

El término cuadrático positivo captura que el efecto de la distancia se atenúa: cae fuerte en los primeros km y se aplana.

**Segunda etapa:** ponderada por empleo **específico del grupo** en el año base $t-1$ (la primera etapa se pondera por empleo total de 1990).

### 4.3 Por qué regresiones anuales sumadas y no una diferencia larga

No es un detalle técnico. Son dos motivos sustantivos (p. 458):

1. **Dinámica.** Correr año a año ($t$ vs. $t-1$) sobre el **mismo regresor fijo** $\Delta C^{92-90}_j$ y sumar los coeficientes de 1991 a 1993 permite ver *cuándo* se ajusta cada margen. Hallazgo: **el salario responde de inmediato; el empleo sigue cayendo hasta 1993** aunque el share checo ya había tocado techo en 1992.

2. **Sesgo de selección composicional en salarios.** Si el shock expulsa desproporcionadamente a trabajadores de bajo salario, el salario promedio observado *sube* por composición y enmascara el efecto real. Solución: en el análisis salarial **restringen la muestra a individuos empleados en el mismo municipio en $t$ y en $t-1$** — posible solo porque los registros de seguridad social son longitudinales y cubren toda la fuerza laboral. Así la composición queda fija entre periodos.

> 🔑 **La prueba de que esto importa está en la Tabla V, col. (5)** (§6.4). Es una contribución metodológica que trasciende el tema del paper. **Anótala para tu §6.**

### 4.4 Los tres supuestos de identificación, y su defensa

**Supuesto 1 — Tendencias paralelas respecto a la distancia.** En ausencia del influjo, la evolución de salarios y empleo por subgrupo debe ser no correlacionada con la distancia a la frontera.

Defensa en cuatro capas:
- Tabla O.I: la distancia no predice tendencias pre-política, con una sola excepción.
- **Placebo formal:** estiman (7) y (8) para $t \le 1990$ y contrastan $H_0:\beta_{gs}=0$, $H_0:\delta_{gs}=0$. **Lo que lo hace válido:** *no* emparejaron los controles sobre tendencias previas, así que es una falsificación genuina y no una tautología. (Angrist–Krueger 1999 hacen algo análogo con Mariel.)
- **Event study** (Figura IV): coeficientes acumulados 1986–1995, planos y no significativos antes de 1990.
- Reportan con y sin **tendencias lineales específicas por municipio**, identificadas con 1987–1989.

**Supuesto 2 — No contaminación de los controles (SUTVA).** Si los nativos desplazados se mudan a las áreas de control, contaminas el contrafactual (bajas salarios y subes empleo allí) y **sobreestimas** el efecto.

Defensa: el shock es despreciable a escala nacional, así que los distritos interiores emparejados están limpios. Como chequeo, el **control sintético** compara la región fronteriza interior *completa* contra un promedio ponderado de controles, descartando toda la variación intra-frontera — internaliza cualquier reacomodo entre municipios fronterizos.

**Supuesto 3 — Restricción de exclusión.** La apertura de la frontera no puede afectar a las zonas cercanas por *otro* canal que el influjo de trabajadores.

Canales descartados: **comercio** (en 1993 aún había restricciones; ~1% del total alemán), **IED** (~1.9 mil millones USD en 1990–96, concentrada en Praga), **acceso a mercados** (Redding–Sturm 2008: las ganancias de comercio tardan; aquí el foco es corto plazo).

> Pero el argumento fuerte es **econométrico, no narrativo**: todos esos shocks afectarían a la región fronteriza **como bloque**. Cuando tiran los controles interiores y usan **solo variación intra-frontera** (Tabla V, col. 3), los resultados apenas cambian. Eso descarta cualquier confusor a nivel regional. **Este es el truco de identificación que puedes copiar.**

### 4.5 Selección de controles

Emparejan sobre 1989 (año previo a la reunificación y a la caída del Telón), con diferencias ponderadas por varianza en: shares de empleo por educación, share de extranjeros, log salario medio, share de observaciones censuradas por el tope de seguridad social, nivel de empleo, y shares de cuatro grupos de edad. Solo distritos de Alemania Occidental de densidad urbana similar.

**Deliberadamente NO emparejan sobre tendencias previas** — para preservar la validez del test placebo. Resultado: **24 distritos = 1,259 municipios**.

(En el control sintético sí emparejan sobre resultados de 1986–1989, à la Abadie–Diamond–Hainmueller. Los dos ejercicios son complementarios por diseño.)

### 4.6 Inferencia

- Como el estimador procede en varias etapas, los errores analíticos son complicados → **wild bootstrap, 500 repeticiones** (Cameron–Gelbach–Miller 2008), agrupando a nivel **distrito** aunque la estimación sea municipal.
- Adicionalmente, **errores SHAC de Conley (1999)** con kernel uniforme y ancho de banda de 100 km, que permiten correlación entre áreas geográficamente cercanas *aunque pertenezcan a distritos administrativos distintos* (à la Kline–Moretti 2014). **Salen prácticamente iguales** a los bootstrapeados.
- Implementan SHAC en la especificación de diferencia larga, ignorando la incertidumbre de la primera etapa; muestran en la Tabla O.III que eso cambia poco.

---

## 5. Resultados — dónde el modelo empieza a pagar

### 5.1 Efectos agregados (Tabla IV, Panel A)

Por cada punto porcentual de aumento en el share de empleo checo, hacia 1993:

| | 2SLS | OLS |
|---|---|---|
| Salarios | **−0.134** (0.047) | −0.058 (0.038) |
| Empleo nativo | **−0.926** (0.251) | −0.263 (0.184) |

**(a) OLS < IV en magnitud.** Consistente con que los checos entraron preferentemente a municipios con mayor crecimiento de empleo y salarios — el sesgo hacia cero clásico del enfoque de áreas. El IV lo corrige, y esto valida el instrumento indirectamente.

**(b) Magnitud salarial en contexto.** −0.13% **no** implica caída de salarios reales: el crecimiento real de los que permanecían empleados era ~3% anual. Es desaceleración, no caída.

**(c) 🔑 Primer momento en que modelo y empírica se unen cuantitativamente.** Si el empleo nativo cae 0.926% y entra 1% de checos, el **empleo total sube 0.074%** mientras el salario cae 0.134%. El cociente

$$|\phi| = \frac{0.074}{0.134} \approx 0.54$$

es exactamente la **pendiente de la curva de demanda agregada de trabajo** del modelo, $\phi = -\frac{\alpha\lambda}{1-\alpha+\lambda}$. Es recuperar un parámetro estructural de dos coeficientes reducidos. Cae en el rango de la literatura (0.15–0.75; Hamermesh 1993, Lichter–Peichl–Siegloch 2015) → validación externa.

> Y tiene contenido económico inmediato: en el modelo, **si el capital fuera perfectamente elástico, $\phi = 0$ y no habría efecto salarial alguno.** Que $\hat\beta<0$ significativamente es evidencia directa de que **la oferta local de capital no es perfectamente elástica en el corto plazo**. Razón sugerida: el permiso era de dos años renovable, así que las firmas pudieron ver el shock como temporal y ser reacias a expandir capital.

> ⚠️ **Nota de calibración para tu propio proyecto:** este 0.54 es la pendiente de la demanda **agregada local** con capital imperfectamente elástico, y por eso sí coincide con el ancla LPS — a diferencia de tu $|\varepsilon_D|$ de largo plazo. Ver la advertencia de magnitud de `proceso_estimacion_epsilonD_2026-08-07.md` §0. **No confundas los dos objetos al comparar.**

### 5.2 Por habilidad (Tabla IV, Paneles B y C) — el modelo estándar funciona

Checos mucho más no calificados: 50.5% vs. 27.6%. En el modelo, $\pi^I_U/\pi^N_U > \Pi$. Predicción de la ec. (5) bajo elasticidades homogéneas: salarios **y** empleo de los no calificados caen más.

| | Salarios | Empleo |
|---|---|---|
| No calificados | **−0.202** (0.048) | **−1.371** (0.395) |
| Calificados | −0.106 (0.051) | −0.501 (0.214) |

Se cumple en ambas dimensiones. **Aquí el modelo estándar no se rechaza.**

**Validación dosis-respuesta adicional:** estiman el baseline por separado para **9 ocupaciones a 1 dígito** y grafican los coeficientes contra la exposición de cada ocupación (share de checos en la ocupación / share promedio). Relación negativa clara en salarios y empleo (Figura V). Lo mismo por industria (Figura O.II). *Este ejercicio es barato y muy convincente — replicable.*

### 5.3 ★ Por edad (Tabla VI) — aquí el modelo se vuelve indispensable

**Este es *el* resultado del paper y la razón por la que la Sección II existe.** Si el modelo te pareció decorativo, es por no haber llegado aquí.

Los checos estaban concentrados en edad media: **61.9% en 30–49** vs. 40.8% de nativos; solo **3.7% con 50+** vs. 15.7%.

**Predicción del modelo estándar** ($\eta$ común, sin rigidez heterogénea): salario **y** empleo deben caer más para los de **30–49** dentro de cada grupo de habilidad.

**Lo que encuentran (cols. 1–2, sin ajuste de tendencia):**

| Grupo | Share checos | Efecto salario | Efecto empleo |
|---|---|---|---|
| **Todos** — <30 | 0.031 | **−0.316** | −0.832 |
| Todos — 30–49 | 0.040 | −0.100 | −0.534 |
| Todos — 50+ | 0.007 | −0.068 | **−1.945** |
| **No calif.** — <30 | 0.112 | **−0.558** | −2.262 |
| No calif. — 30–49 | 0.107 | −0.179 | −0.704 |
| No calif. — 50+ | 0.011 | −0.097 | −1.364 |
| **Calificados** — <30 | 0.017 | **−0.276** | −0.283 |
| Calificados — 30–49 | 0.025 | −0.090 | −0.191 |
| Calificados — 50+ | **0.005** | −0.066 | **−1.636** |

Lee la última fila: **calificados 50+ es el grupo menos expuesto de todos** (0.005, la sexta parte del de 30–49) **y sufre con mucho la mayor caída de empleo** (−1.636). Y los menores de 30, que tampoco son los más expuestos, sufren la mayor caída salarial.

Esto son los **"efectos perversos"**: los efectos relativos de salario y de empleo tienen **signos cruzados** respecto a la exposición.

> **Ningún modelo estándar puede generar esto** — por más grupos de habilidad o anidamientos CES que agregues (Card–Lemieux 2001, Borjas 2003) — mientras $\eta$ y la rigidez sean comunes entre grupos. Y el modelo de la Sección II **sí** lo genera, vía la ecuación (6): con $\eta_g$ heterogénea, el grupo más expuesto puede incluso ver **subir** su salario relativo mientras su empleo se desploma.

Dos mecanismos, no excluyentes:

1. **Oferta local más elástica para los mayores** ($\eta_{50+} > \eta_{<30}$): mejor acceso a prestaciones por desempleo y prejubilación → se retiran ante un deterioro marginal. Los jóvenes aceptan recortes para evitar el *scarring* de un mal arranque de carrera.
2. **Mayor rigidez a la baja para los mayores:** los jóvenes están en trayectoria de crecimiento salarial empinada, así que "bajarles el salario" es solo crecer menos — invisible y fácil. Los mayores tienen salarios planos: el ajuste exige un recorte real, visible y difícil.

> Fíjate en el entrelazado: el mecanismo 2 depende críticamente de que el análisis salarial esté restringido a empleados en dos periodos consecutivos (§4.3). **El diseño de medición y la interpretación teórica están cosidos.**

**⚠️ Advertencia honesta del propio paper:** los dos mecanismos son **observacionalmente equivalentes** con estos datos. La conclusión es sobre la **clase de modelo** que se necesita, no sobre cuál de los dos opera.

Las cols. (3)–(4), con ajuste de tendencia, atenúan el patrón (empleo: −0.604 / −0.964 / −1.428) pero **el orden por edad se mantiene**, y el gradiente salarial también (−0.305 / −0.147 / −0.172).

### 5.4 Márgenes de ajuste (Tablas VII y VIII)

Descomponen el efecto de empleo en **dos dimensiones ortogonales**. Muy replicable con datos longitudinales.

**Dimensión 1 — Entradas vs. salidas:**

$$\frac{L^N_{gt,j}-L^N_{gt-1,j}}{L^N_{gt-1,j}} = \frac{Inflow^N_{g,j}}{L^N_{gt-1,j}} - \frac{Outflow^N_{g,j}}{L^N_{gt-1,j}}$$

| | Total | Entradas | Salidas |
|---|---|---|---|
| Todos | −0.989 | **−0.878** | +0.111 |

Las entradas explican **al menos 87%** del efecto total en todos los grupos. La respuesta de entradas es **inmediata**; la de salidas es **retrasada** (empieza en 1991).

> 🔑 **Giro conceptual real.** La caída de empleo **no** significa que los nativos pierdan sus trabajos cuando llegan los checos. Significa que trabajadores **no empleados en el área afectada** (posiblemente empleados en otras) **dejan de ser contratados**. Los *outsiders* absorben el golpe y **escudan a los *insiders***.

Dos explicaciones — y son otra vez las dos ramas del modelo: los *outsiders* son muy elásticos (tienen alternativas), o los *insiders* están protegidos por rigidez y costos de despido mientras las firmas sí pueden ajustar contratación de inmediato. El margen de salidas es mayor justo donde el modelo lo predice: **para los 50+ (28% del efecto en ese grupo)**.

**Dimensión 2 — No empleo vs. movimiento geográfico:**

| | Total | No empleo | Entre áreas (directo) | Entre áreas (incl. vía no empleo) | Población |
|---|---|---|---|---|---|
| Todos | −0.989 | −0.821 | −0.168 (**17%**) | −0.287 (**29%**) | −0.299 |

La medida "directa" (empleado en A en $t-1$, en B en $t$) subestima la movilidad, porque hay quien se muda tras un periodo de no empleo. Reclasificando (si dentro de **tres años** aparece empleado en otro municipio, cuenta como movimiento geográfico) el 17% sube a **29%**. Con ventana de cinco años, similar.

**Matiz de la Tabla VIII que vale oro:** descomponiendo los movimientos geográficos en entradas y salidas, casi todos son **reducción de entradas** (−0.233 directo), no aumento de salidas (−0.066, no significativo).

> **El arbitraje espacial no ocurre porque la gente se vaya de las áreas afectadas, sino porque deja de llegar a ellas.** Contra la lectura habitual de la literatura (Peri–Sparber 2011), y consistente con Monras (2015b) sobre la Gran Recesión en EE.UU.

Diferencias por grupo:

| Grupo | Lectura |
|---|---|
| **No calificados** | El efecto es *enteramente* no empleo (movimiento entre áreas: +0.033, cero) |
| **Calificados** | 25–37% es movimiento geográfico (mayor movilidad; Amior 2015) |
| **<30** | 27% es movimiento geográfico; menor efecto absoluto de empleo |
| **50+** | Casi todo (−1.203 de −1.349) es no empleo; movimiento geográfico ≈ 0 (−0.050) |

> La última fila es **evidencia directa del mecanismo de $\eta$ alta** que postularon para la Tabla VI: acceso a prestaciones y prejubilación. El modelo predijo y la descomposición confirmó.

**★ Resultado con implicaciones para toda la literatura (col. 7).** El influjo checo reduce la población local **0.299%** por punto porcentual. Como los checos *no residen* en Alemania, esto es emigración neta de nativos. Consecuencia: medido como cambio en la razón empleo/población (lo estándar en la literatura), el coeficiente sería **−0.611 en vez de −0.926 — un 30% más pequeño**.

> **La métrica convencional empleo/población subestima sistemáticamente el desplazamiento**, porque el denominador también se ajusta. Ver también n. 22 sobre por qué su normalización difiere de la de Card (2001) o Altonji–Card (1991).

---

## 6. Robustez (§V.C, Tabla V)

| | (1) Baseline | (2) Con tendencias | (3) Solo frontera | (4) Frontera interior vs. interior | (5) Dif. larga + SHAC |
|---|---|---|---|---|---|
| **Salarios — Todos** | −0.134 (0.047) | −0.209 (0.056) | −0.134 (0.096) | −0.142 (0.050) | **0.002** (0.053) |
| No calificados | −0.202 | −0.282 | −0.303 | −0.205 | −0.057 |
| Calificados | −0.106 | −0.190 | −0.093 | −0.114 | −0.052 |
| **Empleo — Todos** | −0.926 (0.251) | −0.927 (0.311) | −0.952 (0.456) | −0.897 (0.275) | −0.930 (0.243) |
| No calificados | −1.371 | −1.417 | −1.036 | −1.368 | −1.203 |
| Calificados | −0.501 | −0.866 | −0.586 | −0.507 | −0.522 |
| N municipios | 1,550 | 1,550 | 291 | 1,405 | 1,550 |

**Cada columna ataca un supuesto distinto** — así es como se lee una tabla de robustez bien construida:

- **(2) Tendencias por municipio**, identificadas con 1987–1989. → Ataca el Supuesto 1. Empleo: idéntico. Salarios: **más grandes** en magnitud. Corregir por tendencias *refuerza* el resultado; no es artefacto de tendencias diferenciales.
- **(3) Solo región fronteriza** (291 municipios, tira todos los controles). → Ataca el Supuesto 3: elimina cualquier confusor que afecte a la región como bloque (comercio, IED, acceso a mercados). Muy similar, con errores mayores por menor variación.
- **(4) "Frontera interior" vs. interior:** parten la región por la mediana del valor **ajustado de la primera etapa**; los 145 municipios con influjo predicho sobre la mediana (~5.8% del empleo) son el tratamiento. Casi idéntico al baseline.
- **(5) Diferencia larga con salarios promediados sobre todos los empleados en cualquiera de los dos años**, más errores SHAC. → **El empleo aguanta; los efectos salariales se evaporan.**

> 🔑 **La columna (5) no es un fallo de robustez, es un resultado metodológico.** Es lo que harías con cortes transversales repetidos, que es lo que usa la mayoría de la literatura. Implicación: *si la inmigración genera respuestas de empleo selectivas, los estudios basados en cortes transversales separados por años pueden **subestimar o no detectar** efectos salariales adversos que sí existen.* Los trabajadores de bajo salario son los que salen o no entran. **Anótalo para tu §6 y para el seminario.**

**Control sintético (§V.C.3, Figura VI)** — la alternativa más exigente:

- Compara la región fronteriza interior completa contra un promedio ponderado de controles, emparejando **sí sobre tendencias previas** (resultados 1986–1989), a diferencia del baseline. Descarta *toda* la variación intra-frontera → internaliza cualquier reacomodo entre municipios fronterizos.
- Brechas a 1993: **−0.007** salarios, **−0.079** empleo. Escaladas por el share checo de la región (5.8%): **−0.12** y **−1.36**. Compárense con −0.13 y −0.93 del baseline: mismo orden de magnitud.
- **Test de permutación** aplicando el método a los 85 distritos de control: la brecha de **empleo es excepcionalmente grande** (significativa); la de **salarios no**. Esperable — descartar la variación intra-frontera cuesta mucha precisión.
- **Lo que compra este ejercicio:** prueba que la caída de empleo es una caída **regional real**, no un reacomodo de trabajadores entre municipios de la zona fronteriza.

**Otros chequeos:**
- Formas funcionales alternativas de la primera etapa (Tabla O.II): polinomio cúbico, splines, distancia por carretera, tiempo de manejo. Primeras etapas y 2SLS muy similares.
- Excluir los 3 distritos de control vecinos a la frontera (n. 25).
- Estimaciones por género (Tabla O.V).
- Especificaciones con share checo **específico por habilidad** (Tabla O.VI) — que, advierten, **solo identifican efectos relativos**, no totales. Consistente con §1.3.
- Nota metodológica menor pero honesta (n. 34): un ejercicio militar de la OTAN (REFORGER 88) distorsionó los flujos de 1987–88, así que en las Tablas VII–VIII usan solo 1989–1990 para las tendencias, en vez de 1987–1989.

---

## 7. La costura, en cinco pasos (resumen ejecutivo)

1. **El modelo define los objetos estimables.** $\beta_{gs}$ y $\delta_{gs}$ de (7)-(8) *son* las derivadas $d\log w_g/dI$ y $d\log L^N_g/dI$ de las ecs. (2), (4) y (5). No hay traducción intermedia.
2. **El modelo justifica el diseño empírico.** Que la ec. (2) escriba el shock como $dI$ total, con la heterogeneidad entrando vía $\pi^I_g/\pi^N_g$, es lo que legitima regresar resultados por grupo sobre el influjo **total** — lo único cuasi-aleatorio y lo único inmune al error de clasificación por *downgrading*.
3. **El modelo convierte coeficientes reducidos en parámetros estructurales.** De $\hat\beta=-0.134$ y $\hat\delta=-0.926$ sale $\hat\phi \approx 0.54$, y de ahí: **el capital no es perfectamente elástico en el corto plazo**.
4. **El modelo diagnostica lo que sin él sería ruido.** Los efectos perversos por edad (Tabla VI) son incompatibles con cualquier modelo estándar y solo se explican con $\eta_g$ heterogénea o rigidez heterogénea — la aportación de la Sección II. **Este es el clímax del paper.**
5. **La descomposición de márgenes contrasta el mecanismo directamente.** El $\eta$ alto de los mayores no se postula: se ve en que su ajuste es casi todo hacia no empleo (Tabla VII, Panel C) y en que son el único grupo con margen de salidas apreciable (28%).

### Cierre conceptual del paper

El patrón agregado — salarios pegajosos en empleos en curso, caída fuerte de empleo, casi toda por menor contratación y no por más separaciones — **es el mismo que documenta la literatura de ciclos económicos para una recesión** (Hall 2005; Shimer 2005, 2012; Rogerson–Shimer 2011). Sugieren que sus resultados dicen algo general sobre cómo se ajustan los mercados laborales a shocks, no solo sobre inmigración.

### Limitaciones que ellos mismos declaran

- **Todo es corto plazo** (hasta 1993), y el corto plazo puede ser más adverso: los salarios pueden ser rígidos hoy y flexibles mañana; el capital puede responder después, sobre todo porque el shock fue inesperado y quizá percibido como temporal.
- **Márgenes de largo plazo no observados:** cambio tecnológico (Lewis 2011), inversión en educación de los entrantes (Hunt 2012; Smith 2012), *upgrading* ocupacional (Peri–Sparber 2009).
- **Contraargumento que ofrecen:** las respuestas de corto plazo **moldean los incentivos** para hacer esas inversiones, así que son insumo necesario para entender el ajuste largo.

### Validez externa — el caveat que hay que registrar

Los checos **conmutaban, no residían**: no consumían en la región. Eso **elimina el canal de demanda por consumo** que existe en casi todos los demás episodios estudiados, y es probablemente parte de por qué los efectos aquí son más adversos que en, digamos, Card (1990) sobre Mariel. El paper añade dos razones más: era un shock **inesperado y excepcionalmente grande** sobre una región **sin historia previa de inmigración** (a diferencia de Miami, con 35.5% de población nacida en el extranjero y una estructura industrial ya adaptada), y las firmas pudieron verlo como **temporal**.

---

## 8. Qué te llevas para el Ensayo 1

Cuatro cosas concretas, en orden de valor:

1. **El molde de la costura modelo↔empírica.** Tu §7 (Interpretación) tiene el mismo problema que este paper resuelve: cómo hablar de un parámetro estructural sin estimarlo estructuralmente. La respuesta de DSS es escribir las estáticas comparativas *en la forma de un coeficiente de regresión* y hacer explícita la tabla de correspondencia. **Copia esa tabla como plantilla.**

2. **El argumento de identificación de la col. (3) de la Tabla V.** "Si el confusor opera a nivel región, entonces la especificación que usa solo variación *dentro* de la región lo elimina; y como los resultados no cambian, el confusor no está operando." Es un argumento econométrico, no narrativo, y es mucho más fuerte que la enumeración de canales. **Aplicable directamente a tus amenazas de §6.**

3. **La advertencia sobre selección composicional en salarios (col. 5).** Tu diseño es de **diferencias largas decenales sobre censos** — exactamente el caso donde este sesgo muerde. No tienes el panel longitudinal que les permite a ellos fijar la composición, así que **esto es una limitación declarada, no un chequeo**. Mejor decirlo tú en §8 que oírlo en el seminario. Ver `proceso_estimacion_epsilonD_2026-08-07.md` §6.

4. **El diseño de commuters** — ya identificado en `checkin_datos_EconLab_2026-08-09.md` §3.2 y `PLAN_ensayo1_maestria_2026-08-09.md` §6.3. Lo que esta ficha añade: el mecanismo de enforcement (permiso especial + doble registro) es lo que hace *creíble* la separación trabajo/consumo. Tú no tienes enforcement, tienes `LLAVE_MUNICIPIO_TRABAJO`: **es una separación medida, no impuesta**. Diferencia material — argumentala como tal, no como equivalencia.

**Un quinto punto, de contraste:** el resultado de población (−0.299) implica que la métrica empleo/población subestima el desplazamiento en ~30%. Si en algún momento reportas efectos sobre razones cuyo denominador también responde al shock, **acuérdate de este número.**
