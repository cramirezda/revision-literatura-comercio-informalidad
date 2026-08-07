# Guía de lectura v3 — ε_D en mercados laborales locales (MX), ruta EMPÍRICO-primero

**Fecha:** 2026-08-07 · Para: Carlos Ramírez (ITAM)
**Supersede a** `GUIA_LECTURA_top10_v2_2026-08-03.md` (reemplazo completo: conserva sus Bloques 1–4 y añade los Bloques 5 y 6).
**Supersede el orden de** `GUIA_LECTURA_top10_2026-07-22.md` (v1, teoría-primero; sigue siendo válida como mapa de la capa de modelo).
**Documentos de referencia:** diseño en `ruta_empirica_shift_share_migracion_2026-07-23.md` · viabilidad en `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md` · bibliografía canónica en `elasticidad_demanda_bibliografia_2026-07-22.md` · vulnerabilidades en `../../critique/elasticidad_demanda_local_critique_2026-07-22.md`

---

## Qué cambia respecto de v2

v2 ordenó las lecturas alrededor del **diseño de identificación**. Faltaban dos cosas que v3 agrega:

1. **Bloque 5 — la arquitectura.** v2 tenía papers que *estiman* ε_D (Bloque 2) y papers que *modelan* estructuralmente (Bloque 4), pero **ningún ejemplo de la arquitectura completa**: estimar una elasticidad *design-based* y después usarla para responder una pregunta estructural. Esa arquitectura es la decisión **Q1** de la tesis ("empírico primero, modelo interpreta") y estaba sin molde. Los nueve papers del Bloque 5 son ese molde.
2. **Bloque 6 — lo espacial.** La Ruta 2 (spatial lag/Durbin con W = commuting) quedó degradada por Q1, pero "lo espacial" no es una sola cosa: dos de sus tres versiones son **obligatorias** para el núcleo. v3 las separa y añade la advertencia técnica sobre por qué el SAR no va en el núcleo.

Además: **Notowidigdo (2020) sube** del Bloque B de la bibliografía (rank 4) al Bloque 5, y se añade **Borusyak-Hull-Jaravel (2025)** al Bloque 1.

**Regla de lectura:** Bloque 1 antes de escribir una línea de la propuesta. Bloques 2, 3 y 5 en paralelo con el esbozo del proceso de estimación. Bloque 6 al cerrar la sección de amenazas. Bloque 4 solo con el diseño cerrado.

---

## Bloque 1 — El diseño (esto *es* la tesis)

| # | Referencia | Por qué | Estado |
|---|---|---|---|
| 1 | **Card (2001)**, *Immigrant Inflows, Native Outflows, and the Local Labor Market Impacts of Higher Immigration*, JOLE 19(1) — con **Altonji & Card (1991)** (en Abowd & Freeman, eds., *Immigration, Trade, and the Labor Market*, NBER/UChicago) | El instrumento de enclaves literal: shares de origen en año base × push nacional. **Es tu ecuación.** El título además nombra la amenaza espacial (*native outflows*) — ver Bloque 6. | ⬇ conseguir |
| 2 | **Dustmann, Schönberg & Stuhler (2017)**, *Labor Supply Shocks, Native Wages, and the Adjustment of Local Employment*, QJE 132(1) | La implementación moderna más limpia de un shock de **oferta** trazando la demanda. Bonus decisivo: usa *commuters* checos que **trabajan pero no consumen** en el destino → respuesta directa a la amenaza residual "migrantes = consumidores" (§5 de la nota de ruta). **Si lees uno solo, este.** | ⬇ conseguir |
| 3 | **Goldsmith-Pinkham, Sorkin & Swift (2020)**, *Bartik Instruments: What, When, Why, and How*, AER 110(8), 2586–2624 | El marco donde vive tu identificación: **los shares son los exógenos**, y el estimador es una suma ponderada de Rotemberg. Te da el diagnóstico de qué orígenes cargan la identificación. | ⬇ conseguir |
| 4 | **Borusyak, Hull & Jaravel (2022)**, *Quasi-Experimental Shift-Share Research Designs*, REStud 89(1), 181–213 | La alternativa: exogeneidad en los **shifts** (cuasi-aleatorios entre muchos orígenes), shares como mera exposición. Tienes que declarar explícitamente en cuál de los dos marcos paras — y por qué. | ⬇ conseguir |
| 5 | **Borusyak, Hull & Jaravel (2025)**, *A Practical Guide to Shift-Share Instruments*, JEP 39(1), 181–204 | **Añadido en v3.** El manual operativo posterior a los dos marcos: checklists de validación, diagnósticos, errores comunes. Detalle que lo hace obligatorio para ti: **su ejemplo corrido es estimar la inversa de la elasticidad de oferta regional** regresando crecimiento salarial sobre crecimiento de empleo con shifters Bartik de demanda — el **espejo exacto de tu regresión**. Lo citas para justificar tu especificación por simetría. | ⬇ conseguir |
| 6 | **Jaeger, Ruist & Stuhler (2018)**, *Shift-Share Instruments and the Impact of Immigration*, NBER WP 24285 | **La crítica que te van a hacer en el seminario:** los enclaves predicen migración pasada *y* demanda local persistente; el estimador mezcla respuesta de corto y largo plazo. Determina tu elección de año base lejano, controles pre-periodo y (posible) diseño de dos instrumentos. | ⬇ conseguir |

