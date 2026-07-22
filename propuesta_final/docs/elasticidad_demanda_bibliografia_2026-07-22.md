# Bibliografía canónica anotada — Elasticidad de la demanda de trabajo en mercados laborales locales de México (EG estático)

**Generado:** 2026-07-22
**Para:** Tesis de Maestría en Economía, ITAM (Carlos Ramírez) — reunión con asesor 2026-07-21/22
**Tipo de lista:** Canónica/foundational, **no exhaustiva** (~36 fuentes)
**Rutas cubiertas:** (1) Estructural — EG estático formal/informal, σ tipo Raval; (2) Espacial/redes — spatial lag/Durbin con W = commuting/migración
**Ancla:** México + espejo internacional

---

## §0. Header y veredicto de cobertura

**Veredicto: la literatura de insumos (bloques A, C, D, E) está bien cubierta y es tratable; el objeto exacto de la tesis — elasticidad de *demanda* de trabajo recuperada de un EG estático calibrado a mercados locales mexicanos, con matriz de commuting como W — no tiene un antecedente que lo haga de forma integrada.** Eso es la buena noticia (hueco real) y la mala noticia (no hay un solo "paper molde" que clonar; hay que ensamblar piezas de 3-4 tradiciones distintas).

Por ruta:

- **Ruta 1 (estructural):** cobertura **alta** en modelos EG formal/informal (Ulyssea 2010/2018, Amaral-Quintin 2006, Galiani-Weinschelbaum 2012, Meghir-Narita-Robin 2015, Satchi-Temple 2009 calibrado a México) y en el método de identificación de σ (Raval 2019). Ninguno de estos papers **reporta o interpreta explícitamente una elasticidad de demanda de trabajo** como objeto de output — la mayoría reporta salarios de equilibrio, tamaño del sector informal o TFP. Ensamblar σ (Raval) + estructura formal/informal (Ulyssea/Amaral-Quintin) + participaciones factoriales para *computar* ε_D es trabajo original de la tesis, no algo que exista ya hecho.
- **Ruta 2 (espacial):** cobertura **alta** en fundamentos (Anselin 2003, LeSage-Pace 2009, Corrado-Fingleton 2012) y **media-alta** en aplicaciones a mercados laborales locales (Molho 1995, Helm 2020, Monte-Redding-Rossi-Hansberg 2018). El hueco específico: nadie usa la matriz de flujos casa-trabajo que define los 777 mercados de Aldeco et al. como W en un spatial lag/Durbin — es una oportunidad casi "lista para usar" porque el crosswalk y los flujos ya existen en la base.
- **Puente entre rutas:** Monte-Redding-Rossi-Hansberg (2018) y Moretti (2011) son los dos papers que formalmente conectan EG estático de mercados locales con apertura al commuting — son la bisagra teórica de la tesis y deben citarse en la introducción de ambas rutas.
- **Sutileza de identificación (recordatorio):** los Bartik de la base Aldeco et al. son *shifters de demanda* → identifican elasticidad de **oferta** (lo hace el mimeo companion Aldeco-Chiquiar-Pérez Pérez-Salcedo, no verificable públicamente — ver nota en Bloque A). Para la elasticidad de **demanda**, la tesis necesita la ruta estructural (recuperar ε_D de σ + participaciones) o un *supply shifter* en forma reducida (redes migratorias, Cadena-Kovak / Caballero-Cadena-Kovak).

**Total de fuentes:** 36 (9 Bloque A, 5 Bloque B, 7 Bloque C, 8 Bloque D, 7 Bloque E). Se añadieron a la semilla original 4 fuentes canónicas no listadas por el usuario pero necesarias: Bartik (1991, origen del shock que la base usa), Notowidigdo (2020, incidencia de shocks de demanda local), Moretti (2011, Handbook, marco de EG de mercados locales) y Combes-Gobillon (2015, Handbook, métodos empíricos de aglomeración) — las dos últimas fueron sugeridas explícitamente en el encargo. **Se evaluó y se excluyó** Kline-Moretti (2014, *Annual Review*, bienestar de políticas de desarrollo local) por ser tangencial al objeto de elasticidad de demanda; se menciona en §1 por transparencia. También se dejó fuera Blanchard-Katz (1992, *Regional Evolutions*) de la tabla principal — es el precedente de "ajuste regional" que antecede a Bartik/ADH, pero su rol es de contexto histórico, no de insumo directo; se referencia en la narrativa.

