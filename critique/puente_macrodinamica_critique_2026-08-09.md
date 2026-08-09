# Crítica referee — Puente Dynamic Macro II (Meza) → tesis de ε_D (dos ensayos)

**Fecha:** 2026-08-09 · **Documento evaluado:** `propuesta_final/docs/puente_macrodinamica_tesis_2026-08-09.md` (documento de diseño del Ensayo 2 y su enganche al Ensayo 1) · **Modelo crítico:** claude-opus-4-8 · **Biblioteca metodológica de referencia:** `reader-out/NOTEBOOK.md` + `reader-out/CHEATSHEET.md` (curso Meza, 22 archivos/323 pp.) · **Antecedente:** `critique/elasticidad_demanda_local_critique_2026-07-22.md` (V1–V8).

> **Naturaleza y calibración.** Esto evalúa una **propuesta de tesis de maestría**, no un paper terminado. El estándar aplicado es "¿sobrevive a un comité y es ejecutable en el tiempo restante?", no "¿entra al AER?". Se corre en modo no interactivo: se omite el diálogo socrático y se entrega el dictamen estructurado. Las preguntas puntuales van embebidas como preguntas de sínodo.

---

## 1. Veredicto (sin anestesia)

El puente es **inteligente en la retórica y frágil en la juntura**. Acierta en tres cosas —que el toolkit del curso es efectivamente la caja de herramientas del Ensayo 2, que descartar la vía monetaria está bien fundado (`y=n`, `w≡1`, ε_D=∞), y que Cobb-Douglas trivializa el ejercicio— pero **su columna vertebral analítica no aguanta peso**: el objeto que el Ensayo 1 estima (elasticidad **local, de largo plazo, con capital móvil entre mercados y composición sectorial endógena**) **no es** el `−1/α` del `Proyecto.pdf` (elasticidad **condicional, de corto plazo, con capital fijo, un sector**), y el propio documento lo demuestra sin querer en V10 (bajo CD con capital móvil la demanda de largo plazo es *perfectamente elástica*). La coincidencia de que ambos ronden "3" es un **accidente de magnitud presentado como validación**, no un puente. Peor: la joya de §4 —Correia (1996) con informalidad como factor no gravable Z— descansa en un **error de ruteo de parámetro** (el σ que el Ensayo 1 puede entregar es capital–trabajo à la Raval; el que firma el resultado de Correia es la sustituibilidad informal–capital, `F_zk`, que es de la familia σ_FI que la crítica V5 ya declaró **no identificable** con el censo) y en una **analogía teóricamente insostenible** (la informalidad es un margen *endógeno* de elección sectorial, no un factor fijo Z). El dictamen: **el Ensayo 1 sigue siendo la tesis defendible; el Ensayo 2 tal como está en el puente no es un capítulo, es un segundo doctorado mal diagnosticado.** Y todo esto se está diseñando mientras la espina de datos (Q3) lleva 2+ semanas bloqueada — se está puliendo el segundo piso sin haber colado los cimientos.

---

## 2. Estatus de V1–V8 (de la crítica del 2026-07-22)