---

## Bloque 2 — El objeto estimado y su inferencia

| # | Referencia | Por qué | Estado |
|---|---|---|---|
| 7 | **Hamermesh (1993)**, *Labor Demand*, Princeton UP (cap. de leyes Hicks-Marshall) + **Lichter, Peichl & Siegloch (2015)**, *The Own-Wage Elasticity of Labor Demand: A Meta-Regression Analysis*, EER 80, 94–119 | Qué determina ε_D y qué magnitud es defendible (**\|ε_D\| ≈ 0.25–0.7**, sobre 942 estimaciones). Sin este ancla no puedes decir si tu número es razonable o un artefacto. | ⬇ conseguir |
| 8 | **Monte, Redding & Rossi-Hansberg (2018)**, *Commuting, Migration, and Local Employment Elasticities*, AER 108(12), 3855–3890 | **Tu rival conceptual (V1) y tu marco de interpretación.** La elasticidad de empleo local depende de la apertura al commuting → tu ε_D por mercado **no es un parámetro tecnológico**, mezcla σ con fuga espacial. Tienes que decirlo en la primera página (tú la estimas *design-based*; ellos la derivan estructuralmente). Citado en la nota de Aldeco. | ⬇ conseguir |
| 9 | **Adão, Kolesár & Morales (2019)**, *Shift-Share Designs: Theory and Inference*, QJE 134(4), 1949–2010 | **Tus errores estándar.** Los residuos están correlacionados entre mercados con shares parecidos; clustering por CZ no basta. Sin esto la tabla principal no pasa referee. Ver también la tensión AKM ↔ SAR en el Bloque 6. | ⬇ conseguir |

---

## Bloque 3 — México, migración interna, y el push nacional

| # | Referencia | Por qué | Estado |
|---|---|---|---|
| 10 | **Boustan, Fishback & Kantor (2010)**, *The Effect of Internal Migration on Local Labor Markets: American Cities during the Great Depression*, JOLE 28(4) | El análogo más cercano a **Q2 (migración interna como shifter de oferta)**: cómo se arma el instrumento cuando el flujo es doméstico y **cómo se maneja el desplazamiento de nativos** (= tu amenaza espacial, Bloque 6). | ⬇ conseguir |
| 11 | **Monras (2020)**, *Immigration and Wage Dynamics: Evidence from the Mexican Peso Crisis*, JPE | Plantilla de cómo se construye el **shift nacional con datos mexicanos** (crisis del peso 95 como push) y de la dinámica de ajuste salarial post-shock. | ⬇ conseguir |
| 12 | **Aldeco, Calderón, Chiquiar, Hanson, Pérez Pérez & Velázquez (2024)**, *Local Labor Markets in Mexico*, Banxico/EconLab | **Relectura quirúrgica**, no completa: **eq. (2) p.11** (definición del Bartik), **§3.3 p.11** ("*such as the elasticity of labor supply*" ← tu hueco) y **footnote 18 p.11** (módulos de migración "*within project's scope in the next stage*" ← oportunidad + aviso de scooping, V4). | ✅ en repo (`papers/00_nucleo_tema/{2BB5ECD9…}.pdf`) |

