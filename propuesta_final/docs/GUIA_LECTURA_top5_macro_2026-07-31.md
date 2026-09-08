# Guía de lectura — TOP 5 para **definir el modelo ya**

**Fecha:** 2026-07-31 · Para: Carlos Ramírez (ITAM)
**Contexto:** `brecha_producto_misallocation_local_2026-07-31.md` (memo del giro) · Reordena en prioridad —no anula— a `GUIA_LECTURA_top10_2026-07-22.md`

**Criterio de orden:** lo que te permite **escribir las ecuaciones**. Nada más. Las lecturas que afectan el *framing* (por qué importa, contra quién compites) bajan a acompañamiento.

> **Nota de riesgo, una sola vez:** Alvarez & Ruane (2024) puede debilitar la premisa "informalidad → estancamiento". Pero afecta **lo que afirmas que tu modelo explica**, no **las ecuaciones que escribes**. Por eso es defendible construir el modelo primero: si la premisa se mueve, cambia la introducción y el contrafactual que destacas, no el andamiaje. Léelo antes de la reunión con el asesor, no antes de escribir.

---

## TOP 5 — leer en este orden

| # | Referencia | Qué bloque del modelo te da | Estado |
|---|---|---|---|
| **1** | **Ulyssea (2010)**, *Regulation of entry, labor market institutions and the informal sector*, JDE 91:87–99 | **El bloque de producción, listo para copiar.** Bien final CES sobre intermedios formal/informal: `Y=(a·Y_F^ρ+(1−a)·Y_I^ρ)^{1/ρ}`, σ=1/(1−ρ), con PMg `p_F=a·Y_F^{ρ−1}·Y^{1−ρ}`. Toma la estructura de producción; ignora el matching. | ✅ **en repo** (`papers/00_nucleo_tema/ulyssea 2010.pdf`) — **empieza hoy** |
| **2** | **Antón & Leal (2021)**, *Taxing Labor Income in an Economy with High Employment Informality*, *Economía* | **La arquitectura completa.** GE **estático** de elección ocupacional con heterogeneidad en habilidad laboral y empresarial, estructura detallada de **cuñas** (ISR + subsidios al empleo formal), **calibrado a México**. Es lo más cercano que existe a lo que quieres escribir — plantilla y competidor a la vez. | ⬇ conseguir |
| **3** | **Hamermesh (1993)**, *Labor Demand*, cap. de **Hicks-Marshall** | **La ecuación del parámetro objetivo.** Te da el mapeo explícito ε_D = f(σ, participaciones factoriales, elasticidad de demanda del producto). Es literalmente lo que la crítica referee te exigió escribir en la página 1 (V1). Sin esto no puedes definir *qué* estimas. | ⬇ conseguir |
| **4** | **Raval (2019)**, *The micro elasticity of substitution and non-neutral technology*, RAND | **Cómo se estima σ.** Recupera la elasticidad de sustitución usando variación de **salarios locales** — exactamente la variación de tus 777 mercados. Es lo que convierte tu ε_D en *estimada* y no *calibrada*: el diferenciador central frente a toda la literatura mexicana. | ⬇ conseguir |
| **5** | **Baqaee & Farhi (2020)**, *Productivity and Misallocation in General Equilibrium*, QJE | **Cómo el modelo produce la respuesta.** Agregación no paramétrica con distorsiones, separando eficiencia **técnica** de **asignativa**. Es tu salida al choque "estático ≠ crecimiento". El más pesado de los cinco: presupuesta tiempo, y déjalo para cuando ya tengas los bloques 1–4. | ⬇ conseguir |

**Los dos primeros son el 70% del trabajo.** Ulyssea te da la función de producción; Antón & Leal te da cómo meterle cuñas y cerrar el equilibrio en México. Con esos dos ya puedes escribir un primer borrador de modelo.

---

## Acompañamiento (no bloquean escribir el modelo)

Estas afectan calibración y framing, no ecuaciones. Léelas en los huecos.

