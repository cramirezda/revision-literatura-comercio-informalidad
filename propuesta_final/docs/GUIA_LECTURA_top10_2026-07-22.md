# Guía de lectura — Elasticidad de demanda de trabajo en mercados locales (MX) vía EG estático

**Fecha:** 2026-07-22 · Para: Carlos Ramírez (ITAM) · Objetivo: leer esta semana para formalizar la propuesta en pocos días.
**Prioridad elegida:** *teoría/modelos primero*. Ver viabilidad en `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md`.

---

## TOP 10 para esta semana (en orden de lectura)

> Meta: llegar a la reunión con (i) un modelo-base elegido, (ii) claridad de identificación, (iii) el rol de datos.

| # | Referencia | Por qué leerlo primero | Estado |
|---|---|---|---|
| 1 | **Ulyssea (2010)**, *Regulation of entry, labor market institutions and the informal sector*, JDE 91:87-99 | Modelo dos-sectores formal/informal con **agregador CES** (σ=1/(1−ρ)) y demanda de trabajo derivada de PMg. El lado de producción es tu plantilla más directa. | ✅ en repo (`ulyssea 2010.pdf`) |
| 2 | **Amaral & Quintin (2006)**, *A competitive model of the informal sector*, JME | GE **competitivo** (≈estático) de informalidad: formal/informal difieren por acceso a financiamiento y sustitución K–L no calificado. El más cercano a "EG estático con informalidad". | ⬇ conseguir |
| 3 | **Raval (2019)**, *The micro elasticity of substitution and non-neutral technology*, RAND | **El método** para recuperar ε_D estructural: estima σ K–L con variación de **salarios locales** — justo la variación de los 777 mercados. | ⬇ conseguir |
| 4 | **Monte, Redding & Rossi-Hansberg (2018)**, *Commuting, Migration, and Local Employment Elasticities*, AER | Puente estructural↔espacial: elasticidad de empleo local depende de la **apertura al commuting** (gravity). Une tus dos rutas. Citado en el doc de Aldeco. | ⬇ conseguir |
| 5 | **Satchi & Temple (2009)**, *Labor markets and productivity in developing countries*, RED | GE con informalidad + migración **calibrado a México**. Referencia de "estructura macro con informalidad". | ⬇ conseguir |
| 6 | **Aldeco et al. (2024)**, *Local Labor Markets in Mexico*, Banxico | Tu **base de datos**: definición de 777 mercados, proxy de informalidad, Bartik, crosswalk municipio→mercado. Léelo como manual de datos. | ✅ en repo (`{2BB5ECD9…}.pdf`) |
| 7 | **Hamermesh (1993)** *Labor Demand* (cap. Hicks-Marshall) **+ Lichter, Peichl & Siegloch (2015)** meta-regresión ε_D | El objeto que estimas: qué determina ε_D y qué magnitudes esperar (|ε_D|≈0.25–0.7). | ⬇ conseguir |
| 8 | **Galiani & Weinschelbaum (2012)**, *Modeling informality formally: households and firms*, Econ. Inquiry | Microfundamento del margen formal/informal (firmas y trabajadores eligen sector; dos mercados). | ⬇ conseguir |
| 9 | **Anselin (2003)** *Spatial externalities, multipliers…* **+ LeSage & Pace (2009)** intro | Ruta espacial: efectos directos/indirectos, matriz W, multiplicadores. Necesario para la capa reduced-form/robustez. | ⬇ conseguir |
| 10 | **Goldsmith-Pinkham, Sorkin & Swift (2020)**, *Bartik: What, When, Why, How*, AER | La base **trae Bartik** y estos identifican **oferta** (no demanda): entender esto es clave para tu framing de identificación. | ⬇ conseguir |

**Must-get en paralelo (pídelos ya):**
- **Aldeco, Chiquiar, Pérez Pérez & Salcedo**, *Estimación de la elasticidad de la OFERTA de trabajo en México* (mimeo Banxico) → tu paper-espejo obligado. Pedir a **econlab@banxico.org.mx**.
- **Meghir, Narita & Robin (2015)**, *Wages and Informality in Developing Countries*, AER → estimación estructural de salarios con informalidad (canónico).

---

## Referencias canónicas rankeadas por bloque (semilla para el researcher + guía completa)

### A. Datos y definición de mercados locales / shift-share
1. Aldeco et al. (2024) — Local Labor Markets in Mexico [✅]
2. Aldeco, Chiquiar, Pérez Pérez, Salcedo — Elasticidad de la oferta (mimeo) [companion]
3. Autor, Dorn & Hanson (2013) — The China Syndrome, AER [✅ en `papers/01_trade_labor/`]
4. Tolbert & Sizer (1996); Fowler & Jensen (2020) — commuting zones
5. Goldsmith-Pinkham, Sorkin & Swift (2020) — Bartik
6. Borusyak, Hull & Jaravel (2022) — shift-share quasi-experimental, REStud
7. Adão, Kolesár & Morales (2019) — shift-share inference, QJE

### B. Elasticidad de demanda de trabajo (empírica + analítica)
8. Hamermesh (1993) — Labor Demand [canónico]
9. Lichter, Peichl & Siegloch (2015) — meta ε_D
10. Raval (2019) — elasticidad de sustitución con salarios locales
11. Clark & Freeman (1980) — how elastic is labor demand, REStat

### C. EG estructural dos-sectores formal/informal
12. Ulyssea (2010) [✅]
13. Amaral & Quintin (2006)
14. Galiani & Weinschelbaum (2012)
15. Satchi & Temple (2009) — calibrado México
16. Ulyssea (2018) — Firms, Informality and Development, AER [✅ en `papers/01_trade_labor/`]
17. Meghir, Narita & Robin (2015) — Wages and Informality, AER
18. La Porta & Shleifer (2014) — Informality and Development, JEP

### D. Econometría espacial / redes
19. Anselin (2003) — spatial externalities & multipliers
20. LeSage & Pace (2009) — Introduction to Spatial Econometrics [texto]
21. Molho (1995) — spatial autocorrelation, desempleo local (migración+commuting)
22. Helm (2020) — trade shocks, local labor markets, spillovers, REStud
23. Corrado & Fingleton (2012) — "Where is the economics in spatial econometrics" [caveat W]
24. Monte, Redding & Rossi-Hansberg (2018) — puente estructural↔espacial

### E. Contexto México / identificación (supply shifters)
25. Chiquiar (2008) — regional wage differentials, Stolper-Samuelson, JIE
26. Fernández & Meza (2015) — informal employment & business cycles, RED
27. Leyva & Urrutia (2020) — informality, labor regulation, business cycle, JIE
28. Busso, Fazio & Levy (2012) — (In)formal and (un)productive, misallocation MX
29. Alvarez & Ruane (2019) — informality and aggregate productivity, MX
30. Cadena & Kovak (2016); Caballero, Cadena & Kovak (2021) — redes migratorias como supply shifter

*El `researcher` expandirá esta semilla a ~30 canónicas con anotación, gap-map y diseño (formato lista + guía, sin descargar PDFs). Ver [[project-tesis-elasticidad-demanda-local]].*
