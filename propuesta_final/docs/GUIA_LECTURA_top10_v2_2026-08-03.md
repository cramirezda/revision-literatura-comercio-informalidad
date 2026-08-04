# Guía de lectura v2 — ε_D en mercados laborales locales (MX), ruta EMPÍRICO-primero

**Fecha:** 2026-08-03 · Para: Carlos Ramírez (ITAM)
**Supersede el orden de** `GUIA_LECTURA_top10_2026-07-22.md` (esa era *teoría-primero*; sigue siendo válida como mapa de la capa de modelo).
**Documentos de referencia:** diseño en `ruta_empirica_shift_share_migracion_2026-07-23.md` · viabilidad en `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md` · vulnerabilidades en `../../critique/elasticidad_demanda_local_critique_2026-07-22.md`

---

## Por qué cambia el orden

La decisión **Q1 (2026-07-23)** fijó el núcleo de la tesis: **ε_D *design-based*** vía shift-share de enclaves migratorios (Card), con el EG estático como **capa que interpreta** (recupera σ, hace contrafácticos, descompone formal/informal). El objeto que hay que dominar primero ya no es el modelo de dos sectores, sino **el diseño de identificación y su inferencia**.

Regla de lectura: **Bloque 1 antes de escribir una línea de la propuesta.** Bloques 2 y 3 en paralelo con el esbozo del proceso de estimación. El Bloque 4 (modelo) solo cuando el diseño esté cerrado.

---

## Bloque 1 — El diseño (esto *es* la tesis)

| # | Referencia | Por qué | Estado |
|---|---|---|---|
| 1 | **Card (2001)**, *Immigrant Inflows, Native Outflows, and the Local Labor Market Impacts of Higher Immigration*, JOLE 19(1) — leer junto con **Altonji & Card (1991)** (en Abowd & Freeman, eds., *Immigration, Trade, and the Labor Market*, NBER/UChicago) | El instrumento de enclaves literal: shares de origen en año base × push nacional. **Es tu ecuación.** | ⬇ conseguir |
| 2 | **Dustmann, Schönberg & Stuhler (2017)**, *Labor Supply Shocks, Native Wages, and the Adjustment of Local Employment*, QJE 132(1) | La implementación moderna más limpia de un shock de **oferta** trazando la demanda. Bonus decisivo: su diseño usa *commuters* checos que **trabajan pero no consumen** en la región destino → es la respuesta directa a tu amenaza residual **"migrantes = consumidores"** (§5 de la nota de ruta). **Si lees uno solo, este.** | ⬇ conseguir |
| 3 | **Goldsmith-Pinkham, Sorkin & Swift (2020)**, *Bartik Instruments: What, When, Why, and How*, AER 110(8) | El marco donde vive tu identificación: **los shares son los exógenos**, y el estimador es una suma ponderada de Rotemberg. Te da además el diagnóstico de qué orígenes cargan la identificación. | ⬇ conseguir |
| 4 | **Borusyak, Hull & Jaravel (2022)**, *Quasi-Experimental Shift-Share Research Designs*, REStud 89(1) | La alternativa: exogeneidad en los **shifts** (cuasi-aleatorios entre muchos orígenes), shares como mera exposición. Tienes que declarar explícitamente en cuál de los dos marcos paras — y por qué. | ⬇ conseguir |
| 5 | **Jaeger, Ruist & Stuhler (2018)**, *Shift-Share Instruments and the Impact of Immigration*, NBER WP | **La crítica que te van a hacer en el seminario:** los enclaves predicen migración pasada *y* demanda local persistente; el estimador mezcla respuesta de corto y largo plazo. Determina tu elección de año base lejano, controles pre-periodo y (posible) diseño de dos instrumentos. | ⬇ conseguir |

---

## Bloque 2 — El objeto estimado y su inferencia

| # | Referencia | Por qué | Estado |
|---|---|---|---|
| 6 | **Hamermesh (1993)**, *Labor Demand*, Princeton UP (cap. de leyes Hicks-Marshall) + **Lichter, Peichl & Siegloch (2015)**, *The own-wage elasticity of labor demand: a meta-regression analysis*, EER 80:94-119 | Qué determina ε_D y qué magnitud es defendible (**\|ε_D\| ≈ 0.25–0.7**). Sin este ancla no puedes decir si tu número es razonable o un artefacto. | ⬇ conseguir |
| 7 | **Monte, Redding & Rossi-Hansberg (2018)**, *Commuting, Migration, and Local Employment Elasticities*, AER 108(12) | **Tu rival conceptual (V1).** Elasticidades de empleo local en EG con commuting: la apertura al commuting determina la respuesta local. Tienes que decir en la primera página en qué te distingues (tú estimas ε_D *design-based*; ellos la derivan estructuralmente). Citado en la nota de Aldeco. | ⬇ conseguir |
| 8 | **Adão, Kolesár & Morales (2019)**, *Shift-Share Designs: Theory and Inference*, QJE 134(4) | **Tus errores estándar.** Los residuos están correlacionados entre mercados con shares parecidos; el clustering por CZ no basta. Sin esto la tabla principal no pasa referee. | ⬇ conseguir |