---

## Bloque 4 — Puente al modelo (solo con el diseño ya cerrado)

| # | Referencia | Por qué | Estado |
|---|---|---|---|
| 13 | **Raval (2019)**, *The Micro Elasticity of Substitution and Non-Neutral Technology*, RAND 50(1), 147–167 | Cómo se recupera σ (K–L) con variación de **salarios locales** — exactamente la variación de los 777 mercados. Es el eslabón ε_D → σ. Leer junto con Oberfield-Raval (2021), Bloque 5-C. | ⬇ conseguir |
| 14 | **Ulyssea (2010)**, *Regulation of Entry, Labor Market Institutions and the Informal Sector*, JDE 91, 87–99 | Lado de producción CES formal/informal: la plantilla que **interpreta** tu ε_D y habilita la descomposición por sector. | ✅ en repo (`papers/00_nucleo_tema/ulyssea 2010.pdf`) |

---

## Bloque 5 — La arquitectura: elasticidad estimada → pregunta estructural *(nuevo en v3)*

**Por qué existe este bloque.** El veredicto §0 de la bibliografía canónica dice que "no hay un solo paper molde que clonar". Eso sigue siendo cierto para el **objeto** (ε_D en mercados locales de un país en desarrollo, con margen formal/informal). Pero **sí hay molde para la arquitectura**, y no estaba documentado. Estos nueve papers estiman una elasticidad con un diseño creíble y después la usan para contestar una pregunta estructural — que es literalmente Q1.

### Familia A — elasticidad *design-based* → EG espacial → contrafáctico de incidencia

| Referencia | Por qué |
|---|---|
| **Suárez Serrato & Zidar (2016)**, *Who Benefits from State Corporate Tax Cuts? A Local Labor Markets Approach with Heterogeneous Firms*, AER 106(9), 2582–2624 | **El más cercano a tu arquitectura de todos.** Estima elasticidades locales de oferta **y demanda** de trabajo con variación cuasi-experimental y luego las invierte dentro de un EG espacial con firmas heterogéneas para contestar incidencia (quién paga el impuesto). Es exactamente "la forma reducida disciplina la estructura". **Bonus de valor referee:** tiene **Comment y Reply publicados en AER** que cuestionan precisamente esos estimados — leer los tres te enseña cómo se ataca un ejercicio de este tipo antes de que te lo hagan a ti. |
| **Kline & Moretti (2014)**, *Local Economic Development, Agglomeration Economies, and the Big Push: 100 Years of Evidence from the Tennessee Valley Authority*, QJE 129(1), 275–331 | Elasticidades locales de un cuasi-experimento incrustadas en equilibrio espacial para hacer análisis de bienestar. ⚠️ **Nota de cita:** este **no** es el Kline-Moretti (2014) que la bibliografía canónica excluyó — aquella exclusión (§1, "Nota sobre exclusiones deliberadas") se refiere a *People, Places and Public Policy*, **Annual Review of Economics** 6, 629–662, descartado por tangencial. Son dos papers distintos del mismo par de autores y el mismo año; **el QJE sí es on-point.** |
| **Diamond (2016)**, *The Determinants and Welfare Implications of US Workers' Diverging Location Choices by Skill: 1980–2000*, AER 106(3), 479–524 | Demanda laboral local estimada con Bartik dentro de un modelo estructural de elección de localidad. Plantilla de la capa "el modelo interpreta". |
| **Notowidigdo (2020)**, *The Incidence of Local Labor Demand Shocks*, JOLE 38(3), 687–725 | **PROMOVIDO en v3** (estaba en Bloque B de la bibliografía con rank 4). Shock Bartik + equilibrio espacial para incidencia por nivel de calificación: la misma arquitectura, en el lado espejo (demanda en vez de oferta). |

