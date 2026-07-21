# PROPUESTAS DE TESIS A NIVEL MAESTRÍA EN ECONOMÍA
## Comercio Internacional e Informalidad en México
### Inspiradas en Modelos de Equilibrio General con Fricciones Laborales

---

## PROPUESTA 1: Exposición Comercial y Transiciones Formal-Informal en Mercados Laborales Locales Mexicanos
### (Inspiración: Dix-Carneiro & Kovak 2019 + Ulyssea 2020 + Méndez 2015)

### **1.1 Motivación y Pregunta de Investigación**

**Pregunta central:** ¿Cómo afecta la exposición al comercio internacional (importaciones competidoras y oportunidades de exportación) las transiciones entre desempleo, informalidad y formalidad en mercados laborales locales mexicanos? ¿Juega el sector informal un rol amortiguador (buffering) durante shocks comerciales negativos?

**Hipótesis principal:** Regiones más expuestas a importaciones competidoras experimentan:
1. Mayor transición U→I (desempleo a informalidad)
2. Menor transición U→F o I→F
3. Mayor tasa de persistencia en informalidad (menor movilidad hacia sector formal)
4. Pero reducción en desempleo de largo plazo (efecto buffer)

**Novedad:** A diferencia de Méndez (2015) que enfatiza movilidad geográfica, esta propuesta se enfoca en **movilidad ocupacional** (formal-informal-desempleo) usando datos de panel de trabajadores.

---

### **1.2 Marco Teórico**

#### **Arquitectura del modelo (simplificado respecto Ulyssea et al.)**

**Tres estados laborales:**
- **Formal (F):** Requiere búsqueda en mercado formal, tiene costo de búsqueda $c_F$, salario $w_F$, seguridad laboral
- **Informal (I):** Requiere búsqueda, costo $c_I < c_F$, salario $w_I < w_F$, sin protección
- **Desempleo (U):** Sin ingreso, búsqueda activa

**Fricciones en mercado laboral:**
- Búsqueda y matching tipo Pissarides (2000)
- Tasa de oferta de empleo: $\lambda_j(t)$ donde $j \in \{F,I\}$ depende de exposición comercial
- Shock comercial negativo: ↓ $\lambda_F(t)$ pero puede mantener $\lambda_I(t)$ (estabilidad informalidad)
- Shock comercial positivo: ↑ $\lambda_F(t)$ → transiciones U→F, I→F

**Exposición comercial en mercado laboral local $i$:**
$$\text{Exp}_{it} = \sum_j w_{ijt} \left[ \frac{M_{jt}}{C_{jt}} - \frac{M_{jt-k}}{C_{jt-k}} \right]$$

Donde:
- $M_{jt}$ = Importaciones industria j, año t
- $C_{jt}$ = Consumo aparente industria j
- $w_{ijt}$ = Peso empleo industria j en mercado laboral local i
- Variación: También usar $X_j/Y_j$ para oportunidades exportación

---

### **1.3 Datos y Fuentes**

| Componente | Fuente INEGI | Disponibilidad |
|-----------|-----------|---|
| **Transiciones laborales** | Encuesta Nacional de Ocupación y Empleo (ENOE) - Panel 5 trimestres | 2005-2023 (panel corto) |
| **Empleo por clase industrial** | Encuesta Industrial Mensual (EIM) + Encuesta de Servicios | 2003-2023 |
| **Empleo formal/informal** | ENOE, Censo Económico (quinquenal) | 2000-2020 (saltos quinquenales) |
| **Importaciones-Exportaciones** | Banxico, SAT, UN Comtrade | 1998-2023 (mensual/anual) |
| **Producción y ventas** | Censos Económicos (2004, 2009, 2014, 2019) | Cada 5 años |
| **Mercados laborales locales** | ENOE por Zona Metropolitana (ZM) | 32 ZM cubiertas |

**Construcción panel:**
- Año base: 2010 (post-TLCAN maduro, pre-crisis)
- Años observación: 2010, 2015, 2020
- Unidad análisis: 32 Zonas Metropolitanas INEGI
- Industrias: 21 clases grandes (manufactureras + servicios)

---

### **1.4 Estrategia Econométrica**

#### **Ecuación principal (Differences-in-Differences):**

$$\text{Trans}_{ijt} = \beta_0 + \beta_1 \text{Exp}_{jt} + \beta_2 \text{Exp}_{jt} \times \text{Post}_{t} + X'_{ijt}\gamma + \mu_i + \delta_t + e_{ijt}$$

Donde:
- $\text{Trans}_{ijt}$ = Tasa de transición (U→F, U→I, I→F, etc.) en ZM i, industria j, período t
- $\text{Exp}_{jt}$ = Exposición comercial industria j
- $\text{Post}_t$ = Indicador post-shock comercial (ej: post-crisis 2008)
- $X_{ijt}$ = Controles: composición demográfica, educación, tamaño firma
- $\mu_i$ = Efectos fijos ZM
- $\delta_t$ = Efectos fijos período

**Instrumentación:** Expo comercial instrumentada por importaciones de China a **otros países LAC** (similar Méndez 2015)

#### **Heterogeneidad:**
$$\text{Trans}_{ijt} = \beta_1 \text{Exp}_{jt} + \beta_2 \text{Exp}_{jt} \times \text{EdHigh}_{it} + \beta_3 \text{Exp}_{jt} \times \text{Firm Size}_{jt} + ...$$

- Por nivel educativo trabajador
- Por tamaño firma (pequeña vs. grande)
- Por tipo industria (manufactura vs. servicios)

---

### **1.5 Resultados Esperados**

**Hallazgo principal:** Exposición a importaciones competidoras:
- ↓ Tasa U→F (efecto negativo)
- ↑ Tasa U→I (efecto positivo, "buffer" informalidad)
- ↓ Tasa I→F (efecto negativo)
- **Desempleo de largo plazo ↓** (efecto buffer neto)

**Heterogeneidad esperada:**
- Mayor efecto en trabajadores **menos educados**
- Mayor efecto en **pequeñas firmas**
- Efecto más fuerte en **manufactura** vs. servicios