**Marcadas como ya en el repo del usuario** (`papers/`): Ulyssea (2010), Aldeco et al. (2024), Autor-Dorn-Hanson (2013), Ulyssea (2018).

**Correcciones de cita hechas respecto a la semilla original** (ver también §4):
1. Lichter, Peichl & Siegloch (2015) → *European Economic Review* 80, no *Journal of Economic Surveys*.
2. Satchi & Temple (2009) → *Review of Economic Dynamics* 12(1), no *AEJ: Macroeconomics* (sí confirmado: calibrado a México).
3. Galiani & Weinschelbaum (2012) → *Economic Inquiry* 50(3), venue confirmada.
4. Molho (1995) → título correcto es *"Spatial Autocorrelation in British Unemployment"* (no "wage data"), *Journal of Regional Science*.
5. Monte, Redding & Rossi-Hansberg (2018) → *American Economic Review* 108(12), no *Econometrica*.
6. Fowler & Jensen (2020) → *Environment and Planning A: Economy and Space* 52(7), no *BLS Monthly Labor Review*.
7. Aldeco, Calderón, Chiquiar, Hanson, Pérez Pérez, Velázquez (2024) → orden de autores verificado como Aldeco, Chiquiar, Calderón, Hanson, Pérez Pérez, Velázquez en algunas fuentes secundarias; se usa el orden del documento adjunto del usuario.

---

## §1. Mapa de literatura y gap honesto por ruta

### Ruta 1 — Estructural (EG estático formal/informal, σ tipo Raval)

La familia de modelos EG competitivos de dos sectores (Amaral-Quintin 2006; Galiani-Weinschelbaum 2012) da el andamiaje estático correcto: firmas y/o trabajadores heterogéneos que se auto-seleccionan en formal/informal, sin fricciones de búsqueda. Ulyssea (2010, 2018) aporta el bloque de producción CES formal-informal (σ=1/(1-ρ)) que es directamente transferible al núcleo de la tesis, aunque el resto de su aparato es dinámico/de búsqueda. Meghir-Narita-Robin (2015) es el benchmark de wage-posting con informalidad más citado, pero su elasticidad relevante es de **salarios**, no de **empleo/demanda**. Satchi-Temple (2009) es la referencia de calibración a México más cercana en espíritu (aunque con fricciones de matching y migración rural-urbana, no un EG puramente estático walrasiano).

**El gap real:** ninguno de estos siete papers computa o reporta una elasticidad de demanda de trabajo como objeto de interés per se — la definen implícitamente vía la curva de PMg pero no la extraen ni la discuten como parámetro de política. La tesis puede posicionarse como la primera en **hacer explícito el mapeo ε_D = f(σ, participaciones factoriales, elasticidad de demanda de producto)** en un EG formal/informal calibrado con variación de salarios locales (Raval 2019) para México — un ejercicio de traducción metodológica no trivial, no una aplicación mecánica.

**Debate no resuelto:** si σ_FI (sustitución formal-informal) debe estimarse o calibrarse. Casi toda la literatura (Ulyssea incluido) lo calibra por falta de una fuente de variación limpia que mueva formal vs. informal diferencialmente dentro del mismo mercado. Candidatos de identificación exógena para México: la prohibición de outsourcing de 2021 (fuera de esta lista por no ser foundational, pero relevante como shock de robustez) o cambios en cuotas patronales IMSS.

### Ruta 2 — Espacial/redes (spatial lag/Durbin, W = commuting)

Anselin (2003) y LeSage-Pace (2009) dan el aparato taxonómico y de estimación estándar (multiplicadores espaciales, efectos directos/indirectos). Corrado-Fingleton (2012) es la advertencia metodológica obligada: el W debe tener fundamento económico, no ser data-driven arbitrario — la matriz de flujos casa-trabajo que define los 777 mercados de Aldeco et al. **sí** lo tiene, porque es la misma matriz de conectividad usada para construir la geografía. Molho (1995) y Helm (2020) son los precedentes empíricos más cercanos de spillovers de demanda vía commuting/migración, aunque en contextos no mexicanos (Reino Unido y Alemania respectivamente). Monte-Redding-Rossi-Hansberg (2018) es la pieza puente: un EG cuantitativo donde la elasticidad de empleo local depende explícitamente de la apertura al commuting — el ejercicio más parecido a "casar Ruta 1 con Ruta 2" que existe en la literatura, aunque para EE.UU. y sin dimensión de informalidad.

