# Memo — De la elasticidad al estancamiento: brecha de producto y mala asignación laboral en mercados locales

**Fecha:** 2026-07-31 · **Autor:** Carlos Ramírez (Maestría en Economía, ITAM) · **Sesión:** evaluación del giro macro (¿por qué no crece México?) y comparación contra la propuesta original

**Documentos previos:** `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md` (viabilidad), `../../critique/elasticidad_demanda_local_critique_2026-07-22.md` (crítica referee)

---

## 0. Veredicto ejecutivo

El giro hacia **"¿por qué no crece México?"** resuelve el problema más serio de la propuesta original —que estimaba un parámetro sin una pregunta económica que lo justificara— pero introduce un problema conceptual nuevo (estático ≠ crecimiento) y te mete a un campo **muy poblado y de alto nivel** (Econometrica, EER, QJE).

Tres conclusiones:

1. **Las dos propuestas no son alternativas: la nueva contiene a la vieja.** No puedes hacer la calibración macro sin estimar ε_D primero. Por tanto la decisión no es "A o B", es **"¿hasta dónde llego?"**. Esto convierte la elección en un diseño graduado, no en una apuesta.
2. **Sí alcanza con ε_D + ε_S para el bloque laboral, y para nada más.** El insumo que verdaderamente te falta no es una elasticidad: es **la cuña τ**. Buena noticia: se construye con datos institucionales (cuotas IMSS), sin estimar nada. Mejor noticia: **varía espacialmente de forma mecánica**, lo cual regala variación al diseño de mercados locales (§4.3).
3. **El cubo agregado NO alcanza solo.** Te da el split de *empleo* formal/informal, pero no el split de *salarios*, que es la variable que hace o rompe el ejercicio. Tienes que bajar al microdato individual — que también es público y trae el id de mercado local. No es bloqueante, es trabajo adicional (§5).

---

## 1. Qué gana y qué pierde el giro

### 1.1 Lo que arregla

| Vulnerabilidad de la crítica referee | Estado bajo el nuevo framing |
|---|---|
| **V1** — ambigüedad del objeto; ¿en qué difiere de MRRH (2018)? | **Resuelta.** ε_D deja de ser el producto final y pasa a ser un insumo con propósito. MRRH responde "¿cuánto se mueve el empleo local ante un shock?"; tú respondes "¿cuánto producto se pierde por la mala asignación?". Son preguntas distintas. |
| **V2** — la ruta estructural *impone* ε_D en vez de estimarla | **Resuelta.** ε_D pasa a ser un **momento que disciplina el modelo**, no un parámetro que enchufas. Estimas → pinneas σ → computas el contrafactual → reportas la sensibilidad al intervalo de confianza de ε_D. |
| **V4** — scooping del EconLab | **Muy debilitada.** El EconLab estima elasticidades; no cuantifica el costo agregado de la mala asignación. Ya no compites con ellos: los citas como insumo. |
| **V8** — sobre-alcance | **Empeora.** El giro añade un capítulo, no lo quita. Ver §6. |

### 1.2 Lo que rompe: estático ≠ crecimiento

Este es el punto que tu asesor va a señalar en los primeros cinco minutos, así que hay que resolverlo antes de la reunión:

> **Un modelo estático produce *niveles*, no tasas de crecimiento.** Reasignar trabajo de informal a formal genera un salto de nivel de una sola vez. No genera crecimiento sostenido. Si escribes "modelo estático que explica el crecimiento", el objeto y la pregunta no encajan y es una crítica fatal.

**La salida:** Baqaee & Farhi [3] dan fórmulas no paramétricas para agregar economías con distorsiones, separando explícitamente **eficiencia técnica** de **eficiencia asignativa**. Es teoría de agregación **estática**, pero aplicada repetidamente en el tiempo produce una **descomposición del crecimiento de la PTF**. (En EE.UU. encuentran que la eficiencia asignativa explica ~la mitad del crecimiento de la PTF agregada 1997–2015.)

Reformulación operativa:

> No modelas el crecimiento. Modelas el **nivel** de eficiencia asignativa en 1990, 2000, 2010 y 2020. La **trayectoria** de ese nivel es tu contribución al debate del estancamiento.

**Nota sobre el diseño:** la frecuencia decenal del censo, que era una *limitación* en la propuesta original (§7 del memo de viabilidad, riesgo "frecuencia decenal"), aquí se vuelve **exactamente la estructura que el ejercicio necesita**. Cuatro cortes censales = cuatro mediciones de eficiencia asignativa = una descomposición. El defecto se convierte en característica.

