# Cuatro propuestas de tesis — Maestría en Economía
### Documento condensado para reunión con asesor · 2026-07-21
*Preparado: 2026-07-20 · Autor: Carlos Ramírez · Enfoque metodológico: modelos estructurales tratables · Datos: públicos escalables a administrativos*

---

## Cómo leer este documento

Cuatro apuestas **distintas y simultáneas**, pensadas como un menú para decidir dirección de tesis. Tres comparten un hilo (informalidad / empleo) y la cuarta es un pivote financiero de mayor riesgo. Cada propuesta trae: **resumen condensado**, **pregunta**, **justificación y gap** (con literatura reciente validada), **modelo/método**, **datos y limitaciones**, **contribución** y **riesgos**. La literatura se validó con el conector Consensus. La bibliografía exhaustiva de la **Propuesta 1** ya está en `research/comercio_informalidad_estructural_2026-07-20.md` (50 fuentes); las de P2/P4/P6 y una pasada del agente `critic` quedaron pendientes por límite de sesión (re-ejecutables tras el reset). El **mapa de vulnerabilidades estilo referee** al final se elaboró inline con el grounding disponible.

**Criterio transversal de factibilidad para maestría:** que exista una versión *reduced-form / semi-estructural* entregable con datos públicos (ENOE, Censos Económicos, Banxico, mercado) y una versión *estructural completa* como techo de ambición.

---

## Cuadro comparativo

| # | Apuesta | Pregunta en una línea | Corazón metodológico | Datos base (público → admin) | Riesgo | Novedad | Horizonte |
|---|---------|----------------------|----------------------|------------------------------|:------:|:------:|:--------:|
| **1** | Comercio × informalidad | ¿Cómo redistribuye un shock comercial firmas y empleo entre formal/informal en equilibrio general? | Melitz + formalidad endógena, SMM, contrafáctico China/TLCAN | Censos Económicos + ENOE → IMSS | Medio | Media-alta | 16-22 m |
| **2** | Monopsonio × informalidad | ¿El poder del empleador (markdowns) empuja a la informalidad y comprime salarios? | Search-matching con wage-setting + salida informal; estimación de markdowns | ENOE + Censos (HHI local) → IMSS | Medio | **Alta** | 16-20 m |
| **4** | Política monetaria × empleo F/I | ¿La informalidad amortigua o amplifica la transmisión de la política monetaria al empleo? | Shocks de tasa de alta frecuencia + local projections sobre transiciones F↔I; NK dual | Banxico + ENOE panel (públicos) | Medio-alto | Media-alta | 14-18 m |
| **6** | Cripto/stablecoins × (finanzas→empleo) | ¿Cómo transmiten los shocks de stablecoins a los mercados y (¿al empleo?) en México? | SVAR-IV de alta frecuencia + regímenes (mixture models); puente exploratorio a empleo | Mercado HF + Banxico + remesas | **Alto** | Alta (arriesgada) | 14-20 m |

---

## PROPUESTA 1 · Comercio internacional e informalidad en equilibrio general

**Resumen condensado.** Un modelo de equilibrio general con firmas heterogéneas (Melitz) y **decisión de formalidad endógena** bajo enforcement imperfecto, calibrado a México, para cuantificar cómo un shock comercial (China shock / apertura TLCAN) reasigna firmas y empleo entre los sectores formal e informal, y cuánto amplifica o atenúa las ganancias de bienestar el margen informal. Traslada a México un enfoque estructural ya maduro para Brasil.

**Pregunta de investigación.** ¿Cómo redistribuye un shock comercial la masa de firmas y el empleo entre formal e informal en equilibrio general? ¿El sector informal funciona como amortiguador ("buffer") del empleo o como "buffer de bienestar"? ¿Cuánto cambia la respuesta de política si se ignora la informalidad?