---

### **1.6 Literatura Seminal**

#### **Tópico A: Trade Shocks y Mercados Laborales Segmentados**

1. **Dix-Carneiro, R., & Kovak, B. K. (2019).** "Trade Liberalization and Regional Inequality" *Econometrica*, 87(4), 1139-1190.
   - Primer paper que documenta efecto "buffer" informalidad en Brasil
   - Usa variación regional en exposición arancelaria
   - Metodología: IV con variación histórica aranceles como instrumento

2. **McCaig, B., & Pavcnik, N. (2018).** "Export Markets and Labor Allocation in a Low-Income Country" *American Economic Review*, 108(7), 1899-1941.
   - Estudia Vietnam post-liberalización
   - Muestra que exportaciones pueden ser "formalizing force"
   - Mecanismo: Firmas exportadoras pagan más, requieren más estándares

3. **Goldberg, P. K., & Pavcnik, N. (2003).** "The Response of the Informal Sector to Trade Liberalization" *Journal of Development Economics*, 72(2), 463-496.
   - Paper seminal: ¿Informalidad sube o baja con trade liberalization?
   - Mecanismo: Depende de regulaciones laborales y enforcement
   - Evidencia Brasil, Colombia

---

#### **Tópico B: Matching Models with Informality**

1. **Ulyssea, G. (2020).** "Firms, Informality, and Development" *Annual Review of Economics*, 12, 181-204.
   - Revisión sistemática de modelos matching + informalidad
   - Frameworks: Search & Matching equilibrio general
   - Énfasis en implicaciones policy

2. **Lise, J., & Postel-Vinay, F. (2020).** "Multidimensional Skills, Sorting, and Human Capital Accumulation" *American Economic Review*, 110(8), 2328-2376.
   - Modelo matching heterogéneo con absorción de skills
   - Relevancia: Analizar sorting formal-informal por habilidades

3. **Bontemps, G., Robin, J. M., & Van den Berg, G. N. (1999).** "Empirical Equilibrium Job Search Model with Search on the Job and Heterogeneous Worker and Firm Productivity" *International Economic Review*, 40(4), 1039-1065.
   - Clásico: Estimación empírica matching models
   - Técnica: Metodología para recuperar heterogeneidad

---

#### **Tópico C: Medidas de Exposición Comercial**

1. **Autor, D. H., Dorn, D., & Hanson, G. H. (2013).** "The China Syndrome: Local Labor Market Effects of Import Competition in the United States" *American Economic Review*, 103(6), 2121-2168.
   - Metodología construcción índices exposición comercial
   - Validación: Falsification tests, análisis robustez
   - Benchmark en literatura

2. **Topalova, P. (2010).** "Factor Immobility and Regional Impacts of Trade Liberalization: Evidence on Poverty from India" *American Economic Journal: Applied Economics*, 2(4), 1-41.
   - Construcción índices exposición a nivel distrital
   - Énfasis en heterogeneidad espacial
   - Aplicación país en desarrollo (India)

3. **Revenga, A. L. (1997).** "Employment and Wage Effects of Trade Liberalization: The Case of Mexican Manufacturing" *Journal of Labor Economics*, 15(3S), S20-S43.
   - Primera aplicación México trade shocks
   - Datos planta manufacturera (IMSS)
   - Metodología: Diff-in-diffs con datos administrativos

---

---

## PROPUESTA 2: Competencia Importadora, Innovación Firmas, y Decisión Formalización
### (Inspiración: Bloom et al. 2012 + Lileeva & Trefler 2010 + Iacovone et al. 2013)

### **2.1 Motivación y Pregunta de Investigación**

**Pregunta central:** ¿Cómo responden las firmas informales mexicanas a shocks de competencia importadora? ¿Existe trade-off entre innovación (mejorar TFP) e informalidad? ¿Las firmas formalizan por necesidad de calidad/estándares para competir?

**Hipótesis:** Firmas enfrentando competencia importadora aumentada:
1. Si TFP es **baja:** Exit o permanencia en informalidad
2. Si TFP es **media-alta:** **Formalizan** para acceder a: financiamiento, tecnología, cadenas valor
3. Si TFP **muy alta:** Expanden sin formalizar (informales "sofisticadas")

**Novedad:** Integrar decisión endógena formalización con competencia importadora a nivel firma.

---

### **2.2 Marco Teórico**

#### **Modelo dinámico de firma heterogénea**

**Estado firma: $(z_t, \ell_t, j_t)$**
- $z_t$ = Productividad (TFP) estocástica, evolución AR(1)
- $\ell_t$ = Estatus: Informal (0) o Formal (1)
- $j_t$ = Industria j

**Decisión formalización endógena:**

Firma elige $\ell^* = \arg\max \{ \pi^F(z,j,M) - F_F, \pi^I(z,j,M) - F_I \}$

Donde:
- $\pi^F(z,j,M)$ = Beneficio formal = $p_j(M) \cdot y(z) - w - \tau - c_{reg}$
  - Paga impuestos $\tau$ y costos regulación $c_{reg}$
  - Accede a mercado formal (precio cae si importaciones suben)
  - Pero puede innovar → aumenta z con inversión
  
- $\pi^I(z,j,M)$ = Beneficio informal = $(p_j(M) + \rho) \cdot y(z) - w^I$
  - Prima de precio $\rho$ por evasión
  - Salarios más bajos $w^I < w_F$
  - **No puede innovar** (sin acceso crédito, tecnología)
  - Riesgo cierre probabilístico $\theta(M)$ que aumenta con competencia

**Competencia importadora $M_j(t)$:**
- ↑ Importaciones → ↓ $p_j$ → comprime márgenes
- ↑ Importaciones → ↑ $\theta_j$ riesgo cierre (mayor enforcement)
- ↑ Importaciones → ↑ demanda por calidad/estándares

---

### **2.3 Datos y Fuentes**