**El gap real:** no hay, hasta donde se pudo verificar, un estudio que use la matriz de flujos commuting/migración de los 777 mercados mexicanos como W en un spatial lag/Durbin sobre shocks de demanda (Bartik) o empleo — es una casilla vacía casi "lista para llenar" dado que los datos ya existen en la base EconLab. El riesgo metodológico es la crítica de Corrado-Fingleton: hay que justificar teóricamente por qué el W de commuting (y no el de distancia inversa o el de migración) es el relevante para el fenómeno de demanda de trabajo (respuesta: el commuting es la definición misma del "mercado" en la ruta 1, así que ambas rutas comparten la misma red).

### Nota sobre exclusiones deliberadas
- **Kline & Moretti (2014)**, *Annual Review of Economics*, "People, Places and Public Policy" — bienestar de políticas de desarrollo local. Considerado y excluido: el foco es evaluación de política de lugar, no estimación de ε_D.
- **Blanchard & Katz (1992)**, *Brookings Papers on Economic Activity*, "Regional Evolutions" — antecedente de ajuste regional/empleo que precede a la tradición Bartik/ADH. Se menciona como contexto histórico, no se tabula, para no diluir el foco en demanda de trabajo con un paper sobre migración/desempleo regional agregado.

---

## §2. Tablas por bloque (A–E)

### Bloque A — Datos / definición de mercados locales / shift-share

| Cita completa | Aporte | Ruta | Rank |
|---|---|---|---|
| Aldeco, L., Calderón, M., Chiquiar, D., Hanson, G., Pérez Pérez, J., & Velázquez, C. (2024). *Local Labor Markets in Mexico: Definition, Databases, and Descriptive Analysis*. Banco de México, EconLab. | **Activo de datos central**: 777 mercados laborales locales, microdato censal 1990-2020, proxy de informalidad y Bartik pre-construidos. **✓ Ya en repo.** | Datos (ambas rutas) | 5 |
| Aldeco, L., Chiquiar, D., Pérez Pérez, J., & Salcedo, A. (mimeo). *Estimación de la elasticidad de la oferta de trabajo en México*. Banco de México. | Companion que estima ε_S con los Bartik de la base — define por qué la tesis debe apuntar a demanda, no oferta. **No verificable públicamente** (mimeo interno, no indexado en RePEc/SSRN al momento de la búsqueda). | Datos / identificación | 5 |
| Autor, D., Dorn, D., & Hanson, G. (2013). "The China Syndrome: Local Labor Market Effects of Import Competition in the United States." *American Economic Review*, 103(6), 2121-2168. | Aplicación canónica de shift-share a mercados laborales locales (commuting zones); metodología que Aldeco et al. replican para México. **✓ Ya en repo.** | Datos / Ruta 2 | 5 |
| Tolbert, C., & Sizer, M. (1996). "U.S. Commuting Zones and Labor Market Areas: A 1990 Update." USDA Economic Research Service, Staff Paper AGES-9614. | Metodología original de clustering jerárquico sobre flujos casa-trabajo — antecedente directo del algoritmo que usa Aldeco et al. para los 777 mercados. | Datos | 4 |
| Fowler, C., & Jensen, L. (2020). "Bridging the Gap Between Geographic Concept and the Data We Have: The Case of Labor Markets in the USA." *Environment and Planning A: Economy and Space*, 52(7), 1395-1414. | Actualización/crítica de la delimitación de commuting zones; útil para robustez de la definición de mercado. | Datos | 3 |
| Goldsmith-Pinkham, P., Sorkin, I., & Swift, H. (2020). "Bartik Instruments: What, When, Why, and How." *American Economic Review*, 110(8), 2586-2624. | Marco de referencia para interpretar el Bartik de la base como instrumento de shares/shocks; aclara que identifica elasticidad de oferta bajo el diseño estándar. | Datos / identificación | 5 |
| Borusyak, K., Hull, P., & Jaravel, X. (2022). "Quasi-Experimental Shift-Share Research Designs." *Review of Economic Studies*, 89(1), 181-213. | Marco alternativo de identificación shift-share (aleatoriedad en los shocks, no en los shares) — relevante para inferencia correcta con los Bartik de Aldeco et al. | Datos | 5 |
| Adão, R., Kolesár, M., & Morales, E. (2019). "Shift-Share Designs: Theory and Inference." *Quarterly Journal of Economics*, 134(4), 1949-2010. | Muestra que errores estándar convencionales sub-rechazan en diseños shift-share; correción de inferencia necesaria para cualquier regresión con los Bartik de la base. | Datos | 5 |
| Bartik, T. J. (1991). *Who Benefits from State and Local Economic Development Policies?* W.E. Upjohn Institute for Employment Research. | Origen del "shock Bartik" (shares locales × crecimiento nacional por industria) — la construcción exacta que la base de Aldeco et al. pre-calcula. Omitirlo dejaría sin citar la fuente primaria del método central de identificación de oferta. | Datos | 5 |