---

## 2. El eslabón: por qué ε_D *es* la respuesta, no un adorno

En cualquier ejercicio de mala asignación, la ganancia de eliminar una cuña τ es, a primer orden, un triángulo de Harberger:

$$\Delta Y \;\approx\; \tfrac{1}{2}\,\tau^{2}\cdot\underbrace{\frac{\varepsilon_{D}\,\varepsilon_{S}}{\varepsilon_{D}+\varepsilon_{S}}}_{\text{elasticidad de reasignación}}\cdot\, L$$

Léelo así: **las elasticidades no decoran el ejercicio, determinan la magnitud de la respuesta de política.** Con demanda inelástica, remover la cuña de informalidad casi no mueve nada y las ganancias son triviales. Con demanda elástica, mueve mucho.

**Aquí está tu hueco real.** Toda la literatura mexicana de misallocation —Leal-Ordóñez [7], Busso-Fazio-Levy [10], Antón & Leal [12]— **calibra** ese parámetro por falta de una estimación creíble. Tú lo **estimarías** con variación local en 777 mercados, y además con **heterogeneidad espacial**: ε_D no es un escalar, es un vector de 777 entradas (o de N regiones). Eso permite decir *dónde* duele más la cuña, que es una afirmación de política que ningún paper nacional puede hacer.

---

## 3. Qué es exactamente la "cuña τ"

Es el objeto que te falta y sobre el que preguntaste. Definición: **la brecha entre el costo de emplear a un trabajador formalmente y el costo de emplearlo informalmente**, expresada como fracción del salario. Es lo que hace que el producto marginal del trabajo difiera entre sectores, y por tanto es la fuente de la mala asignación.

### 3.1 Las cuotas del IMSS: qué son

Cuando un patrón contrata formalmente en México, además del salario paga contribuciones a la seguridad social sobre el **Salario Base de Cotización (SBC)**. Las ramas (Ley del Seguro Social) son:

| Rama | Quién paga | Notas |
|---|---|---|
| **Enfermedades y Maternidad** | Patrón + trabajador | Incluye una **cuota fija patronal** indexada a la UMA por trabajador, más componentes proporcionales sobre el excedente del SBC respecto a 3 UMA |
| **Invalidez y Vida** | Patrón + trabajador | Tasas proporcionales |
| **Riesgos de Trabajo** | Patrón | **Variable por prima de riesgo de la firma** (rango amplio según clase de riesgo) |
| **Retiro, Cesantía y Vejez (RCV)** | Patrón + trabajador | La **reforma de pensiones 2020** subió la aportación patronal de Cesantía y Vejez de forma **gradual y escalonada por nivel salarial**, con incrementos anuales hasta 2030 |
| **Guarderías y Prestaciones Sociales** | Patrón | Tasa proporcional |
| **INFONAVIT** | Patrón | Vivienda |

**Orden de magnitud:** el costo no salarial patronal ronda el **25–35% del salario**, y la carga total (patrón + trabajador) supera el 30%. **No cites números precisos sin verificar las tablas vigentes** — la reforma 2020 introdujo un calendario escalonado que sigue subiendo hasta 2030, así que la τ de 1990 no es la de 2020. Fuente primaria: LSS y las tablas de cuotas publicadas por el IMSS.

### 3.2 Pero τ ≠ tasa de contribución (el punto de Levy)

Esto es crucial y es donde la literatura mexicana se juega el argumento. Si los trabajadores **valoraran plenamente** las prestaciones que reciben a cambio, la contribución sería un **precio por un servicio**, no un impuesto — y no habría cuña ni mala asignación. Levy [2] argumenta que no es así, por dos razones que se suman:

$$\tau \;=\; \underbrace{c_F\,(1-\beta)}_{\substack{\text{contribución formal no valorada}\\ \beta\,=\,\text{valoración del trabajador}}} \;+\; \underbrace{s_I}_{\substack{\text{subsidio implícito}\\ \text{a la informalidad}}}$$

- **Primer término:** los trabajadores valoran las prestaciones en menos que su costo (β < 1) → la parte no valorada es un impuesto puro al empleo formal.
- **Segundo término:** los programas **no contributivos** (Seguro Popular → IMSS-Bienestar, Pensión para Adultos Mayores) entregan beneficios *sin exigir formalidad*. Eso es un **subsidio implícito a permanecer informal** y amplía la cuña por el otro lado.