| Referencia | Para qué | Cuándo |
|---|---|---|
| **Alcaraz, Chiquiar et al. (2015)** — 10–20% de informalidad involuntaria | **Parámetro de segmentación**, calibrado en vez de asumido. Contrasta con Duval-Hernández (2022), ~80%. Lo firma el mismo Chiquiar de tu base. | Al calibrar |
| **Levy (2008 / 2018)** | El origen de la descomposición τ = contribución no valorada + subsidio implícito. No lo leas completo: te interesa el capítulo de la cuña. | Al construir τ |
| **Alvarez & Ruane (2024)**, EER | Desacopla informalidad y PTF en México. Define **qué puedes afirmar**, no qué puedes escribir. | Antes de la reunión |
| **Hanson (2010)**, JEL | El mapa del debate, del mismo Hanson que coautorea tu base. Survey → rápido. Es tu introducción casi servida. | Al escribir la intro |
| **Tablas de cuotas IMSS** (LSS vigente + años previos) | No es lectura académica: es tu fuente de τ. Necesarias para verificar la variación espacial de la cuña (§3.3 del memo). | En paralelo, ya |

**Pídelos ya (no bloquean):** el mimeo **Aldeco, Chiquiar, Pérez Pérez & Salcedo** sobre elasticidad de **oferta** — ahora es un **insumo directo** (ε_S), no solo un paper-espejo. A econlab@banxico.org.mx.

---

## Qué pasa con el TOP 10 anterior (22-jul)

No se anula: se reordena. Bajo el framing A (ε_D como producto final) esas diez eran el camino completo. Bajo el framing B (ε_D como insumo de un ejercicio de mala asignación) tres suben, tres siguen, y cuatro bajan.

### El TOP 10 original, tal cual quedó

1. **Ulyssea (2010)**, JDE — modelo dos sectores, agregador CES ✅ *en repo*
2. **Amaral & Quintin (2006)**, JME — GE competitivo de informalidad
3. **Raval (2019)**, RAND — σ con salarios locales
4. **Monte, Redding & Rossi-Hansberg (2018)**, AER — puente estructural↔espacial
5. **Satchi & Temple (2009)**, RED — GE con informalidad calibrado a México
6. **Aldeco et al. (2024)**, Banxico — tu base de datos ✅ *en repo*
7. **Hamermesh (1993)** + **Lichter, Peichl & Siegloch (2015)** — qué es ε_D y qué magnitudes esperar
8. **Galiani & Weinschelbaum (2012)**, Econ. Inquiry — microfundamento del margen F/I
9. **Anselin (2003)** + **LeSage & Pace (2009)** — econometría espacial
10. **Goldsmith-Pinkham, Sorkin & Swift (2020)**, AER — Bartik

*Must-get en paralelo: mimeo de oferta (Aldeco et al.); Meghir, Narita & Robin (2015), AER.*

### Cómo se reordena

| Movimiento | Cuáles | Por qué |
|---|---|---|
| **⬆ Suben a núcleo** | #1 Ulyssea, #3 Raval, #7 Hamermesh | Son ahora los bloques 1, 4 y 3 del nuevo TOP 5. Hamermesh sube más que ninguno: pasó de "contexto" a **la ecuación que define tu objeto**. |
| **= Se mantienen** | #6 Aldeco (manual de datos), #10 GPSS (los Bartik identifican **oferta**, no demanda), #7-b Lichter et al. (magnitudes \|ε_D\|≈0.25–0.7 — ahora importan más porque **escalan tu contrafactual** vía Harberger) | Sin cambio de rol. |
| **⬇ Bajan** | #4 MRRH | Era **existencial** bajo el framing A (tenías que diferenciar tu ε_D de la suya — vulnerabilidad V1). Bajo B, ε_D ya no es el producto final. Sigue vivo si conservas la capa espacial. |
| **⬇ Bajan** | #2 Amaral-Quintin, #5 Satchi-Temple, #8 Galiani-Weinschelbaum | Eran el menú de plantillas. **Antón & Leal (2021) los reemplaza** por ser estático, con cuñas explícitas y calibrado a México. Consérvalos como referencia de microfundamento. |
| **⬇ Bajan** | #9 Anselin + LeSage-Pace | La ruta espacial quedó como **capítulo de robustez** (rec. 3 de la crítica referee, §6.3 del memo). Léelos cuando llegues ahí. |

### Entran nuevas al radar

- **Leal-Ordóñez (2014)**, RED — el benchmark cuantitativo mexicano (19–34%). Tu número se comparará contra el suyo: importa saber **qué incluye él que tú no** (capital, entrada, competencia monopolística).
- **Misch et al. (2020)** — mala asignación vs. ingreso per cápita **entre estados**. La versión estatal de tu ejercicio; tú bajas a 777 mercados.
- **Zárate (2022)** — mala asignación espacial + informalidad, CDMX. El vecino más cercano por el lado espacial.
- **Busso, Fazio & Levy (2012)** — antecedente de misallocation por informalidad en México.

---

