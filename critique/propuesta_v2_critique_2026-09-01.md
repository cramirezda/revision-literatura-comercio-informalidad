# Crítica referee — PROPUESTA v2: elasticidad de demanda de trabajo en mercados laborales locales de México

**Fecha:** 2026-09-01
**Documento evaluado:** `propuesta_final/docs/PROPUESTA_v2_2026-09-01.md`
**Contexto leído:** `CUADERNO_EXPLORACION_2026-09-01.md` · `inventario_datos_EconLab_LLM_2026-09-01.md`
**Modelo crítico:** claude-opus-5
**Biblioteca metodológica de referencia:** `propuesta_final/docs/elasticidad_demanda_bibliografia_2026-07-22.md` (36 fuentes)
**Antecedentes:** `critique/elasticidad_demanda_local_critique_2026-07-22.md` (V1–V8) · `critique/puente_macrodinamica_critique_2026-08-09.md` (V9–V15)

> **Modo y calibración.** Corrida no interactiva (subagente): **se omite el diálogo socrático**. Donde el formato pide "respuesta del autor", se evalúa en su lugar **la defensa anticipada que el propio documento ofrece**, que es más exigente y más útil. El estándar aplicado es "¿sobrevive a un sínodo del ITAM y produce un número defendible en ~4 meses?", no "¿entra al AER". Las objeciones que abajo se marcan como **[BLOQUEANTE]** son las que, si no se atienden antes de S4, hacen que el número que salga no sea interpretable.

---

## 1. Resumen del trabajo

La propuesta estima la pendiente de la curva de demanda de trabajo local, ε_D ≡ −∂ln L/∂ln w, mediante 2SLS sobre diferencias largas entre los 777 mercados laborales locales de México (base EconLab/Banxico, olas censales 1990–2020), instrumentando Δln L con un shift-share de enclaves de migración **interna**: la exposición del mercado *l* al empuje nacional de salida de cada estado de origen *o*, pesada por los shares de lugar de nacimiento de 1990 (excluyendo el estado propio). La contribución declarada es entregar "la mitad faltante" de un par de elasticidades —la base publicada trae choques Bartik de demanda, que identifican **oferta**, y el mimeo companion de Banxico ya estima ε_S— para predecir la incidencia salario/empleo de una política. La versión v2 corrige el claim de "casilla vacía" (encuentra a Mishra 2007 y Hanson 2005 como antecedentes mexicanos), verifica varias preguntas de datos contra los `.dta` reales, y abre dos ramas de política: **A** (simulación ex-ante de incidencia con ε_D propia + ε_S ajena) y **B** (evaluación ex-post del salario mínimo 2016–2020, con validación fuera de muestra de ε_D).

**Lo que hay que reconocer antes de atacar.** La v2 es materialmente más fuerte que la v1 y que el puente de agosto. Cinco cosas son trabajo real y bien hecho: (i) la autocorrección del claim de novedad, que es exactamente lo que un autor honesto hace y casi nadie hace; (ii) la verificación de que `EmpleoTot_MTL` en `_Trade0/_Trade1` es sectorial, que convierte el diseño de tres columnas en un día de trabajo; (iii) el hallazgo de que `LLAVE_EXPORTADORA` es una clasificación de *exportabilidad*, no de *no transabilidad*, encontrado leyendo el catálogo y no dando por buena la herencia; (iv) el descubrimiento de `CAT_INGRESOS` 4/5, que vuelve medible lo que era una amenaza; (v) la corrección de que el diseño DSS pertenece al nivel municipio-dentro-de-mercado y no al nivel mercado, que es una observación fina y correcta sobre la construcción de la partición. Nada de lo que sigue debe leerse como si la propuesta estuviera en el mismo lugar que hace seis semanas. No lo está.

---

## 2. Mapa de vulnerabilidades

| Dimensión | Dominio | Exposición | Racional en una línea |
|---|---|---|---|
| **Instrumento débil / pocos shocks efectivos** | Inferencia | **ALTA** | K=32 orígenes, ~6 expulsores dominan; la expansión a 192 celdas no crea shocks nuevos; el umbral "F≥10" usa el error estándar equivocado |
| **Restricción de exclusión (objeción de Hanson)** | Identificación | **ALTA** | La respuesta 1 ("otro objeto: destino, no origen") no corta el canal causal; la respuesta 3 (residualizar) puede ser un *bad control* |
| **Error de medición no clásico / mercados chicos** | Datos | **ALTA** | La ola 2010 es endpoint de dos diferencias contiguas ⇒ artefacto de reversión a la media con el **signo que la tesis busca**, concentrado en los 279 mercados unimunicipales |
| **Sobreidentificación "gratis" (§5 Rama A)** | Especificación | **ALTA** | El sistema es **exactamente identificado** una vez que se admite que la escala del Bartik es desconocida: no hay prueba; el "test" propuesto rechaza sí y solo sí λ≠1 |
| **Mecanismo: el corte transable como *prueba*** | Canales | **ALTA** | Los dos errores de la bandera de la casa apuntan al **mismo lado** (achican la brecha); y bajo insensibilidad de precios de factores la predicción se invierte ⇒ el signo del contraste es teóricamente ambiguo |
| **Estimando / validez externa (exclusión del estado propio)** | Validez | **ALTA** | Tras excluir el estado propio, el complier es el mercado urbano-destino de migración de larga distancia; los 279 mercados rurales (36%) no identifican nada |
| **Alcance (Rama B)** | Especificación | **ALTA** | 4–6 semanas sobre un plan de 4 semanas cuyo núcleo aún no corre; reproduce V15 |
| **Ancla numérica 3–10** | Literatura | **MEDIA-ALTA** | Sin fuente en la biblioteca; la mitad superior de la banda es el recíproco de no-rechazos; e invertir β para reportar ε_D rompe la inferencia bajo instrumento débil |
| **Inferencia: conjuntos de confianza** | Inferencia | **MEDIA-ALTA** | ε_D = −1/β; con β̂ cerca de cero el intervalo es no acotado y disconexo (Fieller/Dufour). No hay mención de Anderson-Rubin en ninguna parte |
| **Controles / *bad controls*** | Especificación | **MEDIA-ALTA** | `ResIngresoEE` residualiza por educación, que es **post-tratamiento** respecto del choque migratorio; y el objeto declarado es la demanda de trabajo *total* |
| **Concordancia de estimandos (ε_D + ε_S)** | Validez | **MEDIA-ALTA** | V14 nunca se cerró y ahora es el supuesto que carga toda la Rama A |
| **Deflactor espacial ausente** | Datos | **MEDIA-ALTA** | El sesgo **no es neutro en signo**: apunta hacia la banda pre-registrada |
| **Pre-tendencias / placebo** | Identificación | **MEDIA-ALTA** | El único test que responde directamente a Hanson está condicionado a S0, que sigue abierto |
| **SUTVA / derrames** | Identificación | MEDIA | Desplazamiento de nativos y exposición de vecinos están nombrados; la movilidad de capital entre mercados no la aísla ningún test propuesto |
| **Cobertura y muestra (ola 2015)** | Datos | MEDIA | Como endpoint de dos diferencias, la Intercensal es peor que "una ola de robustez" |
| **Selección del conjunto de orígenes** | Micro/control | MEDIA | 50 mercados cruzan fronteras estatales ⇒ la regla de exclusión no es homogénea entre unidades |
| **Multiplicidad de pruebas** | Inferencia | MEDIA | 8 especificaciones × 2 banderas × 2 ventanas × cortes demográficos, con una banda objetivo pre-anunciada |
| **Scooping (R6/V4)** | Literatura | MEDIA | Abierto desde 2026-07-22; fn. 18 dice que el equipo ya tiene los módulos de migración en su hoja de ruta |
| **Forma funcional** | Especificación | BAJA-MEDIA | Diferencias largas log-log es lo estándar; sin discusión de no linealidad, pero no es de primer orden aquí |
| **Alternativas metodológicas ignoradas** | Literatura | BAJA-MEDIA | Cadena-Kovak (2016) está en la biblioteca y contradice el supuesto que la Rama A necesita; no se cita en §5 |
| **Construcción del grupo de control** | Micro | BAJA | No hay grupo de control: es variación continua de exposición. No aplica |
| **Tratamiento escalonado (CS/SA)** | Micro | BAJA | No es un DiD escalonado. Correctamente fuera |
| **No estacionariedad / rezagos / VAR** | Macro | BAJA | No aplica |
| **Identificación estructural (SVAR/DSGE)** | Macro | BAJA | Congelado con el Ensayo 2. Correcto |

**Las cinco de mayor exposición, en orden:** error de medición no clásico → la prueba de sobreidentificación (error algebraico) → la objeción de Hanson → el corte transable como prueba → pocos shocks efectivos. La Rama B y el ancla 3–10 vienen inmediatamente después.

---

## 3. Estatus de V1–V15 — qué está cerrado, qué no, y qué el autor *cree* cerrado

El §7 de la propuesta lista R1–R7 vivas y declara V1, V3 cerradas y V5, V10, V12, V13 "cerradas por alcance". **V2, V4, V6, V7, V8, V11, V14 y V15 no aparecen en la tabla en ninguna forma.** Ese silencio no es neutro: tres de ellas están vivas y una de ellas es hoy el supuesto que carga el argumento de relevancia.