Este es el corazón de *Good Intentions, Bad Outcomes* y de *Under-Rewarded Efforts*. Para tu tesis significa: **τ tiene un componente institucional medible (c_F) y un componente que debes calibrar o citar (β, s_I)**. Reporta resultados bajo un rango de β, no bajo un punto.

### 3.3 El regalo: τ varía espacialmente sin que hagas nada

Este es el hallazgo más útil de esta sesión para tu diseño.

La estructura de cuotas **no es proporcional**: tiene una **cuota fija por trabajador** (Enfermedades y Maternidad) y componentes atados a múltiplos de la **UMA**, además de topes. Consecuencia aritmética directa:

> **La cuña efectiva como fracción del salario es más alta en mercados de salario bajo.** Un componente fijo pesa más sobre un salario pequeño.

Es decir: los mercados del **sur** enfrentan una τ efectiva **mayor** que los del **norte**, puramente por la interacción entre la estructura de cuotas y la distribución salarial local. Y la distribución salarial por mercado **sí está en el cubo agregado**.

Implicaciones:
1. Puedes construir **τ_l para los 777 mercados** sin datos adicionales, solo cruzando las tablas de cuotas con la distribución salarial local.
2. Esa variación es **mecánica e institucional**, no conductual → mucho más defendible que un instrumento.
3. Refuerza el ángulo de mercados locales: la cuña *no es nacional*, y esa es una afirmación que ningún paper de la literatura ha explotado.
4. El subsidio implícito s_I también varía espacialmente (cobertura de programas no contributivos por municipio, vía CONEVAL) → segunda fuente de variación.

**Este es probablemente el activo más original de la tesis.** Vale la pena verificarlo numéricamente antes de comprometerse, pero si sobrevive, es el argumento central.

---

## 4. ¿Alcanza con ε_D + ε_S para calibrar?

Respuesta corta: **para el bloque laboral sí; para todo lo demás no.**

| Insumo | ¿Lo tienes? | Fuente |
|---|---|---|
| ε_S (oferta laboral) | ✅ | Companion Aldeco/EconLab (Bartik) |
| ε_D (demanda laboral) | 🔨 tu estimación | 777 mercados, ruta estructural (Raval) |
| Participaciones sectoriales F/I por mercado | ✅ | Proxy censal, cubo agregado |
| Participaciones factoriales | ✅ | Censo / cuentas nacionales |
| **Cuña τ_l** | 🔨 construible | Tablas IMSS + distribución salarial local (§3) |
| Valoración β de prestaciones | ⚠️ calibrar | Literatura (Levy); reportar rango |
| PTF sectorial A_F, A_I | ❌ | Censos Económicos — fuera del cubo |
| Margen de entrada de firmas | ❌ | Fuera de alcance; asúmelo cerrado |
| Acumulación de capital | ❌ | Fuera de alcance; K fijo o perfectamente móvil |

**Veredicto:** ε_D + ε_S + participaciones + τ = suficiente para un ejercicio estático de **eficiencia asignativa del trabajo**. Insuficiente para capital, entrada de firmas o dinámica de PTF.

Eso es una tesis de maestría bien delimitada, **con una condición**: tienes que decir explícitamente, en la página 1, que mides **un canal** y no explicas el estancamiento completo. Si sobrevendes, el referee te compara contra Alvarez & Ruane [4] y pierdes.

---

## 5. ¿Sirve el cubo agregado para la propuesta arriesgada?

**Respuesta: te lleva ~80% del camino y se atora en una variable específica.**

### 5.1 Lo que el cubo agregado SÍ te da

Según la documentación de Aldeco et al. (2024), la base agregada a mercado local trae: empleo, salarios, composición demográfica/educativa, **% de empleo informal** (total/hombres/mujeres), pobreza, vulnerabilidad y **shocks Bartik**, para 1990–2020 en 777 mercados. De ahí sale directo:

- **L_F,l y L_I,l** (empleo formal e informal por mercado) = empleo × share de informalidad ✅
- **Participaciones y composición** ✅
- **Distribución salarial local** → insumo para construir τ_l ✅
- **Bartik** para la capa reduced-form ✅

### 5.2 Dónde se atora: el salario por condición de informalidad

El cubo reporta **salarios** y **share de informalidad** como variables *separadas*. No reporta —hasta donde documenta el paper— **el salario medio formal y el salario medio informal por mercado**. Y esa es precisamente la variable que necesitas: sin el gap salarial F/I por mercado, no hay brecha de PMg, y sin brecha de PMg no hay mala asignación que medir.

