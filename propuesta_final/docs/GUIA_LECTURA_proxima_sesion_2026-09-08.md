# Guía de lectura — de aquí a la próxima sesión

**Fecha:** 2026-09-08 · **Para:** Carlos Ramírez (ITAM)
**Contexto:** cierre de la sesión del 2026-09-07, donde se mergeó PROPUESTA v3, se leyeron los cinco papers en texto completo y la crítica referee (`critique/propuesta_v3_critique_2026-09-07.md`) tumbó v3 como rama de identificación autónoma.

**Las tres tareas que esta lectura tiene que habilitar:**
1. Correr la **prueba de conmutantes** (el número que va a la reunión con el asesor).
2. Escribir el **memo al asesor** con las debilidades de v2 **y** v3.
3. Reordenar el repo y escribir **v4**.

> **Regla de esta guía:** no es un catálogo. Cada entrada dice **qué secciones**, **por qué**, y **cuánto**. Lo que no está aquí, no se lee esta semana.

---

## Nivel 1 — Para correr la prueba de conmutantes

### 1. Dustmann, Schönberg & Stuhler (2017), QJE — §V.C (Tabla V col. 3) y Tablas VII–VIII
- **Dónde:** `papers/Dustmann-LABORSUPPLYSHOCKS-2017.pdf`. **Ya tienes la ficha de 400 líneas**: `docs/ficha_DSS2017_QJE_estrategia_empirica_2026-08-19.md` §4.4, §5.4 y §6.
- **Por qué es el #1.** La columna (3) de la Tabla V es **el argumento que vas a copiar literalmente**: *"si el confusor opera a nivel región, la especificación que usa solo variación dentro de la región lo elimina; y como los resultados no cambian, el confusor no está operando."* Es econométrico, no narrativo, y es exactamente la forma de la prueba de conmutantes: el canal de consumo opera **a nivel mercado**, así que una especificación de solo variación **intra-mercado** lo mata por construcción.
- **Y las Tablas VII–VIII** son el molde para **medir φ sin postularlo**: descomponen el efecto de empleo en entradas vs. salidas, y en no-empleo vs. movimiento geográfico. Es la alternativa honesta a tratar φ_l como parámetro estructural.
- **Tiempo:** ~90 min leyendo con la ficha al lado. No releas el paper completo.

### 2. Tus propios documentos: v2 §4.5 y §3.3d, + `PLAN_ensayo1_maestria_2026-08-09.md` §6.3
- **Por qué.** El diseño de conmutantes ya está especificado ahí, incluida la decisión de **municipio dentro de mercado**. No lo rediseñes desde cero.
- **Recordatorio de datos (verificado esta sesión contra los `.dta`):** `LLAVE_MUNICIPIO_TRABAJO` **está en las cinco olas, incluida 1990**.
- **Tiempo:** ~30 min.

---

## Nivel 2 — Para el memo al asesor

### 3. Blyde, Busso, Park & Romero (2023), IDB WP-1418 — §4, Tabla 2 paneles A y B, y la subsección de servicios
- **Dónde:** `papers/Short--and-Long-Run-Labor-Market-Adjustment-to-Import-Competition.pdf`
- **Por qué.** Es el **ancla empírica de tu impugnación**, y es el único paper mexicano que discrimina los dos canales por el signo. Ante el choque negativo de China: el canal de consumo predice que el empleo informal **cae**; el de desplazamiento, que **sube**. Lo observado es que **sube (1%)** ⇒ el desplazamiento domina en neto. Y en servicios/comercio reportan caída de formales *"without an accompanying increase in informal employment"* y **"modest negative spillover effects"** ⇒ el canal de consumo existe, es medible, y es modesto.
- **Retén también** el efecto salarial: **−0.016** log points sobre formales, sin efecto sobre informales, y su nota 11 sobre no poder fijar composición. Es la mitad del bloqueante #1.
- **Tiempo:** ~60 min.