### Genuinamente cerradas
- **V1 — objeto ambiguo vs. MRRH.** ✅ **Cerrada, y bien.** §1 pone la respuesta en la página 1 con el argumento correcto: MRRH reportan una elasticidad de empleo local *de equilibrio* de la que ε_D es un insumo. Es un error de categoría presentarlas como rivales, y la propuesta lo dice antes de que lo pregunten.
- **V2 — la ruta estructural *impone* ε_D en vez de estimarla.** ✅ **Cerrada** por el pivote a diseño empírico. Ya no hay CES ni σ calibrado en el núcleo. (No está listada; debería estarlo, porque su cierre es un logro.)
- **V5 — σ_FI no identificable con el censo.** ✅ Cerrada por alcance.
- **V6 — espacial (reflexión, W endógeno, inferencia).** ✅ Cerrada. El argumento del Bloque 6 (§2) de por qué AKM y SAR son respuestas incompatibles al mismo hecho es correcto y está bien escrito.
- **V12, V13 — ruteo de σ hacia Correia; informalidad como factor Z fijo.** ✅ Cerradas por el congelamiento del Ensayo 2.
- **V7 (mitad de informalidad)** — el proxy de informalidad sale del núcleo. ✅

### Abiertas y correctamente identificadas por el autor
- **R1 = instrumento débil.** Abierta, es el go/no-go. Pero el criterio propuesto es el equivocado (§4.1 abajo).
- **R2 = objeción de Hanson.** Abierta. Las cuatro respuestas son desiguales (§4.2).
- **R3 = bandera transable.** Abierta con solución parcial (§4.4).
- **R4 = error de medición.** Abierta, pero **subvalorada de robustez a amenaza de primer orden** (§5.3).
- **R5 = S0 / `RES5A` en 1990.** Abierta. Bloquea más de lo que el documento reconoce.
- **R7 = deflactor espacial.** Abierta, con el sesgo mal caracterizado como neutro (§6).

### El autor cree que están cerradas, y no lo están

- **V3 — remesas contaminan el destino. ⚠️ PARCIAL, no cerrada.** El §7 la declara cerrada porque "ahora son medibles". **Medible ≠ neutralizada**, y además la medición contesta otra pregunta. V3 era: *el desplazador de oferta también desplaza la demanda local de no transables*. Lo que `LLAVE_INGRESO` 4/5 permite medir es el **flujo de remesas**, que es un desplazador de demanda de *otra* fuente. El canal que V3 nombraba —el migrante interno que llega y **gasta donde vive**— no genera ninguna remesa y por lo tanto es invisible a `CAT_INGRESOS`. La prueba propuesta ("las remesas internas fluyen al origen, no al destino") valida un supuesto distinto y más débil. El canal de consumo del migrante interno sigue sin neutralizar; su tratamiento real es el corte sectorial (que tiene su propio problema, §4.4) y el diseño de conmutantes (que sí lo neutraliza por diseño). **Reclasificar como parcialmente resuelta.**

- **V4 = R6 — scooping. ⚠️ ABIERTA Y SIN MITIGAR, seis semanas.** La acción es un correo. Está pendiente desde 2026-07-22 y la razón declarada para no mandarlo ("decidir antes si preguntar previene o invita el scooping") ha consumido más tiempo del que costaría el correo. Mientras tanto la fn. 18 dice, textual, que los módulos de migración están *"within project's scope in the next stage"* — es decir, el equipo que construyó la base y que incluye a Hanson tiene tu instrumento en su hoja de ruta declarada. Es el ítem abierto más barato de todo el proyecto y el único cuyo costo de espera crece de forma monótona.

- **V7 (mitad de frecuencia/potencia). ⚠️ NO CERRADA, y es más grave de lo que parece.** El cálculo de potencia sigue listado como pendiente (inventario §12, ítem 6) y no aparece en ninguna parte de la propuesta. Y el problema no es N: es que **N no es 1,554**. Adão-Kolesár-Morales (2019) muestran que en un diseño shift-share la unidad efectiva de inferencia es el *shock*, no la observación; con ~6 orígenes de peso alto, la N relevante para los errores estándar está entre 6 y 32, no en 1,554. La propuesta reconoce la corrección AKM como un ítem de la lista de §4.4, pero no ha extraído su consecuencia: **el tamaño de muestra efectivo de esta tesis es de un dígito.** Eso cambia lo que se puede afirmar, cambia el criterio de la primera etapa y cambia qué robusteces tienen sentido.

- **V8 / V11 — sobre-alcance. ⚠️ REABIERTA por §5 Rama B.** El recorte se congeló el 2026-08-09 con un plan de 4 semanas. La Rama B añade 4–6 semanas y una segunda identificación, y la propia propuesta lo admite en la tabla comparativa ("¿cabe en el alcance congelado? No"). Que esté honestamente etiquetada no la vuelve inocua: la sección existe, está desarrollada, y ya consumió esfuerzo de diseño.

- **V10 — el estimando no es un parámetro tecnológico. ⚠️ NO CERRADA; migró de dueño.** Está listada como "cerrada por alcance" junto con V12/V13, y es cierto que congelar el Ensayo 2 elimina la necesidad de mapear ε_D → σ. Pero V10 no era sobre σ: era sobre **qué se mantiene fijo y a qué horizonte** en el objeto que se estima. Ese problema sigue vivo en dos lugares nuevos: (i) en §4.5(c) la propuesta declara que la entrada de capital y de empresas "*es* la definición de la elasticidad local de largo plazo" —lo cual es una declaración, no una identificación: no hay ninguna prueba propuesta que separe curvatura tecnológica de movilidad de capital; y (ii) en la Rama A, sumar ε_D + ε_S exige que ambas sean las dos caras del mismo mercado al mismo horizonte. **La recomendación de agosto —escribir el estimando en una página— sigue sin ejecutarse, y ahora tiene un consumidor distinto (la aritmética de incidencia) en vez del que tenía (el modelo de Ramsey).**

- **V14 — combinar tu ε_D con la ε_S del mimeo exige objetos alineados. ⚠️ ABIERTA, y ascendida sin ser resuelta.** En agosto era una objeción periférica a una "dualidad" retórica. Hoy **es el supuesto sobre el que descansa toda la Rama A**, que el §0 promovió a "el mensaje de política sube al centro". Un objeto que era decorativo se volvió portante sin pasar por ninguna verificación. Los requisitos son concretos y todos incontrolables desde este lado: mismos 777 mercados, mismas olas, misma longitud de diferencia, mismo concepto de salario (`LogSalario` vs `ResIngresoE` vs `ResIngresoEE`), mismo concepto de empleo, misma ponderación, mismos controles. Ver §5.2.

- **V15 — se optimiza la capa siguiente mientras la espina empírica está bloqueada. ⚠️ RECURRE, en traje nuevo.** El patrón de agosto era: diseñar el Ensayo 2 mientras Q3 llevaba dos semanas trabado. El patrón de hoy es: diseñar dos ramas de política y un menú de seis evaluaciones ex-post mientras **S0 sigue abierto y S4 no ha corrido**. El §8 de la propuesta lo pone bien —S0 es el paso 1— pero la distribución del documento no lo refleja: §5 (dos ramas de política, con menú fechado y contexto verificado del salario mínimo) es más larga y está más desarrollada que §4.4 (las pruebas de exogeneidad), que es donde se decide si hay tesis. **No es un problema de alcance: es de orden de ejecución, y es el mismo de hace tres semanas.**

**Ranking de peligro para el sínodo:**
V-nueva-1 (error de medición no clásico) > V-nueva-2 (la prueba de sobreidentificación no existe) > R2/V-Hanson > V-nueva-3 (el corte transable no es una prueba) > R1 > V14 > V10 > V8/V11 (Rama B) > V15 > V7-potencia > V4.

---

## 4. Los cinco costurones nuevos

### 4.1 Instrumento débil con 32 orígenes: ¿las 192 celdas son un arreglo? **[BLOQUEANTE]**

- **Dimensión:** Inferencia — instrumento débil / número efectivo de shocks.
- **Pasaje:** §3.3(b) y §4.4. *"expandir el origen a **celdas** estado × sexo × grupo de educación (192), que es lo que hace Card (2001) con origen × ocupación"* y *"Si sale < 10, el régimen BHJ no es defendible con orígenes-estado y hay que ir a celdas."*
- **Anclaje:** Borusyak, Hull & Jaravel (2022, *REStud* 89(1)) — el número efectivo de shocks y el requisito de que los shocks sean *mutuamente poco correlacionados*; Goldsmith-Pinkham, Sorkin & Swift (2020, *AER* 110(8)) — pesos de Rotemberg; Adão, Kolesár & Morales (2019, *QJE* 134(4)) — la unidad efectiva de inferencia; Montiel Olea & Pflueger (2013) — la F efectiva bajo no homocedasticidad.

**Desafío.** La expansión a celdas es, en el mejor de los casos, neutral, y en el peor **empeora el diagnóstico sin mejorar la identificación**. Hay tres cosas que hay que separar y la propuesta las trata como una.

**(i) Si el shift no varía por celda, el instrumento es numéricamente idéntico.** Si g_ot es el empuje del estado *o* y se aplica el mismo a todas las celdas, entonces
Z_l = Σ_{o,s,e} s_ol^{(s,e)} · g_ot = Σ_o g_ot · [Σ_{s,e} s_ol^{(s,e)}] = Σ_o s_ol g_ot.
**El mismo instrumento, letra por letra.** Cero ganancia. Para que las celdas hagan algo, hay que construir g^{(s,e)}_ot — el empuje de salida de Chiapas *de hombres con primaria*, separado del de mujeres con secundaria. Eso es factible con `RES5A` × `SEXO` × `ESCOLARIDAD`, pero es una construcción distinta que la propuesta no ha especificado.

