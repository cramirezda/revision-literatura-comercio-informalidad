# Puente: Dynamic Macro II (Meza) → tesis de elasticidad de demanda de trabajo

**Fecha:** 2026-08-09 · Para: Carlos Ramírez (ITAM)
**Insumo:** `reader-out/NOTEBOOK.md` (22 archivos, 323 pp. del curso, extraídos 2026-08-09)
**Contrasta con:** `proceso_estimacion_epsilonD_2026-08-07.md`, `ruta_empirica_shift_share_migracion_2026-07-23.md`, `critique/elasticidad_demanda_local_critique_2026-07-22.md`

**Decisiones del usuario que este documento asume (2026-08-09):**
arquitectura de **dos ensayos separados**; modelo a nivel **agregado nacional** con ε_D como momento externo; política **a determinar por viabilidad**; Meza fue profesor del curso, no asesor.

---

## 0. Resumen ejecutivo

El curso no es un curso de RBC. Es un curso de **política fiscal en modelos de crecimiento + tributación óptima de Ramsey + monetario**, resuelto con **log-linealización y el toolkit de Uhlig**. Eso significa que el material que acabas de subir no es un insumo tangencial: es, casi literalmente, la caja de herramientas del Ensayo 2 que pediste.

Tres conclusiones, en orden de importancia:

1. **El gancho existe y es exacto.** En el modelo del `Proyecto.pdf` la demanda de trabajo es `W = (1−α)Y/N`, que invertida da **ε_D = −1/α con capital predeterminado**. Con α ≈ 1/3 el curso *impone* ε_D ≈ −3. Tu rango esperado (3–10) contiene ese valor. Tu Ensayo 1 estima el parámetro que el curso calibra a ojo.

2. **Pero con Cobb-Douglas el ejercicio es vacío, y esto es una restricción de diseño vinculante.** Si la producción es CD, entonces ε_D = −1/α y α es la participación del capital, que se lee directo de cuentas nacionales. Estimar ε_D con 1,554 observaciones y un shift-share de enclaves para acabar recuperando un número que ya está en el INEGI no es una tesis. **El Ensayo 2 tiene que usar CES, no Cobb-Douglas.** Solo bajo CES el parámetro σ es libre y tu ε_D lo identifica. Esto reactiva V2 de la crítica de referee ("la ruta estructural puede *imponer* ε_D en vez de estimarla") en su forma más aguda.

3. **La ruta de política ganadora no es la que esperabas, y sí es de eficiencia.** No es el choque de gasto ni la monetaria: es **Correia (1996)** del Topic 2.3, aplicada a México con **trabajo informal como el factor no gravable Z**. Ver §4.

---

## 1. Qué contiene realmente el curso

| Tema | Modelo | ¿Hay demanda de trabajo con curvatura? | Instrumentos | Solución |
|---|---|---|---|---|
| **1.1–1.2** | RBC estándar + **McGrattan (1994)** fiscal | **Sí** — CD `k^θ n^{1−θ}` | τ_k, τ_n estocásticos en VAR; g; T | Calibración + momentos |
| **2.1** | Dotación pura, equivalencia ricardiana | **No** — sin producción | g, τ lump-sum, B | Analítico |
| **2.2** | Crecimiento con impuestos distorsionantes (CEDT) | **Solo al final** — ver §3.1 | τ_c, τ_k, τ_n, τ_h, **τ_i** | **Shooting** + IRF |
| **2.3** | **Ramsey óptimo**: Chamley dual, Judd 1985, primal, **Correia 1996** | Genérica `F(k,n)` | τ_k, τ_n, b, Φ | Analítico |
| **3.1** | Monetario shopping-time | **No** — dotación pura | τ, B, M, i, señoreaje | Gráfico |
| **3.2** | Ramsey monetario con trabajo | **No** — `y = n`, w ≡ 1 | τ sobre trabajo, R_m | Gráfico |
| **4.2** | Crecimiento exógeno + impuestos, **detrending** | Genérica `F(K, ZL)` | τ^c, τ^x, τ^k, τ^l, tr | Prerrequisito técnico |
| **5** | Log-linealización + **Uhlig** | RBC con Hansen indivisible | — | **Toolkit Uhlig v4.3 (Matlab)** |
| **Proyecto** | RBC con **GHH** y trabajo endógeno | **Sí, explícita** — CD, ε_D = −1/α | — | Uhlig completo + IRF |

Detalle que vale la pena subrayar: **Topic 2.2 Tercera Parte trae una aplicación a la reforma fiscal mexicana de 2014**, con la distinción entre experimento de impulso-respuesta y experimento de transición. Es el precedente metodológico de que en este curso ya se hacen contrafácticos fiscales para México.