### Bloque B — Elasticidad de demanda de trabajo (empírica + analítica)

| Cita completa | Aporte | Ruta | Rank |
|---|---|---|---|
| Hamermesh, D. S. (1993). *Labor Demand*. Princeton University Press. | El tratado de referencia: leyes de Hicks-Marshall, teoría estática y dinámica de demanda de trabajo, marco para analizar salario mínimo/impuestos sobre nómina. | Estructural | 5 |
| Lichter, A., Peichl, A., & Siegloch, S. (2015). "The Own-Wage Elasticity of Labor Demand: A Meta-Regression Analysis." *European Economic Review*, 80, 94-119. | Meta-análisis de 942 estimaciones — benchmark de magnitudes esperables (|ε_D| ≈ 0.25-0.7) y de qué explica la heterogeneidad entre estudios (protección al empleo, sector, país). | Estructural | 5 |
| Raval, D. (2019). "The Micro Elasticity of Substitution and Non-Neutral Technology." *RAND Journal of Economics*, 50(1), 147-167. | **El método central de la tesis**: estima σ capital-trabajo (0.3-0.5) usando variación en salarios locales de planta — exactamente el tipo de variación que ofrecen los 777 mercados mexicanos. | Estructural | 5 |
| Clark, K. B., & Freeman, R. B. (1980). "How Elastic Is the Demand for Labor?" *Review of Economics and Statistics*, 62(4), 509-520. | Referencia histórica: muestra que restricciones inválidas en series de tiempo sesgan ε_D a la baja; contexto para no repetir ese error de especificación. | Estructural | 3 |
| Notowidigdo, M. J. (2020). "The Incidence of Local Labor Demand Shocks." *Journal of Labor Economics*, 38(3), 687-725. | Modelo de equilibrio espacial para la incidencia de shocks de demanda local sobre trabajadores de baja/alta calificación — complementa la interpretación de bienestar de ε_D heterogénea. | Estructural / Ruta 2 | 4 |

### Bloque C — EG estructural formal/informal

| Cita completa | Aporte | Ruta | Rank |
|---|---|---|---|
| Ulyssea, G. (2010). "Regulation of Entry, Labor Market Institutions and the Informal Sector." *Journal of Development Economics*, 91(1), 87-99. | Bloque de producción CES formal-informal (σ=1/(1-ρ)) directamente transferible al núcleo estático de la tesis. **✓ Ya en repo.** | Estructural | 4 |
| Amaral, P. S., & Quintin, E. (2006). "A Competitive Model of the Informal Sector." *Journal of Monetary Economics*, 53(7), 1541-1553. | EG **competitivo** (sin fricciones) donde formal/informal difieren por acceso a financiamiento y sustitución capital-trabajo no calificado — el modelo más cercano en espíritu a "EG estático con informalidad". | Estructural | 5 |
| Galiani, S., & Weinschelbaum, F. (2012). "Modeling Informality Formally: Households and Firms." *Economic Inquiry*, 50(3), 821-838. | Firmas y trabajadores heterogéneos eligen sector óptimamente; dos mercados laborales separados; explica hechos estilizados (tamaño de firma, calificación, trabajador secundario). | Estructural | 4 |
| Satchi, M., & Temple, J. (2009). "Labor Markets and Productivity in Developing Countries." *Review of Economic Dynamics*, 12(1), 183-204. | GE con fricciones de matching, autoempleo informal y migración rural-urbana, **calibrado explícitamente a datos de México** (hoja de cálculo de calibración pública). Precedente directo de "estructura macro con informalidad para México". | Estructural / México | 5 |
| Ulyssea, G. (2018). "Firms, Informality, and Development: Theory and Evidence from Brazil." *American Economic Review*, 108(8), 2015-2047. | Estado del arte: margen extensivo (registro) e intensivo (trabajadores no declarados) de informalidad en un modelo de firmas heterogéneas. **✓ Ya en repo.** | Estructural | 5 |
| Meghir, C., Narita, R., & Robin, J-M. (2015). "Wages and Informality in Developing Countries." *American Economic Review*, 105(4), 1509-1546. | Benchmark de wage-posting con firmas heterogéneas formal/informal y búsqueda on/off-the-job; referencia obligada aunque su elasticidad relevante es de salarios, no de demanda de empleo. | Estructural | 5 |
| La Porta, R., & Shleifer, A. (2014). "Informality and Development." *Journal of Economic Perspectives*, 28(3), 109-126. | Síntesis de 5 hechos estilizados de informalidad en desarrollo; motiva por qué modelos duales (no de "elección libre") son los consistentes con la evidencia. | Estructural / contexto | 4 |