---

## Bloque 3 — México, migración interna, y el push nacional

| # | Referencia | Por qué | Estado |
|---|---|---|---|
| 9 | **Boustan, Fishback & Kantor (2010)**, *The Effect of Internal Migration on Local Labor Markets: American Cities during the Great Depression*, JOLE 28(4) | El análogo más cercano a **Q2 (migración interna como shifter de oferta)**: cómo se arma el instrumento cuando el flujo es doméstico y cómo se maneja el desplazamiento de nativos. | ⬇ conseguir |
| 10 | **Monras (2020)**, *Immigration and Wage Dynamics: Evidence from the Mexican Peso Crisis*, JPE | Plantilla de cómo se construye el **shift nacional con datos mexicanos** (crisis del peso 95 como push) y de la dinámica de ajuste salarial post-shock. | ⬇ conseguir |
| 11 | **Aldeco, Calderón, Chiquiar, Hanson, Pérez Pérez & Velázquez (2024)**, *Local Labor Markets in Mexico*, Banxico | **Relectura quirúrgica**, no completa: **eq. (2) p.11** (definición del Bartik), **§3.3 p.11** ("*such as the elasticity of labor supply*" ← tu hueco) y **footnote 18 p.11** (módulos de migración "*within project's scope in the next stage*" ← oportunidad + aviso de scooping, V4). | ✅ en repo (`papers/00_nucleo_tema/{2BB5ECD9…}.pdf`) |

---

## Bloque 4 — Puente al modelo (solo con el diseño ya cerrado)

| # | Referencia | Por qué | Estado |
|---|---|---|---|
| 12 | **Raval (2019)**, *The micro elasticity of substitution and non-neutral technology*, RAND 50(1) | Cómo se recupera σ (K–L) con variación de **salarios locales** — exactamente la variación de los 777 mercados. Es el eslabón ε_D → σ. | ⬇ conseguir |
| 13 | **Ulyssea (2010)**, *Regulation of entry, labor market institutions and the informal sector*, JDE 91:87-99 | Lado de producción CES formal/informal: la plantilla que **interpreta** tu ε_D y habilita la descomposición por sector. | ✅ en repo (`papers/00_nucleo_tema/ulyssea 2010.pdf`) |

---

## Must-get en paralelo (pedir/descargar ya)

- **Aldeco, Chiquiar, Pérez Pérez & Salcedo**, *Estimación de la elasticidad de la oferta de trabajo en México*, mimeo Banxico → **tu paper-espejo obligado**. Confirmado en las referencias de la nota de 2024, pero no indexado. Pedir a **econlab@banxico.org.mx**.
- **Hong & McLaren**, *Are Immigrants a Shot in the Arm for the Local Economy?*, NBER WP → cuantifica el canal **"migrantes = consumidores"**; es la evidencia con la que justificas restringir la estimación al **sector transable**.
- **Caballero, Cadena & Kovak**, redes migratorias México–EE.UU. → construcción de la red; **solo necesario si activas la robustez con red EE.UU.** ⚠️ *Año y revista por verificar* (en notas previas aparece como 2018 y como 2021 en distintos lugares).
- **Dustmann, Schönberg & Stuhler (2016)**, *The Impact of Immigration: Why Do Studies Reach Such Different Results?*, JEP 30(4) → mapa de por qué los estimados difieren (skill-cell vs área vs mixto); útil para posicionar tu especificación.

---

## Qué se degrada respecto de la guía v1

No se descartan; dejan de ser bloqueantes y pasan a la capa de modelo/robustez, para leer **después** del Bloque 1:

- **Amaral & Quintin (2006)**, JME — GE competitivo con informalidad.
- **Satchi & Temple**, RED — GE con informalidad calibrado a México.
- **Galiani & Weinschelbaum (2012)**, Econ. Inquiry — microfundamento del margen formal/informal.
- **Anselin (2003)** / **LeSage & Pace (2009)** — econometría espacial; relevante solo si se activa la ruta de spillovers con la matriz de commuting.
- **Meghir, Narita & Robin (2015)**, AER — estructural de salarios con informalidad; canónico, pero de la capa de modelo.

---

## Estado del acervo

De este top, **solo 2 están en el repo** (Aldeco 2024 y Ulyssea 2010, ambos en `papers/00_nucleo_tema/`). Todo el Bloque 1 —el núcleo del diseño— está pendiente de rescate manual. Sugerencia de destino al descargarlos: `propuesta_final/papers/06_shift_share_migracion/`.

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]].*
