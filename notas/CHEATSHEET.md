# Cheatsheet — Revisión de Literatura
## Comercio, Informalidad y Mercados Laborales en México

## Métodos Empíricos Disponibles

| Método | Cuándo usar | Papers de referencia |
|--------|-------------|---------------------|
| Diff-in-Diff (DiD) | Evaluar efecto de shocks comerciales con treatment/control | Autor et al. 2013, Dix-Carneiro & Kovak 2017 |
| Instrumental Variables (IV) | Endogeneidad en exposición comercial | Méndez 2015, Autor et al. 2013 |
| Synthetic Control | Países/regiones pequeños, pocos tratados | Abadie et al., Cattaneo et al. 2025 |
| Local Projections | Dinámicas temporales, impulse responses | Jordà 2005 |
| Matching Models | Sorting trabajador-firma, formal-informal | Meghir et al. 2015, Bontemps et al. 1999 |
| Structural Estimation | Calibración modelo equilibrio general | Melitz 2003, Ulyssea 2018 |
| Gaussian Mixtures | Detectar subgrupos latentes (formal/informal) | mclust, FMM literature |
| SMM (Simulated Moments) | Estimación modelos estructurales con informality | Meghir et al. 2015 |

## Hallazgos Empíricos Clave

1. **Trade shocks → informalidad**: La competencia importadora china aumenta informalidad en Brasil y México (Dix-Carneiro & Kovak 2017, Méndez 2015)
2. **Informalidad como buffer**: El sector informal absorbe trabajadores desplazados por shocks comerciales negativos (Dix-Carneiro & Kovak 2017)
3. **Efectos persistentes**: Los efectos del trade liberalization crecen con el tiempo, no se disipan (Dix-Carneiro & Kovak 2017)
4. **Innovación por competencia**: La competencia importadora estimula innovación en firmas productivas (Bloom et al. 2016)
5. **Minimum wages**: Efectos heterogéneos; bordes estatales permiten identificación limpia (Dube)
6. **Violencia y trade**: Desplazamiento laboral por trade → reclutamiento en narcotráfico (Dell et al. 2019)
7. **EGC con informalidad**: Ganancias trade son 2.3x mayores en settings con alta informalidad (Dix-Carneiro et al. 2025)

## Fuentes de Datos para México

| Fuente | Variables | Período | Acceso |
|--------|-----------|---------|--------|
| ENOE | Transiciones laborales, informalidad | 2005-2023 | Público |
| Censos Económicos | Firmas, ventas, empleo | 2004,2009,2014,2019 | Público |
| IMSS | Empleo formal, salarios | 2000-2023 | Restringido |
| SAT | Exportaciones, impuestos | 2000-2023 | Restringido |
| UN Comtrade | Importaciones-exportaciones | 1998-2023 | Público |
| BANXICO | Tipos de cambio, balanza comercial | 1998-2023 | Público |
| OECD TIVA | Value Added in Trade | 2003-2018 | Público |

## Matching: Propuestas de Tesis ↔ Metodología

| Propuesta | Método principal | Datos clave | Dificultad |
|-----------|-----------------|-------------|------------|
| 1. Transiciones F-I-U | DiD + IV | ENOE panel, Comtrade | Media |
| 2. Innovación + Formalización | DiD + IV | Censos, SAT | Media-Alta |
| 3. CGV + Formalización | EGC + I-O tables | OECD TIVA, Censos | Alta |
| 4. EGC Melitz + Informal | SMM structural | Todos censos | Muy Alta |
| 5. Sorting Matching | Two-way FE + SMM | Linked employer-employee | Alta |

## Fórmulas Esenciales

**Exposición Comercial (Autor et al.):**
$$Exp_{jt} = \sum_j w_{ijt} \left[ \frac{M_{jt}}{C_{jt}} - \frac{M_{jt-k}}{C_{jt-k}} \right]$$

**DiD con IV:**
$$Trans_{ijt} = \beta_0 + \beta_1 Exp_{jt} + \beta_2 Exp_{jt} \times Post_t + X'_{ijt}\gamma + \mu_i + \delta_t + e_{ijt}$$

**Matching Model (Pissarides):**
$$y_{ij} = w_0 + \alpha(\xi_i, \psi_j) + \epsilon_{ij}$$

**TFP (Olley-Pakes):**
$$\ln(TFP_{ijt}) = \ln(Y_{ijt}) - \alpha_K \ln(K_{ijt}) - \alpha_L \ln(L_{ijt})$$