### Bloque D — Econometría espacial / redes

| Cita completa | Aporte | Ruta | Rank |
|---|---|---|---|
| Anselin, L. (2003). "Spatial Externalities, Spatial Multipliers, and Spatial Econometrics." *International Regional Science Review*, 26(2), 153-166. | Taxonomía fundacional de especificaciones espaciales (lag, error, Durbin) derivadas de una forma reducida con multiplicadores espaciales. | Espacial | 5 |
| LeSage, J., & Pace, R. K. (2009). *Introduction to Spatial Econometrics*. Chapman & Hall/CRC. | El texto de referencia: estimación, efectos directos/indirectos, métodos bayesianos para modelos espaciales — manual operativo de la Ruta 2. | Espacial | 5 |
| Molho, I. (1995). "Spatial Autocorrelation in British Unemployment." *Journal of Regional Science*, 35(4). | Evidencia temprana de spillovers de shocks de demanda local vía commuting (interacción local) y migración (rezago, campo espacial amplio) — separa los dos mecanismos que la tesis quiere capturar con W. | Espacial | 3 |
| Helm, I. (2020). "National Industry Trade Shocks, Local Labour Markets, and Agglomeration Spillovers." *Review of Economic Studies*, 87(3), 1399-1431. | Estima spillovers de empleo entre mercados locales alemanes vía exposición indirecta a shocks de comercio de industrias vecinas — plantilla empírica más cercana a "Bartik + spillover espacial". | Espacial | 4 |
| Corrado, L., & Fingleton, B. (2012). "Where Is the Economics in Spatial Econometrics?" *Journal of Regional Science*, 52(2), 210-239. | Advertencia metodológica central: el W debe tener fundamento económico explícito, no ser data-driven — justifica por qué el W de commuting (y no uno arbitrario) es el correcto aquí. | Espacial | 4 |
| Monte, F., Redding, S. J., & Rossi-Hansberg, E. (2018). "Commuting, Migration, and Local Employment Elasticities." *American Economic Review*, 108(12), 3855-3890. | **La pieza puente**: la elasticidad de empleo local a un shock de demanda depende de la apertura al commuting; EG cuantitativo con trade + commuting + migración calibrado con gravedad. | Estructural + Espacial | 5 |
| Moretti, E. (2011). "Local Labor Markets." In O. Ashenfelter & D. Card (Eds.), *Handbook of Labor Economics*, Vol. 4, Ch. 14, 1237-1313. Elsevier. | Marco de EG de mercados locales con trabajo heterogéneo y equilibrio espacial de precios — el andamiaje conceptual que une "EG estático" con "mercado local" antes de introducir commuting explícito. | Estructural + Espacial | 5 |
| Combes, P-P., & Gobillon, L. (2015). "The Empirics of Agglomeration Economies." In *Handbook of Regional and Urban Economics*, Vol. 5, 247-348. Elsevier. | Marco integrado para la literatura empírica de determinantes locales de aglomeración; guía práctica de endogeneidad y forma funcional aplicable al diseño espacial de la tesis. | Espacial | 4 |

### Bloque E — Contexto México / supply shifters