- **V1 — Objeto ambiguo + novedad vs MRRH.** *Medio-resuelto en lo empírico, REABIERTO en la capa de modelo.* El pivote empírico-primero reencuadra bien el objeto como efecto design-based; pero el puente lo vuelve a confundir al afirmar `ε_D = −1/α = α del modelo`, que es exactamente la conflación que V1 advertía.
- **V2 — La ruta estructural puede *imponer* ε_D.** *AGRAVADA, y el propio puente lo admite ("reactiva V2 en su forma más aguda").* Pasar a CES solo **reetiqueta** el parámetro libre de α a σ; no demuestra que los datos —y no la forma CES + participaciones + elasticidad de demanda de producto— identifiquen σ.
- **V3 — Exclusión del instrumento de oferta (remesas).** *RESUELTA en lo esencial.* Migración interna mata el canal transfronterizo; la restricción a transables neutraliza el residuo "migrantes = consumidores". Buen trabajo. Pendiente menor: definición operativa de "transable".
- **V4 — Scooping frente al EconLab.** *IGNORADA, con señal de AGRAVAMIENTO.* No hay evidencia de haber escrito a econlab; el reencuadre "el mimeo es mi mitad complementaria" es narrativa, no mitigación, y la footnote 18 (los módulos de migración "within project's scope in the next stage") muestra que **el mismo equipo ya tiene tu instrumento en su hoja de ruta**.
- **V5 — σ_FI no identificable con el censo.** *IGNORADA y silenciosamente AGRAVADA.* El capstone de §4 depende de un objeto de la familia σ_FI (sustituibilidad informal–capital) mientras lo etiqueta como "σ" y lo rutea desde Raval (K–L). Se construye el resultado principal sobre el parámetro que V5 marcó como no estimable.
- **V6 — Espacial (reflexión, W endógeno, inferencia AKM).** *RESUELTA (bien).* AKM obligatorio, SAR fuera del núcleo con argumento técnico correcto, shares 1990 predeterminados, exposición de vecino tipo Helm.
- **V7 — Frecuencia decenal + proxy de informalidad ruidoso.** *Nombrada, NO resuelta.* Solo 2 periodos (1,554 obs); potencia sin evaluar; error de medición del proxy sin re-tratar.
- **V8 — Sobre-alcance para maestría.** *AGRAVADA por diseño (vía V11).* Se eligieron dos ensayos tras la advertencia y se sumó un modelo cuantitativo de Ramsey con calibración, óptimos y transiciones de bienestar.

---

## 3. Auditoría de las auto-diagnosticadas V9–V11

### V9 — "Cobb-Douglas vuelve el Ensayo 1 redundante → usar CES"
**Diagnóstico:** direccionalmente correcto; **fix insuficiente; severidad residual mal estimada.**
- Correcto que, bajo CD, la elasticidad *condicional* (capital fijo) `−1/α` queda fijada por la participación del capital y leerla del INEGI hace vacío estimarla.
- **Pero el argumento de redundancia choca con V10:** si lo que estimas es la elasticidad local de largo plazo, **no es `−1/α` ni siquiera bajo CD** (es casi perfectamente elástica cuando el capital se mueve, como el propio puente reconoce). No pueden ser verdad a la vez "`ε_D = −1/α`" (§2) y "bajo CD con capital móvil ε_D→∞" (V10). El puente usa las dos según le conviene.
- **El fix "cambiar a CES" no resuelve V2, lo renombra.** Bajo CES la elasticidad de demanda *condicional a capital fijo* **no** es función de σ solamente: depende de σ **y de las participaciones** (la de producto constante es `−σ(1−s_L)`; la de capital fijo es otra, también dependiente de shares). Sin variación exógena que separe σ de las participaciones y de la elasticidad de demanda de producto, sigues calibrando con otro nombre.
- **La consecuencia práctica está subestimada:** el puente dice que rederivar CD→CES "no es difícil, es el hola-mundo". Falso como framing: log-linealizar el bloque CES y rehacer los coeficientes indeterminados de Uhlig mete σ y las participaciones de estado estacionario en cada coeficiente `α_1…α_6`; la condición `w=y−n` deja de valer. Es factible, pero **el trabajo real no es reescribir matrices: es establecer el mapeo `ε_D → σ` bajo un experimento mental consistente en horizonte** — y eso es casi todo el contenido intelectual del Ensayo 2.
- **Veredicto:** severidad ALTA **correcta**; "resuelto por CES" **incorrecto**. Riesgo residual tras el fix: sigue ALTO.