**Justificación y gap.** La literatura reduced-form documenta efectos agregados de shocks comerciales sobre informalidad, con evidencia mixta según instituciones y enforcement ([Goldberg & Pavcnik 2003](https://consensus.app/papers/details/16882561383d5c7e8bf2f3c2ef2a4356/?utm_source=claude_desktop)) y con dos márgenes opuestos —extensivo (firmas no registradas) e intensivo (trabajadores off-the-books en firmas formales)— como muestra el caso de Perú ([Cisneros-Acevedo 2021](https://consensus.app/papers/details/a1ef30b7747850bcaf1c2b4938ae684b/?utm_source=claude_desktop)) y de China ([Wang et al. 2021](https://consensus.app/papers/details/87b8e19ebdc85ca7b71ad53a738feaf0/?utm_source=claude_desktop)). El frente **estructural** está consolidado para **Brasil**: economías pequeñas abiertas con fricciones laborales y regulación imperfectamente aplicada, donde las firmas se auto-seleccionan a formal/informal ([Ulyssea et al. 2021](https://consensus.app/papers/details/8931201c59d751cba62bc1c82c688d50/?utm_source=claude_desktop)), y modelos cuantitativos donde la informalidad amplifica las ganancias de comercio ([Dix-Carneiro et al. 2026, *Econometrica*](https://consensus.app/papers/details/e18d6d3b082950668dccae187017c32b/?utm_source=claude_desktop)).

> **⚠️ El gap, afinado con la búsqueda profunda (importante para la reunión):** **sí existe** un modelo EG con informalidad endógena calibrado a México — **Alvarez & Ruane (IMF WP 19/257, 2019 → *European Economic Review* v.167, 2024)**, sobre Censo Económico 1998-2013 — pero es de **economía cerrada**, estimación **estática por GMM**, y su motor son **reformas regulatorias domésticas**, no un shock comercial externo. Y DGMU (2026, *Econometrica*) hace el puente completo pero **para Brasil**. **La contribución de la tesis es la intersección exacta:** llevar la familia DGMU/Alvarez-Ruane a un régimen **dinámico de shock comercial** (arancelario TLCAN + penetración china) con **calibración SMM** y trayectoria de transición, disciplinada con la elasticidad de enforcement mexicana de **Samaniego de la Parra (2024, AEJ:Applied)** (480,000 inspecciones IMSS/STPS). **Hecho estilizado motivador:** la "paradoja mexicana" de **Fentanes & Levy (2024)** — las exportaciones subieron de 7% a 33% del PIB, pero la informalidad laboral apenas cambió, la informalidad *de firmas* subió y el TFP agregado cayó. El gemelo reduced-form más limpio para validar la primera etapa es **Bas & Bombarda (2026, JDE)**: la liberalización de insumos formaliza, la competencia en outputs informaliza.

**Modelo y método.** Melitz con dos sectores (formal/informal), costos de formalización y enforcement estocástico; equilibrio con entrada endógena y sorteo formal/informal por productividad. Calibración a México vía **SMM** con momentos objetivo (share de empleo informal ~55%, prima salarial formal-informal, distribución de tamaños, tasas de entrada/salida). Contrafácticos: reversión del China shock, cambios arancelarios. **Versión maestría:** empezar replicando la lógica de [Meghir, Narita & Robin (2015)](https://consensus.app/papers/details/16882561383d5c7e8bf2f3c2ef2a4356/?utm_source=claude_desktop) adaptada, con validación reduced-form (exposición comercial regional tipo Autor-Dorn-Hanson) antes de la calibración completa.

**Datos y limitaciones.** Censos Económicos (2004-2019, SCIAN 6 dígitos) + ENOE para calibración y transiciones; comercio de Banxico/UN Comtrade. Escala a IMSS para validar transiciones formal↔informal. *Limitación central:* la informalidad intensiva (off-the-books en firmas formales) es difícil de medir sin administrativos; la calibración estructural completa es ambiciosa para el plazo.

**Contribución.** Primer modelo EG **con shock comercial externo** que integra informalidad endógena para México (distinto de Alvarez-Ruane, que es cerrado y estático); cuantificación del papel del margen informal en las ganancias/pérdidas de bienestar del comercio; implicaciones de política (enforcement selectivo vs. costos de formalización, en línea con la predicción testeable de Ulyssea 2020).

**Riesgos.** (a) **Novedad acotada:** la contribución es una intersección, no un modelo nuevo — hay que venderla como "puente dinámico comercial" y no como "primer modelo para México". (b) Complejidad de la calibración SMM. (c) Sensibilidad a la definición de informalidad. *Mitigación:* entregar primero la capa reduced-form (Bas-Bombarda para México) como resultado autónomo, y usar Samaniego (2024) para disciplinar enforcement.

---

## PROPUESTA 2 · Poder de mercado del empleador (monopsonio) e informalidad — *la más novedosa*

**Resumen condensado.** Un modelo de búsqueda y emparejamiento donde la firma **fija salarios** (poder monopsónico) y el sector informal es la opción de salida del trabajador, para medir cuánto de la informalidad mexicana es "expulsión monopsónica" (salarios comprimidos que empujan fuera del sector formal) frente a elección voluntaria. Cierra un vínculo estructural casi vacío empíricamente.

**Pregunta de investigación.** ¿El poder de mercado del empleador —medido como markdown laboral o baja elasticidad de oferta laboral a la firma— aumenta la probabilidad de que el trabajador transite a la informalidad y comprime su salario? ¿Cuánta informalidad es monopsonio y cuánta es elección?

**Justificación y gap.** El monopsonio laboral es hoy consenso empírico: los markdowns reducen sustancialmente la participación del trabajo en el ingreso en economías en desarrollo ([Brooks et al. 2019](https://consensus.app/papers/details/e94d58fca7905537ade10d0972fcfd87/?utm_source=claude_desktop), China e India), y las reseñas recientes lo formalizan vía oligopsonio, diferenciación de puestos y fricciones de búsqueda ([Manning 2020](https://consensus.app/papers/details/16f4c48bb16a5abe858618a637930a08/?utm_source=claude_desktop); [Azar & Marinescu 2024](https://consensus.app/papers/details/5357146a447e5873a531e1287dc8f15b/?utm_source=claude_desktop)). El puente al **empleo formal** ya apareció con datos administrativos de Brasil: el monopsonio afecta más a trabajadores de mayor productividad y el salario mínimo interactúa con la formalidad ([Bils et al. 2025, *Robinson Meets Roy*](https://consensus.app/papers/details/84a353c7cfa658d79d69359d7787cf99/?utm_source=claude_desktop)), y hay un intento de modelo integrado informalidad-salario mínimo-monopsonio ([Salguero 2025](https://consensus.app/papers/details/f815a4235f0f51cf9a854812909a9707/?utm_source=claude_desktop)). **Para México** solo existe evidencia *reduced-form*: concentración (HHI) × salario mínimo × informalidad, con spillovers mayores para informales ([Valverde 2023](https://consensus.app/papers/details/900db2304ba159d3b422bd33837e37d8/?utm_source=claude_desktop)). **El gap:** nadie ha modelado *estructuralmente* el canal monopsonio → informalidad para México.

**Modelo y método.** Búsqueda y emparejamiento con fijación de salarios por la firma (elasticidad de oferta laboral finita) y sector informal como estado de salida; estimación de markdowns à la [Brooks et al. (2019)](https://consensus.app/papers/details/e94d58fca7905537ade10d0972fcfd87/?utm_source=claude_desktop) o vía elasticidad de separaciones. Identificación reduced-form de primer paso: HHI por mercado laboral local (zona metropolitana × industria) con Censos Económicos, interactuado con transiciones a informalidad en ENOE. Segundo paso: calibración del modelo de matching.

**Datos y limitaciones.** ENOE (transiciones, salarios, características) + Censos Económicos (concentración por mercado local); escala a IMSS para elasticidad de separaciones firma-nivel. *Limitación central:* identificar markdowns sin datos de producto marginal; la concentración local puede ser proxy imperfecto del poder de mercado.

**Contribución.** Primera cuantificación estructural del canal monopsonio→informalidad; descomposición informalidad "por expulsión" vs. "por elección"; implicaciones para política de competencia laboral y salario mínimo en México.

**Riesgos.** Medición de markdowns; endogeneidad de la concentración. *Mitigación:* triangular varias medidas de poder de mercado (HHI, elasticidad de separaciones, dispersión salarial residual).

---

## PROPUESTA 4 · Política monetaria y empleo formal/informal

**Resumen condensado.** Identificar shocks de política monetaria de **alta frecuencia** para México y estimar, con **local projections**, su efecto sobre el empleo y las **transiciones formal↔informal** en el panel ENOE, interpretados con un modelo Nuevo-Keynesiano de mercado laboral dual. Prueba directamente si la informalidad amortigua o amplifica el canal de tasa.

**Pregunta de investigación.** ¿Cómo transmite la política monetaria a través del margen de informalidad en México? Ante un shock contractivo, ¿el empleo informal absorbe al formal desplazado (buffer) y debilita el canal de tasa, o lo amplifica? ¿Cuál es el efecto distributivo sobre trabajadores de bajos ingresos?

**Justificación y gap.** Frente teórico muy activo: modelos NK-DSGE de dos sectores muestran que la informalidad actúa como *buffer* de shocks de demanda, debilita el canal de tasa y eleva el sacrifice ratio ([Castillo & Montoro 2010](https://consensus.app/papers/details/2fb6ba53d8b3593cb4022890c96df507/?utm_source=claude_desktop); [Alberola & Urrutia 2020](https://consensus.app/papers/details/fceb5c97a7ae56fbb5334aa9bfa3dbb1/?utm_source=claude_desktop)), y para **México** ya hay precedentes calibrados/estimados ([Leyva & Urrutia 2020, con ENOE](https://consensus.app/papers/details/4613a68b2b2351488e99853025b0e446/?utm_source=claude_desktop); [Mirfatah et al. 2024](https://consensus.app/papers/details/df9512f865df5f2c8f4fa1f0a67dbf68/?utm_source=claude_desktop); [Yépez 2025](https://consensus.app/papers/details/2f149dd247ec5c67b7e9c64e63e0421c/?utm_source=claude_desktop)). **El ángulo libre** es empírico y micro: identificar shocks de tasa de alta frecuencia y estimar sus efectos sobre **transiciones individuales** F↔I con local projections — hecho ya para **Brasil** ([Gomes et al. 2023](https://consensus.app/papers/details/8f2437f40d3555f4acc04136d1c4fd21/?utm_source=claude_desktop)) pero **no para México**. Aprovecha los papers de local projections (Jordà) y de Phillips curve del corpus.

**Modelo y método.** (i) Construcción de sorpresas de política monetaria de alta frecuencia (ventana alrededor de decisiones de Banxico). (ii) **Local projections** (Jordà) de respuestas de empleo formal, informal, salarios y tasas de transición al shock. (iii) Interpretación con un NK de dos sectores para racionalizar signos y magnitudes. Posibles asimetrías (contracciones vs. expansiones) como en Brasil.

**Datos y limitaciones.** Todo público: Banxico (tasa objetivo, sorpresas), INEGI/ENOE (empleo, transiciones panel de 5 trimestres). *Limitación central:* pocas "sorpresas" limpias de política monetaria en México (calendario de decisiones acotado) → poder estadístico limitado; el panel corto de ENOE restringe horizontes largos.

**Contribución.** Primera evidencia para México de transmisión monetaria vía transiciones formal↔informal con identificación de alta frecuencia; medición del efecto buffer a nivel micro; lectura distributiva de la política monetaria.

**Riesgos.** Poder estadístico por escasez de shocks; identificación de la sorpresa monetaria. *Mitigación:* combinar con shocks externos (spillovers de la Fed) para ganar variación.

---

## PROPUESTA 6 · Shocks de cripto/stablecoins: del mercado financiero al empleo (WILDCARD)

**Resumen condensado.** Dos capas. **Núcleo sólido:** identificar shocks de demanda de stablecoins/cripto de alta frecuencia y estimar su transmisión a variables financieras mexicanas (tipo de cambio, tasas, spreads) con SVAR-IV y detección de regímenes vía mixture models. **Extensión exploratoria (alto riesgo):** tender un puente hacia la economía real / empleo formal-informal vía remesas y dolarización. Es la apuesta más original y más arriesgada; su valor es tantear un pivote de subcampo con el asesor.

**Pregunta de investigación.** *(Núcleo)* ¿Cómo transmiten los shocks de stablecoins/cripto a los mercados financieros mexicanos y cómo cambian los regímenes de volatilidad? *(Extensión)* ¿Existe un canal detectable de estos shocks hacia el empleo formal/informal en México, vía remesas y dolarización?

**Justificación y gap.** El núcleo financiero está **bien anclado**: existen medidas de shocks de stablecoins de alta frecuencia con identificación SVAR-IV y efectos causales sobre yields, dólar y mercados ([Cerutti et al. 2026, IMF](https://consensus.app/papers/details/b675c3c353925d0cb4e8d96f78e996fa/?utm_source=claude_desktop)) y spillovers documentados a **mercados FX** —clave para una economía con remesas como México— ([Aldasoro et al. 2026, IMF](https://consensus.app/papers/details/b076ec6bcbe35439a7146ad3163ea62a/?utm_source=claude_desktop)); además, spillovers globales cripto→mercados financieros ([Vukovic et al. 2024, JIMF](https://consensus.app/papers/details/ec28fdf8bbf6510a85e795508d93dff1/?utm_source=claude_desktop)). **El puente al empleo está casi vacío empíricamente:** lo disponible es cualitativo (remesas en stablecoins y dolarización en LatAm, [Robins 2024](https://consensus.app/papers/details/462ce84a86c75221a08cd498137568dc/?utm_source=claude_desktop); pago de trabajo de plataforma en cripto, [Posada 2024](https://consensus.app/papers/details/72c82de7ab3352f0bd3c161ade810ae4/?utm_source=claude_desktop)) o macro-agregado ([Guo et al. 2025](https://consensus.app/papers/details/6f6c5b4727965144a4bae82535d81e4c/?utm_source=claude_desktop)). El único precedente **estructural** de mercado laboral con informalidad + digital para México es de adopción digital, no de shocks cripto ([Finkelstein Shapiro et al. 2023, WB Econ Review](https://consensus.app/papers/details/d8639a65d1265ea595cef6e356f3c48f/?utm_source=claude_desktop)). **Gap:** el núcleo México-específico no está hecho; el puente al empleo sería genuinamente nuevo pero de alto riesgo.

**Modelo y método.** *(Núcleo)* SVAR-IV con identificación por heteroscedasticidad y datos de alta frecuencia (capitalización de USDC/USDT, narrativa de noticias), respuestas del peso, tasas y spreads soberanos; **detección de regímenes** con mixture models / Markov-switching (aprovecha el corpus `04_mixture_models`). *(Extensión)* series de tiempo de remesas y actividad real, con local projections, para rastrear un eventual canal al empleo formal/informal.

**Datos y limitaciones.** Núcleo: datos de mercado de alta frecuencia (cripto, FX), series Banxico. Extensión: remesas (Banxico), ENOE. *Limitación central y honesta:* el eslabón finanzas→empleo informal carece de literatura y de un mecanismo de identificación claro; el riesgo de "no encontrar nada" en la extensión es real.

**Contribución.** *(Núcleo)* Primera caracterización de la transmisión de shocks de stablecoins a mercados mexicanos con regímenes. *(Extensión)* Exploración pionera —y explícitamente especulativa— del canal cripto→empleo.

**Riesgos.** Altos. La extensión al empleo puede no ser identificable. *Mitigación / recomendación:* estructurar la tesis sobre el **núcleo financiero** (autónomo y publicable) y presentar el puente al empleo como sección exploratoria, no como corazón.

---

## Recomendación de priorización (para discutir con el asesor)

- **Si el objetivo es máxima originalidad con factibilidad razonable:** Propuesta **2** (monopsonio × informalidad) — el vínculo estructural está casi vacío y hay datos.
- **Si se prioriza terminar sólido y rápido con datos públicos:** Propuesta **4** (política monetaria × empleo) — reduced-form/LP entregable, aunque frontera concurrida.
- **Si atrae la ambición teórica de equilibrio general:** Propuesta **1** (comercio × informalidad) — mayor techo, mayor costo de calibración.
- **Si se quiere pivotar a finanzas cuantitativas:** Propuesta **6** — quedarse en el núcleo financiero; el puente al empleo es upside arriesgado.

**Preguntas abiertas para la reunión con el asesor:**
1. ¿El asesor tiene red/acceso para microdatos IMSS-SAT (habilita el techo estructural de 1, 2)?
2. ¿Prefiere un paper "limpio" reduced-form o una tesis estructural con calibración?
3. ¿La línea del asesor es comercio-trabajo, macro-monetaria, o financiera? (define cuál de las 4 tiene mejor mentoría)
4. ¿Horizonte real de la tesis y expectativa de publicación (journal regional vs. tier-2)?

---

## Nota de datos y acceso

- **Públicos, sin trámite:** ENOE (panel 5 trimestres), Censos Económicos (SCIAN 6 díg.), ENOE informalidad, Banxico (tasas, tipo de cambio, remesas), UN Comtrade, datos de mercado cripto/FX de alta frecuencia.
- **Administrativos (2-4 meses de aprobación, sala de datos INEGI/IMSS):** IMSS (afiliación patronal, altas/bajas, salarios) — habilita el techo estructural de las Propuestas 1, 2 y la validación de transiciones de la 4.
- **Estrategia mixta/escalable:** las cuatro propuestas están diseñadas para entregar una primera versión con datos públicos y escalar a administrativos si el acceso se aprueba.

---

## Mapa de vulnerabilidades — stress-test estilo referee (anticipando al asesor)

*Elaborado inline (el agente `critic` y los researchers de P2/P4/P6 se pueden re-correr tras el reset de cuota, 1:30am CDMX). Para cada propuesta: las objeciones más duras que probablemente hará el asesor y una defensa sugerida.*

### P1 · Comercio × informalidad
- **[Novedad — la más peligrosa]** "Esto es DGMU (2026) aplicado a México, o Alvarez-Ruane con comercio. ¿Qué hay de nuevo?" → **Defensa:** la contribución no es el modelo sino el **régimen dinámico de shock comercial externo** y reconciliar los canales opuestos que documenta Bas-Bombarda (2026) —insumos formalizan, outputs informalizan— dentro de un solo marco cuantitativo con transición. No es mecánico: el signo neto es una pregunta cuantitativa abierta.
- **[Identificación/calibración]** "La calibración SMM tiene muchos parámetros libres." → **Defensa:** disciplinar el enforcement con el momento externo de Samaniego (2024, 480k inspecciones IMSS) en lugar de dejarlo libre.
- **[Datos]** El margen intensivo (off-the-books en firmas formales) no se observa en datos públicos; los Censos son quinquenales → dinámica limitada.
- **[Alcance maestría]** Modelo completo + SMM es probablemente demasiado. → **Mitigación:** entregar la réplica reduced-form (Bas-Bombarda con China shock) como núcleo autónomo; la estructural como extensión/techo.

### P2 · Monopsonio × informalidad
- **[Identificación — la más peligrosa]** "Los markdowns no se observan y el HHI local es endógeno y ruidoso; ¿cómo distingues monopsonio de heterogeneidad no observada o de laxitud del mercado local?" → **Defensa:** triangular tres medidas (HHI local, elasticidad de separaciones firma-nivel con IMSS, dispersión salarial residual) y buscar shocks a la concentración (entradas/salidas de grandes empleadores) como fuente exógena.
- **[Causalidad inversa]** ¿El monopsonio causa informalidad, o la informalidad da poder de mercado a la firma formal? → **Defensa:** usar la estructura tipo Roy de Bils et al. (2025) para separar selección de poder; anclar temporalmente (poder en t → transición en t+1).
- **[Novedad adyacente]** Existe Valverde (2023, México reduced-form) y Bils (2025, Brasil estructural). → **Defensa:** el modelo estructural monopsonio→informalidad **para México** no existe; es hueco genuino.
- **[Datos]** ENOE no identifica la firma → el primer paso necesita IMSS para separaciones. Sin IMSS, el alcance se reduce a la evidencia de concentración local.

### P4 · Política monetaria × empleo F/I
- **[Poder estadístico — la más peligrosa]** "Banxico decide ~8 veces al año; hay poquísimas sorpresas limpias → tus local projections no tendrán poder." → **Defensa:** aumentar variación con shocks externos (spillovers de la Fed, sorpresas de tasa externas), muestra larga, y complementar con SVAR de restricciones de signo.
- **[Novedad]** Frontera concurrida con precedentes mexicanos (Leyva-Urrutia 2020, Mirfatah 2024, Yépez 2025). → **Defensa:** el ángulo micro —transiciones individuales F↔I con identificación de alta frecuencia— no se ha hecho para México (Gomes et al. 2023 lo hizo para Brasil).
- **[Datos]** El panel ENOE es corto (5 trimestres) con atrición rotativa → limita horizontes y medición de transiciones.
- **[Interpretación]** Un LP reduced-form no da el mecanismo; el NK que lo interpreta reintroduce supuestos de calibración.

### P6 · Cripto/stablecoins × (finanzas→empleo) — *wildcard*
- **[El puente — la más peligrosa]** "El canal cripto→empleo informal no está identificado en ninguna parte; riesgo alto de resultado nulo." → **Defensa (y recomendación):** estructurar la tesis sobre el **núcleo financiero** (stablecoin shocks → FX/tasas/spreads mexicanos, sólido y publicable) y presentar el empleo como sección **exploratoria**, no como corazón.
- **[Desajuste de frecuencia]** Datos financieros de alta frecuencia vs. ENOE trimestral → vincularlos es difícil y frágil.
- **[Relevancia]** El núcleo es novedoso y factible, pero "¿por qué importa para una tesis de economía mexicana?" → **Defensa:** anclar a un hook de política (dolarización, remesas, estabilidad financiera).
- **[Modelado de regímenes]** La detección de regímenes con mixture models es una elección de modelo; riesgo de sobreajuste / regímenes arbitrarios. → **Defensa:** validar con criterios de información y estabilidad fuera de muestra.
- **[Encaje de subcampo]** Pivota fuera de la identidad laboral/informalidad — conviene confirmar con el asesor si ese giro es deseado.

---

## Referencias clave validadas (Consensus)

**Comercio × informalidad:** [Goldberg & Pavcnik 2003](https://consensus.app/papers/details/16882561383d5c7e8bf2f3c2ef2a4356/?utm_source=claude_desktop) · [Ulyssea et al. 2021](https://consensus.app/papers/details/8931201c59d751cba62bc1c82c688d50/?utm_source=claude_desktop) · [Dix-Carneiro et al. 2026 (Econometrica)](https://consensus.app/papers/details/e18d6d3b082950668dccae187017c32b/?utm_source=claude_desktop) · [Cisneros-Acevedo 2021 (Perú)](https://consensus.app/papers/details/a1ef30b7747850bcaf1c2b4938ae684b/?utm_source=claude_desktop) · [Wang et al. 2021 (China)](https://consensus.app/papers/details/87b8e19ebdc85ca7b71ad53a738feaf0/?utm_source=claude_desktop) · [Paz 2022 (Brasil)](https://consensus.app/papers/details/db4d88363e4253d699a277e5cfb164b7/?utm_source=claude_desktop)

**Monopsonio × informalidad:** [Brooks et al. 2019](https://consensus.app/papers/details/e94d58fca7905537ade10d0972fcfd87/?utm_source=claude_desktop) · [Manning 2020](https://consensus.app/papers/details/16f4c48bb16a5abe858618a637930a08/?utm_source=claude_desktop) · [Azar & Marinescu 2024](https://consensus.app/papers/details/5357146a447e5873a531e1287dc8f15b/?utm_source=claude_desktop) · [Bils et al. 2025 (Brasil)](https://consensus.app/papers/details/84a353c7cfa658d79d69359d7787cf99/?utm_source=claude_desktop) · [Valverde 2023 (México)](https://consensus.app/papers/details/900db2304ba159d3b422bd33837e37d8/?utm_source=claude_desktop) · [Salguero 2025](https://consensus.app/papers/details/f815a4235f0f51cf9a854812909a9707/?utm_source=claude_desktop)

**Política monetaria × empleo informal:** [Castillo & Montoro 2010 (Perú)](https://consensus.app/papers/details/2fb6ba53d8b3593cb4022890c96df507/?utm_source=claude_desktop) · [Alberola & Urrutia 2020](https://consensus.app/papers/details/fceb5c97a7ae56fbb5334aa9bfa3dbb1/?utm_source=claude_desktop) · [Leyva & Urrutia 2020 (México)](https://consensus.app/papers/details/4613a68b2b2351488e99853025b0e446/?utm_source=claude_desktop) · [Mirfatah et al. 2024 (México)](https://consensus.app/papers/details/df9512f865df5f2c8f4fa1f0a67dbf68/?utm_source=claude_desktop) · [Yépez 2025](https://consensus.app/papers/details/2f149dd247ec5c67b7e9c64e63e0421c/?utm_source=claude_desktop) · [Gomes et al. 2023 (Brasil)](https://consensus.app/papers/details/8f2437f40d3555f4acc04136d1c4fd21/?utm_source=claude_desktop)

**Cripto/stablecoins × finanzas y empleo:** [Cerutti et al. 2026 (IMF)](https://consensus.app/papers/details/b675c3c353925d0cb4e8d96f78e996fa/?utm_source=claude_desktop) · [Aldasoro et al. 2026 (IMF, FX)](https://consensus.app/papers/details/b076ec6bcbe35439a7146ad3163ea62a/?utm_source=claude_desktop) · [Vukovic et al. 2024 (JIMF)](https://consensus.app/papers/details/ec28fdf8bbf6510a85e795508d93dff1/?utm_source=claude_desktop) · [Finkelstein Shapiro et al. 2023 (México)](https://consensus.app/papers/details/d8639a65d1265ea595cef6e356f3c48f/?utm_source=claude_desktop) · [Robins 2024](https://consensus.app/papers/details/462ce84a86c75221a08cd498137568dc/?utm_source=claude_desktop) · [Posada 2024](https://consensus.app/papers/details/72c82de7ab3352f0bd3c161ade810ae4/?utm_source=claude_desktop)

---

*Documento listo para la reunión. Pendiente opcional (tras reset de cuota 1:30am CDMX): re-correr researchers de P2/P4/P6 para bibliografías exhaustivas y una pasada del agente `critic` sobre el documento completo.*