**(ii) Si el shift sí varía por celda, los 192 shocks no son 192 shocks.** El empuje masculino-baja-educación de Chiapas y el femenino-media-educación de Chiapas comparten un componente estatal común y grande. BHJ exigen shocks **mutuamente poco correlacionados**; el objeto correcto no es 1/Σŝ² sobre 192 celdas sino el número efectivo de **clusters independientes de shock**, que aquí sigue siendo el estado. La recomendación de errores estándar de BHJ es agrupar *a nivel shock*: con celdas anidadas en estados, ese nivel es el **estado**, no la celda. El número efectivo honesto no se mueve.

**(iii) Y el diagnóstico se ve mejor mientras la identificación no cambia — que es lo peligroso.** Partir un origen en 6 celdas parte su peso de Rotemberg α_o en 6 pedazos impulsados por el mismo choque subyacente. Un Herfindahl calculado sobre 192 α's dará una concentración **aparentemente** seis veces menor. Ese es un artefacto de contabilidad, no una mejora de diseño. Reportar el número efectivo de shocks sobre celdas sin reportarlo también sobre estados sería, involuntariamente, presentar un diagnóstico manipulado.

**(iv) Hay una inconsistencia interna entre §4.4 y §3.3(b).** §4.4 declara que **GPSS es el marco principal** *precisamente porque* K=32 es chico y "la identificación honestamente viene de la variación transversal de los shares". Correcto. Pero si GPSS es el marco, entonces el número efectivo de shocks **no es el diagnóstico vinculante** — el requisito vinculante es la exogeneidad de los shares de peso alto, que es exactamente la objeción de Hanson. Y las celdas **empujan hacia la vulnerabilidad**, no lejos de ella: pasar a celdas definidas por *educación* exige exogeneidad de shares de enclave por nivel educativo, que es literalmente el objeto que Hanson dice que está contaminado. **La salida propuesta para R1 agrava R2.**

**(v) El criterio "F ≥ 10" es el criterio equivocado, dos veces.** Primero, *qué* F: bajo un diseño shift-share los errores estándar convencionales sobre-rechazan (AKM 2019), y la F de primera etapa se construye con esos mismos errores estándar ⇒ **la F convencional está inflada por la misma razón que los t-statistics**. La F que vale es la calculada con errores estándar agrupados a nivel shock o con la corrección AKM, y va a ser sustancialmente menor. Segundo, *qué umbral*: el 10 de Stock-Yogo es para errores iid; bajo agrupamiento la referencia correcta es la **F efectiva de Montiel Olea-Pflueger** con sus propios valores críticos. Un go/no-go que se juega en un solo número tiene que jugarse en el número correcto.

**Lo que sí expandiría el espacio de shocks:** shares a nivel **municipio de origen** vía `MUNICIPIO_RES5A` (2,469 orígenes), que es la única de las tres salidas de §3.3(b) que genuinamente multiplica la variación — y que depende de S0. Eso hace de S0 algo más que una verificación de cobertura: es la bifurcación entre un diseño con muchos shocks y uno con seis.

**Defensa anticipada del documento y su evaluación.** El documento sí ordena calcular el número efectivo *antes* de escribir §4 y *antes* de S4 (§8 ítem 7; cuaderno §3). Es la secuencia correcta y hay que reconocerlo. Lo que falta es la conclusión: si sale por debajo de 5-10, la respuesta no es "ir a celdas", es **cambiar de régimen argumentativo** (asumir GPSS plenamente y defender los seis orígenes de peso alto uno por uno, que es honesto y hacible) o **cambiar de granularidad de origen** (municipio, vía S0).

**Veredicto: no resuelta.** La salida propuesta relabela la variación y mejora el diagnóstico sin mejorar la identificación.

---

### 4.2 La objeción de Hanson: ¿cuál de las cuatro respuestas carga peso? **[BLOQUEANTE]**

- **Dimensión:** Identificación — restricción de exclusión.
- **Pasaje:** §4.3, las cuatro respuestas.
- **Anclaje:** Hanson (2005, WP NBER); Jaeger, Ruist & Stuhler (2018, NBER WP 24285) — la versión moderna; Goldsmith-Pinkham, Sorkin & Swift (2020) — balance de shares de peso alto; Borusyak & Hull (2023, *Ecma* 91(6)) — recentrado; Chiquiar & Hanson (2005) — selección de migrantes mexicanos.

**Respuesta 1 — "el objeto no es el mismo: destino, no origen". Es un movimiento retórico, no una defensa.** Esta es la pregunta directa del encargo y la respuesta es: **no carga peso como está escrita.**

La exclusión que hace falta es E[s_ol · ε_l] = 0, donde ε_l es el residual de *crecimiento salarial del mercado destino l*. El mecanismo de Hanson —la oportunidad de emigrar moldea la acumulación de capital humano de quien nace en *o*— **se transporta al destino a través de la composición de la fuerza de trabajo del destino**. Un mercado con share alto de nacidos en *o* tiene una fuerza laboral cuya trayectoria de salarios difiere por razones que no tienen nada que ver con el choque de oferta. Eso *es* la violación. Cambiar de dónde está parado el individuo no rompe la cadena causal; solo cambia el punto de observación.

Peor: el diseño de destino es vulnerable a una versión **más fuerte** que la del origen. s_ol,1990 no es solo "el tamaño de la red": codifica también **la regla de selección** que gobernó quién de *o* fue a *l* en las décadas previas. Chiquiar & Hanson (2005) es precisamente sobre selección de migrantes mexicanos. Si la regla histórica de selección o→l correlaciona con la trayectoria salarial posterior de *l* (migración calificada hacia el Valle de México vs. no calificada hacia la frontera), la exclusión falla por un canal que nada tiene que ver con capital humano de origen. **La respuesta 3 (residualizar) concede implícitamente que la contaminación está en la muestra del destino; si no lo estuviera, no habría nada que residualizar.**

**Respuesta 2 — "es migración interna, no emigración". Parcialmente válida, y omite el problema que sí es grave.** El canal de Hanson pasa por el valor de opción de irse, no específicamente por el premio salarial estadounidense; y los diferenciales salariales regionales internos en México son grandes (Chiquiar 2008, en la biblioteca). Así que el canal se debilita, no se apaga. Pero el problema real es otro y no está en el documento: **los estados de alta emigración a EE.UU. y los estados de alta emigración interna son casi el mismo conjunto** (Zacatecas, Michoacán, Guanajuato, Jalisco, Guerrero, Oaxaca). Los shares del instrumento están, por lo tanto, **correlacionados con la exposición a la emigración internacional**, que es la variable sobre la que Hanson hace su afirmación. La objeción de Hanson contamina el diseño interno **por correlación**, no por analogía — y ninguna de las cuatro respuestas toca eso. Es además directamente testeable y barato: regresar los shares de peso alto contra la tasa estatal de emigración a EE.UU. Si cargan, la defensa "es otro fenómeno" es empíricamente falsa y hay que saberlo antes de escribirla.

**Respuesta 3 — "el salario está residualizado por edad y educación". Es la más débil y puede ser contraproducente.** Tres problemas:
1. Residualizar por *años* de escolaridad absorbe composición observable, no **calidad** de la escolaridad — que es exactamente lo que Hanson nombra en la cita textual (*"the quality of education the individual received as a youth"*). Mismos años, distinta calidad ⇒ la residualización no hace nada.
2. **Puede ser un *bad control*.** El choque migratorio cambia la composición educativa del mercado. Residualizar el salario contra educación contemporánea es condicionar sobre una variable **post-tratamiento**. El sesgo resultante no tiene signo obvio; no es "absorbe buena parte", es "introduce un sesgo de dirección desconocida".
3. **Es inconsistente con el objeto declarado.** §4.5(b) dice que el objeto es la demanda de trabajo **total**, y por eso la complementariedad no es sesgo. Pero entonces el precio relevante es el salario *promedio*, no el purgado de composición. Con L = headcount (`Empleada_T`) y w = salario ajustado por composición, β no es −1/ε_D de ninguna curva de demanda bien definida: numerador y denominador están medidos sobre conceptos de trabajo distintos. **Esto exige una decisión declarada:** o el objeto es la demanda de unidades de eficiencia (y entonces L también debe ajustarse), o es la demanda de headcount (y entonces el resultado principal debe correr con `LogSalario`, con `ResIngresoEE` como robustez). Correr los dos y reportar la diferencia es barato y convierte el problema en un resultado.

**Respuesta 4 — "es testeable, no una condena". Es la buena, y hay que apoyarse en ella — con tres advertencias.**
1. **Baja potencia.** Con ~6 orígenes efectivos, no rechazar es evidencia débil. Pre-comprometer qué cuenta como "pasar" y reportar **magnitudes de desbalance y el sesgo implícito**, no p-valores.
2. **El recentrado no es un ítem de menú.** §4.3 promete "recentrar (Borusyak-Hull 2023) si falla". El recentrado exige un **proceso contrafactual de asignación** que se pueda simular. Con shares de enclave de 1990 no hay una distribución de permutación natural. Recentrar un diseño GPSS de shares endógenos no es una salida disponible en un pie de página; hay que decir hoy cuál sería el proceso de asignación, o retirar la promesa.
3. **El balance en niveles no es la prueba correcta.** El mecanismo de Hanson genera **tendencias** diferenciales de capital humano. La prueba que responde a Hanson es el placebo de pre-tendencia (espec. 7) — y **está condicionado a S0**: si `RES5A` no está poblado en 1990, no hay shift para 1990→2000 y el placebo hay que rediseñarlo (el cuaderno lo admite en F11). **S0 no decide solo si hay una cuarta diferencia: decide si se puede correr la prueba que contesta la objeción principal de la tesis.** Eso hay que decirlo en §7 con esas palabras.