### 4. Fiess, Fugazza & Maloney (2010), JDE — §3.3 y Tabla 2 (columnas de México)
- **Dónde:** `papers/Informal self-employment and macroeconomic fluctuations.pdf`
- **Por qué.** Para poder decirle al asesor, con la fuente en la mano, **por qué "buffer" no es un parámetro sino un régimen**: México sale integrado con informalidad **procíclica** en 1987-91, segmentado en 1992-98, integrado de nuevo en 1999-04. Cambia de signo dentro de tu ventana censal.
- **⚠️ Sáltate §3.1–3.2.** Es álgebra de un modelo dinámico de economía abierta (Euler, acumulación de capital) que **no** vas a usar. FFM te sirve por la **taxonomía de regímenes**, no como plantilla.
- **Tiempo:** ~45 min.

---

## Nivel 3 — Para v4 (solo después de que el asesor se pronuncie)

### 5. Goldsmith-Pinkham, Sorkin & Swift (2020), AER — §II–III y la aplicación de elasticidad de oferta
- **Dónde:** `papers/goldsmithpinkman2020.pdf`
- **Por qué.** Dos cosas. Primera: el *setting* canónico que ellos usan para exponer (`y` = crecimiento salarial, `x` = crecimiento del empleo, β₀ = inversa de la elasticidad de **oferta**) **es literalmente tu ecuación** — entender por qué su β₀ es oferta y el tuyo pretende ser demanda es el corazón del posicionamiento de la tesis. Segunda: la equivalencia numérica (Bartik ≡ shares como instrumentos) implica que **la exogeneidad se juzga sobre los shares**, que es el estándar que cualquier share sectorizado F/I tiene que pasar.
- **Tiempo:** ~2 h.

### 6. ⚠️ Adão, Kolesár & Morales (2019), QJE — **NO ESTÁ EN EL REPO**
- **Por qué importa más que el resto.** Es el criterio de inferencia, y **la N efectiva de un dígito es el go/no-go real de la tesis** — no la F convencional ni los 1,554 mercados. Sin esto no puedes cerrar §4.2 bis de v2 ni defenderlo en sínodo.
- **Acción:** conseguirlo. Es el hueco bibliográfico más caro que tienes.

---

## Opcional, pero de alto retorno para el memo

### 7. ⚠️ Moretti (2010, AER), *Local Multipliers* — **NO ESTÁ EN EL REPO**
- **Por qué.** Cuantifica el canal de consumo (un empleo transable genera del orden de 1.6 empleos no transables locales). Es exactamente el número que te permite **acotar** el canal en el memo en vez de argumentarlo cualitativamente. Convierte "el canal es modesto" en una magnitud.

---

## Lo que NO hay que leer esta semana

- **Bossler & Popp (2026) completo.** Ya sabes lo que necesitas: es **nivel firma**, con vacantes, tensión y 1,200 ocupaciones, **irreproducible en EconLab**. Si quieres el molde de "modelo → ecuación estimable", lee solo *Theoretical Model*, pp. 621–626 (~30 min). Su bloque de search-and-matching **se tira entero**: existe solo porque su variable de interés es el *tightness*, y tú no lo tienes ni lo necesitas.
- **Ulyssea, Dix-Carneiro, Baqaee-Farhi, Antón-Leal.** Fuera del registro que acotó el asesor ("modelos más sencillos, pero sí hay un modelo detrás").
- **FFM §3.1–3.2**, como se dijo arriba.

---

## Bandera de acervo, para la tarea de reordenar el repo

Las carpetas `papers/06_shift_share_migracion/` y `papers/07_arquitectura_elasticidad_estructural/` **están vacías** — y son el núcleo del diseño. Faltan, como mínimo: **Adão-Kolesár-Morales**, **Borusyak-Hull-Jaravel**, **Card (2001)**, **Moretti (2010)**, **Jaeger-Ruist-Stuhler (2018)**. Llenarlas es parte de la tarea 3, no un extra.

---

*Documentos hermanos: `PROPUESTA_v2_2026-09-01.md` (la rama viable), `PROPUESTA_v3_elasticidad_demanda_buffer_2026-07-31.md` (evaluada y degradada), `ficha_DSS2017_QJE_estrategia_empirica_2026-08-19.md`, `../../critique/propuesta_v3_critique_2026-09-07.md`.*