### V10 — "Brecha entre la elasticidad estimada y el parámetro del modelo"
**Diagnóstico:** **la vulnerabilidad correcta, bien identificada como *load-bearing*, con la observación letal correcta** (capital móvil ⇒ demanda de largo plazo perfectamente elástica ⇒ tu ε_D podría medir movilidad de capital, no tecnología). **Pero ninguno de los tres fixes basta, y son mutuamente inconsistentes.**
- **Fix 1 (disciplinar el estado estacionario, no las IRFs):** el más honesto sobre la frecuencia, pero **aterriza el momento justo donde es menos informativo de σ.** En el largo plazo con capital móvil, la elasticidad la dominan la movilidad de capital y la elasticidad de demanda de producto, no la curvatura tecnológica σ. Es decir: el horizonte en que ε_D se estima creíblemente es el horizonte en que **menos** dice sobre el σ que el modelo necesita. El fix esquiva la frecuencia y cae en "el momento ya no identifica".
- **Fix 2 (apuntar a σ porque es más portable):** cierto como *instinto* (σ es más profundo que una elasticidad reducida), pero **es la meta reescrita como método, no un método.** Recuperar σ de un ε_D contaminado por horizonte requiere modelar explícitamente qué varía en 10 años (capital, sectores, nativos); y Raval (2019) identifica σ con variación *entre plantas* de participaciones/salarios, **no** con una pendiente local de largo plazo. "Apuntar a σ" = adoptar la identificación de Raval = otro ejercicio empírico, no el shift-share.
- **Fix 3 (convertir la brecha en la pregunta):** intelectualmente el más atractivo y el que yo empujaría, **pero (a) disuelve el puente de §4** —si la pregunta es "cuánto de la elasticidad local es tecnología vs movilidad de capital", ya no hay un σ limpio que pasarle a un modelo de Ramsey óptimo; los dos ensayos dejan de conectar por σ— y **(b) sobre-promete una descomposición que el diseño no entrega limpiamente:** los contrastes transable/no-transable y de dos niveles de agregación identifican el canal *consumidor* y el de *desplazamiento/spillover*, respectivamente; **la movilidad de capital entre mercados es un tercer canal que ninguno de los dos aísla.**
- **Veredicto:** severidad ALTA×ALTA **correcta**; resolución **NO lograda**. El único fix real es **escribir el estimando**: qué se mantiene fijo (¿capital? ¿producto? ¿composición sectorial?) y a qué horizonte, y luego estimar ese objeto o mapearlo a σ con un modelo explícito de los márgenes intermedios. Ese es el verdadero núcleo del Ensayo 2 — no Correia. **La elevo a la vulnerabilidad #1 de toda la tesis.**

### V11 — "Dos ensayos empujan contra V8"
**Diagnóstico:** correcto; **mitigación sana pero contradicha por el propio documento.** La recomendación (Ensayo 1 se defiende solo; Ensayo 2 colapsable a capítulo de extensión) es exactamente la correcta. Pero **§4 construye un capstone de Ramsey óptimo con informalidad que es todo menos colapsable**: calibración, óptimos, transición por shooting, defensa del modelado de informalidad frente a Levy/Ulyssea. La severidad MEDIA-ALTA está **subestimada** dado §4, y la mitigación es **internamente inconsistente** con el resto del puente. El documento no sigue su propio consejo.

---

## 4. Mapa de vulnerabilidades NUEVAS (severidad × probabilidad)

### V12 — El σ que el Ensayo 1 puede entregar NO es el σ del que depende Correia (error de ruteo de parámetro). **[ALTA · ALTA]**
El resultado estrella de §4 firma el signo de τ_k vía **`F_zk`**, la cross-parcial entre el factor no gravable (trabajo informal, Z) y el capital — un objeto de sustituibilidad **informal–capital** (familia σ_FI). El Ensayo 1 entrega, en el mejor caso, un σ **capital–trabajo** à la Raval. `σ_{KL} ≠ σ_{informal,K}`. **El pipeline "Ensayo 1 → σ → firma Correia" está roto en la juntura**, y reactiva V5 (σ_FI no identificable con el censo). Es el defecto nuevo más dañino porque **corta exactamente el puente que el documento existe para vender.**
> *Sínodo:* "Escribe `F_zk`. ¿Qué elasticidad de sustitución es esa, y con qué variación de tus 777 mercados la identificas? Si es la K–L de Raval, ¿por qué firmaría el signo de un τ_k que depende de la sustituibilidad informal–capital?"