| Cita completa | Aporte | Ruta | Rank |
|---|---|---|---|
| Chiquiar, D. (2008). "Globalization, Regional Wage Differentials and the Stolper-Samuelson Theorem: Evidence from Mexico." *Journal of International Economics*, 74(1), 70-93. | Documenta diferenciales salariales regionales por exposición a comercio en México (1990-2000) — hecho estilizado de validación/calibración del EG. | México | 5 |
| Fernández, A., & Meza, F. (2015). "Informal Employment and Business Cycles in Emerging Economies: The Case of Mexico." *Review of Economic Dynamics*, 18(2), 381-405. | Empleo informal contracíclico y rezagado en México — momento de calibración si la tesis incorpora dinámica de ciclo. | México | 4 |
| Leyva, G., & Urrutia, C. (2020). "Informality, Labor Regulation, and the Business Cycle." *Journal of International Economics*, 126. | Modelo de ciclo económico de economía pequeña y abierta con fricciones laborales e informalidad calibrado a México — plantilla macro para robustez dinámica. | México | 4 |
| Busso, M., Fazio, M. V., & Levy, S. (2012). "(In)Formal and (Un)Productive: The Productivity Costs of Excessive Informality in Mexico." IDB Working Paper Series No. IDB-WP-341. | Competencia monopolística + Censos Económicos: costo en productividad de mala asignación por informalidad en México — evidencia de magnitud del canal formal/informal. | México | 4 |
| Alvarez, J., & Ruane, C. (2019/2024). "Informality and Aggregate Productivity: The Case of Mexico." IMF Working Paper 19/257 → *European Economic Review*, 167 (agosto 2024). | Modelo de firmas heterogéneas + informalidad endógena **ya calibrado a México** (Censos Económicos 1998-2013) — el precedente estructural mexicano más cercano; la tesis debe diferenciarse explícitamente de este paper. | Estructural / México | 5 |
| Cadena, B., & Kovak, B. (2016). "Immigrants Equilibrate Local Labor Markets: Evidence from the Great Recession." *American Economic Journal: Applied Economics*, 8(1), 257-290. | Plantilla metodológica de *supply shifter*: migrantes de baja calificación responden a shocks de demanda mucho más que nativos, amortiguando el ajuste local — mecanismo exacto que se necesita para instrumentar oferta y aislar ε_D en forma reducida. | Espacial / identificación | 5 |
| Caballero, M. E., Cadena, B., & Kovak, B. (2021/2023). "The International Transmission of Local Economic Shocks Through Migrant Networks." NBER WP 28696 → *Journal of International Economics*, 145 (2023), 103832. | Aplica el mecanismo anterior directamente al lado mexicano: shocks de demanda en EE.UU. se transmiten a comunidades mexicanas vía redes migratorias — el candidato más directo de *supply shifter* para identificar ε_D en los 777 mercados. | Espacial / identificación | 5 |

---

## §3. Diseño / estrategia empírica sugerida (conectando ambas rutas)

**Paso 1 — Núcleo estructural (Ruta 1), agregado, sin informalidad.**
EG estático competitivo con función de producción anidada CES (trabajo por nivel de calificación, capital) en cada uno de los 777 mercados. La demanda de trabajo se deriva de la condición de primer orden (PMg = salario); ε_D es función de σ (sustitución factores) y de las participaciones factoriales (Hamermesh 1993, leyes de Hicks-Marshall). σ se identifica a la Raval (2019) explotando la variación de salarios *locales* entre los 777 mercados — la misma variación que documenta Chiquiar (2008) para el periodo de apertura comercial. Validar contra los momentos ya calculados por Aldeco et al. (2024): convergencia salarial regional post-2000, caída de la prima de habilidad.

**Paso 2 — Extensión con informalidad (Ruta 1).**
Añadir un segundo sector (informal) siguiendo la estructura de producción CES formal-informal de Ulyssea (2010) — σ_FI se calibra inicialmente (siguiendo Satchi-Temple 2009 y Amaral-Quintin 2006 como referencia de magnitudes), documentando explícitamente que la identificación de σ_FI requeriría un shock sectorial diferencial (fuera del alcance de la semilla, pero mencionable como extensión: reforma de subcontratación 2021, cambios en cuotas IMSS). El proxy de informalidad ya viene en la base de Aldeco et al., evitando depender de IMSS/ENOE para el núcleo.

**Paso 3 — Piso reduced-form para validar el signo/magnitud de ε_D.**
Dado que el Bartik de la base identifica oferta (mimeo companion Aldeco-Chiquiar-Pérez Pérez-Salcedo), usar como *supply shifter* alternativo la exposición de cada mercado a shocks de demanda en EE.UU. transmitidos vía redes migratorias (Caballero-Cadena-Kovak 2021/2023; Cadena-Kovak 2016). Una regresión de salario/empleo local sobre este instrumento de oferta traza movimientos a lo largo de la curva de demanda, dando una estimación reduced-form de ε_D que sirve como *validación externa* del parámetro estructural del Paso 1-2.