**Una quinta respuesta que falta y es barata.** JRS (2018) se descarta en el Bloque 6 ("con dos periodos no hay potencia") — razonable para el diseño de dos instrumentos completo. Pero la versión pobre sí cabe: **incluir el instrumento rezagado como control**, o construir el instrumento con shares contemporáneos (t−1) además de los de 1990 y mostrar que las estimaciones no divergen. Ataca directamente "los shares son persistentes y mezclan corto y largo plazo", cuesta una columna, y es lo que un referee que conoce JRS va a pedir.

**Veredicto: parcialmente atendida.** La estructura (sección propia, no pie de página) es correcta y hay que mantenerla. Pero la respuesta 1 no sostiene peso, la 3 puede hacer daño, y la 4 —la buena— depende de S0. **Reescribir §4.3 concediendo que el mecanismo también vive del lado del destino, y luego mostrando el trabajo empírico que lo acota**, es más fuerte y más creíble que la formulación actual. Un sinodal que conozca a Hanson va a leer la respuesta 1 como una esquiva.

---

### 4.3 Excluir el estado propio: ¿endogeneidad, estimando, o población no representativa?

- **Dimensión:** Validez externa / construcción del instrumento.
- **Pasaje:** §4.1 (*"Se excluye el estado propio del mercado"*) y inventario §9.1 (*"y probablemente también los contiguos"*).
- **Anclaje:** Card (2001, *JOLE*); Goldsmith-Pinkham, Sorkin & Swift (2020) — sobre qué se identifica y con qué peso; Imbens & Angrist (1994) — el estimando como promedio ponderado por compliers.

**Primero, lo que está bien: la decisión es correcta y necesaria.** No excluirlo es peor. Con shares propios de 70–90%, Z sería esencialmente g_{o(l),t} — el empuje nacional de salida del propio estado del mercado — que es función de las condiciones del propio destino (la gente sale de un estado porque le va mal). La crítica no es sobre la decisión; es sobre que **sus tres consecuencias no están cotizadas.**

**(a) ¿Reintroduce endogeneidad?** No en el sentido clásico —la regla de exclusión es geográfica, no depende de resultados— pero sí crea un problema de **comparabilidad entre unidades** que es real. Los **50 mercados que cruzan fronteras estatales** (inventario §2.1) no tienen un "estado propio" único. Cualquier regla que se elija (soltar el modal; soltar todos) hace que la **fracción de la población del mercado cubierta por los orígenes retenidos varíe sistemáticamente** con una característica del mercado (estar en una frontera estatal), que a su vez correlaciona con geografía económica. El instrumento deja de estar definido de la misma manera en todas las unidades.
→ *Fix concreto:* definir el conjunto de exclusión a nivel mercado (soltar todo estado que contenga alguno de los municipios del mercado), y **reportar mercado por mercado la fracción de población cubierta por los orígenes retenidos**. Si esa fracción vive entre 10% y 30% y covaría con características, hay que condicionar o ponderar por ella. Es una figura, y va en §5 de la tesis.

**(b) ¿Cambia el estimando? Sí, y esto es lo importante.** Tras la exclusión, Z mide exposición a migración **interestatal de larga distancia** exclusivamente. El estimando 2SLS es un promedio ponderado de elasticidades de demanda **con pesos de complier**: los mercados cuyo empleo responde a la llegada de migrantes de lejos. Por la F5 del cuaderno, ésos son frontera norte, Valle de México y polos turísticos. Los **279 mercados unimunicipales (36% de la muestra) no identifican prácticamente nada**, porque su enclave no-propio es delgado. Es decir: **ε_D no es "la elasticidad de demanda de los mercados laborales locales de México"; es la de los mercados urbanos receptores de migración de larga distancia.** Eso no invalida nada, pero cambia la frase de la conclusión y cambia el título de la tabla. Hay una conveniencia aquí que conviene explotar: la ponderación por empleo —que §3.5 propone por razones de error de medición— es también la ponderación **sustantivamente correcta**, porque alinea los pesos de la estimación con los pesos del complier. Ese es un argumento mejor que el que el documento da.

**(c) ¿Población de migrantes no representativa? Sí.** El tratamiento es ahora "llegada de migrantes internos de larga distancia", que están positivamente seleccionados respecto de los de corta distancia (lógica Roy estándar). Si ε_D difiere por calificación —que es lo que la propia T6 predice— el estimando también se mueve con la composición de calificación de los compliers. Combinado con el problema de `ResIngresoEE` de §4.2, se acumulan dos capas de ambigüedad sobre *de qué trabajo* es la demanda que se está trazando.

**(d) Advertencia sobre "y probablemente los contiguos".** Es un salto mucho mayor de lo que suena. La migración interna decae fuerte con la distancia; soltar propio + contiguos elimina el grueso de los flujos y deja como variación identificadora la migración de muy larga distancia: chica, y seleccionada de otra manera. **Aquí es donde el costurón 3 choca de frente con el costurón 1:** cada exclusión adicional reduce Var(Z), reduce la primera etapa, y concentra aún más los pesos de Rotemberg. No se puede decidir "contiguos sí o no" en el vacío: hay que reportar la F y el número efectivo de shocks **bajo las tres reglas** (todos los orígenes / sin propio / sin propio ni contiguos) en una sola tabla, y elegir con ese cuadro a la vista.

**(e) Una alternativa que domina la exclusión total,** y que conviene al menos reportar: conservar todos los orígenes en el instrumento pero **incluir el componente propio (s_{o(l)l} · g_{o(l)t}) como control** en vez de tirarlo. Preserva la lógica de exclusión, y la diferencia entre las dos versiones **te dice cuánta de la primera etapa era mecánica** — que es exactamente el número que un sinodal escéptico va a querer ver.

**Veredicto: decisión correcta, consecuencias sin cotizar.** Ninguna de las tres es fatal; las tres cambian lo que se puede afirmar.

---

### 4.4 El corte transable/no transable como *la prueba* del canal consumidor **[BLOQUEANTE para la interpretación]**

- **Dimensión:** Canales — identificación del mecanismo.
- **Pasaje:** §4.5 (*"El corte sectorial deja de ser robustez y pasa a ser **la prueba**"*) y §3.3(a).
- **Anclaje:** Hong & McLaren (2015) — el argumento de precios locales de no transables; Dustmann, Schönberg & Stuhler (2017, *QJE*) — la neutralización del canal de consumo por diseño; el teorema de insensibilidad de precios de factores / Rybczynski.

**Primero, verificar el signo, porque la propuesta lo tiene bien.** Con canal consumidor, la entrada de migrantes desplaza oferta *y* demanda de no transables ⇒ Δw cae menos ⇒ |β| menor ⇒ |ε_D| mayor. Sí: no transables debe salir más elástico. La predicción de F12 está bien derivada.

**Problema 1 — con la bandera de la casa, los dos errores apuntan al mismo lado, y ese lado es el de la conclusión preferida del autor.** Esto la propuesta no lo ha notado y es el punto técnico más importante de este costurón.
- SCIAN 485 (transporte urbano de pasajeros: camión, colectivo, taxi) es el servicio local no transable arquetípico, y es empleo grande en mercados metropolitanos. Meterlo del lado **transable** carga la columna transable con empleo expuesto al canal consumidor ⇒ la estimación transable sale más elástica de lo que debería ⇒ **la brecha se achica**. Igual con comercio al por mayor (43x), que es en buena medida servicio local.
- 721/722 (hoteles y restaurantes) del lado **no transable**: en Cancún, Los Cabos, Vallarta y Playa la demanda del producto es nacional e internacional, no local. Y ésos son justamente los mercados receptores de migración que dominan la identificación tras la exclusión del estado propio (§4.3b). Es decir: en los mercados de mayor peso, la columna "no transable" contiene un sector genuinamente transable y exportador ⇒ la estimación no transable sale menos elástica ⇒ **la brecha se achica otra vez**.

**Los dos errores tienen el mismo signo.** Con la bandera de la casa, el modo de falla del test **no es ruido: es confirmación**. Encontrar "transables y no transables salen iguales" —que §3.3(a) y F12 anticipan como posible— sería exactamente lo que la mala clasificación fabrica, y se leería como "el canal consumidor no opera, la estimación transable es limpia". Presentar la bandera de la casa como "la definición de la casa, para comparabilidad" le da un estatus de co-igual que no merece: **es una especificación cuyo sesgo conocido apunta hacia la conclusión del autor.** Debe reportarse etiquetada como tal.

