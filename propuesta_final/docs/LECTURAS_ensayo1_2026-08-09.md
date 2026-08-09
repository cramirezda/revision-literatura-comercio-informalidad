# Top de lecturas — Ensayo 1 (todo el acervo: papers + documentos internos)

**Fecha:** 2026-08-09 · Alcance: solo Ensayo 1 recortado (ver `PLAN_ensayo1_maestria_2026-08-09.md`).
**Criterio de orden:** lo que bloquea escribir va primero; lo que solo enriquece va al final.

> **Regla general.** El repo acumuló material de tres direcciones distintas del proyecto. Para el Ensayo 1, **una parte grande de lo que tienes NO está en la ruta crítica**. La sección final dice explícitamente qué no leer ahora, y eso vale tanto como la lista de lo que sí.

---

## Nivel 0 — Documentos internos (empieza aquí: son tuyos, gratis y rápidos)

| # | Documento | Qué te da | Tiempo |
|---|---|---|---|
| 1 | `docs/PLAN_ensayo1_maestria_2026-08-09.md` | El plan operativo: alcance congelado, especificaciones con signos, pruebas, calendario | 20 min |
| 2 | `docs/proceso_estimacion_epsilonD_2026-08-07.md` | **El diseño.** Relee sobre todo **§0** (el objeto y la advertencia de magnitud) y **§8** (orden de ejecución) | 30 min |
| 3 | `docs/checkin_datos_EconLab_2026-08-09.md` | Qué viene pre-construido en la base y qué construyes tú. **Nuevo hoy** — cambia el §8 del diseño | 20 min |
| 4 | `critique/elasticidad_demanda_local_critique_2026-07-22.md` | **V1–V8.** Corto (66 líneas) y de alto rendimiento: V1 es literalmente lo que tienes que contestar en la página 1 | 15 min |
| 5 | `docs/ruta_empirica_shift_share_migracion_2026-07-23.md` | La nota de ruta. **Ojo:** su §5 (amenazas) **no incluye** el desplazamiento de nativos — hueco documental pendiente | 25 min |
| 6 | `docs/GUIA_LECTURA_top_v3_2026-08-07.md` | **Solo Bloques 1, 2, 3 y 6.** Los Bloques 4 y 5 son del Ensayo 2 | 20 min |
| 7 | `docs/elasticidad_demanda_bibliografia_2026-07-22.md` | 36 fuentes con notas. Úsalo como índice, no como lectura lineal | consulta |
| 8 | `docs/elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md` | Memo de viabilidad. **Leer con reserva:** todavía describe el encuadre viejo (estructural-primero), superado por la ruta empírico-primero | 20 min |

**Dato de la base, no de literatura:** `datos/Banxico_EconLab_LLM_nota_metodologica_2024-04.pdf` — las tablas de variables (Tabla 1 individual, Tabla 10 agregados). No se "lee", se consulta mientras construyes. Es tu manual.

---

## Nivel 1 — Antes de escribir una sola línea de la propuesta (6 papers)

| # | Referencia | Para qué sección | Por qué es obligatoria |
|---|---|---|---|
| 1 | **Dustmann, Schönberg & Stuhler (2017)**, *Labor Supply Shocks, Native Wages, and the Adjustment of Local Employment*, QJE 132(1) | §4, §6 | **Si lees uno solo, este.** El shock de oferta trazando demanda, hecho limpio. Y su diseño de *commuters* es el que ahora puedes replicar con `LLAVE_MUNICIPIO_TRABAJO` |
| 2 | **Card (2001)**, *Immigrant Inflows, Native Outflows...*, JOLE 19(1) — con **Altonji & Card (1991)** | §4, §6 | Tu ecuación literal. El título nombra tu amenaza espacial: *native outflows* |
| 3 | **Borusyak, Hull & Jaravel (2025)**, *A Practical Guide to Shift-Share Instruments*, JEP 39(1), 181–204 | §4, §6, §7 | El manual operativo. **Su ejemplo corrido es el espejo exacto de tu regresión** (elasticidad inversa de oferta regional con shifters Bartik) — lo citas para justificar tu especificación por simetría |
| 4 | **Goldsmith-Pinkham, Sorkin & Swift (2020)**, *Bartik Instruments: What, When, Why, and How*, AER 110(8), 2586–2624 | §4, §6 | El marco donde vive tu identificación (**los shares son los exógenos**) y los pesos de Rotemberg |
| 5 | **Jaeger, Ruist & Stuhler (2018)**, *Shift-Share Instruments and the Impact of Immigration*, NBER WP 24285 | §4, §6, §8 | La crítica que te van a hacer en seminario. Determina año base lejano y controles pre-periodo |
| 6 | **Monte, Redding & Rossi-Hansberg (2018)**, *Commuting, Migration, and Local Employment Elasticities*, AER 108(12), 3855–3890 | **§1** | **No es opcional:** es V1. Sin este párrafo de posicionamiento, tu casilla vacía se colapsa |

---

## Nivel 2 — En paralelo con la exploración de datos (4 papers)

| # | Referencia | Para qué |
|---|---|---|
| 7 | **Adão, Kolesár & Morales (2019)**, *Shift-Share Designs: Theory and Inference*, QJE 134(4), 1949–2010 | **Tus errores estándar.** Sin esto la tabla principal no pasa referee |
| 8 | **Boustan, Fishback & Kantor (2010)**, *The Effect of Internal Migration on Local Labor Markets*, JOLE 28(4) | El análogo más cercano: migración **interna** como shifter, y cómo se maneja el desplazamiento de nativos |
| 9 | **Monras (2020)**, *Immigration and Wage Dynamics: Evidence from the Mexican Peso Crisis*, JPE | Plantilla del push nacional **con datos mexicanos** |
| 10 | **Borusyak, Hull & Jaravel (2022)**, *Quasi-Experimental Shift-Share Research Designs*, REStud 89(1), 181–213 | El marco alternativo. Tienes que **declarar en cuál paras** (GPSS o BHJ) y por qué |