### V13 — "Trabajo informal = factor fijo Z de Correia" es teóricamente insostenible. **[ALTA · ALTA]**
El Z de Correia es **inelásticamente ofertado y exógeno** (`z_t=Z` fijo; ver `CHEATSHEET.md`, supuestos de Topic 2.3 Segunda Parte). La informalidad es el **margen endógeno** formal/informal (Ulyssea 2010, Levy): su tamaño **responde** a τ_n, τ_k y la fiscalización. Modelarla como Z fijo **asume desaparecido el mecanismo central de la informalidad**. Y endogeneizarla al estilo Ulyssea (elección de sector/entrada) **rompe** el resultado limpio "`F_zk` firma τ_k", porque el margen deja de ser una cross-parcial suave y pasa a ser una asignación discreta con enforcement. **Corolario duro: puedes tener el resultado limpio de Correia O un modelo creíble de informalidad mexicana, no ambos.** El gancho de venta de §4 no sobrevive el modelado realista.
> *Sínodo:* "Si subes el impuesto al trabajo formal y la informalidad crece endógenamente, ¿sigue siendo Z 'inelásticamente ofertado'? Si no, ¿qué queda del teorema que citas?"

### V14 — La "dualidad que fija ν−1+α" trata dos objetos reducidos locales como si fueran los α y ν estructurales. **[MEDIA-ALTA · ALTA]**
El denominador `ν−1+α` es una propiedad del equilibrio del `Proyecto.pdf`: **un mercado, agente representativo, capital fijo** (`n_t = z_t/(ν−1+α)+…`). Ni tu ε_D (local, largo plazo, capital móvil) ni la elasticidad de oferta del mimeo (local, con margen migratorio) **son** los objetos de ese equilibrio — es la misma brecha de V10, ahora **también del lado de la oferta**. Combinar dos números desalineados en horizonte y agregación en un solo denominador estructural no es válido sin un modelo que mapee cada uno a su contraparte. Además exige una **consistencia entre estudios** (mismos mercados, periodos, concepto de salario) que no controlas del lado del mimeo. La dualidad es correcta como *lógica de identificación* (Econometría I: un desplazador de una curva traza la otra) pero **no fija el denominador estructural**, y **no neutraliza el scooping** — la footnote 18 lo agrava.
> *Sínodo:* "Para sumar tu α y el ν del mimeo en `ν−1+α`, ambos deben ser los parámetros de ese equilibrio de un mercado con capital fijo. ¿Lo son? Si no, ¿qué exactamente estás fijando?"

### V15 — Se optimiza el Ensayo 2 mientras la espina empírica (Q3) lleva 2+ semanas bloqueada (riesgo de secuencia/cronograma). **[ALTA · ALTA]**
La ruta crítica es **Q3 → datos → primera etapa → ε_D**. El §6 lista bien Q3 como paso 1, pero **el 90% del documento es arquitectura del Ensayo 2**, que no puede empezar hasta que el Ensayo 1 produzca un número creíble. Si Q3 falla o el instrumento sale débil (F marginal, Montiel-Olea-Pflueger), **el Ensayo 2 es discutible en el vacío.** Los pasos 2 (verificar casilla Correia) y 3 (rederivar CES) están colocados **antes** de que exista una primera etapa: es optimización prematura. Esto es distinto de V8/V11 (que son de *alcance*): V15 es de *orden de ejecución*.
> *Sínodo:* "Si el 1 de octubre todavía no tienes primera etapa, ¿qué de todo lo que diseñaste en el puente sirve para defender la tesis en el comité?"

**Ranking de severidad para el comité (orden de peligro):**
**V10 (no resuelta) > V12 > V13 > V9 (fix insuficiente) > V15 > V14 > V11/V8.**

---

## 5. Recomendaciones accionables (en orden de prioridad)