**Esto ya estaba anticipado en tu propio memo de viabilidad** (Anexo A.1, punto 1): *"El proxy censal de informalidad permite partir el empleo y computar salario medio formal/informal por mercado"*. La palabra clave es **computar** — hay que construirlo, no está servido.

### 5.3 La solución (no es bloqueante)

Bajas al **microdato individual censal**, que también es público en SIDIE y **ya trae el identificador de mercado local**. Con eso computas w_F,l y w_I,l tú mismo, y de paso ganas la capacidad de construir salarios residuales (controlando por educación, edad, sexo), que es lo que realmente necesitas para no confundir composición con precio.

**Costo:** trabajo de procesamiento, no acceso. Los códigos Stata del equipo están publicados, así que hay andamiaje.

### 5.4 Lo que el cubo NO te dará nunca

Producto, capital, o cualquier cosa a nivel firma. Si quieres A_F y A_I (productividad sectorial), necesitas **Censos Económicos** — que no se agregan al mercado local con la misma limpieza porque son de establecimientos, no de residencia. **Recomendación: no vayas por ahí en la maestría.** Trabaja el lado laboral y toma la productividad como residuo o como calibración externa.

---

## 6. Comparación: propuesta original (A) vs. brecha de producto (B)

### 6.1 Lado a lado

| Dimensión | **A — Estimar ε_D local** | **B — Brecha de producto / mala asignación** |
|---|---|---|
| **Pregunta** | ¿Cuánto vale la elasticidad de demanda de trabajo en los mercados locales de México? | ¿Cuánto del rezago de producto por trabajador se explica por mala asignación laboral F/I dentro de mercados locales? |
| **Objeto final** | Un parámetro (vector de 777) | Un contrafactual de política |
| **Rol de ε_D** | Es el producto | Es el insumo que escala la respuesta |
| **Interés económico** | ⚠️ Bajo por sí solo — "¿y qué?" | ✅ Alto — conecta con el debate central de la economía mexicana |
| **Datos** | Cubo agregado ✅ | Cubo + microdato individual + tablas IMSS |
| **Riesgo de identificación** | Alto (V3: exclusión del instrumento migratorio) | Igual de alto — **lo hereda completo** |
| **Competencia** | Estrecha: el companion del EconLab | Amplia: Levy, Leal-Ordóñez, Alvarez-Ruane, Antón-Leal, Dix-Carneiro |
| **Riesgo de scooping** | ⚠️ Alto (mismo equipo, mismos datos) | ✅ Bajo |
| **Novedad defendible** | "Nadie ha estimado la demanda con esta base" | "Nadie ha medido la mala asignación con elasticidades **estimadas** y cuña **espacialmente variable**" |
| **Alcance** | ✅ Cabe en una maestría | ⚠️ Se pasa si incluyes producción/capital |
| **Si falla** | Queda un parámetro sin narrativa | Queda A intacto |

### 6.2 El punto estratégico que cambia la decisión

**B contiene a A.** No puedes hacer el ejercicio de mala asignación sin estimar ε_D primero. Por tanto:

- Elegir A no te ahorra el trabajo de B; te ahorra **un capítulo**.
- Elegir B te obliga a hacer A de todos modos.
- **No estás eligiendo entre dos proyectos. Estás eligiendo dónde parar.**

Eso reduce el riesgo de B casi a cero en términos de viabilidad: si la calibración macro decepciona o no da tiempo, **te quedas con A completa y defendible**. Es exactamente la misma filosofía de "diseño graduado" que ya adoptaste para el acceso a IMSS.

### 6.3 Recomendación

**Núcleo A, remate B. Vender por B.**

```
Cap. 1-2   Marco + datos (777 mercados, cuña τ_l institucional)
Cap. 3     [A] Estimación de ε_D local + heterogeneidad espacial   ← el core verificable
Cap. 4     [B] Agregación à la Baqaee-Farhi: eficiencia asignativa   ← el payoff
           en 1990/2000/2010/2020 + contrafactual de remover τ
Cap. 5     Robustez: capa espacial, rangos de β y σ, validación ENOE
```

Enmarca la tesis con la pregunta de B (es lo que hace que alguien la lea) pero entrega el resultado de A como el núcleo verificado. Si el capítulo 4 da números chicos, ese *es* el resultado —y es publicable— siempre que lo presentes como "la reasignación laboral pura explica poco; el estancamiento está en otros márgenes".