---

## 2. El puente formal, en cuatro líneas de álgebra

Del `Proyecto.pdf`, con `Y = Z K^α N^{1−α}` y utilidad GHH `ln(C − τN^ν/ν)`:

- **Demanda** (K predeterminado): `w_t = z_t + α k_t − α n_t` ⟹ **ε_D = −1/α**
- **Oferta** (GHH, sin efecto riqueza): `n_t = (1/(ν−1)) w_t` ⟹ **Frisch = ε_S = 1/(ν−1)**
- **Equilibrio:** `n_t = [z_t + α k_t] / (ν − 1 + α)`

El denominador **(ν − 1 + α)** gobierna toda la propagación del modelo: cada IRF de empleo, cada multiplicador fiscal, cada respuesta a un cambio de τ_n pasa por él. **α es la mitad de ese denominador y es exactamente lo que tu Ensayo 1 identifica.** ε_D no es adorno de calibración: es la mitad del coeficiente que manda en el modelo.

### 2.1 La dualidad que ordena toda la tesis

El propio material del curso plantea el problema de identificación sin resolverlo: solo se observa la intersección de oferta y demanda, así que α y ν no se separan del par (w, n) de equilibrio. Se necesita un desplazador de una curva para trazar la otra.

| | Desplazador | Curva que traza | Quién lo hace |
|---|---|---|---|
| Choque de TFP `z_t` | **Demanda** | **Oferta** → ν | El curso (RBC); el Bartik de Aldeco et al.; el mimeo de Banxico |
| Shift-share de enclaves | **Oferta** | **Demanda** → α, σ | **Tu Ensayo 1** |

Esta es la mejor frase de venta que tiene la tesis, y sale del curso, no de la literatura de shift-share:

> El mimeo de Banxico mueve la demanda y recupera la elasticidad de oferta. Yo muevo la oferta y recupero la de demanda. **Juntas, las dos estimaciones fijan (ν − 1 + α) sin calibrar ninguno de los dos parámetros** — y ese es el objeto del que dependen todos los multiplicadores del modelo.

Es una defensa directa contra V4 (riesgo de *scooping*): el mimeo deja de ser competencia y pasa a ser la mitad complementaria de tu ejercicio.

---

## 3. Las tres rutas de política, evaluadas contra lo que el curso realmente soporta

### 3.1 Impuestos y subsidios al trabajo — **RECOMENDADA**

**A favor.** Topic 1.2 trae McGrattan (1994) con τ_k y τ_n estocásticos en un VAR y calibración completa (τ_k = 0.5, τ_n = 0.23, g/y = 0.22): es un vehículo listo para "choque impositivo → empleo". Topic 2.2 trae el equilibrio competitivo con impuestos distorsionantes completo — τ_c, τ_k, τ_n, τ_h y el **subsidio a la inversión τ_i** — con el algoritmo de shooting y el precedente de la reforma mexicana de 2014. Topic 4.2 resuelve el detrending.

**El obstáculo, que hay que nombrar.** En el sistema base de Topic 2.2 la oferta de trabajo es **inelástica**, y bajo ese supuesto **τ_n literalmente desaparece de las ecuaciones** (hay incluso una anotación tuya a mano en la p. 4: *"No hay en el modelo"*). El trabajo endógeno solo se enciende en las últimas dos láminas, con utilidad log separable `ln c + ψ ln(1−n)`. Es decir: **la maquinaria fiscal trabajada del curso apaga justo el margen del que habla tu ε_D.**

**La síntesis concreta.** No hay que inventar nada: el modelo del Ensayo 2 es **el bloque del `Proyecto.pdf` (trabajo endógeno + Uhlig + IRFs) con las cuñas fiscales del Topic 2.2 insertadas**, y la producción cambiada de CD a CES. Todas las piezas ya están en tu carpeta.

### 3.2 Choque al gasto público — viable, valor marginal bajo

`g_t` aparece en casi todos los temas, pero en Topic 2.1 el entorno es ricardiano con impuestos de suma fija y sin producción: ε_D no tiene dónde entrar. En Topic 1.2 y 2.2 sí importa, pero el multiplicador del gasto está gobernado sobre todo por la **elasticidad de oferta** (el debate de la literatura es sobre ν y sobre reglas de financiamiento, no sobre α). Tu número quedaría de reparto.

### 3.3 Política monetaria — **DESCARTAR** (y ahora se puede probar por qué)