### Familia B — shock de oferta → curva de demanda → parámetro CES

**Esta es tu identificación, y hasta v3 no la citabas.** Toda esta familia hace lo que tú vas a hacer: usar un shock de oferta migratoria para trazar la curva de demanda y mapear el resultado a una estructura CES.

| Referencia | Por qué |
|---|---|
| **Borjas (2003)**, *The Labor Demand Curve Is Downward Sloping: Reexamining the Impact of Immigration on the Labor Market*, QJE 118(4), 1335–1374 | El título es tu tesis. Oferta migratoria para trazar la demanda, y mapeo del resultado a una CES anidada. |
| **Ottaviano & Peri (2012)**, *Rethinking the Effect of Immigration on Wages*, JEEA 10(1), 152–197 | La réplica: **cómo la anidación de la CES cambia el σ que recuperas del mismo shock.** Con Borjas te da el debate completo sobre *qué* elasticidad estás estimando realmente. Crítico para no vender tu ε_D como algo que no es. |
| **Card (2012)**, *The Elusive Search for Negative Wage Impacts of Immigration*, JEEA 10(1) | En el mismo número que Ottaviano-Peri; cierra el debate por el lado del diseño de área (que es el tuyo). |
| **Llull (2018)**, *Immigration, Wages, and Education: A Labour Market Equilibrium Structural Model*, REStud 85(3), 1852–1896 | La versión totalmente estructural del mismo shock, con respuesta endógena de educación. El extremo "modelo primero" del espectro — útil para posicionar tu punto intermedio. |

### Familia C — micro-elasticidad → agregación → pregunta macro

| Referencia | Por qué |
|---|---|
| **Oberfield & Raval (2021)**, *Micro Data and Macro Technology*, Econometrica 89(2), 703–732 (DOI 10.3982/ECTA12807) | **Completa a Raval (2019), que ya es tu eslabón ε_D → σ.** Estiman σ micro con variación de salarios locales, prueban el **teorema de agregación micro→macro**, y con eso responden una pregunta macro (la caída de la participación del trabajo). Es el molde metodológico exacto de tu capa "el modelo interpreta el momento reducido". |

### Nota de posicionamiento (para la primera página)

**Ninguno de los nueve tiene dimensión formal/informal, y ninguno estima ε_D para mercados locales de un país en desarrollo.** El hueco del *objeto* sigue intacto. Lo que estos papers te dan es el molde de la *arquitectura* — y citarlos es lo que impide que el seminario lea tu diseño como ad hoc.

---

## Bloque 6 — Lo espacial: qué sobrevive de la Ruta 2 *(nuevo en v3)*

La Ruta 2 (spatial lag/Durbin con **W = matriz de commuting de los 777**) quedó degradada por Q1. Pero "lo espacial" son **tres cosas distintas**, y solo una es opcional:

**(i) Amenaza a la validez de ε_D — OBLIGATORIA.** Si el empujón de oferta hacia el mercado *l* desplaza nativos hacia *l'*, tus mercados de control también están tratados: **violación de SUTVA → ε_D sesgada.** Ya está cubierto por lecturas del Bloque 1 y 3 sin que estuviera nombrado como espacial: Card (2001) lo lleva en el título (*native outflows*) y Boustan-Fishback-Kantor (2010) lo maneja para migración **interna**, que es tu caso (Q2).
⚠️ **Pendiente documental:** §5 de `ruta_empirica_shift_share_migracion_2026-07-23.md` lista las amenazas al diseño y **no incluye ésta**. Falta agregarla con su mitigación.