---

## 7. Riesgos nuevos que introduce el giro

### R1 — Alvarez & Ruane (2024, EER) puede matar la premisa. **[SEVERIDAD ALTA]**
Con censos mexicanos encuentran que *"los factores más importantes para la caída de la productividad agregada no fueron impulsores importantes del aumento de la informalidad, y viceversa"* [4]. **Desacoplan informalidad y PTF en México.** Si tu tesis asume informalidad → estancamiento, este paper es el referee que te hunde.
> **Acción:** léelo **primero**. Es la lectura que decide si el giro sobrevive. Posiciónate explícitamente: tu objeto es la asignación *laboral entre sectores dentro de mercados locales*, no la composición firma-nivel que ellos estudian.

### R2 — Si la informalidad es voluntaria, no hay mala asignación. **[ALTA]**
**Alcaraz, Chiquiar et al. (2015)** [5] —*el mismo Chiquiar de tu base de datos*— estiman que solo **10–20%** de los informales mexicanos preferirían un empleo formal. Duval-Hernández (2022) [6], con un módulo especial de la ENOE 2015, obtiene ~80% en sentido contrario. Si la informalidad es voluntaria, el gap salarial **no es** un gap de PMg (hay diferenciales compensatorios y selección) y la mala asignación se evapora.
> **Acción — y es una oportunidad:** usa el 10–20% de Alcaraz-Chiquiar para **calibrar el grado de segmentación** en vez de asumirlo. Citar al equipo de Banxico para disciplinar tu propio parámetro es elegante, honesto, y blinda el flanco. Reporta el contrafactual bajo ambos extremos (10% y 80%).

### R3 — Los números van a salir chicos. **[MEDIA · casi segura]**
Con |ε_D| ≈ 0.25–0.7 y triángulos de Harberger, la reasignación laboral pura probablemente dé ganancias de un dígito. Leal-Ordóñez [7] llega a 19–34%, pero eso incluye capital, entrada y competencia monopolística.
> **Acción:** anticipa el resultado modesto en el diseño y enmárcalo como hallazgo, no como fracaso. Baqaee-Farhi [3] te da el lenguaje para decir "esto es el componente asignativo; el resto es técnico".

### R4 — Antón & Leal (2021) ya hizo algo muy parecido. **[MEDIA-ALTA]**
Tienen un **GE estático de elección ocupacional con cuñas laborales detalladas, calibrado a México** [12]. Es tu plantilla más cercana **y** tu competidor más cercano.
> **Acción:** léelo antes de escribir una línea de modelo. Tu diferenciador tiene que ser explícito: ellos son nacionales con cuña uniforme; tú eres **local con cuña espacialmente variable y elasticidades estimadas**.

### R5 — El sobre-alcance empeora (V8 de la crítica anterior). **[MEDIA]**
> **Acción:** la estructura de §6.3 es la mitigación. Capital y entrada de firmas quedan fuera, explícitamente, en la página 1.

---

## 8. Próximos pasos

**Esta semana (orden estricto):**
1. **Alvarez & Ruane (2024)** [4] — decide si la premisa sobrevive. Todo lo demás depende de esto.
2. **Baqaee & Farhi** [3] — tu marco de agregación y la salida al problema estático/crecimiento.
3. **Antón & Leal (2021)** [12] — tu plantilla y tu competidor.
4. **Alcaraz, Chiquiar et al. (2015)** [5] — el parámetro de segmentación.

**En paralelo (no requiere leer nada):**
5. **Verificar numéricamente §3.3:** bajar las tablas de cuotas IMSS vigentes y de un par de años anteriores, cruzarlas con la distribución salarial de dos o tres mercados contrastantes (p. ej. Monterrey vs. un mercado de Chiapas) y confirmar que la τ efectiva difiere materialmente. **Si esto sobrevive, es el corazón de la tesis.**
6. **Inventariar el cubo agregado** y confirmar si trae o no el salario por condición de informalidad (§5.2). Determina cuánto microdato tienes que procesar.
7. **Correo al EconLab** (econlab@banxico.org.mx) — sigue pendiente y ahora es más fácil: pides el mimeo de oferta sin competir con ellos.

**Pendientes heredados que este giro NO resuelve:**
- V3 (exclusión del instrumento migratorio) — se hereda completo.
- V6 (endogeneidad del W espacial, inferencia AKM) — vive si conservas la capa espacial.
- Correr el agente `critic` completo cuando se restaure el presupuesto.