No es cuestión de gusto. En Topic 3.1 el modelo es de **dotación pura**: no hay firma, no hay función de producción, no hay salario. En Topic 3.2 —el Ramsey monetario con trabajo y tributación distorsionante, que en principio sonaba prometedor— la tecnología es **lineal, `y_t = n_t`, con el salario real normalizado a 1**. Sin capital y sin producto marginal decreciente, la demanda de trabajo es **perfectamente elástica: ε_D = ∞**.

Es decir: en los modelos monetarios de este curso **tu parámetro no tiene dónde entrar**. Para usar la vertiente monetaria tendrías que construir un bloque nuevokeynesiano desde cero, que no está en el material. Recomendación: sacarla del alcance y, si acaso, dejarla como extensión lejana en las conclusiones.

---

## 4. La mejor idea que salió del contraste: Correia (1996) con informalidad

Topic 2.3 Segunda Parte cubre el enfoque primal del problema de Ramsey y luego la **extensión de Correia (1996)**: qué pasa cuando existe un factor de producción **Z que el gobierno no puede gravar**. El resultado es que el teorema de Chamley-Judd (impuesto óptimo al capital = 0 en estado estacionario) **se rompe**, y el signo del τ_k óptimo depende de **F_zk**, la complementariedad o sustituibilidad entre el factor no gravable y el capital.

Ahora traduce: **en México el factor que el gobierno no puede gravar es el trabajo informal.**

Eso da un Ensayo 2 con esta forma:

> **Pregunta.** Cuando una fracción grande del trabajo es informal —y por tanto no gravable— ¿cuál es la estructura tributaria óptima, y cuánto empleo y bienestar cuesta la que México tiene?
>
> **Teoría.** Correia (1996) desde el Topic 2.3, con Z = trabajo informal.
> **Parámetro crítico.** El signo y la magnitud del resultado dependen de la sustituibilidad entre factores, es decir de **σ**.
> **De dónde sale σ.** Del Ensayo 1: ε_D estimado con el shift-share de enclaves, traducido a σ à la Raval (2019), agregado con Oberfield-Raval (2021).
> **Cómputo.** Log-linealización + Uhlig del Topic 5 y del `Proyecto.pdf`; shooting del Topic 2.2 para la transición.
> **Salidas.** Empleo formal/informal, producto, recaudación, y **bienestar** — la métrica de eficiencia que pediste.

Por qué esta ruta domina a las otras:

- Es la única en la que **σ no es un parámetro de calibración más, sino el que determina el signo del resultado principal**. Ahí una estimación cuidadosa se justifica sola.
- Usa la dimensión de informalidad que ya venías arrastrando (Ulyssea 2010; el proxy de seguridad social ya está en la base de EconLab) en vez de dejarla como extensión opcional.
- Entrega eficiencia y bienestar, no solo respuestas de empleo.
- Todo el aparato teórico y computacional ya está en la carpeta que subiste.

**Advertencia honesta:** Correia (1996) es un resultado de estado estacionario en un modelo de agente representativo con compromiso. Convertirlo en un ejercicio cuantitativo calibrado a México es trabajo real, y la literatura de informalidad mexicana (Leal-Ordóñez 2014, Busso-Fazio-Levy 2012, Antón-Hernández-Levy) ya pisa terreno vecino. Hay que verificar que la casilla exacta —Ramsey óptimo con informalidad como factor no gravable, con σ estimado— esté libre antes de comprometerse. Es la primera tarea de investigación del Ensayo 2, no un supuesto.

---

## 5. Las tres vulnerabilidades que este puente crea o agrava

### V9 — Cobb-Douglas vuelve el Ensayo 1 redundante *(severidad ALTA, probabilidad ALTA si no se corrige)*

Bajo CD, `ε_D = −1/α` y α es la participación del capital, observable. Un sinodal razonable pregunta: *¿para qué el shift-share si el número sale de cuentas nacionales?* **Corrección obligatoria: el Ensayo 2 usa CES.** Consecuencia práctica: las matrices de Uhlig del `Proyecto.pdf` cambian, porque la condición de demanda de trabajo deja de ser `w = y − n`. No es difícil, pero hay que hacerlo y presupuestarlo.

### V10 — La brecha entre la elasticidad estimada y el parámetro del modelo *(severidad ALTA, probabilidad ALTA)*

Es la vulnerabilidad central del Ensayo 2 y hay que nombrarla antes de que la nombren por ti. Tu ε_D es:

| Tu estimación | El α / σ del modelo agregado |
|---|---|
| Local (777 mercados) | Nacional |
| Largo plazo (diferencias a 10 años) | Frecuencia de ciclo (trimestral en RBC) |
| Con capital que se reasigna entre mercados | Con capital fijo en el corto plazo |
| Con composición industrial endógena | Un solo sector |

Esto es la misma advertencia que ya está en `proceso_estimacion_epsilonD_2026-08-07.md` §0 (el ancla LPS de 0.25–0.7 no aplica a tu número), pero reaparece más fuerte en la capa de modelo. Oberfield-Raval (2021) resuelve la agregación **micro→macro entre plantas**; no resuelve el salto **local-largo-plazo → agregado-ciclo**.

Y hay un detalle que lo hace mordaz: bajo CD con retornos constantes y capital perfectamente móvil, la demanda de trabajo de largo plazo es **perfectamente elástica**. Tus diferencias decenales están cerca de ese límite. Así que un ε_D grande podría estar midiendo movilidad del capital entre mercados, no tecnología.

Tres respuestas posibles, en orden de honestidad:
1. **Disciplinar el estado estacionario, no las IRFs.** Usar ε_D como momento de comparación estática de largo plazo (para lo que sirve el shooting del Topic 2.2), y calibrar la dinámica de alta frecuencia por separado.
2. **Apuntar a σ, no a α.** σ es un parámetro tecnológico más portable entre horizontes que la elasticidad de demanda reducida. Es lo que ya planea el §7 del esbozo de estimación.
3. **Convertir la brecha en la pregunta.** "¿Cuánto de la elasticidad local de largo plazo es tecnología y cuánto es movilidad del capital?" es una pregunta legítima y tiene respuesta con tu diseño (contraste transable/no transable, dos niveles de agregación).

### V11 — Dos ensayos empujan contra V8 *(severidad MEDIA-ALTA, probabilidad ALTA)*

La crítica del 2026-07-22 ya marcó **V8 — sobre-alcance para una tesis de maestría** con probabilidad alta, y eso fue *antes* de agregar un segundo ensayo con modelo cuantitativo, calibración y contrafácticos de bienestar. Pediste dos ensayos y así está construido este documento, pero la recomendación es explícita:

**El Ensayo 1 es el que se defiende solo.** Está diseñado hasta el nivel de tabla (`proceso_estimacion_epsilonD_2026-08-07.md`), tiene la casilla vacía verificada y su mínimo publicable son los pasos 4–5 de su §8. El Ensayo 2 debería escribirse de modo que **pueda colapsarse a un capítulo de extensión** —"qué disciplina este número en un modelo cuantitativo"— sin que la tesis pierda su tesis. Si el calendario aprieta, eso es lo que se recorta.

---

## 6. Qué haría yo, en orden

| # | Paso | Depende de | Nota |
|---|---|---|---|
| 1 | **Confirmar Q3** (espina de datos) | — | Lleva 2+ semanas bloqueando el Ensayo 1 |
| 2 | Verificar que la casilla "Ramsey + informalidad como factor no gravable" esté libre | — | Antes de comprometerse con §4. Es una búsqueda, no un supuesto |
| 3 | Reescribir el bloque de producción del `Proyecto.pdf` de CD a **CES** y rederivar las matrices de Uhlig | 2 | Resuelve V9. Es el "hola mundo" del Ensayo 2 |
| 4 | Ejecutar los pasos 4–5 del §8 del esbozo de estimación (primera etapa + 2SLS) | 1 | El mínimo publicable del Ensayo 1 |
| 5 | Escribir la sección de agregación que enfrenta V10 | 3, 4 | No dejarla para el final |
| 6 | Pedir el mimeo de oferta a econlab@banxico.org.mx | — | Ahora con mejor argumento: es la mitad complementaria, no competencia |
| 7 | Pendientes vivos del esbozo: amenaza de desplazamiento de nativos en §5 de la nota de ruta; definición operativa de "transable"; cálculo de potencia | — | Independientes de todo esto |

---

## 7. Lo que este documento NO resolvió

1. **No verifiqué en línea** si la casilla de §4 (Ramsey + informalidad) está ocupada. Es el paso 2 de arriba.
2. **No revisé el detalle de Topic 4.2 ni del midterm** más allá de sus bloques laboral y de política; están completos en `reader-out/NOTEBOOK.md` si los necesitas.
3. **La cita de Correia (1996)** viene de las láminas; hay que verificar la referencia exacta (revista, volumen) antes de citarla en la propuesta.
4. **No hay cálculo de costo en tiempo** para el Ensayo 2. Dado V11, conviene hacerlo antes de comprometerse con el formato de dos ensayos.

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]].*