| Componente | Fuente INEGI | Disponibilidad |
|-----------|-----------|---|
| **Firma nivel formal** | IMSS + SAT administrativos | 2000-2023 (acceso restringido) |
| **Firma nivel informal** | ECINF (Economía Informal Urbana) | 2005, 2010, 2015, 2020 |
| **Censo Económico** | Censos Económicos quinquenales | 2004, 2009, 2014, 2019 |
| **Ventas, empleo, inversión** | ENECE (Encuesta Nacional Esperanzas) | 2010-2023 |
| **TFP estimada** | Construir usando KLEMS: K, L, E, M, S | Datos censos + ENOE |
| **Importaciones-industria** | UN Comtrade, BANXICO | 1998-2023 |
| **Precio importaciones** | Unit values UN Comtrade | Proxy para cambio precios |

**Muestra construcción:**
- Período: 2004-2019 (dos ciclos censales)
- Cobertura: ~5 millones firmas censadas (formal + informal)
- Industrias: 65 clases SCIAN (4-dígitos)
- Balance: Trackear firmas entre censos (cohortes)

---

### **2.4 Estrategia Econométrica**

#### **Ecuación 1: Probabilidad formalización**

$$\text{Formalize}_{ijt} = \Lambda(\beta_0 + \beta_1 \text{ImportExp}_{jt} + \beta_2 \text{TFP}_{i,t-5} + \beta_3 \text{ImportExp}_{jt} \times \text{TFP}_{i,t-5} + X'_{it}\gamma + \mu_j + e_{ijt})$$

Donde:
- $\text{Formalize}_{ijt}$ = Indicador transición I→F
- $\text{ImportExp}_{jt}$ = Exposición importaciones (M/CA)
- Interacción $\text{ImportExp} \times \text{TFP}$ captura heterogeneidad: ¿Formalizan firmas productivas bajo competencia?

#### **Ecuación 2: Decisión innovación (inversión I+D, adopción tecnología)**

$$\text{Innovation}_{ijt} = \alpha + \alpha_1 \text{Status}_{it} + \alpha_2 \text{ImportExp}_{jt} + \alpha_3 \text{ImportExp}_{jt} \times \text{Status}_{it} + \text{Controls} + e_{ijt}$$

- $\text{Status}_{it}$ = Formal (1) vs. Informal (0)
- Hipótesis: $\alpha_1 > 0$ (formales innovan más)
- Hipótesis: $\alpha_3 < 0$ (competencia reduce innovación en informales especialmente)

#### **Ecuación 3: TFP growth (mecanismo)**

$$\Delta \text{TFP}_{ijt} = \theta_0 + \theta_1 \text{Formalize}_{it-5} + \theta_2 \text{Innovation}_{it} + \theta_3 \text{ImportExp}_{jt} + \text{Controls} + e_{ijt}$$

Interpreta causalidad: ¿Formalización → innovación → crecimiento TFP?

**Identificación:** 
- Usar variación histórica en importaciones (2000 vs. 2010) como instrumento para ImportExp
- Control por características observables: edad firma, educación propietario, localización

---

### **2.5 Resultados Esperados**

1. **Competencia importadora aumenta probabilidad formalización** para firmas con TFP **media-alta**
   - Efecto heterogéneo por productividad (estimado interacción)
   
2. **Formales innovan más** (mayor inversión en tecnología)
   - Efecto causal potencial si se estima dirección con lags

3. **Innovación firma formal causa crecimiento TFP** relativo a competencia

4. **Crecimiento TFP en competencia importadora** requiere formalización como canal

---

### **2.6 Literatura Seminal**

#### **Tópico A: Trade Competition y Innovation Decisions**

1. **Bloom, N., Draca, M., & Van Reenen, J. (2016).** "Trade Induced Technical Change? The Impact of Chinese Imports on Innovation, IT and Productivity" *Review of Economic Studies*, 83(1), 87-117.
   - Documenta que competencia importadora china **estimula innovación** en firmas UK
   - Mecanismo: Precio cae → márgenes presionados → invierten en mejora TFP
   - Metodología: IV con demanda china como instrumento

2. **Lileeva, A., & Trefler, D. (2010).** "Improved Access to Foreign Markets Raises Plant-Level Productivity... For Some Plants" *American Economic Review*, 100(3), 1204-1225.
   - Estudio Canadá: Exportadores innovan más post-liberalización
   - Heterogeneidad: Solo firmas suficientemente productivas exportan
   - Mecanismo sorting: Exporting requiere estándares → selección TFP alta

3. **Iacovone, L., Rauch, F., & Winters, L. A. (2013).** "Trade as an Engine of Creative Destruction: Mexican Experiences with Chinese Competition" *Journal of International Economics*, 89(2), 379-392.
   - China competition → plant-level exit, reallocation hacia productive plants
   - México data (Encuestas industriales)
   - Resultado: TFP agregada sube aunque employment baja

---

#### **Tópico B: Formalización como respuesta a presiones competencia**

1. **Ulyssea, G., & Ponczek, V. (2022).** "Trade Liberalization and the Demand for Institutional Quality" *American Economic Journal: Macroeconomics*, (forthcoming NBER WP 28389)
   - Documento que formalizaciónes surge como respuesta a trade shocks
   - Mecanismo: Acceso mercados exportación requiere estándares (ISO, etc.)
   - Modelo equilibrio general

2. **Hallak, J. C. (2006).** "Product Quality and the Direction of Trade" *Journal of International Economics*, 68(1), 238-265.
   - Firmas países ricos venden productos alta-calidad
   - Requisito: Producción formal, estándares
   - Implicación: Trade requiere formalización

3. **Bustos, P. (2011).** "Trade Liberalization, Exporting, and Technology Upgrading: Evidence on the Impact of MERCOSUR on Argentinian Firms" *American Economic Review*, 101(1), 304-340.
   - Argentina: Trade liberalization → formales exportan, informales quedan
   - Mecanismo: Acceso mercados requiere tecnología (formal) vs. subsistencia (informal)

---

#### **Tópico C: Firma Heterogeneidad y Decisiones Formalización**

1. **Hsieh, C. T., & Klenow, P. J. (2009).** "Misallocation and Manufacturing TFP in China and India" *Quarterly Journal of Economics*, 124(4), 1403-1448.
   - Seminal: Heterogeneidad TFP entre firmas formal-informal
   - Medida: Distortion wedges
   - Policy: Eliminar distortiones → TFP agregada puede subir 50%+

2. **Bartelsman, E., Haltiwanger, J., & Scarpetta, S. (2013).** "Cross-Country Differences in Productivity: The Role of Allocation and Dynamics" *American Economic Review*, 103(1), 305-334.
   - Misallocation más severa en países con informal sector grande
   - TFP agregada cae por ineficiencia asignación recursos

3. **Rauch, F. (2013).** "Firms and Informality in Developing Countries: A Quantitative Model" *Mimeo*, LSE.
   - Modelo dinámico optimal informal/formal choice
   - Estimación datos Brasil

---

---

## PROPUESTA 3: Redes Globales de Valor (CGV) y Formalización de Proveedores
### (Inspiración: Kee & Tang 2016 + Fort 2017 + Antras et al. 2020)

### **3.1 Motivación y Pregunta de Investigación**

**Pregunta central:** ¿Mejora la participación en Cadenas Globales de Valor (CGV) la formalización de proveedores informales mexicanos? ¿Qué mecanismos operan: presión por estándares de calidad, acceso a financiamiento, mejor salarios?

**Contexto México:** 
- ~30-40% de exportaciones son part de CGV
- Maquiladoras requieren estándares ISO, trazabilidad → presionan formalización
- Pero también existe exploración: bajos salarios, evasión laboral

**Hipótesis:** Integración a CGV:
1. **Corto plazo:** ↑ Presión formalización (estándares técnicos)
2. **Mediano plazo:** ↑ Salarios formales (acceso mercados premium)
3. **Heterogeneidad:** Depende de tipo CGV (manufactura de precisión vs. ensamble simple)

---

### **3.2 Marco Teórico**

#### **Modelo simplificado: Integración GVC como calidad/estándares**

**Firma proveedor i vende a:**
- Mercado doméstico (sin estándares) → puede ser informal
- Cadena global de valor (con requisitos estándares) → debe ser **formal**

**Decisión participación GVC:**

$$\text{Join}_{it}^* = \begin{cases} 
1 & \text{si } \pi^{GVC}(z,x) - \phi > \pi^{DOM}(z) \\
0 & \text{en otro caso}
\end{cases}$$

Donde:
- $\pi^{GVC}(z,x)$ = Beneficio unirse a cadena
  - Requiere inversión en calidad/cumplimiento $\phi$ (fijo, irreversible)
  - Acceso a mercados con precio premium $p_{GCV}(x)$ donde x = nivel calidad
  - Requiere ser formal: $\ell = 1$
  
- $\pi^{DOM}(z)$ = Beneficio solo mercado doméstico
  - Menos regulación
  - Precio menor $p_{DOM}$
  - Puede ser informal

**Presión formalización:** Si $\pi^{GVC}$ aumenta (demanda mundial sube), firma informal se ve presionada a formalizar para capturar ganancias GVC.

**Mecanismo salarios:** Integración GCV → ↑ productividad → ↑ salarios → atrae trabajadores calificados → requiere formalidad (credibilidad pago pensiones).

---

### **3.3 Datos y Fuentes**

| Componente | Fuente | Disponibilidad |
|-----------|--------|---|
| **Participación CGV firma** | Input-Output Tables INEGI + Trade data | 2003, 2008, 2013, 2018 |
| **Estatus formal-informal** | ENECE, Censos Económicos | 2004, 2009, 2014, 2019 |
| **Exportaciones firma** | SAT (Servicio de Administración Tributaria) - Registro aduanal | 2000-2023 |
| **Cadenas internacionales** | OECD TIVA (Trade in Value Added) + WJobs | Mapas CGV |
| **Salarios** | IMSS registros + ENOE | 2000-2023 |
| **Inversión calidad** | Encuesta ENECE: Tech adoption, equipment | 2010-2023 |
| **Regulación laboral** | Cumplimiento IMSS/CFDI | Indirecto en datos administrativos |

**Construcción muestra:**
- Período: 2004-2019
- Muestra: Firmas manufactureras (SCIAN 31-33) vinculadas en I-O tables
- Identificación participación CGV: Usar tablas insumo-producto abierto para identificar proveedores
- Alternativa: Usar datos SAT de exportadores + importadores insumos

---

### **3.4 Estrategia Econométrica**

#### **Ecuación 1: Efecto participación CGV en probabilidad formalización**

$$\text{Formalize}_{ijt} = \Phi(\beta_0 + \beta_1 \text{GCV Share}_{i,t-5} + \beta_2 \text{GCV Shock}_{j,t} + \beta_3 \text{GCV Share} \times \text{GCV Shock} + X'_{it}\gamma + \mu_i + e_{ijt})$$

Donde:
- $\text{GCV Share}_{i,t-5}$ = Proporción inputs de GCV usados (lag para endogeneidad)
- $\text{GCV Shock}_{jt}$ = Cambio exógeno en demanda de GCV industria j
  - Instrumental: Demanda global de valor agregado en cadenas (TIVA)
  
- Variable dependiente: Transición I→F entre períodos censales

#### **Ecuación 2: Efecto en salarios (mecanismo)**

$$\ln(\text{Wage}_{ijt}) = \alpha_0 + \alpha_1 \text{In GCV}_{it} + \alpha_2 \text{Formal}_{it} + \alpha_3 \text{In GCV} \times \text{Formal} + X'_{ijt}\gamma + \mu_i + \delta_t + e_{ijt}$$

- Hipótesis: $\alpha_1 > 0$ (participar en GCV → salarios mayores)
- Hipótesis: $\alpha_3 > 0$ (efecto amplificado si formal)

#### **Ecuación 3: Heterogeneidad por tipo CGV**

$$\text{Formalize}_{ijt} = \beta_1 \text{GCV Share Low-Tech}_{i} + \beta_2 \text{GCV Share High-Tech}_{i} + ... $$

- Tipología: CGV Ensamble Simple vs. Manufactura Precisión vs. Servicios
  - Simple: Maquiladoras típicas (costura, electrónica básica)
  - Precisión: Autopartes, componentes electrónicos complejos
  - Servicios: Outsourcing IT, call centers

---

### **3.5 Resultados Esperados**

1. **Participación CGV aumenta probabilidad formalización** especialmente si firma entra (no solo aumenta volumen)
2. **Efecto heterogéneo:** Más fuerte en CGV **alta-tech/precisión** que ensamble simple
3. **Mecanismo salarios:** Firmas en GCV formal pagan 10-15% más
4. **Efecto dinámico:** Desfase 1-2 años entre entrada GCV y formalización (tiempo inversión)

---

### **3.6 Literatura Seminal**

#### **Tópico A: CGV y Upgrading Firmas en Países en Desarrollo**

1. **Kee, H. L., & Tang, H. (2016).** "Domestic Value Added in Exports: Theory and Firm Evidence from China" *American Economic Review*, 106(6), 1402-1436.
   - Documenta que participación CGV sube valor agregado doméstico
   - Mecanismo: Aprendizaje en innovación, estándares
   - China case study (similar a México en integración)

2. **Fort, T. C. (2017).** "Technology and Production Fragmentation: Domestic versus Foreign Sourcing" *Journal of Political Economy*, 125(3), 1637-1677.
   - Muestra que cambios en fragmentación global → reallocation doméstica
   - Firmas integrarse GVC requieren cambios tecnológicos
   - USA evidence

3. **Antràs, P., Fort, T. C., & Tintelnot, F. (2017).** "The Margins of Global Sourcing: Theory and Evidence from US Firms" *American Economic Review*, 107(9), 2514-2564.
   - Heterogeneidad firmas en decisions de sourcing
   - Productividad determina si sourcing doméstico vs. GCV
   - Metodología: Structural estimation

---

#### **Tópico B: Estándares, Calidad, y Formalización**

1. **Hallak, J. C., & Sivadasan, J. (2013).** "Product and Process Productivity: Implications for Quality Choice and Conditional Exporting" *Journal of International Economics*, 91(1), 53-67.
   - Teoría: Producción calidad-premium requiere tecnología-intensiva
   - Proxies formal sector acceso a tecnología
   - Implicación: GCV → formales vs. informales

2. **Fernandes, A. M., & Paunov, C. (2012).** "Foreign Direct Investment in Services and Manufacturing Productivity: Evidence for Chile" *Journal of Development Economics*, 99(2), 404-414.
   - FDI en servicios → presión estándares en proveedores locales
   - Spillovers hacia firmas no-FDI
   - Mecanismo: Quality upgrading

3. **Criscuolo, C., & Garicano, L. (2010).** "Firm-Level Productivity in India: Evidence from a Large Household-Based Manufacturing Survey" *Journal of Development Economics*, 94(2), 168-180.
   - Documentan correlación entre: Exportación → Formalización → Productividad
   - India (país en desarrollo similar a México)

---

#### **Tópico C: CGV México y Maquiladoras**

1. **López-Córdova, J. E., & Meissner, C. M. (2005).** "Exchange Rate Appreciation and Manufacturing Exports: Evidence from Mexico" *Cuadernos de Economía*, 42(125), 3-27.
   - CGV México-US post-TLCAN
   - Documentan integración maquiladoras

2. **Blyde, J. S., Kugler, M., & Stein, E. (2010).** "Commodity Prices and Inequality" *IDB Working Paper IDB-WP-125*
   - Integración cadenas México en manufactura

3. **Mendoza-González, R., & Cuadra, G. (2016).** "Drivers of Aggregate Fluctuations in Mexico since 1929" *Journal of Development Economics*, 119, 76-98.
   - Ciclos manufactura e integración GCV

---

---

## PROPUESTA 4: Dinámicas Firma Heterogénea con Crecimiento Endógeno de Informalidad
### (Inspiración: Melitz 2003 + Hopenhayn 1992 + Meghir et al. 2015)

### **4.1 Motivación y Pregunta de Investigación**

**Pregunta central:** ¿Cómo shocks de comercio redimensionan la distribución de firmas entre formal e informal en equilibrio general? ¿Qué rol juega la dinámica firma heterogénea (entrada, crecimiento, salida) en transmisión shocks?

**Diferencial respecto Prop 2:** Aquí enfatizamos **dinámicas agregadas** en distribución firmas, no decisión individual formalización.

**Hipótesis:** Liberalización comercial:
1. ↓ Rentabilidad promedio sector (precio cae)
2. **Sorting:** Firmas baja TFP → informal; alta TFP → formal/exporter
3. Reallocación within-sector amplifica shocks negativos en empleo informal
4. Pero entrada nuevas firmas (post-shock) puede ser más informal (mayor incertidumbre)

---

### **4.2 Marco Teórico**

#### **Modelo Melitz (2003) con status formal/informal endógeno**

**Firma heterogénea en productividad z ~ G(z)**

Entra mercado pagando costo $f_e$ (igual formal e informal). Al entrar, obtiene z.

**Decisión post-entrada:**
- **Formal:** Paga impuestos $\tau$, costos regulación $c_r(w,z)$, pero accede a mercados exportación
- **Informal:** Evasión, pero: (i) salarios más bajos, (ii) riesgo cierre $\theta(w,z)$ que ↑ con tamaño

**Rentabilidad firma:**

$$\pi_j(z) = [p(M) y(z) - w_j z - c_j(z)] - \sigma_j \lambda_j$$

Donde:
- $j \in \{F, I\}$ = status
- $\sigma_j$ = tasa salida exógena
- $\lambda_j$ = valor de continuación

**Costo regulación formal:** $c_r(z)$ puede depender de tamaño, p.ej. $c_r(z) = \gamma z^\rho$ (compliance burden aumenta con tamaño firma)

**Externalidad informales:** Como informales pagan menos impuestos y regulación, compiten con precio artificialmente bajo → presionan formales.

---

### **4.3 Datos y Fuentes**

| Componente | Fuente | Período |
|-----------|--------|---|
| **Dinamica firma (entrada-salida)** | Censo Económico links + ENECE panel | 2004-2019 |
| **Distribución tamaños** | Todos censos 5-dígitos | 2004, 2009, 2014, 2019 |
| **TFP estimada** | KLEMS (K-L-E-M-S) - construir | 2000-2019 |
| **Salarios formal vs. informal** | IMSS + ENOE | 2000-2023 |
| **Comercio industria** | BANXICO, UN Comtrade | 1998-2023 |
| **Aranceles** | UNCTAD TRAINS database | 1998-2023 |

**Construcción:**
- Panel firmas 2004-2019 (dos ciclos censales)
- Estimar TFP por firma: $\ln(TFP) = \ln(Y) - \alpha_K \ln(K) - \alpha_L \ln(L) - ...$
- Calibrar modelo en 2005, simular shocks 2005-2020, validar contra datos realizados

---

### **4.4 Estrategia Econométrica**

#### **Componente 1: Estimación TFP firma**

$$\ln(Y_{ijt}) = \beta_0 + \alpha_K \ln(K_{ijt}) + \alpha_L \ln(L_{ijt}) + \alpha_M \ln(M_{ijt}) + \omega_{ijt}$$

Donde $\omega_{ijt}$ = TFP + error
- Estimación: Proxy variable methods (Olley-Pakes, Levinsohn-Petrin, ACF)
- Regresar cambio TFP en cambio tamaño/edad para validez

#### **Componente 2: Calibración modelo Melitz + Informalidad**

Estimar/calibrar parámetros:
- Distribución TFP: $\ln(z) \sim N(\mu_z, \sigma_z^2)$
- Costos entrada $f_e$
- Costos regulación $c_r(z)$
- Salarios formal $w_F$, informal $w_I = \phi w_F$ donde $\phi < 1$
- Tasa salida $\sigma_F, \sigma_I$
- Elasticidad demanda $\theta$

**Calibración targets:**
- Share empleo informal observado (50%)
- Distribución tamaños (log-normal)
- Prime salarial formal-informal (15-20%)
- Tasa entrada/salida firmas observada

#### **Componente 3: Contrafácticos dinámicos**

Simular trayectorias temporales:

1. **Shock arancelar:** Reducción 33% en aranceles 2005-2010
2. **Salida firmas formal-informal (endógena)**
3. **Reallocation employment** dentro-entre sectores

Comparar:
- Predicción modelo vs. Datos realizados 2005-2019
- Descomponer shock en componentes: Mecánico (precio) + Reallocación + Entry/Exit dinámicas

---

### **4.5 Resultados Esperados**

1. **Shock comercial induce exit diferenciado:**
   - Formales baja TFP: Exit alto
   - Informales baja TFP: Exit moderado (salarios bajos absorben)
   
2. **Reallocación employment:**
   - Del informal baja TFP al formal alta TFP
   - Pero inicial informal puede ↑ (si compite con precio bajo)

3. **Dinámicas entrada:**
   - Post-shock, nuevas entrantes son **más informales** (incertidumbre)
   - Entry barrier formal ↑ (presión competencia)

4. **Amplificación dinámicas:**
   - Efecto TFP agregada 2x mayor que efectos estáticos (Ulyssea result)

---

### **4.6 Literatura Seminal**

#### **Tópico A: Modelos Equilibrio General Firma Heterogénea Trade**

1. **Melitz, M. J. (2003).** "The Impact of Trade on Intra-Industry Reallocations and Aggregate Industry Productivity" *Econometrica*, 71(6), 1695-1725.
   - Seminal: Heterogeneidad firma, trade-induced reallocación
   - Mecanismo: Precio bajo → margin comprímido → exit baja TFP
   - Resultado: Reallocación amplifica TFP agregada

2. **Chaney, T. (2014).** "The Network Structure of International Trade" *American Economic Review*, 104(11), 3600-3634.
   - Extensión Melitz: Redes comercio (múltiples destinos, buyers)
   - Heterogeneidad bilateral
   - Aplicación: México-US data

3. **Eaton, J., Kortum, S., & Kramarz, F. (2011).** "An Anatomy of International Trade: Evidence from French Firms" *Econometrica*, 79(5), 1453-1498.
   - Empirical equilibrium model con données firmas francesas
   - Destinos múltiples exportación
   - Metodología estimación estructural

---

#### **Tópico B: Informalidad en Modelos EGC**

1. **Meghir, C., Narita, R., & Robin, J. M. (2015).** "Wages and Informality in Developing Countries" *American Economic Review*, 105(4), 1509-1546.
   - Modelo EGC Brasil con matching formal-informal
   - Estimación: Método simulación moments (SMM)
   - Contrafácticos: Reforma laboral, cumplimiento regulación

2. **Ulyssea, G. (2020).** "Firms, Informality, and Development" *Annual Review of Economics*, 12, 181-204.
   - Revisión literature: Dinámicas firma heterogénea + informalidad
   - Énfasis mecanismos enforcement, regulación

3. **Lopes de Melo, R. (2018).** "Sorting in the Labor Market: Theory and Measurement" *Journal of Political Economy*, 126(4), 1411-1460.
   - Sorting equilibrium general con heterogeneidad
   - Workers self-select formal vs. informal
   - Empirical: Structural estimation

---

#### **Tópico C: Dinámicas Firma Entry-Exit Trade**

1. **Arkolakis, C. (2016).** "A Unified Theory of Firm Selection and Growth" *Journal of Political Economy*, 124(6), 1658-1712.
   - Dinámicas firma bajo trade openness
   - Entry/exit endógeno
   - Growth rates heterogéneo

2. **Chor, D. (2010).** "Unpacking Sources of Comparative Advantage: A Quantitative Approach" *Journal of International Economics*, 82(2), 152-167.
   - Fuentes ventaja comparativa: Factor endowments vs. productividad vs. política
   - Separar trade effects en componentes

3. **Pavcnik, N. (2002).** "Trade Liberalization, Exit, and Productivity Improvements: Evidence from Chilean Plants" *Review of Economic Studies*, 69(1), 245-276.
   - Clásico: Liberalización Chile → exit baja productividad
   - Mejora TFP agregada por reallocación
   - Plantea preguntas que Ulyssea actualiza

---

---

## PROPUESTA 5: Emparejamiento Trabajador-Firma Heterogéneo y Sorting Formal-Informal
### (Inspiración: Barth et al. 2016 + Eeckhout & Kircher 2011 + Bontemps et al. 1999)

### **5.1 Motivación y Pregunta de Investigación**

**Pregunta central:** ¿Cómo shocks comerciales afectan el **matching** trabajador-firma entre sectores formal e informal? ¿Hay complementariedades habilidades-firmas que determinan sorting?

**Contexto:** Literatura muestra que "wage inequality" surge no de within-firm cambios sino de **between-firm sorting** (Barth et al. 2016).

**Hipótesis:** 
1. Shocks comerciales desestabilizan matches existentes
2. Trabajadores de baja habilidad: Quedan en informal (reasignación lateral)
3. Trabajadores de alta habilidad: Pueden transicionar F→F o I→F
4. Firmas formal que contraen: Despiden baja habilidad primero → selección
5. **Resultado:** Aumento desigualdad salarial trabajador-nivel pero **mejoría efficiency** matching

---

### **5.2 Marco Teórico**

#### **Modelo Emparejamiento Heterogéneo Bidireccional**

**Agentes:**
- Trabajadores $i$ con habilidad $\xi_i \sim F(\xi)$ (observada + no-observada)
- Firmas $j$ con "calidad" $\psi_j$ (productividad, tamaño)
- Status firma: formal o informal

**Productividad match:**
$$y_{ij} = w_0 + \alpha(\xi_i, \psi_j) + \epsilon_{ij}$$

Donde $\alpha(\xi_i, \psi_j)$ = complementaridad habilidad-firma

**Específicamente:**
- Formal high-quality firm + high-skill worker → complementaridad fuerte
- Informal firm + low-skill worker → complementaridad débil
- Cross-matches (ej. high-skill + informal): Subóptimo pero posible

**Dinámica shock comercial:**
1. Firma formal baja calidad → contrae → despide mixed habilidad
2. Firma informal puede expandir (competencia precio)
3. Reasignación: Trabajadores buscan nuevos matches
4. Si high-skill unemployed: Espera formal job o acepta informal
5. Resultado: Mayor segregación formal-informal por habilidad

---

### **5.3 Datos y Fuentes**

| Componente | Fuente | Disponibilidad |
|-----------|--------|---|
| **Panel trabajadores** | ENOE (panel 5 trimestres) | 2005-2023 |
| **Características trabajador** | ENOE: educación, edad, género, sector | 2005-2023 |
| **Firmas características** | ENECE, Censos económicos | 2010, 2015, 2020 |
| **Empleo firma-nivel** | IMSS registros + SAT (acceso restringido) | 2000-2023 |
| **Salarios observado** | ENOE, IMSS | 2000-2023 |
| **Estimación habilidad latente** | Structural estimation modelo matching | - |
| **Shocks comerciales** | BANXICO, UN Comtrade | 1998-2023 |

**Construcción:**
- Panel trabajadores 2005-2019 (largo para rastrear transitions)
- Linked employer-employee data (si accesible SAT)
- Estimar componente worker ability (habilidad idiosincrática)
- Estimar componente firm quality
- Resta: Residual = match-specific quality

---

### **5.4 Estrategia Econométrica**

#### **Paso 1: Descomposición Wage Variance (Barth et al. 2016)**

$$\ln(w_{ijt}) = \bar{w}_t + \theta_i^t + \psi_j^t + u_{ij}^t$$

Donde:
- $\theta_i^t$ = Worker effect (ability, fixed + time-varying skills)
- $\psi_j^t$ = Firm effect (quality, technology, size)
- $u_{ij}^t$ = Match-specific component
- $\bar{w}_t$ = Base wage

**Estimación:** Fixed effects OLS (two-way): Recuperar $\hat{\theta}_i$ y $\hat{\psi}_j$

**Validación:** Requiere movilidad workers entre firmas (variation identification)

#### **Paso 2: Análisis Sorting Pre-Post Shock**

$$\rho_t = \text{Cov}(\theta_i^t, \psi_j^t)$$

- $\rho_t = 0$ → Random matching
- $\rho_t > 0$ → Positive assortative matching (high-skill en high-quality firms)
- Hipótesis: $\rho_t$ **aumenta** post-shock (mejor sorting efficiency)

**Covariate análisis:**
$$\rho_t^{F} \text{ vs. } \rho_t^{I} \text{ vs. } \rho_t^{F-I \text{ transitions}}$$

- Comparar within-sector (F-F, I-I) vs. cross-sector sorting

#### **Paso 3: Efecto Shock Comercial en Sorting**

$$\Delta \rho_i = \beta_0 + \beta_1 \text{Exp}_{j(i)} + \beta_2 \text{Edu}_i + \beta_3 \text{Exp}_{j(i)} \times \text{Edu}_i + e_i$$

Donde:
- $\Delta \rho_i$ = Cambio posición distribución wages para worker i
- $\text{Exp}_{j(i)}$ = Exposición comercial firma i (industria)
- Resultado esperado: $\beta_1 < 0$ (exposición → baja salarial para given ability)

#### **Paso 4: Heterogeneidad**

$$\text{Trans}^{I \rightarrow F}_{it} = \alpha + \alpha_1 \hat{\theta}_i (\text{ability}) + \alpha_2 \text{Exp}_{jt} + \alpha_3 \hat{\theta}_i \times \text{Exp}_{jt} + e_{it}$$

- Hipótesis: $\alpha_1 > 0$ (ability ↑ → trans F más probable)
- Hipótesis: $\alpha_3 > 0$ (exposure effect is stronger for high-ability)

---

### **5.5 Resultados Esperados**

1. **Sorting mejora post-shock** (eficiencia)
   - Firmas formal baja-calidad exit
   - Trabajadores high-ability se reacomodan a formal high-quality
   - Trabajadores low-ability quedan en informal

2. **Aumento desigualdad salarial**
   - Between-firm component ↑
   - Within-firm component → sin cambio
   
3. **Transitions heterogéneo:**
   - High-ability: Logran I→F post-shock
   - Low-ability: Atrapados en I o U

4. **Wage losses distribuido:**
   - High-ability: Pequeñas pérdidas (rápido reemparejamiento)
   - Low-ability: Grandes pérdidas persistentes

---

### **5.6 Literatura Seminal**

#### **Tópico A: Sorting Equilibrio General Trabajo**

1. **Barth, E., Bryson, A., Haltiwanger, J. C., & Laun, L. (2016).** "It's Where You Work: Increases in the Dispersion of Earnings Across Establishments and Individuals in the United States" *Journal of Labor Economics*, 34(2), 67-97.
   - Decomposición inequality: Entre-firmas vs. dentro-firma
   - Sorted matching explain mucho inequality
   - Datos US administrative (1975-2010)

2. **Eeckhout, J., & Kircher, P. (2011).** "Identifying Sorting" *Econometrica*, 79(4), 1029-1065.
   - Theoretical: Cómo identificar sorting vs. complementariedades
   - Estructural: Requiere variation en wages y empleo
   - Soluciones: Using transitions data

3. **Song, J., Price, D. J., Guvenen, F., Bloom, N., & von Wachter, T. (2019).** "Firming up Inequality" *Quarterly Journal of Economics*, 134(1), 1-50.
   - Modernización estudio Barth et al.
   - Sorting firms explica 70% aumento inequality pre-tax EE.UU.

---

#### **Tópico B: Matching Heterogéneo Estructural**

1. **Bontemps, G., Robin, J. M., & Van den Berg, G. N. (1999).** "Empirical Equilibrium Job Search Model with Search on the Job and Heterogeneous Worker and Firm Productivity" *International Economic Review*, 40(4), 1039-1065.
   - Clásico: Estimación matching model usando LIML
   - Heterogeneidad worker + firm observada y latente
   - Validación: Momentos salarios, transitions

2. **Lopes de Melo, R. (2018).** "Sorting in the Labor Market: Theory and Measurement" *Journal of Political Economy*, 126(4), 1411-1460.
   - Equilibrium general matching model
   - Self-selection workers en formal vs. informal
   - Estimación: Simulated moments (SMM)

3. **Bartolucci, C. (2013).** "Testing for Identification in Semiparametric Models" *Econometric Reviews*, 32(5-6), 635-660.
   - Métodos identificación sorting vs. complementariedades
   - Técnicas econométricas avanzadas
   - Aplicables a México

---

#### **Tópico C: Trade y Labor Market Sorting**

1. **Abowd, J. M., Kramarz, F., Lengermann, P. (2013).** "High-Wage Workers and High-Wage Firms: Identifying the Key Mechanisms" *Revue Économique*, 64(6), 1053-1086.
   - Sorting en presencia trade shocks
   - Descomposición wages en worker + firm effects
   - Francia data (1986-2007)

2. **Navarro, G., Postel-Vinay, F. (2013).** "Why Has Wage Growth Stalled in France?" *Labour Economics*, 25, 108-122.
   - Aplicación Francia: Wage stagnation debido cambios sorting
   - Trade shocks reduce movilidad upward

3. **Dix-Carneiro, R., Song, J. (2021).** "Trade and Inequality: From Theory to Estimation" *NBER WP 29155*
   - Síntesis teórico-empírica: Trade → sorting → inequality
   - Propuesta metodológica para estimar desde reduced-form
   - Aplicable México

---

---

## TABLA COMPARATIVA PROPUESTAS

| Propuesta | Pregunta Central | Framework Principal | Unidad Análisis | Datos Clave | Desafío Principal |
|-----------|---|---|---|---|---|
| **1. Transiciones F-I-U** | ¿Buffer effect informalidad en shocks trade? | Matching fricciones | ZM + industria | ENOE transitions | Panel corto ENOE |
| **2. Innovation Decision** | ¿Formalización respuesta competencia? | Firma heterogénea + innovation | Firma individual | Censos + SAT | Acceso SAT administrativos |
| **3. CGV & Estándares** | ¿CGV fuerza formalización? | Integración cadenas globales | Firma + industria | I-O + Trade data | Mapeo preciso CGV |
| **4. EGC Melitz-Informal** | ¿Dinámica distribución firmas? | Equilibrio general | Mercado nivel | Todos censos | Calibración estructural compleja |
| **5. Sorting Matching** | ¿Cómo reordenarse worker-firm? | Emparejamiento equilibrio general | Worker + firma | Panel ENOE + IMSS | Linked employer-employee data |

---

## GUÍA APLICACIÓN PRÁCTICA

### Para cada propuesta, seguir estos pasos:

#### **FASE 1: Proyecto Tesis (Primer Trimestre)**
1. Replicar paper clave (ej. Méndez 2015 para Prop 1)
2. Adaptar metodología datos México
3. Exploración preliminar datos

#### **FASE 2: Especificación Modelo (Trimestre 2)**
1. Escribir modelo completo (con ecuaciones)
2. Derivar ecuaciones econométricas principales
3. Preparación datos

#### **FASE 3: Estimación y Resultados (Trimestres 3-4)**
1. Estimaciones principales + robustness
2. Análisis heterogeneidad
3. Contrafácticos si aplica

#### **FASE 4: Extensiones y Documento (Final)**
1. Extensiones metodológicas
2. Redacción documento tesis (formato artículo)
3. Defensa

### Cronograma Sugerido: **20 meses** para tesis Master completa

---

## NOTAS FINALES

1. **Datos accesibles:** Todas propuestas usan datos INEGI públicos o semi-públicos. Para SAT (administrativo) requiere solicitud formal a institución.

2. **Factibilidad:** Propuestas 1, 2, 5 más directas (menos modelo). Propuestas 3, 4 requieren modelado más avanzado.

3. **Novedad:** Cada propuesta actualiza literatura clasica (Ulyssea, Méndez, Autor) al contexto méxico 2000-2020.

4. **Publicabilidad:** Propuestas 2, 4, 5 tienen potencial publicación en journals tier-2 (Economía Mexicana, Estudios Económicos, o journal región LACR).