## Ruta de dos semanas (model-first)

**Semana 1 — escribir el modelo.**
Ulyssea (hoy, ya está en el repo) → Antón & Leal → Hamermesh. Entregable al final: **la ecuación del parámetro objetivo escrita** y el esqueleto del modelo (producción, elección de sector, cuña). Eso es exactamente la cirugía V1 pendiente.

**Semana 2 — cerrar estimación y agregación.**
Raval → Baqaee-Farhi. En paralelo: verificación numérica de la variación espacial de τ y correo al EconLab. Entregable: cómo se estima σ y cómo el modelo produce el contrafactual.

**Acompañamiento continuo:** Alvarez-Ruane y Hanson antes de la reunión con el asesor; Alcaraz-Chiquiar al calibrar.

---

## Referencias con enlace

**Núcleo (TOP 5)**
1. [Regulation of entry, labor market institutions and the informal sector](https://consensus.app/papers/details/b7645c54c4e1592b9352a26fc075cf3d/?utm_source=claude_desktop) — Ulyssea (2010), *JDE* ✅ *en repo*
2. [Taxing Labor Income in an Economy with High Employment Informality](https://consensus.app/papers/details/5474feffa5995a6f88e78274d6a7a112/?utm_source=claude_desktop) — Antón & Leal (2021), *Economía*
3. Hamermesh (1993), *Labor Demand*, Princeton UP — libro, sin enlace Consensus. Complemento: [meta-regresión de ε_D](https://consensus.app/papers/details/d9b1a680fa6b54509eb906041fd2507a/?utm_source=claude_desktop) — Lichter, Peichl & Siegloch (2015)
4. [The micro elasticity of substitution and non-neutral technology](https://consensus.app/papers/details/f892ab362d385ae4a31bf7bbfa55d839/?utm_source=claude_desktop) — Raval (2019), *RAND*
5. [Productivity and Misallocation in General Equilibrium](https://consensus.app/papers/details/314b4f322d46510c90fa5ff421e218d9/?utm_source=claude_desktop) — Baqaee & Farhi, *QJE*, 509 citas

**Acompañamiento**
- [Informality and Segmentation in the Mexican Labor Market](https://consensus.app/papers/details/756472845f175c74899589bcc88e8db7/?utm_source=claude_desktop) — Alcaraz, Chiquiar et al. (2015) · contrapunto: [Choices and Constraints](https://consensus.app/papers/details/2bd8fc2ec3ba57d0875e64d16a0e72ba/?utm_source=claude_desktop) — Duval-Hernández (2022)
- [Good Intentions, Bad Outcomes](https://consensus.app/papers/details/b2cc19b610d15e58baa26021a064e3f1/?utm_source=claude_desktop) — Levy (2008) · [Under-Rewarded Efforts](https://consensus.app/papers/details/d70ed405e4815b84b1495ca8f9252b48/?utm_source=claude_desktop) — Levy (2018)
- [Informality and aggregate productivity: The case of Mexico](https://consensus.app/papers/details/c078916d1c2452ae8f4ad3455d4a46a6/?utm_source=claude_desktop) — Alvarez & Ruane (2024), *EER*
- [Why Isn't Mexico Rich?](https://consensus.app/papers/details/f620d95ebd9a59748b1e892d4a0bec8a/?utm_source=claude_desktop) — Hanson (2010), *JEL*

**Radar**
- [Tax collection, the informal sector, and productivity](https://consensus.app/papers/details/bb58f06e3c245bd5a6a8a2e5e1d98ceb/?utm_source=claude_desktop) — Leal-Ordóñez (2014), *RED*
- [The Drivers and Consequences of Resource Misallocation: Mexican Industries and States](https://consensus.app/papers/details/b43501f36f855522bbb2a60b0094df27/?utm_source=claude_desktop) — Misch et al. (2020)
- [Spatial Misallocation, Informality, and Transit Improvements: Mexico City](https://consensus.app/papers/details/9cd08b89b4ca52ce96d406f7b4d4122a/?utm_source=claude_desktop) — Zárate (2022)
- [(In)Formal and (Un)Productive](https://consensus.app/papers/details/56f348c559e05e309ba7c639f22bb4e3/?utm_source=claude_desktop) — Busso, Fazio & Levy (2012)

---

*Ver [[project-tesis-elasticidad-demanda-local]]. Documentos hermanos: `GUIA_LECTURA_top10_2026-07-22.md` (framing anterior), `brecha_producto_misallocation_local_2026-07-31.md` (memo del giro).*