---

## 9. Referencias

[1] [Why Isn't Mexico Rich?](https://consensus.app/papers/details/f620d95ebd9a59748b1e892d4a0bec8a/?utm_source=claude_desktop) — Hanson (2010), *Journal of Economic Literature*, 155 citas. *El survey que enmarca la pregunta.*
[2] [Under-Rewarded Efforts: The Elusive Quest for Prosperity in Mexico](https://consensus.app/papers/details/d70ed405e4815b84b1495ca8f9252b48/?utm_source=claude_desktop) — Levy (2018), 59 citas. *Y su antecesor* [Good Intentions, Bad Outcomes](https://consensus.app/papers/details/b2cc19b610d15e58baa26021a064e3f1/?utm_source=claude_desktop) *(2008, 547 citas) — origen del argumento de la cuña τ.*
[3] [Productivity and Misallocation in General Equilibrium](https://consensus.app/papers/details/314b4f322d46510c90fa5ff421e218d9/?utm_source=claude_desktop) — Baqaee & Farhi (2017), *QJE*, 509 citas. **Tu marco de agregación.**
[4] [Informality and aggregate productivity: The case of Mexico](https://consensus.app/papers/details/c078916d1c2452ae8f4ad3455d4a46a6/?utm_source=claude_desktop) — Alvarez & Ruane (2024), *European Economic Review*. **La amenaza principal.**
[5] [Informality and Segmentation in the Mexican Labor Market](https://consensus.app/papers/details/756472845f175c74899589bcc88e8db7/?utm_source=claude_desktop) — Alcaraz, Chiquiar et al. (2015), 42 citas. *10–20% de informalidad involuntaria.*
[6] [Choices and Constraints: The Nature of Informal Employment in Urban Mexico](https://consensus.app/papers/details/2bd8fc2ec3ba57d0875e64d16a0e72ba/?utm_source=claude_desktop) — Duval-Hernández (2022), *Journal of Development Studies*, 12 citas. *El contrapunto: ~80%.*
[7] [Tax collection, the informal sector, and productivity](https://consensus.app/papers/details/bb58f06e3c245bd5a6a8a2e5e1d98ceb/?utm_source=claude_desktop) — Leal-Ordóñez (2014), *Review of Economic Dynamics*, 110 citas. *Ganancias de 19–34%.*
[8] [The Drivers and Consequences of Resource Misallocation: Variation across Mexican Industries and States](https://consensus.app/papers/details/b43501f36f855522bbb2a60b0094df27/?utm_source=claude_desktop) — Misch et al. (2020), *Economía*. *La versión estatal de tu ejercicio.*
[9] [Spatial Misallocation, Informality, and Transit Improvements: Evidence from Mexico City](https://consensus.app/papers/details/9cd08b89b4ca52ce96d406f7b4d4122a/?utm_source=claude_desktop) — Zárate (2022), 31 citas. *Espacial + informalidad + misallocation, CDMX.*
[10] [(In)Formal and (Un)Productive: The Productivity Costs of Excessive Informality in Mexico](https://consensus.app/papers/details/56f348c559e05e309ba7c639f22bb4e3/?utm_source=claude_desktop) — Busso, Fazio & Levy (2012), 137 citas.
[11] [Dysfunctional Firm Dynamics and Mexico's Dismal Productivity Performance](https://consensus.app/papers/details/a8a1103e37f95f30bf58713a79149922/?utm_source=claude_desktop) — Fentanes et al. (2024), *Economía*.
[12] [Taxing Labor Income in an Economy with High Employment Informality](https://consensus.app/papers/details/5474feffa5995a6f88e78274d6a7a112/?utm_source=claude_desktop) — Antón & Leal (2021), *Economía*. **GE estático con cuñas, calibrado a México. Plantilla y competidor.**
[13] [Trade and Domestic Distortions: The Case of Informality](https://consensus.app/papers/details/e18d6d3b082950668dccae187017c32b/?utm_source=claude_desktop) — Dix-Carneiro et al. (2026), *Econometrica*.

**Fuente institucional (no académica):** Ley del Seguro Social y tablas de cuotas obrero-patronales del IMSS; reforma de pensiones 2020 (calendario escalonado de Cesantía y Vejez hasta 2030). Verificar directamente — las tasas cambian por año y por nivel salarial.

---

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]]. Documentos hermanos: `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md`, `../../critique/elasticidad_demanda_local_critique_2026-07-22.md`.*