---

## Nivel 3 — Al escribir interpretación (§7) (4 papers)

| # | Referencia | Para qué |
|---|---|---|
| 11 | **Hamermesh (1993)**, *Labor Demand* (cap. Hicks-Marshall) + **Lichter, Peichl & Siegloch (2015)**, EER 80, 94–119 | El ancla de magnitud — **y por qué NO aplica a tu número** (§0 del diseño). Necesitas la fuente para poder decir eso |
| 12 | **Borjas (2003)**, *The Labor Demand Curve Is Downward Sloping*, QJE 118(4), 1335–1374 | El título es tu tesis. Oferta migratoria trazando demanda |
| 13 | **Ottaviano & Peri (2012)**, JEEA 10(1), 152–197 | La réplica: cómo la anidación cambia lo que recuperas del mismo shock. Te evita vender tu ε_D como algo que no es |
| 14 | **Card (2012)**, JEEA 10(1) | Cierra el debate por el lado del diseño de área, que es el tuyo |

---

## Nivel 4 — Ya en el repo, relectura quirúrgica (no completa)

| Documento | Qué leer exactamente |
|---|---|
| `papers/00_nucleo_tema/{2BB5ECD9…}.pdf` — **Aldeco et al. (2024)** | **eq. (2) p. 11** (el Bartik), **§3.3 p. 11** (dice textual "*such as the elasticity of labor supply*" ← tu hueco), **fn. 18 p. 11** (módulos de migración "next stage" ← oportunidad y aviso de scooping) |
| `reader-out/NOTEBOOK.md` | **Solo la entrada de `Proyecto.pdf`, sección "Bloque laboral".** Contiene la dualidad de identificación (choque de TFP = desplazador de demanda ⇒ traza oferta; tu shock de enclaves = desplazador de oferta ⇒ traza demanda) y el equilibrio `n_t = [z_t + αk_t]/(ν−1+α)`. **Es la mejor frase de encuadre que tienes para §1 y el contenido de §7** |
| `reader-out/CHEATSHEET.md` | **Solo la sección final "Bloque laboral por modelo - donde vive epsilon_D"** — media página, útil para §7 |

---

## Nivel 5 — Conseguir en paralelo (gestión, no lectura)

- **Mimeo de oferta** (Aldeco, Chiquiar, Pérez Pérez & Salcedo) → `econlab@banxico.org.mx`. **Tu paper-espejo.** En el mismo correo, la pregunta de V4
- **Hong & McLaren**, *Are Immigrants a Shot in the Arm for the Local Economy?*, NBER WP → justifica restringir a transables
- **Dustmann, Schönberg & Stuhler (2016)**, JEP 30(4) → por qué los estimados difieren por nivel de agregación; sostiene la robustez de dos niveles
- **Caballero, Cadena & Kovak (2023)**, *J. of International Economics* 145, 103832 → **solo si activas la robustez de red EE.UU.**

---

## Qué NO leer ahora (y por qué)

Esto es la mitad del valor de esta lista. El repo tiene mucho material que es excelente y está **fuera de la ruta crítica del Ensayo 1**:

| Material | Por qué no ahora |
|---|---|
| **Bloque 5 completo** de la guía v3 (Suárez Serrato-Zidar, Kline-Moretti, Diamond, Notowidigdo, Llull, Oberfield-Raval) | Es la arquitectura "elasticidad → pregunta estructural". Eso es el Ensayo 2, que quedó congelado |
| **Bloque 4** (Raval 2019, Ulyssea 2010) | El puente al modelo. §7 es discusión, no estimación — no necesitas la maquinaria |
| `docs/puente_macrodinamica_tesis_2026-08-09.md` y `critique/puente_macrodinamica_critique_2026-08-09.md` | Del Ensayo 2. Vale la pena tenerlos leídos **antes de la reunión** por si el asesor pregunta hacia dónde va, pero no antes de S4 |
| **El resto de `reader-out/`** (2,395 líneas de NOTEBOOK, el glosario, casi todo el CHEATSHEET) | Material del curso de macro dinámica. Insumo del Ensayo 2 |
| Anselin, LeSage & Pace, Corrado & Fingleton, Molho | Econometría espacial. El SAR quedó fuera del núcleo con justificación técnica |
| `propuestas_anteriores/` completo | Las cuatro propuestas viejas, superadas por el pivote de julio |
| **Bloque 6, parte (iii)** de la guía v3 | El spatial Durbin con W de commuting es tu segundo paper, no éste |

---

## Ruta mínima si tienes poco tiempo

Si solo pudieras leer cinco cosas antes de la reunión con el asesor:

1. `docs/checkin_datos_EconLab_2026-08-09.md` *(interno, 20 min)*
2. `critique/elasticidad_demanda_local_critique_2026-07-22.md` *(interno, 15 min)*
3. **Dustmann, Schönberg & Stuhler (2017)** QJE
4. **Monte, Redding & Rossi-Hansberg (2018)** AER — para poder escribir el párrafo de V1
5. **Borusyak, Hull & Jaravel (2025)** JEP — el manual, y el espejo de tu regresión

Con esas cinco puedes escribir la página 1 y defender el diseño. Todo lo demás refina.

---

**Destinos de descarga:** Niveles 1, 2 y 3 → `papers/06_shift_share_migracion/` (carpeta ya creada). Nivel 5 → la misma. Bloque 5, si algún día se retoma → `papers/07_arquitectura_elasticidad_estructural/` (creada y vacía).

*Ver [[project-tesis-elasticidad-demanda-local]].*