**Paso 4 — Capa espacial (Ruta 2) como robustez/extensión, no como sustituto.**
Estimar un spatial lag o spatial Durbin sobre el shock Bartik (o sobre el residuo de demanda estimado en el Paso 1) usando como **W la matriz de flujos casa-trabajo** que Aldeco et al. ya construyeron para delimitar los 777 mercados — no hay que estimar ni inventar W, ya existe en la base. Esto sigue el precedente de Monte-Redding-Rossi-Hansberg (2018): la elasticidad de empleo local depende de la apertura al commuting del mercado. Reportar efectos directos (propio mercado) e indirectos (spillover a mercados conectados) siguiendo Anselin (2003)/LeSage-Pace (2009), justificando el W con el argumento de Corrado-Fingleton (2012) de que el commuting *es* la definición económica del mercado, no una elección arbitraria. Como robustez adicional (no obligatoria), puede compararse contra W alternativos (migración interestatal, encuestas origen-destino de transporte) para verificar que los resultados no dependen de la red específica elegida — la literatura de selección de W (fuera de esta lista canónica) ofrece herramientas si se necesita este chequeo.

**Cómo se conectan las rutas:** el Paso 1-2 da un ε_D "de mercado aislado"; el Paso 4 relaja ese supuesto y muestra cuánto de la respuesta de demanda se disipa o amplifica por conexión commuting/migración con otros mercados — dando una noción de ε_D "de equilibrio general espacial" en el sentido de Monte-Redding-Rossi-Hansberg/Moretti. El Paso 3 ancla ambos ejercicios con una estimación creíble en forma reducida.

---

## §4. Referencias (con DOI/enlace)

**Bloque A**
- Aldeco, L., Calderón, M., Chiquiar, D., Hanson, G., Pérez Pérez, J., & Velázquez, C. (2024). *Local Labor Markets in Mexico: Definition, Databases, and Descriptive Analysis*. Banco de México. https://www.banxico.org.mx/apps/datasets/merclab/%7B2BB5ECD9-4503-30DD-93A3-B70FFE6A52FF%7D.pdf (ver también resumen en https://jorgeperezperez.com/research/2025-1-24-mexico-llm)
- Aldeco, L., Chiquiar, D., Pérez Pérez, J., & Salcedo, A. *Estimación de la elasticidad de la oferta de trabajo en México*. Mimeo, Banco de México. [No verificable públicamente — solicitar a econlab@banxico.org.mx]
- Autor, D., Dorn, D., & Hanson, G. (2013). "The China Syndrome." *American Economic Review*, 103(6), 2121-2168. https://doi.org/10.1257/aer.103.6.2121
- Tolbert, C., & Sizer, M. (1996). *U.S. Commuting Zones and Labor Market Areas: A 1990 Update*. USDA ERS Staff Paper 9614. https://ideas.repec.org/p/ags/uerssr/278812.html
- Fowler, C., & Jensen, L. (2020). "Bridging the Gap Between Geographic Concept and the Data We Have." *Environment and Planning A*, 52(7), 1395-1414. https://doi.org/10.1177/0308518X20906154
- Goldsmith-Pinkham, P., Sorkin, I., & Swift, H. (2020). "Bartik Instruments." *American Economic Review*, 110(8), 2586-2624. https://doi.org/10.1257/aer.20181047
- Borusyak, K., Hull, P., & Jaravel, X. (2022). "Quasi-Experimental Shift-Share Research Designs." *Review of Economic Studies*, 89(1), 181-213. https://academic.oup.com/restud/article-abstract/89/1/181/6294942
- Adão, R., Kolesár, M., & Morales, E. (2019). "Shift-Share Designs: Theory and Inference." *Quarterly Journal of Economics*, 134(4), 1949-2010. https://academic.oup.com/qje/article-abstract/134/4/1949/5552146
- Bartik, T. J. (1991). *Who Benefits from State and Local Economic Development Policies?* W.E. Upjohn Institute. https://doi.org/10.17848/9780585223940

**Bloque B**
- Hamermesh, D. S. (1993). *Labor Demand*. Princeton University Press. ISBN 0-691-04254-3.
- Lichter, A., Peichl, A., & Siegloch, S. (2015). *European Economic Review*, 80, 94-119. https://doi.org/10.1016/j.euroecorev.2015.08.007
- Raval, D. (2019). "The Micro Elasticity of Substitution and Non-Neutral Technology." *RAND Journal of Economics*, 50(1), 147-167. https://doi.org/10.1111/1756-2171.12265
- Clark, K. B., & Freeman, R. B. (1980). "How Elastic Is the Demand for Labor?" *Review of Economics and Statistics*, 62(4), 509-520. https://www.nber.org/papers/w0309
- Notowidigdo, M. J. (2020). "The Incidence of Local Labor Demand Shocks." *Journal of Labor Economics*, 38(3), 687-725. https://doi.org/10.1086/706048