**(ii) Interpretación del objeto — OBLIGATORIA.** MRRH (#8) + Adão-Arkolakis-Esposito (abajo): tu ε_D local mezcla tecnología con fuga espacial. Esto **es** V1.

**(iii) Spatial lag/Durbin con W de commuting como pregunta propia — OPCIONAL.** El hueco vacío que identificó la bibliografía (nadie usa la matriz que define los 777 como W) sigue vacío. **Es tu segundo paper, no el núcleo** — y sale mejor *después*, porque necesita una primera etapa creíble que el paper de ε_D ya habría construido.

### La advertencia técnica: por qué el SAR NO va en el núcleo

Los instrumentos shift-share están **mecánicamente correlacionados en el espacio**: mercados con shares de enclave parecidos reciben shocks predichos parecidos, estén o no económicamente conectados. Esa es la razón de existir de AKM (2019). Y ahí choca todo:

- **AKM (2019) dice:** esa correlación es un *nuisance* → corrige los errores estándar.
- **SAR/SDM dice:** esa correlación es el *parámetro de interés* → modélala con ρW.

**No se pueden hacer las dos ingenuamente.** Meterle un spatial lag a residuos cuya correlación espacial proviene del diseño del instrumento produce "spillovers económicos" que en parte son artefacto de la estructura de shares.

Peor para identificación: un SAR con regresor endógeno obliga a instrumentar también `W·Δln L`, y separar ρ de β exige que **la estructura espacial del instrumento difiera de W**. En tu caso W (commuting) *es lo que define los mercados* y está correlacionada con la red de enclaves — la gente migra a donde ya hay paisanos y hace commuting dentro de esa misma zona. **Esa condición está al filo de fallar.** Ésta es la razón principal para dejar el SAR fuera del núcleo.

### Qué hacer en su lugar

- **(a) Estimar a dos niveles de agregación** — mercado local y agrupaciones gruesas construidas de la misma matriz de commuting. Si ε_D cambia sistemáticamente con la agregación, **eso es** tu evidencia de spillovers, y es limpia. Método estándar de la literatura de migración; el mapa de por qué los estimados difieren por nivel está en **Dustmann, Schönberg & Stuhler (2016)**, JEP 30(4) (ya en must-get).
- **(b) Exposición del vecino como regresor, estilo Helm (2020)** — exposición indirecta *leave-own-out* de los mercados conectados por commuting. Da efecto directo e indirecto **sin imponer ρW**.
- **(c) SEs de AKM siempre**, independientemente de (a) y (b).

### Lecturas del Bloque 6

| Referencia | Movimiento | Por qué |
|---|---|---|
| **Helm (2020)**, *National Industry Trade Shocks, Local Labour Markets, and Agglomeration Spillovers*, REStud 87(3), 1399–1431 | **PROMOVIDO** (estaba en Bloque D de la bibliografía) | Tu implementación práctica de (b): spillovers entre mercados locales vía exposición indirecta a shocks de industrias vecinas. |
| **Adão, Arkolakis & Esposito**, *General Equilibrium Effects in Space: Theory and Measurement*, NBER WP 25544 | **NUEVO** | El argumento formal de por qué (a) y (b) importan: los efectos indirectos vía links espaciales **refuerzan** el efecto propio, así que los estimados shift-share locales **subestiman** el efecto total. ⚠️ R&R en *AEJ: Macro* (feb 2025) — **verificar publicación al citar.** |
| **Borusyak & Hull (2023)**, *Nonrandom Exposure to Exogenous Shocks*, Econometrica 91(6), 2155–2185 | **NUEVO**, opcional | El arreglo formal (recentrado) cuando la estructura del instrumento genera exposición sistemática y no aleatoria. |
| Anselin (2003) · LeSage & Pace (2009) · Corrado & Fingleton (2012) · Molho (1995) | **Se mantienen degradados** | Solo si activas (iii). |

---

## Must-get en paralelo (pedir/descargar ya)

- **Aldeco, Chiquiar, Pérez Pérez & Salcedo**, *Estimación de la elasticidad de la oferta de trabajo en México*, mimeo Banxico → **tu paper-espejo obligado**. Confirmado en las referencias de la nota de 2024, pero no indexado. Pedir a **econlab@banxico.org.mx**.
- **Hong & McLaren**, *Are Immigrants a Shot in the Arm for the Local Economy?*, NBER WP → cuantifica el canal "migrantes = consumidores"; es la evidencia con la que justificas restringir la estimación al **sector transable**.
- **Caballero, M. E., Cadena, B. & Kovak (2021/2023)**, *The International Transmission of Local Economic Shocks Through Migrant Networks*, NBER WP 28696 → *Journal of International Economics* 145 (2023), 103832 → construcción de la red migratoria MX–EE.UU.; **solo si activas la robustez con red EE.UU.** Su antecedente **Cadena & Kovak (2016)**, AEJ: Applied 8(1), 257–290, es la plantilla de *supply shifter*.
- **Dustmann, Schönberg & Stuhler (2016)**, *The Impact of Immigration: Why Do Studies Reach Such Different Results?*, JEP 30(4) → mapa de por qué los estimados difieren por nivel de agregación (skill-cell vs área vs mixto). **Ahora es doblemente necesario:** sostiene la estrategia (a) del Bloque 6.

---

## Orden de lectura recomendado

1. **Bloque 1 completo** — el diseño. Sin esto no escribes propuesta.
2. **Bloque 5, Familias A y C** (Suárez Serrato-Zidar → Oberfield-Raval) — la arquitectura, para saber hacia dónde apunta el diseño.
3. **Bloque 5, Familia B** (Borjas + Ottaviano-Peri) — qué objeto estás estimando realmente.
4. **Bloques 2 y 3** en paralelo con el esbozo del proceso de estimación.
5. **Bloque 6** al escribir la sección de amenazas.
6. **Bloque 4** solo con el diseño ya cerrado.

---

## Estado del acervo

De todo el top, **solo 2 PDFs están en el repo** (Aldeco 2024 y Ulyssea 2010, ambos en `papers/00_nucleo_tema/`). Todo el Bloque 1 —el núcleo del diseño— y todo el Bloque 5 están pendientes de rescate manual.

Destinos sugeridos al descargar:
- Bloques 1, 3, 6 → `propuesta_final/papers/06_shift_share_migracion/`
- Bloque 5 → `propuesta_final/papers/07_arquitectura_elasticidad_estructural/`

---

## Notas de cita (v3)

Verificadas en línea el 2026-08-07 contra AEA / Econometric Society / Oxford Academic / NBER / RePEc:

1. **Oberfield & Raval (2021)** → Econometrica **89(2), 703–732**, DOI 10.3982/ECTA12807.
2. **Suárez Serrato & Zidar (2016)** → AER **106(9), 2582–2624**; existen Comment y Reply publicados en AER.
3. **Kline & Moretti (2014)** → QJE **129(1), 275–331**. ⚠️ Distinto del Kline-Moretti (2014) *Annual Review of Economics* excluido en la bibliografía canónica.
4. **Diamond (2016)** → AER **106(3), 479–524**.
5. **Borjas (2003)** → QJE **118(4), 1335–1374**.
6. **Ottaviano & Peri (2012)** → JEEA **10(1), 152–197**.
7. **Llull (2018)** → REStud **85(3), 1852–1896**.
8. **Borusyak, Hull & Jaravel (2025)** → JEP **39(1), 181–204**.
9. **Borusyak & Hull (2023)** → Econometrica **91(6), 2155–2185**, DOI 10.3982/ECTA19367.
10. **Adão, Arkolakis & Esposito** → NBER WP 25544, R&R *AEJ: Macro* (feb 2025). ⚠️ **Sin publicación confirmada — reverificar antes de citar.**

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]].*