**Problema 2 — la bandera propia mejora, pero no lo suficiente, y "+ turismo" está mal planteado.**
- Agricultura: precio nacional ✓, pero está concentrada en los mercados unimunicipales rurales que casi no identifican. La columna transable quedará dominada por manufactura en un puñado de mercados.
- **Añadir turismo del lado transable como está propuesto es un error.** 721/722 es mayoritariamente restaurantes, que en casi todos los mercados sirven a residentes. Para hacerlo bien, la bandera tiene que ser **específica del mercado**, no de la industria: "fracción del producto vendida fuera del mercado". Eso es defendible (proxy: share de empleo hotelero, o un índice de turismo) pero es una construcción más ambiciosa que "una bandera desde `LLAVE_ACTECONOMICA`", y mete una variable a nivel mercado que puede correlacionar con el instrumento.
- Manufactura tampoco es tomadora de precios limpia en 1990–2020: el empleo maquilador lo mueve la demanda de EE.UU., que es un choque grande, concentrado en la frontera norte y **correlacionado con la inmigración interna hacia la frontera**. El Bartik industrial controla parte de eso — pero el Bartik se construye **con los mismos shares industriales**, así que en una regresión restringida a transables se está controlando por algo muy cercano al motor del propio tratamiento.

**Problema 3 — y es el que rompe el test: bajo insensibilidad de precios de factores, la predicción se invierte. [ESTO ES LO GRAVE]**
El propio inventario (§9.2, matiz) y el cuaderno (F12, mala noticia #2) anotan que un sector transable perfectamente abierto tiene demanda de trabajo **infinitamente elástica** (Rybczynski / FPI): todo el ajuste ocurre en la composición industrial, con efecto salarial cero. Ambos documentos lo tratan como un caveat a anticipar. **No es un caveat: destruye la interpretación del contraste.**

Póngalo en una línea: la teoría de transables predice ε_D,transable = ∞ (**lo más elástico posible**); el canal consumidor predice ε_D,no-transable > ε_D,transable (**no transable más elástico**). Las dos fuerzas empujan el mismo contraste en **direcciones opuestas**. Por lo tanto:
- una brecha con no transables más elástico ⇒ canal consumidor fuerte **o** transables poco abiertos;
- ninguna brecha ⇒ canal consumidor ausente **o** las dos fuerzas se cancelaron;
- brecha invertida ⇒ transables muy abiertos **o** la clasificación está mal.

**Ningún resultado observado distingue entre las hipótesis.** El corte sectorial no puede ser *la prueba* del canal consumidor: es a lo sumo un elemento de evidencia congruente, e incluso eso solo con la bandera propia y con una discusión explícita del grado de apertura de cada mercado. La propuesta tiene todas las piezas de este argumento repartidas en tres documentos y no las ha juntado.

**Consecuencia mayor, que reactiva V10.** Si la demanda transable es casi infinitamente elástica en mercados abiertos, entonces el ε_D agregado de 3–10 es en parte un **objeto de composición**: una mezcla ponderada por shares de una elasticidad transable casi infinita y una no transable finita. El número principal no sería un parámetro tecnológico sino **un índice del grado de apertura sectorial local**. Es exactamente V10 con sombrero sectorial, y V10 está archivada en §7 como "cerrada por alcance".

**Lo que sí prueba el canal consumidor (en orden de fuerza):**
1. **El diseño de conmutantes** (municipio dentro de mercado, §3.3d). Varía el choque de consumo manteniendo fijo el choque de oferta laboral. Es la respuesta *por diseño* de DSS (2017), y la propuesta ya lo tiene. **Debe subir a ser la prueba; el corte sectorial baja a corroboración.**
2. **Interacción con exposición a remesas.** Si el canal consumidor opera, la respuesta salarial a Z debe estar atenuada donde el desplazador de demanda local es más fuerte. Una columna, con datos que ya están.
3. **Medir el mecanismo, no la elasticidad.** ¿Predice Z el empleo/los precios de no transables? La base tiene vivienda; el empleo sectorial ya está verificado. Un test directo del mecanismo no requiere comparar elasticidades y no sufre la ambigüedad de FPI.
4. El corte sectorial, con la bandera propia, presentado como **cota**, no como test.

**Veredicto: no resuelta, y mal jerarquizada.** La prueba correcta ya está en el documento (conmutantes) pero está catalogada como "diferenciador"; la que se promovió a prueba tiene signo teóricamente ambiguo.

---

### 4.5 Rama B: ¿alcance de maestría? ¿y es la validación fuera de muestra una prueba?

- **Dimensión:** Especificación / alcance; y validez de la prueba propuesta.
- **Pasaje:** §5 Rama B, y en particular *"estimar ε_D con choques migratorios 1990–2010, predecir la respuesta del empleo al salario mínimo 2015→2020, y contrastar contra lo observado"*.
- **Anclaje:** Card (1992) y Card-Krueger (1994) — la medida de *fraction affected* y qué coeficiente identifica; Cengiz, Dube, Lindner & Zipperer (2019, *QJE*) — horizontes de respuesta del salario mínimo; Lee (1999) / Autor, Manning & Smith (2016) — derrames del mínimo hacia arriba de la distribución; Ulyssea (2018, *AER*) — el margen informal como válvula de ajuste.

**Sobre el alcance: rompe el recorte, y reproduce V15.** 4–6 semanas adicionales sobre un plan de 4 semanas cuyo núcleo (S0, S4) no ha corrido. La propia tabla lo admite. No es una extensión marginal: es más que duplicar. Y la recomendación de secuencia del documento —"no decidir hasta después de S4"— es correcta pero **ya fue violada por el propio documento**, que desarrolló la rama (menú de seis políticas fechado, contexto verificado del salario mínimo, cifras de mordida por estado) antes de S4. Ése es el patrón exacto de V15.

**Sobre la validación fuera de muestra: como está escrita, no es una prueba. Cinco razones, en orden.**

**(1) La ecuación de predicción está mal especificada.** Δln L = −ε_D × mordida requiere que "mordida" sea **el cambio proporcional del salario inducido**, no la fracción de trabajadores por debajo del mínimo. T7 define la mordida como fracción afectada — que es la medida de Card (1992), cuyo coeficiente **no es ε_D** sino ε_D × (brecha proporcional promedio entre los afectados). Es construible del microdato (`SalariosResiduales.dta` es de nivel individuo), pero hay que construirlo, y su construcción incorpora un supuesto sobre derrames hacia arriba de la distribución (Lee 1999).

**(2) La informalidad es el elefante y está fuera de alcance por decreto.** El mínimo muerde en el sector formal; el informal (~55%) es donde puede ocurrir el ajuste. La predicción es sobre empleo **formal**; el resultado observado en el censo es empleo **total**. La literatura existente encuentra efectos nulos o pequeños, que es exactamente lo que la reasignación formal→informal predice. **El test puede fallar por una razón que no tiene nada que ver con ε_D**, y V5 (cerrada por alcance) impide arreglarlo.

**(3) El confusor está colineal con la identificación.** La ZLFN de enero 2019 (mínimo ×2, IVA a la mitad, ISR más bajo) golpea 43 municipios fronterizos + todo Baja California — es decir, precisamente los mercados receptores de migración que, tras la exclusión del estado propio, concentran los pesos de Rotemberg. El choque de validación y la variación identificadora viven en los mismos mercados. A eso hay que sumar, en la misma ventana 2015→2020: el gasolinazo de 2017 (que erosiona la mordida real de forma no uniforme), los años récord de homicidios 2017–2019 (que mueven la migración interna, o sea el propio instrumento) y Jóvenes Construyendo el Futuro (subsidio a la demanda de trabajo joven, concentrado en mercados pobres).

**(4) La ventana.** El censo se levantó del 2 al 27 de marzo de 2020: 12 meses después del alza grande, 14 después de la ZLFN. Los efectos de empleo del salario mínimo operan en horizontes de 1–3 años. Se estaría prediciendo una respuesta acumulada a un tratamiento que llegó casi todo en los últimos 14 meses de una diferencia de 5 años.

**(5) Y la razón de fondo: no puede fallar de forma informativa.** Enumere los desenlaces:
- **Predicho ≈ observado** ⇒ el autor lo llamaría validación. Pero la hipótesis nula ("ε_D irrelevante, el mínimo no muerde") **también predice un cambio de empleo cercano a cero**. Con mordidas reales chicas, la predicción y la nula son numéricamente vecinas: el test no tiene potencia para rechazar "el modelo está mal".
- **Predicho ≫ observado** ⇒ ambiguo entre (a) ε_D sobreestimada, (b) el mínimo no muerde, (c) reasignación al informal, (d) **monopsonio** — si el mercado local es monopsónico, el empleo puede *subir* con el mínimo y la predicción tiene el signo equivocado por teoría, no por medición.
- **Predicho ≪ observado** ⇒ ambiguo por las mismas cuatro vías.

Tres de cuatro desenlaces son ininterpretables y el cuarto coincide con la nula. **Eso es una comparación de números, no una prueba**, y el §5 lo intuye al escribir el riesgo ("si falla, el lector puede concluir que ε_D está mal cuando podría ser que el mínimo no fuera binding") sin sacar la conclusión de que ése es un defecto del test, no del lector.

**El rescate, y vale más que la rama entera: compare pendientes, no niveles.** Regrese el Δln L_l observado 2015→2020 contra la mordida_l a través de los 777 mercados, y **pruebe si el coeficiente es igual a −ε̂_D** de la estimación migratoria. Ventajas, todas grandes:
- Es una **restricción de sobreidentificación genuina**, con error estándar calculable (propagando la varianza muestral de ε̂_D) y con forma de test tipo Hausman.
- No exige que el **nivel** del choque esté bien medido — solo su variación transversal, que es lo que la mordida mide bien.
- **Falla de forma informativa:** pendiente de signo contrario ⇒ monopsonio; pendiente cero ⇒ no muerde o reasignación al informal, y esas dos se separan mirando la respuesta *salarial* a la mordida en la misma muestra.
- Cuesta **una regresión**, no una segunda estrategia de identificación.

**Veredicto sobre el costurón 5: rechazar la Rama B como rama; adoptar el test de pendiente dentro de la Rama A** como tercera prueba de consistencia, con dos páginas y los caveats de (2) y (3) impresos. Eso conserva el 80% del valor intelectual de la Rama B a ~10% del costo, y no rompe el recorte congelado.

---

## 5. Las tres evaluaciones adicionales

### 5.1 El ancla ε_D ≈ 3–10 frente al 2.5 implícito en Mishra

**(a) La banda no tiene fuente.** §1 afirma *"La literatura de mercados locales implica |ε_D| de 3 a 10"* sin citar nada, y la biblioteca de 36 fuentes no contiene ese rango. Está ocupando el lugar del prior numérico principal del trabajo y haciendo trabajo real: §4.2 espec. 4 pre-registra β ∈ [−0.3,−0.1] y §1 dice *"si ε_D sale en 0.4, hay que desconfiar, no celebrar"*. **Un prior sin fuente que pre-registra una banda de aceptación es un riesgo de búsqueda de especificación**, sobre todo con los grados de libertad disponibles (dos banderas × dos ventanas × 2015 dentro/fuera × ponderación × regla de exclusión de orígenes × celdas o no). El rango, si se reconstruye honestamente, sale de invertir los efectos salariales de la literatura de inmigración: Borjas (2003) ⇒ ~2.5–3.3; Card (2001) y Ottaviano-Peri (2012) ⇒ efectos menores ⇒ elasticidades mayores; y el extremo superior de la banda **no es una estimación, es el recíproco de un no-rechazo**. Hay que escribirlo así o citar una fuente.

**(b) El contraste con Mishra no es tranquilizador — es mecánico.** El documento dice que el 2.5 de Mishra *"cae justo debajo de esa banda — un contraste externo tranquilizador"*. Dos correcciones:
- Mishra estima sobre **celdas nacionales** educación×experiencia (diseño Borjas 2003), que mantiene aproximadamente fijos el stock de capital nacional y la composición industrial. Eso apaga exactamente los márgenes (entrada de capital, entrada de empresas, recomposición sectorial) que la propuesta invoca para justificar una elasticidad local mayor. Así que sí, 2.5 debería ser una **cota inferior** del número local. La dirección es correcta.
- Pero hay una segunda diferencia que empuja **igual de fuerte y por una razón que no es económica**: los diseños de área están atenuados por la salida de nativos y por los derrames entre mercados —la queja central de Borjas (2003) contra los estudios de área, y el mecanismo que DSS (2017) documenta—, lo que sesga la respuesta salarial local **hacia cero** y por tanto ε_D **hacia arriba, mecánicamente**. Es decir: **que el número local supere a 2.5 está garantizado por un sesgo conocido del diseño, no por la economía.** Obtener 3–10 y llamarlo consistente con Mishra es confirmar un artefacto. La espec. 8 (desplazamiento de nativos) es justamente la que mide ese artefacto: hay que usarla para **acotar** ε_D, no solo para justificar que se use IV.

**(c) La inversión rompe la inferencia, y esto es un fix concreto que falta por completo.** ε_D = −1/β. Si β̂ = −0.15 con e.e. 0.05, el IC 95% de β es [−0.25,−0.05] y el de ε_D es [4,20]; y si el IC de β **incluye cero** —perfectamente posible bajo R1— el conjunto de confianza de ε_D es **no acotado y disconexo** (Fieller; Dufour 1997). El método delta sobre 1/β̂ es inválido exactamente en el escenario que la propia propuesta declara como su riesgo #1.
→ **Reportar la inferencia sobre β, y dar conjuntos de confianza de Anderson-Rubin** (robustos a instrumento débil y invariantes a la reparametrización) para ε_D. No aparece en ningún lugar de la propuesta ni de los documentos compañeros. Dado R1, no es un refinamiento: **es el procedimiento de inferencia correcto**, y es probablemente la recomendación econométrica más barata y de mayor retorno de toda esta crítica.

**(d) Pre-registre la especificación, no la respuesta.** La disciplina del cuaderno —escribir el signo esperado antes de mirar— es exactamente el instinto correcto. Aplíquela a la **especificación núcleo**: fíjela por escrito hoy, y repórtela primero, salga el número que salga.

### 5.2 ¿Es "gratis" la prueba de sobreidentificación de §5 Rama A? **No — y contiene un error algebraico.**

La propuesta afirma que de las regresiones Bartik publicadas se obtienen: Δln L sobre Bartik ⇒ ε_S/(ε_D+ε_S); Δln w sobre Bartik ⇒ 1/(ε_D+ε_S); el cociente ⇒ ε_S; y la segunda con tu ε_D ⇒ una **segunda** estimación de ε_S; y que coincidan es una restricción testeable.

**El álgebra, hecha con cuidado.** Con Δln L^d = −ε_D Δln w + D y Δln L^s = ε_S Δln w + S, el equilibrio da Δln w = (D−S)/(ε_D+ε_S). Ahora bien: el Bartik *B* no **es** D. Es un índice de exposición construido; su relación con el verdadero desplazador de demanda es D = λB + error, con **λ desconocido** (atenuación por error de medición, más los choques de demanda que el Bartik no captura). Entonces, suponiendo Cov(B,S)=0:

- plim coef(Δln w sobre B) = **λ**/(ε_D+ε_S)
- plim coef(Δln L sobre B) = **λ**·ε_S/(ε_D+ε_S)
- cociente = ε_S  ✅ **λ se cancela: esta estimación es válida.**
- segunda ruta: ε_S = (ε_D+ε_S)/λ − ε_D, que **solo es igual a ε_S si λ = 1.**

**Consecuencia exacta: la "prueba" propuesta rechaza si y solo si λ ≠ 1.** Tiene potencia plena contra "la escala del Bartik no es uno" —que está prácticamente garantizado— y **potencia cero contra fallas del marco oferta/demanda**, que es lo que dice estar probando. El documento describe el resultado como *"una restricción testeable de todo el marco"* y *"la respuesta más contundente a MRRH"*. No lo es: es un test de una normalización.

**Y hay algo más fuerte todavía. El sistema es exactamente identificado, así que no hay ninguna prueba disponible.** Dado ε̂_D, las incógnitas son **dos** (ε_S y λ) y los momentos son **dos** (los dos coeficientes de forma reducida). 2 = 2. **No sobra ningún grado de libertad. La prueba de sobreidentificación no existe.**
→ *Lo que sí se puede hacer, y es útil:* **estimar λ en vez de asumirlo**, y reportarlo como diagnóstico. Un λ̂ lejos de 1 dice que el Bartik es un proxy ruidoso del desplazador de demanda — información valiosa sobre el otro lado del par, obtenida gratis. Pero hay que llamarlo diagnóstico, no test.

**Tres costos adicionales que "gratis" tampoco cubre:**
- **La exclusión que hace falta está contradicha por la propia biblioteca.** El cociente da ε_S solo si Cov(B,S)=0: el Bartik no debe desplazar la oferta. Pero **Cadena & Kovak (2016, *AEJ: Applied*)** —Bloque E de la bibliografía, rank 5— muestra exactamente lo contrario: los migrantes se mueven **hacia** los mercados favorecidos por choques de demanda. Cov(B,S) > 0 ⇒ el cociente ya no es ε_S. La fuente que rompe el supuesto está en la propia lista de lecturas y no se cita en §5. **Ésta es la única dimensión "evidencia contradictoria en la biblioteca ignorada" que encontré, y es directa.**
- **Las dos estimaciones no son independientes:** comparten la forma reducida del salario. Cualquier estadístico de comparación debe considerar la covarianza, y su potencia es limitada aunque se arregle λ.
- **O el test interno o la narrativa del par, no ambos.** Para comparar de verdad hacen falta mismos mercados, olas, longitud de diferencia, concepto de salario, concepto de empleo, ponderación y controles. Todo eso lo controlas **si corres tú las regresiones Bartik** (puedes: los insumos están publicados) — pero entonces **no estás comparando con el mimeo**, estás comparando con tu propia reproducción. Eso es mejor para el test interno y **destruye** la narrativa de "entrego la mitad faltante del par de Banxico", que necesita el ε_S del mimeo, cuya especificación no controlas. Es exactamente **V14**, y hoy carga el argumento de relevancia de toda la tesis.

**Veredicto: no es gratis y no es una prueba.** Es un diagnóstico útil de dos páginas, que exige un supuesto de exclusión que la literatura del propio autor contradice. Retirar la frase *"la respuesta más contundente a MRRH"*.

### 5.3 279 mercados unimunicipales + ola 2015: ¿robustez o cambio de diseño? **Cambio de diseño.**

La propuesta lo trata como R4 ("identificado; ponderar por empleo; robustez sin el cuartil chico"). Es insuficiente por tres razones, la segunda de las cuales es la más grave de toda esta crítica.

**(a) La caracterización del sesgo está al revés, y a favor del autor.** §3.5 dice que el error de medición en el regresor endógeno *"atenúa MCO e interactúa con la fuerza del instrumento"*. Bajo error **clásico**, atenúa MCO (correcto) y **no sesga 2SLS** (el resultado de libro de texto: es una de las razones por las que se usa IV). Lo que sí hace es agregar ruido a la variable dependiente de la primera etapa: baja R² y F sin tocar π. Es decir, bajo error clásico la consecuencia es de **potencia**, no de sesgo — lo cual importa mucho dado R1, pero es una historia distinta de la que el documento cuenta.

**(b) Pero el error aquí NO es clásico, y el diseño lo convierte en un artefacto con el signo que la tesis busca. [ESTO CAMBIA EL DISEÑO]**
La ola 2010 es simultáneamente el **final** de la diferencia 2000→2010 y el **inicio** de la diferencia 2010→2020, y ambas entran en la misma regresión núcleo (N=1,554). Sea u_l el error muestral de ln L_{l,2010} en un mercado con muestra delgada. Entonces:
- Δln L_{2000→2010} está inflado en +u_l
- Δln L_{2010→2020} está deflactado en −u_l

y lo mismo ocurre, **con el mismo signo estructural y desde la misma muestra de individuos**, para ln w_{l,2010}. El resultado es una **correlación negativa mecánica entre Δln L y Δln w** inducida por ruido muestral compartido entre diferencias contiguas — clásica reversión a la media. Y esa correlación negativa espuria **tiene exactamente el signo del coeficiente β que la tesis busca**. Está concentrada donde la muestra es delgada: los 279 mercados unimunicipales (36%).

En el panel alterno de 4 diferencias es peor, porque **2015 es endpoint de dos diferencias contiguas** (2010→2015 y 2015→2020) y la Intercensal es una encuesta con ~5.9% de muestra y con municipios explícitamente marcados de *"muestra insuficiente"* en `CAT_COBERTURA`. **El panel de 4 diferencias puede fabricar el resultado principal.** Presentarlo como "especificación alterna que además gana potencia" invierte la evaluación: gana observaciones y añade un artefacto correlacionado con el signo buscado.

Que este canal no esté cerrado por el 2SLS depende de si el instrumento correlaciona con la varianza del ruido, y correlaciona: los shares se construyen del microdato, y los mercados de muestra delgada son los mismos que tienen enclaves delgados. No es solo potencia.

→ **Diagnóstico (barato, obligatorio):** correr β por separado en (i) 2000→2010, (ii) 2010→2020, (iii) las diferencias adyacentes a 2015. Si β es marcadamente más negativo donde hay solapamiento de ola, es el artefacto.
→ **Fix (un día, y los datos ya están en la máquina):** construir ln L_{2010} y ln w_{2010} de **mitades disjuntas** del microdato 2010 (split-sample / par-impar) para las dos diferencias contiguas. Elimina la correlación mecánica de raíz. El mismo procedimiento para 2015 si se conserva el panel de 4. Ésta es una **corrección de construcción, no una robustez**, y debe entrar antes de S4 para que la primera etapa se corra sobre las variables correctas.
→ Nota: en el núcleo, los **shares** de 1990 sí son limpios respecto de los resultados 2000–2020 (no hay solapamiento de muestra). Pero los **shifts** construidos con `RES5A` de la ola *t* comparten muestra con el endpoint *t* del resultado. Mismo remedio.

**(c) La ponderación por empleo es el fix correcto y hay que decir por qué.** Pondera a la baja precisamente los mercados ruidosos y —§4.3(b)— alinea los pesos de la estimación con los del complier. Es una convergencia afortunada de dos argumentos independientes, y es un mejor argumento del que el documento da. Pero ponderar no es prueba: hace falta el diagnóstico de (b).

---

## 6. Enfoques alternativos

### Conjuntos de confianza de Anderson-Rubin (y la F efectiva de Montiel Olea-Pflueger)
- **Aplicabilidad:** el parámetro reportado es una razón (ε_D = −1/β) estimada con un instrumento cuya debilidad el autor declara como riesgo #1. Es el caso de libro de texto de inferencia no invariante.
- **Qué agrega:** conjuntos de confianza válidos aunque la primera etapa sea débil e invariantes a la reparametrización; y un umbral de go/no-go con valores críticos correctos bajo agrupamiento, en lugar del 10 de Stock-Yogo con errores estándar que AKM demuestra inflados. Convierte "F ≥ 10" en un criterio defendible. Costo: bajo (`weakiv`/`twostepweakiv` en Stata).

### Construcción split-sample de los agregados de las olas compartidas (Angrist-Krueger 1995; Angrist-Frandsen 2022)
- **Aplicabilidad:** las olas 2010 (y 2015) sirven de endpoint a dos diferencias contiguas de la misma regresión; el ruido muestral compartido genera correlación negativa espuria entre Δln L y Δln w.
- **Qué agrega:** elimina la principal amenaza mecánica al signo del resultado central. Un día de trabajo con datos que ya están descargados. Es un cambio de construcción, no una robustez.

### El diseño de conmutantes como la prueba del canal consumidor (Dustmann, Schönberg & Stuhler 2017)
- **Aplicabilidad:** la propuesta ya lo corrigió al nivel correcto (municipio dentro de mercado) y sabe que requiere `LLAVE_MUNICIPIO_TRABAJO`, disponible al menos en 2010.
- **Qué agrega:** neutraliza el canal de consumo **por diseño** en lugar de por supuesto, que es precisamente lo que el corte sectorial no puede hacer por la ambigüedad de FPI (§4.4). Debe intercambiar jerarquía con el corte sectorial: conmutantes = prueba; sectorial = corroboración.

### Test de pendiente contra la mordida del salario mínimo, dentro de la Rama A
- **Aplicabilidad:** sustituye a la Rama B completa.
- **Qué agrega:** una restricción de sobreidentificación **genuina** (a diferencia de la de §5 Rama A, que no existe), con error estándar calculable y con modos de falla informativos —pendiente invertida ⇒ monopsonio; pendiente cero ⇒ no muerde o reasignación al informal, separables con la respuesta salarial. Costo: una regresión, contra 4–6 semanas.

### Instrumento rezagado / shares contemporáneos como control (versión barata de Jaeger-Ruist-Stuhler 2018)
- **Aplicabilidad:** el diseño de dos instrumentos completo se descartó bien por potencia; esta versión no requiere potencia adicional.
- **Qué agrega:** ataca directamente "los shares persistentes mezclan corto y largo plazo", que es la formalización moderna de la objeción de Hanson. Una columna en la tabla de robustez.

---

## 7. Inventario de limitaciones

**Reconocidas en el documento (crédito donde toca):** los 32 orígenes y la concentración de los pesos de Rotemberg; la objeción de Hanson, con sección propia; la bandera transable heredada; los 279 mercados unimunicipales y la Intercensal; la ausencia de deflactor espacial; la asimetría temporal entre shares (stock de nacimiento) y shifts (flujo a 5 años); que `CAUSAMIGRACION` no permite filtrar por motivo laboral; que la partición de mercados usa conmutación de 2010 aplicada a 1990 como supuesto; que ε_S es ajena y hay que presentar un rango; el riesgo de scooping.

**No reconocidas, o reconocidas con el signo equivocado:**
- **Sesgo del deflactor faltante no es neutro.** La migración interna sube los costos locales de vivienda; el salario real cae **más** que el nominal deflactado por INPC nacional ⇒ |Δln w| subestimado ⇒ |β| subestimado ⇒ **ε_D sobreestimada**. El sesgo apunta hacia la banda pre-registrada de 3–10. El INPC de 46 ciudades cubre justamente los mercados urbanos que identifican tras la exclusión del estado propio: **súbase de robustez a especificación núcleo para la submuestra identificadora.**
- **Error de medición no clásico por olas compartidas entre diferencias contiguas**, con el signo del resultado buscado (§5.3b).
- **`ResIngresoEE` como bad control** y la inconsistencia entre concepto de salario (ajustado por composición) y concepto de empleo (headcount) (§4.2).
- **El estimando es el de los mercados urbanos receptores de migración de larga distancia**, no el de los mercados laborales locales de México (§4.3b). Los 279 rurales están en la muestra y no en la identificación.
- **N efectivo para inferencia es de un dígito** (número de shocks), no 1,554 (AKM 2019). No hay cálculo de potencia en ninguna parte, pendiente desde el inventario.
- **Multiplicidad:** 8 especificaciones × 2 banderas × 2 ventanas × cortes por sexo y calificación × reglas de exclusión de orígenes, con una banda objetivo anunciada de antemano. Ninguna corrección ni pre-registro de la especificación núcleo.
- **Los shares de enclave correlacionan con la exposición estatal a la emigración a EE.UU.** ⇒ la objeción de Hanson entra por correlación aunque el fenómeno sea distinto (§4.2).
- **Cadena & Kovak (2016)**, en la propia biblioteca, contradice el supuesto Cov(Bartik, oferta)=0 que la Rama A necesita.
- **Movilidad de capital entre mercados** como canal: ningún test propuesto la separa de la curvatura tecnológica (V10 viva).
- **La ZLFN 2019 golpea los mercados de mayor peso de Rotemberg**, así que el confusor de la Rama B es colineal con la identificación de la Rama principal.
- **La bandera de la casa tiene un modo de falla que confirma la hipótesis preferida** — sus dos errores de clasificación apuntan al mismo lado (§4.4).

---

## 8. Veredicto sobre las conclusiones

**(B) Parcialmente sustentadas, con salvedades — y con dos afirmaciones puntuales que son (C), sobreafirmadas.**

El núcleo —"un desplazador de oferta traza la demanda; el shift-share de enclaves internos es un candidato razonable; la casilla de demanda está vacía en esta base y el trabajo entrega la mitad faltante del par"— **es defendible y es una tesis de maestría aprobable**, condicional a que la primera etapa exista. Las dos afirmaciones sobreafirmadas son:

**1. La prueba de sobreidentificación.**
- Dice: *"Que coincidan es una **restricción testeable de todo el marco**, y todos los insumos ya están publicados. Es también la respuesta más contundente a MRRH."*
- Debe decir: *"Con la respuesta de equilibrio al Bartik se puede recuperar una estimación de ε_S como cociente de las dos formas reducidas, que es invariante a la escala del índice de Bartik. Combinada con ε̂_D, el sistema queda exactamente identificado y permite estimar —no probar— el factor de escala λ que relaciona el índice de Bartik con el desplazador de demanda subyacente. Un λ̂ lejos de 1 indica que el Bartik es un proxy ruidoso. El ejercicio es un diagnóstico de consistencia, no una prueba de sobreidentificación, y descansa además en Cov(Bartik, choque de oferta) = 0, supuesto que Cadena y Kovak (2016) ponen en duda."*

**2. El corte sectorial como la prueba del canal consumidor.**
- Dice: *"El corte sectorial deja de ser robustez y pasa a ser **la prueba**: si el canal consumidor importa, no transables debe salir más elástico que transables."*
- Debe decir: *"El corte sectorial es evidencia congruente, no una prueba. Bajo insensibilidad de precios de factores la demanda de trabajo en un sector transable abierto tiende a ser infinitamente elástica, lo que empuja el contraste en dirección opuesta a la que predice el canal consumidor; ningún signo observado de la brecha distingue entre las dos hipótesis. La prueba del canal consumidor es el diseño de conmutantes a nivel municipio dentro de mercado, que neutraliza el gasto local por construcción; el corte sectorial se reporta como cota y como descripción del grado de apertura sectorial de los mercados."*

**Tres afirmaciones menores que también hay que ajustar:**
- *"El 2.5 implícito en Mishra cae justo debajo de esa banda — un contraste externo tranquilizador"* → el diseño de área está sesgado al alza en ε_D por desplazamiento de nativos y derrames, así que superar a Mishra está garantizado mecánicamente. Reformular como cota inferior con el sesgo declarado, y usar la espec. 8 para acotarlo.
- *"F ≥ 10 es el go/no-go"* → especificar **F efectiva de Montiel Olea-Pflueger con errores estándar agrupados a nivel shock / AKM**, y añadir conjuntos de Anderson-Rubin.
- *"V3 cerrada — ahora las remesas son medibles"* → parcialmente resuelta: las remesas miden un desplazador de demanda distinto del que V3 nombraba (el gasto local del migrante interno).

**Sobre la viabilidad, que es la pregunta que importa.** El proyecto sigue siendo viable en ~4 meses **si y solo si** el orden de ejecución se corrige: S0 → construcción con split-sample de las olas compartidas → número efectivo de shocks bajo las tres reglas de exclusión de orígenes → F efectiva con errores estándar correctos → 2SLS con conjuntos AR. Eso es el go/no-go real, y son ~3 semanas. Todo lo demás —dos ramas de política, menú de seis evaluaciones, banderas duales— es posterior a ese punto y hoy está consumiendo el esfuerzo que le toca a esos cinco pasos. Es la tercera vez que la misma observación de secuencia aparece en una crítica de este proyecto.

---

## 9. Preguntas de referee (de sínodo)

1. **Sobre R1 y las celdas.** Los autores deben mostrar que la expansión a celdas estado × sexo × educación construye **shifts que varían dentro de estado** (g^{(s,e)}_{ot} ≠ g_{ot}) y reportar el número efectivo de shocks y la concentración de los pesos de Rotemberg **tanto a nivel celda como a nivel estado**, en la misma tabla. Si el número a nivel estado no se mueve, la expansión mejora el diagnóstico sin mejorar la identificación y no debe presentarse como la respuesta a R1. Adicionalmente, deben reportar la **F efectiva de Montiel Olea-Pflueger con errores estándar agrupados a nivel shock**, no la F convencional, y **conjuntos de confianza de Anderson-Rubin** para ε_D en lugar de intervalos por método delta sobre 1/β̂.

2. **Sobre la objeción de Hanson.** Por favor, reformulen §4.3 concediendo que el mecanismo de acumulación de capital humano se transmite al mercado destino a través de la composición de su fuerza de trabajo, y sustituyan la respuesta 1 por evidencia: (i) la regresión de los shares de peso alto contra la tasa estatal de emigración a EE.UU. —si cargan, "es otro fenómeno" es empíricamente falso—; (ii) el resultado principal con `LogSalario` además de `ResIngresoEE`, dado que residualizar por educación condiciona sobre una variable post-tratamiento; y (iii) el placebo de pre-tendencia, indicando explícitamente en §7 que S0 determina si ese placebo puede correrse.

3. **Sobre el error de medición y la construcción del panel.** Por favor, reporten β estimado por separado en 2000→2010, en 2010→2020 y en las diferencias adyacentes a 2015, y construyan los agregados de las olas que sirven de endpoint a dos diferencias contiguas (2010, y 2015 si se conserva el panel de 4) a partir de **mitades disjuntas del microdato**. El ruido muestral compartido entre diferencias contiguas induce correlación negativa mecánica entre Δln L y Δln w, concentrada en los 279 mercados unimunicipales, y con el mismo signo que el coeficiente de interés. Mientras no exista ese diagnóstico, el panel de 4 diferencias no puede presentarse como una especificación que "gana potencia".

4. **Sobre el canal consumidor.** Los autores deben (i) declarar que los dos errores conocidos de `LLAVE_EXPORTADORA` —transporte urbano de pasajeros del lado transable, turismo del lado no transable— **achican la brecha en la misma dirección**, es decir, sesgan hacia la conclusión de que el canal consumidor no opera; y (ii) resolver la ambigüedad de signo que introduce la insensibilidad de precios de factores, o bien reclasificar el corte sectorial como evidencia congruente y promover el diseño de conmutantes (municipio dentro de mercado) a prueba del canal.

5. **Sobre la Rama A.** Por favor, corrijan la aritmética de §5: la respuesta salarial al Bartik identifica λ/(ε_D+ε_S), no 1/(ε_D+ε_S), donde λ es la escala desconocida del índice. El cociente de las dos formas reducidas sí identifica ε_S y es invariante a λ; la "segunda estimación de ε_S" exige λ=1, de modo que el test propuesto rechaza si y solo si λ≠1 y no tiene potencia contra fallas del marco. Dado ε̂_D el sistema queda exactamente identificado, así que **no hay prueba de sobreidentificación disponible**. Declaren además el supuesto Cov(Bartik, choque de oferta)=0 y discútanlo frente a Cadena y Kovak (2016).

6. **Sobre el alcance.** Los autores deben retirar la Rama B como rama de tesis y conservar su único componente con valor de prueba —regresar el Δln L observado 2015→2020 contra la mordida por mercado y contrastar la pendiente contra −ε̂_D, con error estándar propagado— como tercera prueba de consistencia dentro de la Rama A. En la forma en que está planteada, la validación de niveles no puede fallar de manera informativa: tres de sus cuatro desenlaces son ininterpretables (mínimo no vinculante, reasignación al sector informal, monopsonio) y el cuarto coincide numéricamente con la hipótesis nula.

7. **Sobre el ancla.** Por favor, den fuente para |ε_D| ∈ [3,10] o reconstrúyanla explícitamente invirtiendo los efectos salariales de la literatura de inmigración, señalando que el extremo superior de la banda es el recíproco de no-rechazos y no una estimación; y pre-registren por escrito la **especificación núcleo** —bandera, ventana, ponderación, regla de exclusión de orígenes, 2015 dentro o fuera, concepto de salario— antes de correr S4, reportándola primero sea cual sea el número.

---

## 10. Cierre

La v2 es un salto real: corrige un claim de novedad que casi nadie corrige, verifica contra los `.dta` en vez de contra el diccionario, y encuentra tres cosas del catálogo (la bandera exportadora, las remesas, el nivel correcto del diseño DSS) que un lector apurado no habría encontrado. Esa disciplina es el activo del proyecto, y explica por qué esta crítica puede ser específica: hay suficiente escrito como para poder estar equivocado.

Lo que falla no es el diseño, es la **jerarquía**. La prueba que se promovió a central (el corte sectorial) tiene signo teóricamente ambiguo; la prueba que sí neutraliza el canal por construcción (conmutantes) está catalogada como "diferenciador"; la restricción de sobreidentificación que se vende como gratis y contundente **no existe** una vez que se admite que la escala del Bartik es desconocida; y la amenaza que está clasificada como robustez de mercados chicos es la única capaz de fabricar mecánicamente el signo del resultado principal. Junto a eso, tres vulnerabilidades archivadas como cerradas (V3, V10, V14) están vivas, y V15 —diseñar la capa siguiente mientras la espina está bloqueada— vuelve por tercera vez.

Prioridad en una línea: **cerrar S0, construir con split-sample las olas compartidas, calcular el número efectivo de shocks bajo las tres reglas de exclusión, y correr la primera etapa con la F y los conjuntos de confianza correctos — antes de escribir una línea más de §5.**

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]]. Estatus V1–V15 auditado; V3, V10, V14 reabiertas; V15 recurrente; nuevas amenazas: error de medición no clásico entre diferencias contiguas, inexistencia de la prueba de sobreidentificación, ambigüedad de signo del corte transable, e inferencia no invariante sobre 1/β.*