1. **Congelar el diseño del Ensayo 2 hasta tener primera etapa creíble del Ensayo 1.** Resolver Q3 este mes y correr pasos 4–5 del §8 de `proceso_estimacion_epsilonD_2026-08-07.md` (primera etapa + forma reducida + 2SLS). Sin un ε_D con F defendible, todo el puente es especulación. **Acción de mayor retorno, hoy.**
2. **Escribir el estimando antes que el modelo (resuelve el núcleo de V10).** Una página: ¿qué se mantiene fijo (capital, producto, composición sectorial) y a qué horizonte define tu ε_D? De ahí sale si el objeto se puede mapear a σ y bajo qué supuestos. Esto es el Ensayo 2 de verdad, no Correia.
3. **Degradar §4 (Correia + informalidad) de capstone a sección de discusión / trabajo futuro.** Por V12 (ruteo de σ roto), V13 (analogía insostenible) y su tamaño (segundo doctorado). Si se conserva algo, que sea una *observación cualitativa* — "la presencia de un factor no gravable rompe Chamley-Judd" — explícitamente etiquetada como benchmark teórico, **sin** números de bienestar calibrados a México y **sin** afirmar que el σ del Ensayo 1 firma el resultado.
4. **Corregir la afirmación `ε_D = −1/α` en §0 y §2.** Reconocer explícitamente que es la elasticidad *condicional a capital fijo* del `Proyecto.pdf`, distinta del objeto estimado, y retirar la "coincidencia 3–10 contiene −3" como evidencia de validez (es coincidencia de magnitud, no puente).
5. **Escribir a econlab@banxico.org.mx AHORA** (pendiente desde 2026-07-22): pedir el mimeo **y** preguntar directo si trabajan la demanda / los módulos de migración (footnote 18). Resuelve V4/V14 en la única forma real: información, no narrativa.
6. **Si se conserva la dualidad, venderla como *motivación*, no como identificación del denominador estructural.** Y solo tras confirmar consistencia (mercados/periodos/salario) con el mimeo.
7. **Mantener descartada la vía monetaria** (§3.3 está bien argumentado) y **la vía de gasto** como marginal — aquí el puente acierta y no hay que tocarlo.

---

## 6. Qué cortar si el tiempo aprieta (en orden)

1. **Todo §4 (Correia + informalidad óptima).** Primer corte, mayor alivio. No está en la ruta crítica, es teóricamente frágil (V12/V13) y no es colapsable como pretende V11. → a "extensiones".
2. **La rederivación CD→CES (paso 3 del §6) hasta que exista el número.** No construyas el modelo antes de tener el momento que lo disciplina. Reordenar: Q3 → estimación → *después* decidir CES.
3. **El Ensayo 2 completo colapsa a un capítulo corto "¿qué disciplina este número?"** construido alrededor de la pregunta de V10-fix3 (tecnología vs movilidad de capital), **no** un modelo cuantitativo de tributación óptima. Es lo que la propia V11 recomienda — y lo que §4 contradice.
4. **Techo defendible con lo mínimo:** Ensayo 1 (pasos 4–5 = mínimo publicable; 6–8 = defendible en seminario) + un capítulo interpretativo honesto sobre qué puede y qué no puede decir ese ε_D de la tecnología agregada. Eso **es** una tesis de maestría completa y aprobable. El resto es ambición, no requisito.

---

## 7. Cierre

El puente hace un servicio real: mapea el curso a la tesis con precisión y mata bien la vía monetaria. Pero **sobrevende una juntura que no existe** (`ε_D=−1/α`), **construye su capstone sobre un parámetro mal ruteado y no identificable** (σ_FI disfrazado de σ_KL), y **elige como pieza central una analogía —informalidad = Z fijo— que la propia literatura que el estudiante ya tiene (Ulyssea) desmiente**. La buena noticia es que la tesis **no necesita nada de eso para aprobarse**: el Ensayo 1 se defiende solo y su capa interpretativa honesta (V10 como pregunta, no como problema escondido) es suficiente y más fuerte. Prioridad, en una línea: **cerrar Q3 y sacar la primera etapa; escribir el estimando; y mandar Correia a la sección de trabajo futuro antes de que un sinodal lo mande por ti.**

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]]. Auditoría de V1–V11 completa; nuevas V12–V15 abiertas.*