**Bloque C**
- Ulyssea, G. (2010). *Journal of Development Economics*, 91(1), 87-99. https://doi.org/10.1016/j.jdeveco.2009.04.002
- Amaral, P. S., & Quintin, E. (2006). *Journal of Monetary Economics*, 53(7), 1541-1553. https://doi.org/10.1016/j.jmoneco.2005.07.016
- Galiani, S., & Weinschelbaum, F. (2012). *Economic Inquiry*, 50(3), 821-838. https://doi.org/10.1111/j.1465-7295.2011.00413.x
- Satchi, M., & Temple, J. (2009). *Review of Economic Dynamics*, 12(1), 183-204. https://ideas.repec.org/a/red/issued/06-167.html
- Ulyssea, G. (2018). *American Economic Review*, 108(8), 2015-2047. https://doi.org/10.1257/aer.20141745
- Meghir, C., Narita, R., & Robin, J-M. (2015). *American Economic Review*, 105(4), 1509-1546. https://doi.org/10.1257/aer.20121110
- La Porta, R., & Shleifer, A. (2014). *Journal of Economic Perspectives*, 28(3), 109-126. https://doi.org/10.1257/jep.28.3.109

**Bloque D**
- Anselin, L. (2003). *International Regional Science Review*, 26(2), 153-166. https://doi.org/10.1177/0160017602250972
- LeSage, J., & Pace, R. K. (2009). *Introduction to Spatial Econometrics*. Chapman & Hall/CRC. ISBN 978-1-4200-6424-7.
- Molho, I. (1995). *Journal of Regional Science*, 35(4). https://doi.org/10.1111/j.1467-9787.1995.tb01297.x
- Helm, I. (2020). *Review of Economic Studies*, 87(3), 1399-1431. https://academic.oup.com/restud/article/87/3/1399/5610540
- Corrado, L., & Fingleton, B. (2012). *Journal of Regional Science*, 52(2), 210-239. https://doi.org/10.1111/j.1467-9787.2011.00726.x
- Monte, F., Redding, S. J., & Rossi-Hansberg, E. (2018). *American Economic Review*, 108(12), 3855-3890. https://doi.org/10.1257/aer.20151507
- Moretti, E. (2011). *Handbook of Labor Economics*, Vol. 4, Ch. 14, 1237-1313. https://ideas.repec.org/h/eee/labchp/5-14.html
- Combes, P-P., & Gobillon, L. (2015). *Handbook of Regional and Urban Economics*, Vol. 5, 247-348. https://doi.org/10.1016/B978-0-444-59517-1.00005-2

**Bloque E**
- Chiquiar, D. (2008). *Journal of International Economics*, 74(1), 70-93. https://doi.org/10.1016/j.jinteco.2007.05.009
- Fernández, A., & Meza, F. (2015). *Review of Economic Dynamics*, 18(2), 381-405. https://ideas.repec.org/a/red/issued/12-21.html
- Leyva, G., & Urrutia, C. (2020). *Journal of International Economics*, 126. https://doi.org/10.1016/j.jinteco.2020.103340
- Busso, M., Fazio, M. V., & Levy, S. (2012). IDB Working Paper IDB-WP-341. https://www.econstor.eu/bitstream/10419/89037/1/IDB-WP-341.pdf
- Alvarez, J., & Ruane, C. (2019/2024). IMF WP 19/257 → *European Economic Review*, 167. https://www.sciencedirect.com/science/article/abs/pii/S001429212400120X (WP: https://www.imf.org/en/Publications/WP/Issues/2019/11/27/Informality-and-Aggregate-Productivity-The-Case-of-Mexico-48754)
- Cadena, B., & Kovak, B. (2016). *American Economic Journal: Applied Economics*, 8(1), 257-290. https://doi.org/10.1257/app.20140095
- Caballero, M. E., Cadena, B., & Kovak, B. (2021/2023). *Journal of International Economics*, 145, 103832. https://doi.org/10.1016/j.jinteco.2023.103832 (WP: https://www.nber.org/papers/w28696)

---

*Nota metodológica: ninguna referencia de esta lista fue descargada en PDF; todas se verificaron vía WebSearch/Consensus contra al menos una fuente secundaria (RePEc/IDEAS, AEA, Oxford Academic, ScienceDirect, NBER o la página del autor). La entrada del mimeo companion de oferta laboral no pudo verificarse de forma independiente en fuentes públicas indexadas y se mantiene por instrucción explícita del encargo — se recomienda solicitarlo directamente al EconLab de Banxico antes de citarlo en el documento final de tesis.*
