# Cuaderno de Revisión de Literatura
## Comercio Internacional, Informalidad y Mercados Laborales en México
*Generado por /the-reader - 2026-07-20*
*Corpus: 37 papers procesados*

---

## Índice de Temas

### Trade & Labor Markets (7 papers)
1. The China Syndrome: Chinese Import Competition and US Local Labor Markets (Autor, Dorn, Hanson 2013)
2. Trade Liberalization and Regional Dynamics: Long-Run Effects of Brazilian Trade Reform (Dix-Carneiro & Kovak 2017)
3. Violent Consequences of Trade-Induced Worker Displacement in Mexico (Dell, Feigenberg, Teshima 2019)
4. Margins of Labor Market Adjustment to Trade: Formal vs. Informal Employment in Brazil (Dix-Carneiro & Kovak 2016)
5. Firms, Informality, and Development: Theory and Evidence from Brazil (Ulyssea 2018)
6. Trade as Engine of Creative Destruction: Mexican Experience with Chinese Competition (Iacovone, Rauch, Winters 2013)
7. Effect of Chinese Import Competition on Mexican Local Labor Markets (Mendez 2015)

### Wages & Minimum Wage (11 papers)
8. Effect of Trade Liberalization on Informality and Wages: Evidence from Mexico (Aleman-Castilla 2006)
9. Trend Wage Inflation (TWIn): Constructing a filtered measure of persistent aggregate nominal wage growth using dynamic factor models on CPS worker-level data
10. Review and critical assessment of the econometric methods and economic reasoning used to estimate minimum wage employment effects, focusing on the US literature
11. Estimating minimum wage effects on restaurant employment and earnings using contiguous county pairs across US state borders as identification
12. Comprehensive handbook chapter reviewing the evolution, theory, and empirical evidence on minimum wage effects on employment, wages, inequality, and margins of adjustment globally
13. Estimating the effect of minimum wages on the entire frequency distribution of low-wage jobs using a bunching/difference-in-differences approach
14. Reconceptualizing the missing jobs problem in developing countries as a failure of job conversion mechanisms rather than solely insufficient labor demand
15. Estimating labor market power (wage markdowns) of manufacturing establishments across 82 low and middle-income countries and its relationship with self-employment and labor market institutions
16. Disentangling the effects of a 100% minimum wage increase and a VAT rate cut (16% to 8%) on consumer prices at Mexico's northern border (ZLFN), January 2019
17. Labor Market Power and Development (Armangué-Jubert, Guner, Ruggieri 2024, BSE WP 1446). Structural estimation of oligopsony model showing labor supply elasticity increases with GDP per capita; wage markdowns from 54% (poor) to 24% (rich); misallocation effects on GDP.
18. Panorama Laboral 2023: Annual labor market overview for Latin America and the Caribbean by the ILO, covering macroeconomic context, employment, informality, wages, gender gaps, youth labor, and social protection with 30-year retrospective analysis

### Econometrics & Methodology (6 papers)
19. Local Projections (LPs) - Comprehensive survey by Jordà and Taylor (2024, NBER WP 32822). Estimation of impulse responses, comparison with VARs, inference, smoothing, multipliers, panel data extensions, and nonlinear LP methods.
20. Synthetic Difference-in-Differences (SDID) by Arkhangelsky, Athey, Hirshberg, Imbens, and Wager (2019/2021, NBER WP 25532). A new estimator combining DID and Synthetic Control methods with unit and time weights, consistency/normality results, and placebo simulations.
21. Practical guidance for synthetic control methods by Abadie and Vives-i-Bastida (2021). Seven guiding principles for empirical practice, overfitting biases, validation exercises, trimming, and the role of covariates.
22. scpi software package for uncertainty quantification in synthetic control methods (Cattaneo, Feng, Palomba, Titiunik 2025, JSS). Prediction intervals under random potential outcomes, multiple estimation methods (simplex, lasso, ridge), and implementation in R/Python/Stata.
23. Impact of hosting FIFA World Cup on GDP per capita using synthetic control method (Viana, Barbosa, Sampaio 2018, EconomiA). Application of SC to 7 World Cup hosts (1978-2006).
24. Duplicate of the World Cup SC paper (Viana, Barbosa, Sampaio 2018, EconomiA). Same content as the World Cup file above—impact of hosting FIFA World Cup on GDP per capita via synthetic control method.

### Finite Mixture Models (3 papers)
25. Comprehensive benchmark of Gaussian Mixture Model R packages: EM algorithm, initialisation methods, and estimation performance comparison
26. Finite Mixture Models: comprehensive theoretical review covering formulation, estimation, EM algorithm, Bayesian analysis, normal/t/skew mixtures, and model selection
27. mclust R package version 5: Gaussian finite mixture modeling for clustering, classification, and density estimation with 14 covariance parameterisations, BIC/ICL selection, bootstrap inference, and dimension reduction

### Institutional Reports (1 papers)
28. Informality in Latin America: Exit and Exclusion - A comprehensive World Bank analysis of labor market informality, its causes, consequences, and policy implications across Latin America and the Caribbean

### Working Papers & Trade Theory (6 papers)
29. The China Shock: Learning from Labor Market Adjustment to Large Changes in Trade
30. Trade and Informality in the Presence of Labor Market Frictions and Regulations
31. The Impact of Trade on Intra-Industry Reallocations and Aggregate Industry Productivity
32. Practitioner's Guide to Quantifying the Effects of Trade Policy
33. Nowcasting World Trade with a Multi-Region Factor Model
34. Stablecoin Shocks: How Stablecoins Affect Financial Markets

### Development & Informality (3 papers)
35. OECD (2025): Expanding Social Protection and Addressing Informality in Latin America
36. OECD Economic Surveys: Mexico 2026
37. Trade and Domestic Distortions: The Case of Informality (Academic Paper)

---

# Trade & Labor Markets

## autoretal2013
**Tema:** The China Syndrome: Chinese Import Competition and US Local Labor Markets (Autor, Dorn, Hanson 2013)

### Conceptos Clave
- Chinese import penetration ratio: Δimport_pen_l = Σ_j (ΔM_us_jl / L_l) — measures change in Chinese imports per worker in local labor market l
- Commuting zone (CZ) as geographic unit of analysis for local labor markets
- Adjustment costs: barriers to geographic and sectoral reallocation of labor
- Trade adjustment assistance (TAA) programs as policy response
- Transfer payment dependency as adjustment mechanism
- Bijak-Borjas sectoral reallocation model: labor moves across sectors with adjustment costs
- Exposure index: variation in China import competition driven by pre-existing industry composition across regions

### Resultados / Teoremas
> Hypothesis 1: Regions more exposed to Chinese import competition experience larger declines in manufacturing employment
> Hypothesis 2: Employment declines are partially offset by increases in non-manufacturing employment but net employment falls
> Hypothesis 3: Local labor markets adjust through reduced employment, increased transfer payments (disability, unemployment, welfare), and out-migration rather than wage declines

### Fórmulas
- `Δimport_pen_l = Σ_j [ΔM_us_jl / L_l] where M_us_jl is imports of industry j in location l, L_l is local employment`
- `Exposure instrumental variable: uses changes in Chinese imports to other high-income countries to identify exogenous variation`
- `Total employment effect: ΔY_l / L_l ≈ β₁ × Δimport_pen_l + controls`
- `Transfer payment effect: ΔTransfers_l / L_l ≈ β₂ × Δimport_pen_l`
- `Wage effect: ΔWage_l / L_l ≈ β₃ × Δimport_pen_l (found to be small)`

### Supuestos
> Chinese import competition variation across US regions is exogenous (not driven by local demand shocks)
> Commuting zones approximate local labor markets where workers live and work
> Pre-existing industry composition determines differential exposure to Chinese imports
> Transfer payment and employment data accurately capture adjustment mechanisms

### Intuición
Chinese manufacturing exports created winners and losers across US regions. Regions whose industries competed most directly with Chinese imports experienced substantial job losses (about 2.4 manufacturing jobs per worker of Chinese import exposure), but these losses were not fully offset by gains in other sectors. Workers in affected regions shifted to transfer programs (disability, unemployment insurance) and some migrated away, while wages in affected regions did not decline dramatically — suggesting the margin of adjustment was extensive (employment) rather than intensive (wages). This paper establishes the key empirical framework used by subsequent papers on China shock effects in different countries.

### Conexiones
- Directly relevant to Mexico's experience: China shock affects Mexico both through direct competition and through US market access
- Methodology (import exposure index) used in Bhalotra/Mendez (2015) for Mexico
- Provides framework for understanding how trade shocks create informality (displaced formal workers may enter informal sector)
- Connects to Dell et al. (2019) on violence consequences of trade-induced displacement
- Policy relevance for TAA and welfare programs in developing countries

### Metodología
- **approach:** Empirical, difference-in-differences with instrumental variables
- **data:** US Census, ACS, BLS Quarterly Census of Employment and Wages, BEA regional economic accounts, transfer payment data from SSA and HHS
- **geographic_unit:** Commuting zones (CZs) defined by Tolba (1998)
- **time_period:** 1990-2007, with focus on 2000-2007 China shock period
- **key_innovation:** Use of other countries' imports from China as instruments for US local exposure; high cross-regional variation in exposure

---

## dixcarneiro2017
**Tema:** Trade Liberalization and Regional Dynamics: Long-Run Effects of Brazilian Trade Reform (Dix-Carneiro & Kovak 2017)

### Conceptos Clave
- Trade liberalization index (TRI): measures the degree of tariff reduction experienced by each industry during Brazilian reform
- Regional exposure to trade liberalization: variation in pre-reform industry composition across microregions
- Long-run persistence: regional effects of trade shocks amplify over time rather than dissipating
- Dynamic comparative advantage: regions adjust production patterns slowly over decades
- Migration as adjustment mechanism: workers move from negatively to positively affected regions
- Regional convergence: negatively affected regions converge to lower income levels
- Increasing returns to scale in local economies: trade shocks may trigger self-reinforcing regional decline

### Resultados / Teoremas
> Proposition 1: Regions more exposed to trade liberalization experience initial negative effects that amplify over time
> Proposition 2: Wage and employment effects grow larger 10-20 years after liberalization
> Proposition 3: Migration partially offsets regional effects but is insufficient to eliminate them
> Proposition 4: Regional inequality increases persistently due to trade liberalization

### Fórmulas
- `TRI_j = average tariff reduction in industry j during 1988-1994`
- `Regional exposure_m = Σ_j (employment_jm / employment_m) × TRI_j — weighted average tariff reduction across industries in microregion m`
- `Wage response: Δln(w_m) / Δt ≈ β₁ × TRI_m + β₂ × TRI_m × t — time-varying coefficient`
- `Employment response: ΔEmp_m / L_m ≈ γ₁ × TRI_m + γ₂ × TRI_m × t`
- `Migration rate: Mig_m ≈ δ₁ × TRI_m + δ₂ × TRI_m × t`

### Supuestos
> Pre-reform industry composition across microregions is exogenous to post-reform economic outcomes
> Tariff reductions during 1988-1994 represent the primary trade policy change
> Brazilian microregions approximate local labor markets
> Migration data from census accurately capture regional mobility patterns

### Intuición
Brazil's trade liberalization in the late 1980s/early 1990s created differential effects across regions based on their pre-existing industrial structure. Regions with industries that experienced large tariff cuts (typically capital-intensive manufacturing) saw persistent negative effects on wages and employment. Surprisingly, these effects grew larger over time — 20 years later, negatively affected regions were still declining relative to positively affected ones. This 'increasing' pattern challenges the standard expectation that trade adjustment is temporary. The mechanism appears to involve: (1) slow reallocation of capital and skills, (2) self-reinforcing agglomeration effects where negative shocks trigger further decline, and (3) insufficient migration to equalize wages across regions. This paper is crucial for understanding that trade shocks can create permanent regional inequality.

### Conexiones
- Directly relevant to Mexico: NAFTA created similar differential regional exposure to trade reform
- Methodology used by Dell et al. (2019) and Mendez (2015) for Mexico
- Long-run persistence of effects challenges standard trade models predicting temporary adjustment
- Increasing regional inequality connects to Mexico's North-South divide post-NAFTA
- Migration as adjustment mechanism connects to Mexico-US migration patterns

### Metodología
- **approach:** Empirical, difference-in-differences with regional variation
- **data:** Brazilian Census (1991, 2000, 2010), PNAD household surveys, Ministry of Finance tariff data
- **geographic_unit:** Microregions (733 units) defined by IBGE
- **time_period:** 1988-2010, focusing on 20-year effects of 1988-1994 liberalization
- **key_innovation:** Documenting increasing effects over time; showing trade shocks have permanent rather than temporary regional consequences

---

## dell2019
**Tema:** Violent Consequences of Trade-Induced Worker Displacement in Mexico (Dell, Feigenberg, Teshima 2019)

### Conceptos Clave
- Chinese import penetration in Mexican manufacturing: Δimport_pen_mex_l = Σ_j [ΔM_jl / L_l] — changes in Chinese imports of industry j per worker in local labor market l
- Violence as second-order effect of trade shocks: displacement → recruitment into organized crime → violence
- Narcotrafficking organization (DTO) expansion into new territories and activities
- Recruitment of displaced manufacturing workers by DTOs
- Self-reinforcing violence cycles: violence → reduced investment → further displacement → more violence
- Drug trafficking routes and geographic patterns of violence escalation
- State and municipal government capacity to respond to violence

### Resultados / Teoremas
> Hypothesis 1: Mexican local labor markets more exposed to Chinese import competition experience greater increases in violence
> Hypothesis 2: Violence increases are concentrated in municipalities with significant manufacturing employment losses
> Hypothesis 3: The effect operates through recruitment of displaced workers into narcotrafficking organizations
> Hypothesis 4: Violence has negative effects on subsequent local economic activity

### Fórmulas
- `Δimport_pen_l = Σ_j [ΔM_china_jl / L_l] where M_china_jl is Chinese imports of industry j in municipality l`
- `Violence response: ΔViolence_l ≈ β₁ × Δimport_pen_l + controls`
- `Employment effect: ΔEmp_l / L_l ≈ β₂ × Δimport_pen_l`
- `Heterogeneity: Violence effect β₁ varies by proximity to drug trafficking routes and DTO presence`

### Supuestos
> Chinese import competition variation across Mexican regions is exogenous
> Manufacturing job losses create a pool of potential recruits for narcotrafficking organizations
> DTO expansion into new territories and activities is a response to labor supply
> Violence data from INEGI accurately capture narcotrafficking-related violence

### Intuición
This paper reveals a dark side of trade liberalization in Mexico. When Chinese imports displaced Mexican manufacturing workers, particularly in regions specialized in industries like textiles, electronics, and furniture, some displaced workers were recruited by narcotrafficking organizations (DTOs). DTOs were expanding their operations — not just in drug production and trafficking, but also in extortion, kidnapping, and other illegal activities — and needed personnel. Manufacturing workers, particularly young men with limited education, were attractive recruits. The result was a significant increase in violence (homicides, kidnappings, extortions) in regions most affected by Chinese import competition. This violence, in turn, had further negative effects on local economic activity, creating a vicious cycle. The paper demonstrates that trade shocks can have security consequences that extend far beyond traditional economic channels.

### Conexiones
- Builds directly on Autor et al. (2013) methodology applied to Mexico
- Provides evidence for how trade-induced displacement can create informality through criminal economy recruitment
- Connects to Mexico's security crisis and narcotrafficking dynamics
- Relevant to understanding Mexico's informal sector expansion in regions affected by Chinese competition
- Policy implications for trade adjustment assistance and security spending

### Metodología
- **approach:** Empirical, difference-in-differences with instrumental variables
- **data:** Mexican Census (2000, 2010), INEGI mortality data, INEGI economic censuses, Ministry of Finance trade data
- **geographic_unit:** Municipalities (2,469 units) and local labor markets
- **time_period:** 2000-2010, focusing on effects of Chinese import surge after China's WTO accession
- **key_innovation:** Linking trade-induced displacement to narcotrafficking violence; documenting second-order security consequences of trade shocks

---

## margins2016
**Tema:** Margins of Labor Market Adjustment to Trade: Formal vs. Informal Employment in Brazil (Dix-Carneiro & Kovak 2016)

### Conceptos Clave
- Extensive margin of adjustment: changes in employment (extensive margin = hiring/firing)
- Intensive margin of adjustment: changes in hours or wages (intensive margin = quantity/price adjustment)
- Formal employment: registered with government, subject to labor regulations, social security contributions
- Informal employment: unregistered, outside formal labor market, no social security
- Informal sector as adjustment buffer: workers displaced from formal jobs move to informal sector
- Trade-induced structural transformation: shift across sectors and formality status
- Labor market dualism: formal vs. informal sectors as separate but linked markets
- Worker reallocation: movement of workers across sectors and formality status in response to trade shocks

### Resultados / Teoremas
> Proposition 1: Trade liberalization creates differential effects across formal and informal employment margins
> Proposition 2: Informal employment absorbs workers displaced from formal sector due to trade shocks
> Proposition 3: Formal sector wages adjust more than informal sector wages
> Proposition 4: Total adjustment is split between formal employment, informal employment, and wages

### Fórmulas
- `Total labor market response: ΔL_total = ΔL_formal + ΔL_informal`
- `Wage response: Δw_formal ≠ Δw_informal (asymmetric adjustment)`
- `Employment share response: Δ(L_formal/L_total) ≈ β₁ × trade_shock`
- `Informal employment response: ΔL_informal / L_total ≈ β₂ × trade_shock (positive β₂ = informal absorbs displaced workers)`
- `Formal employment response: ΔL_formal / L_total ≈ β₃ × trade_shock (negative β₃ = formal sector contracts)`

### Supuestos
> Formal and informal sectors are distinct but linked labor markets
> Workers can move between formal and informal sectors in response to trade shocks
> Informal sector employment is accurately measured in household surveys
> Pre-reform industry composition is exogenous to post-reform formality patterns

### Intuición
This paper examines how workers adjust to trade shocks across formal and informal labor markets. The key insight is that the informal sector acts as a buffer — when trade liberalization displaces workers from formal manufacturing jobs, many move to informal employment rather than becoming unemployed or leaving the labor force entirely. This has important implications: (1) traditional measures of 'unemployment' understate the true cost of trade adjustment because they miss informal sector absorption; (2) trade shocks can increase informality rates, with consequences for worker welfare (lower wages, no social security, less job security); (3) the formal sector bears most of the wage adjustment, while informal sector wages are relatively rigid. This paper is crucial for understanding Mexico's high informality rate and how trade shocks interact with labor market institutions.

### Conexiones
- Directly relevant to Mexico: NAFTA and Chinese imports both affect formal/informal composition
- Connects to Ulyssea (2018) on firm-level informality and development
- Provides mechanism for how trade liberalization affects informality rates in developing countries
- Relevant to understanding Mexico's persistent informality (57% of workforce)
- Policy implications: trade adjustment assistance should account for informal sector dynamics

### Metodología
- **approach:** Empirical, difference-in-differences with decomposition across formality margins
- **data:** PNAD (Pesquisa Nacional por Amostra de Domicílios) household surveys 1988-2010, Ministry of Finance tariff data
- **geographic_unit:** Microregions (733 units)
- **time_period:** 1988-2010, focusing on 1988-1994 Brazilian trade liberalization
- **key_innovation:** Decomposing trade adjustment into formal employment, informal employment, and wage margins; showing informal sector as adjustment buffer

---

## ulyssea2018
**Tema:** Firms, Informality, and Development: Theory and Evidence from Brazil (Ulyssea 2018)

### Conceptos Clave
- Extensive margin of informality: entry/exit of informal firms (extensive margin = number of firms)
- Intensive margin of informality: size and productivity of informal firms (intensive margin = scale of operation)
- Misallocation: inefficient allocation of resources across formal and informal firms due to informality costs
- Firm heterogeneity: variation in productivity across formal and informal firms
- Entry costs: fixed costs of entering formal vs. informal sector
- Taxes and regulation: formal firms face higher costs but also higher productivity (due to access to credit, contracts, etc.)
- Productivity distribution: informal firms have lower average productivity than formal firms
- General equilibrium effects: entry of informal firms affects formal firm outcomes through market competition
- Development trap: informality can trap economies in low-productivity equilibrium

### Resultados / Teoremas
> Proposition 1: Informality creates misallocation by allowing low-productivity informal firms to survive alongside high-productivity formal firms
> Proposition 2: Reducing informality costs increases aggregate productivity through reallocation from informal to formal firms
> Proposition 3: Both extensive and intensive margins of informality matter for aggregate outcomes
> Proposition 4: The effect of reducing informality depends on the share of economic activity in the informal sector

### Fórmulas
- `Firm profit (formal): π_f = A_f × L_f^α - w × L_f - F_f (where A_f is productivity, F_f is fixed cost including tax/regulation)`
- `Firm profit (informal): π_i = A_i × L_i^α - w × L_i - F_i (where F_i < F_f due to informality)`
- `Entry condition: firms enter if π ≥ 0`
- `Misallocation measure: MPL_ratio = MPL_formal / MPL_informal > 1 (inefficient if > 1)`
- `Aggregate productivity: Y = Σ_f A_f × L_f^α (depends on allocation across firms)`
- `Informality share: s_informal = Σ_i A_i × L_i^α / Y`

### Supuestos
> Firms choose between formal and informal status based on cost-benefit analysis
> Informal firms have lower fixed costs but also lower productivity (due to lack of access to credit, contracts, etc.)
> Workers can move between formal and informal firms
> General equilibrium: entry of informal firms affects formal firm outcomes through market competition and factor prices
> Constant returns to scale at firm level with firm-level productivity heterogeneity

### Intuición
This paper develops a theoretical and quantitative framework for understanding how informality affects aggregate productivity and development. The key insight is that informality creates misallocation: low-productivity informal firms survive because they avoid taxes and regulations, while high-productivity formal firms face higher costs. This means resources (labor, capital) are not allocated to their most productive uses. The paper shows that both the extensive margin (number of informal firms) and intensive margin (size of informal firms) matter. Reducing informality costs — for example, by simplifying registration, reducing taxes, or improving enforcement — can increase aggregate productivity by causing reallocation from informal to formal firms. This has important implications for developing countries like Mexico, where informality rates are high and trade liberalization may interact with informality dynamics.

### Conexiones
- Directly relevant to Mexico's high informality rate (57% of workforce)
- Connects to Dix-Carneiro & Kovak (2016) on formal/informal adjustment to trade
- Provides theoretical foundation for understanding how trade shocks affect informality through firm entry/exit
- Relevant to Aleman-Castilla (2006) on NAFTA and informality in Mexico
- Policy implications: reducing informality costs can improve aggregate productivity

### Metodología
- **approach:** Theoretical model (Melitz-style with formal/informal firms) + quantitative calibration
- **data:** Brazilian firm-level data from IBGE (Pesquisa Industrial Anual), formal sector employment data from CAGED, informality estimates from PNAD
- **model_type:** General equilibrium model with firm heterogeneity and endogenous formality choice
- **time_period:** Calibration to 2003 Brazilian economy
- **key_innovation:** Separating extensive vs. intensive margins of informality; showing misallocation costs of informality; quantitative policy experiments

---

## jimenez2012
**Tema:** Trade as Engine of Creative Destruction: Mexican Experience with Chinese Competition (Iacovone, Rauch, Winters 2013)

### Conceptos Clave
- Creative destruction: process of firm entry, exit, and product switching driven by competition (Schumpeter)
- Chinese import competition: increased imports from China after China's WTO accession (2001)
- Firm exit: low-productivity firms exit market due to Chinese competition
- Product switching: surviving firms drop products that compete with Chinese imports and move to new products
- Within-firm reallocation: firms shift resources from threatened to non-threatened product lines
- Firm-level productivity: survival and growth of more productive firms
- Product-level competition: Chinese imports directly compete with specific Mexican product lines
- Market selection: trade acts as selection mechanism, eliminating inefficient firms and products
- Industrial upgrading: firms move to higher-value products in response to competition

### Resultados / Teoremas
> Hypothesis 1: Chinese import competition increases firm exit rates in Mexican manufacturing
> Hypothesis 2: Surviving firms drop product lines that compete with Chinese imports
> Hypothesis 3: Product switching leads to movement toward higher-value, more skill-intensive products
> Hypothesis 4: The net effect of creative destruction is positive for surviving firms' productivity

### Fórmulas
- `Firm exit probability: P(exit)_f ≈ β₁ × Chinese_import_exposure_f + controls`
- `Product dropping: ΔProducts_f ≈ β₂ × Chinese_import_exposure_f (negative = dropping products)`
- `Product switching: New_products_f ≈ β₃ × Chinese_import_exposure_f`
- `Productivity change: ΔTFP_f ≈ β₄ × Chinese_import_exposure_f (positive = productivity gain)`
- `Import exposure: Exposure_f = Σ_j (M_china_j / M_j) × Sales_fj — share of firm's sales in industries with high Chinese import penetration`

### Supuestos
> Firm product mix before Chinese import surge determines exposure to competition
> Chinese imports directly compete with specific Mexican product lines
> Firms can adjust product mix in response to competitive pressure
> Product-level data accurately capture firm diversification and switching
> TFP measures accurately capture productivity changes

### Intuición
This paper examines how Mexican manufacturing firms responded to Chinese import competition through creative destruction. The key finding is that trade competition acts as a selection mechanism: low-productivity firms exit, surviving firms drop product lines that directly compete with Chinese imports, and they reallocate resources to new, often higher-value products. This is the 'engine of creative destruction' — trade doesn't just cause job losses, it also forces firms to upgrade and become more productive. However, the process is costly: firm exit destroys jobs and local economic activity, and product switching requires investment in new capabilities. The paper provides evidence that the firms that survive this process are more productive, but the transition costs are significant, particularly for workers and communities dependent on exiting firms.

### Conexiones
- Directly relevant to Mexico's experience with Chinese competition after WTO accession
- Connects to Autor et al. (2013) on labor market effects — this paper focuses on firm-level adjustment
- Provides micro-level evidence on the mechanisms behind aggregate employment losses
- Connects to Mendez (2015) on local labor market effects of Chinese import competition in Mexico
- Relevant to understanding how trade shocks create structural transformation in developing countries

### Metodología
- **approach:** Empirical, firm-level panel data analysis
- **data:** Mexican manufacturing census (ENCOHU/ENEU) 1994-2003, firm-level product data, trade data from INEGI
- **geographic_unit:** Firm-level (thousands of manufacturing establishments)
- **time_period:** 1994-2003, focusing on post-WTO accession Chinese import surge
- **key_innovation:** Product-level tracking within firms; documenting creative destruction mechanism at firm and product level

---

## bhalotra2015
**Tema:** Effect of Chinese Import Competition on Mexican Local Labor Markets (Mendez 2015)

### Conceptos Clave
- Chinese import penetration in Mexican manufacturing: same measure as Autor et al. (2013) applied to Mexico
- Trade diversion: Chinese imports replace not just Mexican production for domestic market but also Mexican exports to US
- Local labor market effects: differential impact across Mexican regions based on industry composition
- Employment share decline: manufacturing employment falls in regions exposed to Chinese competition
- Wage effects: wages decline in exposed regions, though less than employment
- Sectoral reallocation: workers move from manufacturing to services and agriculture
- Geographic mobility: some workers migrate from negatively affected regions
- NAFTA interaction: Chinese competition may have amplified NAFTA effects

### Resultados / Teoremas
> Hypothesis 1: Mexican local labor markets more exposed to Chinese import competition experience larger declines in manufacturing employment
> Hypothesis 2: Employment declines are partially offset by gains in non-manufacturing sectors
> Hypothesis 3: Trade diversion amplifies the effect of Chinese competition on Mexican regions
> Hypothesis 4: Effects are heterogeneous across regions with different pre-existing characteristics

### Fórmulas
- `Chinese import exposure: Δimport_pen_l = Σ_j [ΔM_china_jl / L_l] — same as Autor et al. (2013)`
- `Employment response: ΔEmp_l / L_l ≈ β₁ × Δimport_pen_l`
- `Wage response: ΔWage_l / L_l ≈ β₂ × Δimport_pen_l`
- `Trade diversion measure: ΔTradeDiversion_l = Σ_j [ΔM_china_jl × ExportShare_jl] — Chinese imports in industries where Mexico exports to US`
- `Total effect including diversion: ΔEmp_l / L_l ≈ β₃ × Δimport_pen_l + β₄ × ΔTradeDiversion_l`

### Supuestos
> Chinese import competition variation across Mexican regions is exogenous
> Trade diversion is an important channel: Chinese imports replace Mexican exports to US
> Local labor markets approximate commuting zones where workers live and work
> Pre-existing industry composition determines differential exposure to Chinese imports

### Intuición
This paper applies the Autor et al. (2013) framework to Mexico, showing that Chinese import competition had significant negative effects on Mexican local labor markets. The key innovation is documenting trade diversion: not only did Chinese imports compete with Mexican production for the domestic market, but they also displaced Mexican exports to the US. This means Mexican regions were hit twice — once by direct competition and once by loss of export markets. The effects were substantial: manufacturing employment declined significantly in exposed regions, with partial offset from non-manufacturing sectors. This paper provides important evidence on how the 'China shock' affected developing countries that were themselves competing with China in third markets (like the US).

### Conexiones
- Directly applies Autor et al. (2013) methodology to Mexico
- Connects to Dell et al. (2019) on violence consequences of Chinese import competition in Mexico
- Documents trade diversion channel — important for understanding Mexico's position between US and China
- Relevant to understanding Mexico's manufacturing decline in certain sectors post-WTO
- Provides evidence for how China shock affects developing countries through both direct and indirect channels

### Metodología
- **approach:** Empirical, difference-in-differences with instrumental variables
- **data:** Mexican Census (2000, 2010), ENOE household surveys, INEGI economic censuses, trade data from Ministry of Finance
- **geographic_unit:** Local labor markets (defined based on commuting patterns)
- **time_period:** 2000-2010, focusing on effects after China's WTO accession
- **key_innovation:** Documenting trade diversion channel; showing Chinese competition affects developing countries through both direct competition and export market displacement

---

# Wages & Minimum Wage

## informality_mexico
**Tema:** Effect of Trade Liberalization on Informality and Wages: Evidence from Mexico (Aleman-Castilla 2006)

### Conceptos Clave
- NAFTA (North American Trade Agreement): trade liberalization between US, Mexico, Canada starting 1994
- Trade liberalization measure: tariff reduction across industries during NAFTA implementation
- Informality rate: share of employment in informal sector (unregistered, no social security)
- Wage premium: difference between formal and informal sector wages
- Regional trade exposure: variation across Mexican states/regions in pre-NAFTA industry composition
- Formal sector job destruction: trade liberalization reduces formal employment
- Informal sector absorption: displaced formal workers move to informal employment
- Wage compression: trade liberalization may reduce wage inequality between formal and informal sectors

### Resultados / Teoremas
> Hypothesis 1: Regions more exposed to NAFTA tariff reductions experience larger increases in informality
> Hypothesis 2: Trade liberalization reduces formal sector employment and increases informal employment
> Hypothesis 3: Wage effects are heterogeneous across formal and informal sectors
> Hypothesis 4: NAFTA reduced the formal-informal wage premium in more trade-exposed regions

### Fórmulas
- `Trade exposure: Δtariff_j = tariff_j,pre - tariff_j,post — tariff reduction in industry j during NAFTA`
- `Regional exposure: Exposure_m = Σ_j (employment_jm / employment_m) × Δtariff_j`
- `Informality response: ΔInformality_m ≈ β₁ × Exposure_m`
- `Wage response (formal): Δw_formal_m ≈ β₂ × Exposure_m`
- `Wage response (informal): Δw_informal_m ≈ β₃ × Exposure_m`
- `Wage premium change: Δ(w_formal - w_informal)_m ≈ β₄ × Exposure_m`

### Supuestos
> Pre-NAFTA industry composition across Mexican states is exogenous to post-NAFTA economic outcomes
> NAFTA tariff reductions represent the primary trade policy change during 1994-2000
> Informal sector employment is accurately measured in Mexican household surveys (ENOE/ENE)
> Workers can move between formal and informal sectors in response to trade shocks

### Intuición
This paper provides early evidence on how NAFTA affected Mexico's informal sector. The key finding is that regions with industries that experienced large tariff reductions under NAFTA saw significant increases in informality rates. Workers displaced from formal manufacturing jobs — which were protected by tariffs before NAFTA — moved into informal employment rather than becoming unemployed. This has important implications: (1) NAFTA's benefits may have been overstated if we only look at formal employment; (2) the informal sector absorbed the adjustment costs of trade liberalization; (3) informal workers face lower wages, no social security, and less job security. The paper demonstrates that trade liberalization in developing countries has distributional consequences beyond standard trade models, particularly through the formal-informal labor market channel.

### Conexiones
- Directly relevant to Mexico's NAFTA experience and informality dynamics
- Connects to Dix-Carneiro & Kovak (2016) on formal/informal adjustment margins in Brazil
- Provides early evidence on NAFTA effects before the China shock (Autor et al., Dell et al.)
- Relevant to understanding Mexico's persistent informality despite trade liberalization
- Policy implications for trade adjustment assistance and labor market institutions

### Metodología
- **approach:** Empirical, difference-in-differences with state-level variation
- **data:** Mexican household surveys (ENE/ENOE), Ministry of Finance tariff data, INEGI economic censuses
- **geographic_unit:** Mexican states (32 units) and municipalities
- **time_period:** 1988-2002, focusing on NAFTA implementation 1994-2000
- **key_innovation:** Early evidence on NAFTA's effect on informality; showing informal sector as adjustment buffer to trade liberalization in Mexico

---

## A measure of trend wage inflation.pdf
**Tema:** Trend Wage Inflation (TWIn): Constructing a filtered measure of persistent aggregate nominal wage growth using dynamic factor models on CPS worker-level data

### Conceptos Clave
- **Trend Wage Inflation (TWIn)**: The persistent (trend) component of aggregate nominal wage growth, filtered from noise and transitory fluctuations using a dynamic factor model. Measured as annualized monthly wage growth.
- **Temporal aggregation**: The challenge that CPS wage inflation is measured as a 12-month rate of change rather than month-on-month, requiring explicit modeling to recover monthly persistence.
- **Common vs. sector-specific persistent component**: TWIn decomposes into a component common across all workers/industries (α_{τ,it}·τ_{ct}) and a sector-specific component (τ_{it}), allowing quantification of which drives aggregate dynamics.
- **Dynamic factor model with time-varying parameters**: A state-space model where sector-level wage trends follow random walks with stochastic volatilities and time-varying loadings on a common factor.
- **Composition-adjusted wage inflation**: Median 12-month wage growth for the same individuals observed 12 months apart in the CPS, controlling for workforce composition changes.
- **Labor market tightness**: Measured by the vacancy-to-unemployment ratio (V/U); TWIn is strongly contemporaneously correlated with changes in this measure.
- **Measurement error in CPS wages**: Transitory noise in observed wage growth that scales inversely with sample size, modeled as sector-specific transitory components.
- **Within-worker wage change**: Wage growth measured for the same individual observed 12 months apart in the CPS rotating panel, analogous to within-job changes in the ECI.

### Resultados / Teoremas
> **TWIn decomposition:** w_{it} = (1/12) Σ_{ℓ=1}^{12} τ̃_{i,t+1-ℓ} + ε̃_{it}, where τ̃_{it} = α_{τ,it}·τ_{ct} + τ_{it} is the persistent component and ε̃_{it} = α_{ε,it}·ε_{ct} + ε_{it} is the transitory component.

### Fórmulas
- **Wage inflation definition**: `w_{it} = ln(W_{i,j50,t} / W_{i,j50,t-12})` — 12-month rate of median hourly wage growth for sector i at month t, where j50 denotes the median individual
- **Trend component dynamics**: `τ_{ct} = τ_{c,t-1} + σ_{Δτ,ct}·η_{Δτ,ct}; τ_{it} = τ_{i,t-1} + σ_{Δτ,it}·η_{Δτ,it}` — Common and sector-specific trends follow random walks with innovation standard deviations σ
- **Aggregate trend wage inflation**: `τ̃_t = Σ_{i=1}^{n} s_{it}·τ̃_{it} = (Σ s_{it}·α_{τ,it})·τ_{ct} + Σ s_{it}·τ_{it}` — TWIn is the employment-share-weighted sum of sector-level trends, decomposable into common and sector-specific parts
- **MRPL and wage markdown (used in later paper)**: `mrpl_{it} = ∂r_{it}/∂n_{it} = α · r_{it}/n_{it}` — Marginal revenue product of labor equals the revenue-labor elasticity times average revenue per worker

### Supuestos
> Wage growth is observed as a 12-month rate (temporal aggregation)
> Trends are modeled as random walks (no mean reversion)
> Transitory component ε̃_{it} captures measurement error
> Loadings α_{τ,it} can be time-varying but drift slowly
> Innovations are serially and cross-sectionally independent N(0,1)
> Common transitory component ε_{ct} is small (consistent with sampling-based measurement error)

### Intuición
Just as core inflation filters out volatile food/energy prices, TWIn filters out transitory wage noise. By explicitly modeling how 12-month wage changes aggregate monthly dynamics, the model recovers a timely indicator that moves with labor market tightness—unlike raw CPS measures or the ECI. The common factor explains 50–85% of TWIn declines during recessions and ≥80% of the 2021 inflation surge, suggesting aggregate (not sector-specific) shocks dominate.

### Conexiones
- Directly relevant to understanding Mexican wage dynamics: the methodology can be applied to INEGI/ENOE worker-level data to construct a Mexican TWIn
- The strong co-movement with labor market tightness suggests that similar filtered indicators could track wage pressures in Mexico's formal labor market
- Sector-specific components declining since the 1990s may relate to declining union power and increasing wage dispersion in Mexico
- The framework's ability to separate common from sectoral shocks is relevant for understanding how minimum wage hikes propagate across industries in Mexico

### Metodología
- **empirical_strategy:** Dynamic factor model with time-varying parameters estimated via Bayesian MCMC
- **data_sources:** Current Population Survey (CPS) monthly worker-level data, 1997–2023
- **identification:** Cross-sectional variation across 7 broad industry groups; temporal aggregation structure identifies monthly persistence from 12-month observed rates
- **key_innovation:** Explicit modeling of monthly-to-yearly temporal aggregation in the trend component

---

## German Economic Review - 2019 - Neumark - The Econometrics and Economics of the Employment Effects of Minimum Wages.pdf
**Tema:** Review and critical assessment of the econometric methods and economic reasoning used to estimate minimum wage employment effects, focusing on the US literature

### Conceptos Clave
- **Employment elasticity w.r.t. minimum wage**: The percentage change in employment divided by the percentage change in the minimum wage; the standard parameter of interest. Literature range: -0.1 to -0.2 for low-skilled groups.
- **Close controls (geographically proximate)**: Using only counties/states near a state border as the comparison group, rather than all states. Tends to produce estimates closer to zero.
- **Two-way fixed effects (TWFE)**: Standard DD estimator with state and time fixed effects: E_{st} = β·MW_{st} + X_{st}γ + D_s h + D_t k + ε_{st}. The 'workhorse' of the literature.
- **Triple-differences (DDD)**: Adding a third dimension (e.g., more- vs. less-affected workers within the same state) to isolate the policy effect from confounders common to the state.
- **Synthetic control method**: Data-driven construction of a weighted combination of control states to match the treated state's pre-treatment trends.
- **Non-linearity of minimum wage effects**: The hypothesis that employment effects may be negligible at moderate minimum wages but become large at very high levels (the 'experiment' with $15+ minimums).
- **Endogenous minimum wage variation**: The concern that states raise minimum wages in response to economic shocks, creating spurious correlations between minimum wages and employment.

### Resultados / Teoremas
> **Standard two-way fixed effects estimator:** E_{st} = β̂·MW_{st} + X_{st}γ + D_s h + D_t k + ε_{st}, where β̂ identifies the effect of within-state minimum wage changes over time, assuming ε_{st} ⊥ MW_{st} conditional on controls.
> **Close-controls estimator with region-year interactions:** E_{st} = β̂·MW_{st} + X_{st}γ + D_s h + D_t k + (D_r × D_t)g + ε_{st}, where identification comes from within-region variation in minimum wages.

### Fórmulas
- **TWFE estimator**: `E_{st} = β̂·MW_{st} + X_{st}γ + D_s h + D_t k + ε_{st}` — Log employment rate regressed on log minimum wage with state and year fixed effects
- **Close-controls specification**: `E_{st} = β̂·MW_{st} + X_{st}γ + D_s h + D_t k + (D_r × D_t)g + ε_{st}` — Augmented TWFE adding region×year interactions to absorb regional shocks
- **DDD estimator**: `E_{cst} = β̂·POST_t × H_{cs} + X_{cs}γ + H_{cs}w + D_s h + D_t k + ε_{cst}` — Triple-differences comparing more-affected (H=1) vs. less-affected workers within states after federal minimum wage increases
- **IV first stage**: `MW_{st} = φ_s·MWF_t + X_{st}γ + D_s h + D_t k + ε_{st}` — State minimum wage instrumented by federal minimum wage × historical propensity to let federal floor bind

### Supuestos
> Parallel trends: in the absence of minimum wage changes, treated and control areas would follow similar employment trajectories
> No anticipation: firms/workers do not change behavior before the minimum wage takes effect
> SUTVA: one state's minimum wage does not affect another state's employment
> Exclusion restriction (for IV): the instrument affects employment only through the minimum wage

### Intuición
The literature is deeply divided along methodological lines. National TWFE studies tend to find negative employment effects (-0.1 to -0.2 elasticities), while geographically-proximate designs find effects close to zero. Neumark argues this divergence may stem from: (1) close controls inadequately addressing spatial heterogeneity, (2) sensitivity to trend specification, or (3) endogeneity. The key insight is that predicting effects of very large minimum wage increases (e.g., $15) from studies of small increases is inherently risky—behavioral responses may change qualitatively at higher wage floors.

### Conexiones
- The debate about appropriate counterfactuals is directly relevant to evaluating Mexico's 100% minimum wage increase at the northern border
- The distinction between close-controls and national estimates parallels debates about Mexico's regional minimum wage heterogeneity
- The concern about non-linearity at high minimum wages is crucial for Mexico, where the ZLFN minimum wage represents a very high Kaitz index
- The DDD approach using federal variation is analogous to exploiting the differential 100% vs. 16% increase across Mexican regions

### Metodología
- **empirical_strategy:** Comprehensive literature review and methodological comparison of TWFE, close-controls, DDD, IV, and synthetic control approaches
- **data_sources:** CPS, QCEW, QWI, SIPP across multiple US studies
- **identification:** Comparison across identification strategies; key divide between national and geographically-proximate designs
- **key_innovation:** Framework for evaluating which identification strategies are most credible and why results diverge

---

## Minimum Wage Effects Across State Borders Dube.pdf
**Tema:** Estimating minimum wage effects on restaurant employment and earnings using contiguous county pairs across US state borders as identification

### Conceptos Clave
- **Contiguous border county-pair (CBCP)**: A pair of adjacent counties on opposite sides of a state border, used as a natural experiment where minimum wages differ but local economic conditions are similar.
- **Spatial heterogeneity bias**: Bias in national-level estimates arising from unobserved differences in employment trends across states that are correlated with minimum wage policy but unrelated to it.
- **Pair-period fixed effects**: Fixed effects for each contiguous county-pair and time period, ensuring identification comes only from within-pair variation in minimum wages.
- **Cross-border spillovers**: Potential effects of a minimum wage increase in one county on employment/wages in the adjacent county across the state border.
- **Spatial autocorrelation**: Correlation of error terms across nearby counties, which inflates precision of individual case study estimates when not accounted for.

### Resultados / Teoremas
> **Main result: No adverse employment effects from contiguous county comparisons:** When comparing all contiguous county pairs straddling state borders, the employment elasticity with respect to the minimum wage is indistinguishable from zero, ruling out elasticities more negative than -0.147 at 90% or -0.178 at 95% confidence.

### Fórmulas
- **Traditional fixed-effects specification**: `ln y_{it} = α + γ ln(MW_{it}) + δ ln(y^TOT_{it}) + χ ln(pop_{it}) + φ_i + σ_t + ε_{it}` — Log employment/earnings regressed on log minimum wage with county and period fixed effects, controlling for total employment and population
- **Close-controls specification with census division trends**: `ln y_{it} = α + γ ln(MW_{it}) + δ ln(y^TOT_{it}) + χ ln(pop_{it}) + φ_i + σ_{ct} + ε_{it}` — Same as above but with census-division-specific time fixed effects σ_{ct}
- **Preferred local specification**: `ln y_{ipt} = α + γ ln(MW_{ipt}) + δ ln(y^TOT_{ipt}) + χ ln(pop_{ipt}) + φ_i + σ_{pt} + ε_{ipt}` — Log outcome regressed on log minimum wage with county and pair-period fixed effects, using only within-pair variation

### Supuestos
> E[ln(MW); ε_{ipt}] = 0: minimum wage differences within pairs are uncorrelated with residual employment/earnings differences
> Contiguous counties are valid controls: they share local economic conditions but face different minimum wages
> No cross-border spillovers: employment effects in one county do not contaminate the control county
> Parallel trends: absent minimum wage changes, border county pairs would follow similar employment trajectories

### Intuición
The paper resolves the conflict between national studies (finding negative effects) and case studies (finding none). National estimates suffer from spatial heterogeneity—states that raised minimum wages also had different employment growth trends for reasons unrelated to minimum wages. By comparing only adjacent counties across borders, this heterogeneity is eliminated. Pre-treatment employment levels and trends are nearly zero for border pairs, confirming their validity as controls. The welfare implications are stark: national estimates imply labor demand elasticity near -1 (minimum wage hikes don't raise earnings), while local estimates rule out elasticities below -0.48, suggesting minimum wages substantially raise total earnings at affected jobs.

### Conexiones
- Directly applicable to Mexico's ZLFN, where the 100% minimum wage increase creates a natural experiment similar to US state border discontinuities
- The methodology of comparing contiguous areas across policy borders is the template for analyzing Mexico's differentiated minimum wage
- The finding that spatial heterogeneity biases national estimates has implications for Mexico's national-level minimum wage studies
- The QCEW data approach parallels Mexico's IMSS administrative data for formal sector employment analysis
- The restaurant sector focus is relevant because food services are heavily affected by Mexico's minimum wage changes

### Metodología
- **empirical_strategy:** Difference-in-differences using contiguous border county pairs with pair-period fixed effects
- **data_sources:** Quarterly Census of Employment and Wages (QCEW), 1990Q1–2006Q2, 1,380 counties
- **identification:** Policy discontinuities at state borders; within-pair variation in minimum wages
- **key_innovation:** Pooling all contiguous border county pairs and accounting for spatial autocorrelation in standard errors

---

## Minimum wages in the 21 century.pdf
**Tema:** Comprehensive handbook chapter reviewing the evolution, theory, and empirical evidence on minimum wage effects on employment, wages, inequality, and margins of adjustment globally

### Conceptos Clave
- **Own-wage employment elasticity (OWE)**: The percentage change in employment divided by the percentage change in wages induced by the minimum wage. More comparable across studies than the minimum wage elasticity because it accounts for the bite of the policy.
- **Hicks-Marshall rule of derived demand**: 
- **Kaitz index**: The ratio of the minimum wage to the median (or mean) wage; measures the 'bite' of the minimum wage policy. Higher values indicate more binding minimum wages.
- **Stacked event-study approach**: A pooled event study that creates event-specific datasets (one treated state + clean controls), stacks them, and estimates treatment effects using event-time alignment rather than calendar time.
- **Bunching estimator**: Estimating employment effects by comparing excess jobs at/above the new minimum to missing jobs below it in the wage distribution.
- **Monopsony model**: A labor market model where firms have wage-setting power due to labor market frictions, implying that moderate minimum wage increases can raise both wages and employment.
- **Margins of adjustment**: The various channels through which firms respond to minimum wage increases beyond employment: prices, profits, amenities, capital-labor substitution, firm entry/exit, productivity.
- **Price pass-through**: The fraction of minimum wage-induced labor cost increases that firms pass on to consumers through higher prices.

### Resultados / Teoremas
> **OWE as LATE:** The own-wage employment elasticity can be interpreted as a Local Average Treatment Effect (LATE): OWE = IV = Δln(emp|MW=1)/Δln(wage|MW=1) for compliers affected by the minimum wage change.

### Fórmulas
- **Hicks-Marshall labor demand elasticity**: `ε_{L,W} = -(1/(1-share_L)) · share_K · σ_{K,L} · ε` — The neoclassical prediction for how employment responds to wage changes, decomposed into substitution and scale effects
- **OWE (IV interpretation)**: `OWE = IV = Δln(emp|MW=1)/Δln(wage|MW=1)` — Own-wage employment elasticity as the ratio of the reduced-form employment effect to the first-stage wage effect
- **TWFE-log(MW) specification**: `y_{st} = β·ln(MW_{st}) + X_{st}γ + α_s + δ_t + ε_{st}` — Outcome regressed on log minimum wage with unit and time fixed effects
- **Stacked event-study estimator**: `y_{hs} = Σ_k β_k · [τ=k] × D_{hs} + α_{hs} + δ_{ht} + γ·X_{hst} + ε_{hst}` — Outcome in event h, state s regressed on event-time indicators with event-specific state and time fixed effects
- **LP-DiD estimator**: `ȳ_{st} = β·D_{st} + ε_{st}, where ȳ_{st} = (1/5)Σ_{k=0}^{4}(y_{s,t+k} - y_{s,t-1})` — Long-differenced outcome averaged over post-treatment window, regressed on treatment indicator

### Supuestos
> Competitive labor market (neoclassical baseline): many firms, free entry/exit, homogeneous workers
> Parallel trends: treated and control groups would follow similar trajectories absent the minimum wage change
> No anticipation: behavioral responses occur only after the minimum wage takes effect
> Exclusion restriction (for OWE as LATE): minimum wage affects employment only through wages
> Relevance (for OWE): minimum wage change produces a strong first stage in wages

### Intuición
The chapter synthesizes three decades of 'new minimum wage research' that shifted the field from neoclassical consensus (MW reduces employment) to a more nuanced picture. The key insight is that the OWE framework—treating employment effects as a function of actual wage changes rather than policy changes—resolves many apparent contradictions. Different studies find different MW elasticities but similar OWEs because the 'bite' of the policy varies. The chapter also documents that firms adjust along multiple margins (prices, profits, amenities, productivity), and that the competitive model's prediction of unambiguous job loss is not supported by the bulk of modern evidence, especially for moderate minimum wage levels.

### Conexiones
- The OWE framework is directly applicable to Mexico: scaling employment effects by the actual wage increase from the 100% minimum wage hike at the ZLFN
- The Kaitz index for Mexico's ZLFN would be very high, placing it in the range where non-linear effects might emerge
- Price pass-through evidence is directly relevant to the Calderón et al. paper on Mexico's simultaneous MW and VAT changes
- The margins of adjustment framework explains why Mexico's informal sector may absorb minimum wage effects differently than formal employment
- The event-study methodology proposed here is the gold standard for analyzing Mexico's staggered minimum wage increases across regions
- The developing-country section (Section 6) discusses how informality creates different adjustment mechanisms than in advanced economies

### Metodología
- **empirical_strategy:** Comprehensive review covering TWFE, case studies, stacked event studies, border discontinuity, synthetic control, and bunching estimators
- **data_sources:** CPS, QCEW, administrative data from multiple countries, World Bank Enterprise Surveys
- **identification:** Multiple approaches compared; emphasis on event-study designs with clean controls and proper parallel trends testing
- **key_innovation:** OWE framework for comparable elasticities across studies; demonstration that TWFE-log(MW) is sensitive to sample period and trend specification

---

## THE EFFECT OF MINIMUM WAGES ON LOW-WAGE JOBs Dube.pdf
**Tema:** Estimating the effect of minimum wages on the entire frequency distribution of low-wage jobs using a bunching/difference-in-differences approach

### Conceptos Clave
- **Missing jobs (Δb)**: The decrease in the number of jobs paying below the new minimum wage after a policy increase: Δb = Emp₁[w<MW] - Emp₀[w<MW]. These jobs either get raised to the minimum or are destroyed.
- **Excess jobs (Δa)**: The increase in jobs at and slightly above the new minimum wage, representing workers whose wages were raised into compliance. Fades out at threshold W above the minimum.
- **Net employment effect (Δe = Δa + Δb)**: The sum of excess and missing jobs, measuring the overall employment effect of the minimum wage on affected workers. If Δa + Δb ≈ 0, no net job loss occurred.
- **Bunching at the minimum wage**: The clustering of workers at and just above the new minimum wage after a policy change, analogous to bunching at tax thresholds in the public finance literature.
- **Frequency distribution approach**: Estimating employment changes by wage bins throughout the hourly wage distribution, rather than using aggregate employment measures.
- **Wage spillovers**: Wage increases for workers earning above the new minimum wage, extending up to approximately $3 above the minimum, representing about 40% of the total wage increase.
- **Own-wage employment elasticity**: OWE = Δln(emp)/Δln(wage) = 0.41 (s.e. 0.43), ruling out elasticities more negative than -0.45 at 95% confidence.

### Resultados / Teoremas
> **Main result: No net disemployment from minimum wage increases:** Across 138 prominent state minimum wage increases (1979–2016), the number of excess jobs closely matches the number of missing jobs. Employment for affected workers rose by a statistically insignificant 2.8% (s.e. 2.9%), while average wages rose by 6.8% (s.e. 1.0%).

### Fórmulas
- **Net employment effect**: `Δe = Δa + Δb = Emp₁[w<W] - Emp₀[w<W]` — Total employment change below threshold W equals the sum of excess jobs above the minimum and missing jobs below it
- **Missing jobs**: `Δb = Emp₁[w<MW] - Emp₀[w<MW]` — Change in the number of jobs paying below the new minimum, reflecting either wage increases or job destruction
- **Event-study specification**: `Δy_{s,t+k} = Σ_k β_k · D_{s,t} + α_s + δ_t + ε_{st}` — Change in outcome in state s at event-time k, with state and calendar time fixed effects
- **Own-wage employment elasticity**: `OWE = Δln(emp_affected)/Δln(wage_affected)` — Percentage change in employment of affected workers divided by their percentage wage change

### Supuestos
> Parallel trends in the wage frequency distribution for treatment vs. control states
> The effect of the minimum wage on wages fades out at some threshold W above the minimum
> Upper-tail employment effects are negligible (validated empirically—no changes above W)
> The 138 events studied are representative of minimum wage increases more broadly

### Intuición
This paper's key innovation is decomposing the employment effect into its constituent parts: jobs lost below the minimum and jobs gained at/above it. Unlike aggregate employment measures that can be confounded by unrelated shocks throughout the wage distribution, this localized approach focuses precisely where minimum wages bite. The finding that missing jobs approximately equal excess jobs is powerful evidence against disemployment—the minimum wage reshuffles wages upward without destroying net employment. The event-by-event analysis shows this pattern is robust across events with different Kaitz indices up to approximately 59%, and the pattern of pre-treatment parallel trends validates the identification strategy.

### Conexiones
- The bunching framework can be directly applied to Mexico's ENOE/IMSS data to assess the effect of the 100% minimum wage increase on the wage distribution at the ZLFN
- The finding that non-tradeable sectors show zero disemployment while tradeable sectors show negative effects is relevant for Mexico's border economy, which has significant manufacturing
- The 40% wage spillover finding helps explain how minimum wage increases propagate through the wage distribution in Mexico
- The critique of TWFE-log(MW) is important for Mexican researchers who may use similar specifications
- The Kaitz index threshold of ~59% is relevant for assessing whether Mexico's ZLFN minimum wage (where the Kaitz index is very high) might cross into disemployment territory
- The finding that incumbents experience spillovers but new entrants do not has implications for Mexico's formal-informal labor market dynamics

### Metodología
- **empirical_strategy:** Difference-in-differences event study applied to the frequency distribution of wages, comparing employment changes by wage bins across 138 minimum wage events
- **data_sources:** Current Population Survey (CPS) 1979–2016, hourly wage data
- **identification:** State-level minimum wage increases compared to clean control states within event windows; parallel trends tested pre-treatment
- **key_innovation:** Disaggregating employment effects by wage bins; bunching estimator applied in a difference-in-differences framework

---

## Missing Jobs Are a Conversion Problem, Not Just a Demand Problem.pdf
**Tema:** Reconceptualizing the missing jobs problem in developing countries as a failure of job conversion mechanisms rather than solely insufficient labor demand

### Conceptos Clave
- **Job conversion**: The institutional and market mechanisms that determine whether potential matches between firms and workers are formed, sustained, formalized, and upgraded into durable, productivity-supported employment.
- **Expected match surplus**: Anticipated productivity net of hiring costs, separation risk, and institutional constraints. Shapes vacancy posting, match durability, and investment in productivity-enhancing activities.
- **Employment elasticity of growth**: The responsiveness of employment to output growth; low values indicate that growth occurs without proportional job creation, suggesting conversion failures.
- **Hiring and matching frictions**: Joint frictions affecting workers' search effort and firms' recruitment/screening, amplified by thin information systems, weak credentialing, and limited contract enforceability.
- **Skills mismatch**: Misallocation of human capital across firms, sectors, and tasks—analogous to capital misallocation—constraining hiring in high-productivity activities.
- **Match durability**: The expected duration of an employment relationship; short durations reduce incentives for firm investment in training and worker-specific capital.

### Resultados / Teoremas
> **Conversion-constrained employment equilibrium:** When expected match surplus is depressed by weak conversion mechanisms (hiring frictions, skill misalignment, mobility barriers, regulatory misalignment), vacancy creation slows, matches are short-lived, and upgrading stalls. In equilibrium, this reduces observed labor demand and lowers the employment elasticity of growth.

### Fórmulas
- **Expected match surplus**: `EMS = E[productivity] - hiring costs - separation risk × replacement cost - institutional constraints` — The net expected value of a match to both firm and worker, determining whether matches form, persist, and upgrade

### Supuestos
> Output growth occurs but does not reliably translate into stable wage employment
> High labor force participation coexists with limited durable wage employment
> Informality, high separation rates, and short-duration jobs are widespread
> Minimum macroeconomic conditions are in place but conversion mechanisms are weak

### Intuición
The paper reframes the 'missing jobs' problem from a demand-side to a supply-side institutional issue. In many developing countries, output grows but employment remains informal, short-duration, and low-productivity because the mechanisms connecting firms and workers—matching, screening, mobility, retention, formalization—are broken. The expected match surplus framework unifies three conversion failures: (1) hiring frictions that raise the cost and uncertainty of matching, (2) skills constraints that reduce productivity alignment, and (3) risk/mobility barriers that shorten match duration. Strengthening conversion complements growth-oriented reforms by raising the employment elasticity of growth.

### Conexiones
- The conversion framework directly explains Mexico's high informality rate: despite GDP growth, potential matches don't convert into durable formal employment
- Weak matching and screening mechanisms are relevant for understanding why minimum wage increases may have different effects in formal vs. informal sectors in Mexico
- The framework suggests that minimum wage policies alone cannot address the conversion problem—they must be complemented by strengthening matching, signaling, and mobility
- The discussion of employer market power connects to Amodio et al.'s findings on labor market power in developing countries, including Mexico
- The emphasis on match durability relates to Mexico's high turnover in formal employment and the role of IMSS registration as a barrier to formalization
- The policy agenda (reduce spatial barriers, improve signaling, strengthen match durability, address employer market power) is directly relevant to Mexican labor market reform

### Metodología
- **empirical_strategy:** Theoretical framework based on search-and-matching theory and surplus analysis, supported by evidence from randomized experiments in developing countries
- **data_sources:** Synthesis of experimental and observational evidence from India, Ghana, Uganda, Ethiopia, Bangladesh, and Brazil
- **identification:** Conceptual framework drawing on Mortensen-Pissarides search theory, dual economy models (Lewis), and experimental evidence
- **key_innovation:** Unifying 'missing jobs' and 'missing better jobs' within a single conversion framework

---

## Amodio Global Labor Market Power.pdf
**Tema:** Estimating labor market power (wage markdowns) of manufacturing establishments across 82 low and middle-income countries and its relationship with self-employment and labor market institutions

### Conceptos Clave
- **Wage markdown**: The ratio of the marginal revenue product of labor (MRPL) to the wage paid: λ_{it} = MRPL_{it}/w_{it} = α / (w_{it}·n_{it}/r_{it}). A value >1 indicates firms pay workers less than their marginal product—evidence of monopsony power.
- **Revenue-labor elasticity (α)**: The elasticity of firm revenue with respect to labor input, estimated from a Cobb-Douglas revenue production function. Key parameter for computing wage markdowns.
- **Hump-shaped relationship with self-employment**: Wage markdowns first increase and then decrease with the share of self-employed workers across countries. The quadratic fit explains 24% of cross-country variation in markdowns.
- **Labor supply elasticity to the wage**: ε(w) = φ(c_u)/Φ(c_u) > 0, where φ/Φ is the inverse Mills ratio. The elasticity of aggregate wage-sector labor supply with respect to the wage, determining firms' wage-setting power.
- **Role of unemployment protection**: In countries with unemployment protection, markdowns increase with self-employment (less elastic supply). Without protection, markdowns decrease with self-employment (more elastic supply). Institutions reverse the sign of the relationship.
- **Oligopsonistic labor market model**: A model with Cournot competition among firms for workers, heterogeneous self-employment abilities, and labor market frictions (job finding rate q < 1). Firms set wages below MRPL by a markdown that depends on firm size and labor supply elasticity.

### Resultados / Teoremas
> **Wage markdown decomposition:** ln(λ̃ - 1) = ln(s̃) - ln(ε(w)), where λ̃ is the median wage markdown, s̃ is the median firm-level employment share, and ε(w) is the aggregate wage work supply elasticity.
> **Hump-shaped relationship between markdowns and self-employment:** Without unemployment protection: ∂ε(w)/∂n_s > 0, so markdowns decrease with self-employment. With unemployment protection: ∂ε(w)/∂n_s < 0, so markdowns increase with self-employment. The sign of the relationship flips with institutions.

### Fórmulas
- **Revenue production function**: `ln r_{it} = α ln n_{it} + β ln k_{it} + γ ln m_{it} + ω_{it} + ε_{it}` — Cobb-Douglas revenue function with labor (n), capital (k), materials (m), productivity (ω), and error (ε)
- **MRPL**: `mrpl_{it} = ∂r_{it}/∂n_{it} = α · r_{it}/n_{it}` — Marginal revenue product of labor equals revenue-labor elasticity times average revenue per worker
- **Wage markdown**: `λ_{it} = mrpl_{it}/w_{it} = α · (r_{it}/(w_{it}·n_{it}))` — Ratio of MRPL to wage; equivalently, the revenue-labor elasticity divided by the labor share of revenues
- **Firm-level regression**: `ln λ_{imsct} = δ_{sc} + μ_{mc} + τ_t + β·X_{imsct} + u_{imsct}` — Log wage markdown regressed on firm characteristics with sector×country, local labor market, and year fixed effects
- **Cross-country regression**: `ln λ̃_c = α + β₁·SE_c + β₂·SE_c² + γ·X_c + ε_c` — Log median country-level wage markdown regressed on self-employment share and its square, with country controls
- **Aggregate labor supply with unemployment protection**: `n_w = q·Φ(c_p)/qw, ε(w) = φ(c_p)·qw/(b+q(w-b))` — Aggregate wage work supply and its elasticity, where c_p = log[b+q(w-b)] - μ and b is unemployment benefit

### Supuestos
> Revenue production function is Cobb-Douglas (robust to translog)
> ω_{it} evolves as a first-order Markov process (for proxy-variable estimation)
> Materials are the proxy variable (Levinsohn-Petrin / Ackerberg-Caves-Frazer)
> WBES is representative of manufacturing firms with ≥5 employees
> Self-employment share captures the availability of the outside option
> Unemployment protection is binary (available or not after 1 year of tenure)

### Intuición
This paper provides the first global, methodologically consistent estimate of labor market power across developing countries. The median wage markdown of 2.33 means workers earn about 43% of their marginal revenue product on average—substantial monopsony power. The hump-shaped relationship with self-employment is the key finding: at low self-employment (poor countries), more self-employment means more workers on the margin between sectors, making supply more elastic and reducing firm power. At high self-employment (middle-income countries with no unemployment protection), the same mechanism works. But with unemployment protection, workers are buffered from the risk of job loss, making them less responsive to wage changes, so self-employment correlates positively with power. This explains why labor market institutions matter for the distribution of income between firms and workers.

### Conexiones
- Directly relevant to Mexico: the paper's estimate of 42% wage share for Mexican manufacturing contrasts with 80% in Estefan et al., reflecting different sample compositions (WBES covers firms ≥5 employees only)
- The role of self-employment as an outside option connects to Mexico's ~57% informality rate, which functions similarly to self-employment in reducing firm wage-setting power
- The finding that labor market institutions change the sign of the self-employment–markdown relationship is crucial for Mexico, where labor protections (IMSS, severance pay) provide some buffer against job loss
- The wage markdown framework helps explain why minimum wage increases in Mexico may not lead to large employment losses: firms with monopsony power can absorb some cost increase without reducing employment
- The Cournot competition model with heterogeneous self-employment abilities provides a theoretical foundation for analyzing Mexico's dual labor market (formal vs. informal/self-employed)
- The finding that foreign-owned firms have more labor market power connects to Mexico's maquiladora sector and the role of multinational employers at the northern border

### Metodología
- **empirical_strategy:** Production function estimation using Ackerberg-Caves-Frazer (2015) proxy-variable method on panel data; cross-country comparisons with country-level regressions
- **data_sources:** World Bank Enterprise Survey (WBES) Global Panel, 2006–2021, 13,205 manufacturing establishments in 82 countries; ILO, World Bank WBEW for country characteristics
- **identification:** Proxy-variable methods for production function estimation; within-sector local-labor-market comparisons for firm-level regressions; cross-country regressions with quadratic fits
- **key_innovation:** First globally harmonized estimate of labor market power using consistent methodology; identification of self-employment and institutions as key correlates

---

## Disentangling the Effects of Large Minimum Wage and VAT Changes on Prices_ Evidence from Mexico.pdf
**Tema:** Disentangling the effects of a 100% minimum wage increase and a VAT rate cut (16% to 8%) on consumer prices at Mexico's northern border (ZLFN), January 2019

### Conceptos Clave
- **Zona Libre de la Frontera Norte (ZLFN)**: The free northern border zone created in January 2019 where the minimum wage doubled (from 88.36 to 176.72 pesos/day) and the VAT rate was halved (16% to 8%).
- **Fraction affected (FA_g)**: The percentage of workers in industry g whose December 2018 wage was below the new minimum wage. Used as a continuous measure of minimum wage bite across industries.
- **Triple-difference (DDD) estimation**: A joint estimation strategy that disentangles the minimum wage effect on VAT goods, the minimum wage effect on Non-VAT goods, and the VAT rate reduction effect on VAT goods.
- **VAT pass-through**: The fraction of a VAT rate change that is transmitted to consumer prices. Estimated at 0.32 for Mexico's 2019 reform—higher than previous estimates.
- **Informality and price pass-through**: Goods produced with higher shares of informal labor (Non-VAT goods) show smaller and less precisely estimated minimum wage effects on prices, because informal workers are not directly affected by the legal minimum.

### Resultados / Teoremas
> **Main results: minimum wage vs. VAT effects on prices:** The minimum wage increase raised the CPI at the northern border by 1.2%. The VAT rate reduction decreased it by 2.57%. The combined effect was a 1.37% price reduction—meaning the VAT cut more than offset the minimum wage-driven price increase.

### Fórmulas
- **Minimum wage effect on VAT goods**: `Y_{jct} = α₀ + α₁·Post_t × FA_{g(j)} + α₂·Sale_{jct} + α_{g(j),c} + α_t + ε_{jct}` — Log price regressed on post-treatment indicator interacted with fraction affected, with good×city and time fixed effects
- **Minimum wage effect on Non-VAT goods**: `Y_{jct} = β₀ + β₁·Post_t × ZLFN_c + β₂·Sale_{jt} + β_{g(j),c} + β_t + ε_{jct}` — Log price of Non-VAT items regressed on ZLFN×Post interaction with city×good and time fixed effects
- **VAT effect on VAT goods**: `Joint triple-difference combining the above two strategies` — Separately identifies MW effect on VAT goods, MW effect on Non-VAT goods, and VAT effect on VAT goods by exploiting industry and geographic variation

### Supuestos
> Parallel trends in the counterfactual price evolution across industries with different fractions affected
> Parallel trends in prices of Non-VAT goods across the ZLFN and the rest of the Northern Region
> Parallel trends in prices of VAT goods across the ZLFN and the rest of the Northern Region in the absence of either policy change
> The fraction affected (FA) is a valid measure of minimum wage bite that captures cost pressures
> No other policy changes (e.g., income tax credit) differentially affected the treatment and control groups

### Intuición
This paper tackles a uniquely Mexican natural experiment: the simultaneous 100% minimum wage increase and 50% VAT reduction at the northern border. The identification strategy elegantly disentangles the two policies by exploiting two dimensions of variation: (1) industries with different shares of workers affected by the minimum wage (for MW effects), and (2) the geographic boundary of the ZLFN (for MW and VAT effects). The key finding is that the VAT cut more than offset the minimum wage-driven price increase, resulting in a net price decrease. The role of informality is crucial: Non-VAT goods (produced with more informal labor) show small, insignificant MW effects, while VAT goods (more formal) show significant pass-through. This implies that in highly informal economies, minimum wage increases may have limited price effects because many workers in affected supply chains are not legally covered.

### Conexiones
- This is THE paper directly analyzing Mexico's 2019 minimum wage experiment at the ZLFN—the same policy that motivates much of the literature review
- The finding that informality dampens minimum wage price pass-through is crucial for understanding why minimum wage effects differ between Mexico's formal and informal sectors
- The DDD identification strategy provides a template for analyzing simultaneous policy changes—relevant for Mexico where minimum wage, tax, and social security policies often change together
- The 1.2% price increase from a 100% minimum wage increase suggests relatively low pass-through, consistent with the finding that firms absorb some cost increases (potentially through monopsony power as documented by Amodio et al.)
- The differential effects by informality share directly connect to the conversion framework (Belli & Raju) and the role of formal-informal labor market duality in Mexico
- The simultaneous implementation of MW and VAT changes echoes the policy combination approach discussed in the Dube-Lindner handbook chapter
- The data sources (INEGI INPC microdata, IMSS administrative records) are the same Mexican data infrastructure that researchers analyzing minimum wage effects in Mexico would use

### Metodología
- **empirical_strategy:** Triple-difference estimation exploiting variation in minimum wage bite across industries and geographic variation from the ZLFN boundary, combined with a separate difference-in-differences for the VAT effect
- **data_sources:** INEGI INPC product-level price quotes (semimonthly, 273 goods, 14 cities), IMSS employer-employee administrative data (monthly formal workers), ENOE labor force survey (informal worker shares by industry)
- **identification:** Industry variation in fraction affected by MW (for MW on VAT goods), geographic ZLFN vs. rest of Northern Region (for MW on Non-VAT goods and VAT effect), with dynamic specifications testing parallel trends
- **key_innovation:** Disentangling simultaneous minimum wage and VAT changes using industry × geographic variation; documenting role of labor informality in price pass-through

---

## Armangue-Jubert.pdf
**Tema:** Labor Market Power and Development (Armangué-Jubert, Guner, Ruggieri 2024, BSE WP 1446). Structural estimation of oligopsony model showing labor supply elasticity increases with GDP per capita; wage markdowns from 54% (poor) to 24% (rich); misallocation effects on GDP.

### Conceptos Clave
- **Oligopsony model**: Firms post wages taking into account their labor supply function (upward-sloping due to job differentiation and worker preferences); strategic interaction between firms generates wage-setting power.
- **Labor supply elasticity (ε_L)**: Key parameter measuring labor market competitiveness; low elasticity = high market power. Estimated to range from 0.84 (poorest) to 3.14 (richest countries).
- **Wage markdown**: The gap between wage and marginal product of labor: w_j = [1/(1+1/ε_L^j)] × MPL; ranges from 54% (poor countries) to 24% (rich countries).
- **Firm-size wage premium**: Positive relationship between firm size and wages, ∂ln(w_j)/∂ln(L_j) = 1/ε_L; decreasing with development as labor markets become more competitive.
- **Indirect inference estimation**: Method of Simulated Moments (MSM) matching model-predicted moments (number of firms, average size, size dispersion, wage dispersion, wage premium, GDP) to data moments from World Bank Enterprise Surveys.
- **Misallocation from amenities**: High-amenity low-productivity firms survive due to market power; higher elasticity forces reallocation from low to high-productivity firms.
- **Misallocation from strategic interaction**: When firms strategically interact, markdowns vary across firms (larger firms set higher markdowns), creating additional misallocation beyond amenities.
- **Free entry condition**: J active firms where marginal entrant has π_j = c_e; entry costs increase with development (225% to 1000% of average wage).

### Resultados / Teoremas
> **Proposition 1: Firm-Size Wage Premium and Elasticity:** Everything else equal, the firm-size wage premium ∂ln(w_j)/∂ln(L_j) declines when the elasticity of labor supply ε_L increases.
> **Proposition 2: Size Dispersion and Elasticity:** The size dispersion across firms var[ln(L_j)] = (ε_L/(1+ε_L))² var[ln(z_j)] increases with the elasticity of labor supply ε_L.
> **Proposition 3: Wage Dispersion and Elasticity:** The wage dispersion across firms var[ln(w_j)] = (1/(1+ε_L)²) var[ln(z_j)] + (1/ε_L²) var[a_j] decreases with the elasticity of labor supply ε_L.

### Fórmulas
- **Worker Utility**: `U_{ij} = ε_L ln(w_j) + a_j + v_{ij}` — Worker i's utility from firm j: wage utility (with elasticity ε_L) + amenities + idiosyncratic preference (Type-I EV)
- **Logit Labor Share**: `p_j = exp(ε_L ln(w_j) + a_j) / Σ_k exp(ε_L ln(w_k) + a_k)` — Share of workers choosing firm j follows multinomial logit; higher wages and amenities attract more workers
- **Firm Labor Supply**: `L_j(w_j) = L × p_j = L exp(ε_L ln(w_j) + a_j) / (λ_j + exp(ε_L ln(w_j) + a_j))` — Each firm faces an upward-sloping labor supply function
- **Firm Profit Maximization**: `max_{w_j} π_j = z_j ln(L_j(w_j)) - w_j L_j(w_j)` — Firm chooses wage to maximize profit given upward-sloping labor supply
- **Wage-Size Relation**: `ln(w_j) = (1/ε_L) ln(L_j) - (1/ε_L)[ln(L) + ln(λ) + a_j]` — Positive relationship between wages and firm size; slope = 1/ε_L maps directly to labor supply elasticity
- **Lerner Condition (Wage)**: `w_j = [1/(1+1/ε_L^j)] × z_j/L_j` — Firm-specific wage = markdown × marginal product of labor; ε_L^j depends on firm's market share
- **Size Dispersion**: `var[ln(L_j)] = (ε_L/(1+ε_L))² var[ln(z_j)]` — Size dispersion is an increasing function of labor supply elasticity
- **Wage Dispersion**: `var[ln(w_j)] = (1/(1+ε_L)²) var[ln(z_j)] + (1/ε_L²) var[a_j]` — Wage dispersion decreasing in elasticity (productivity component compressed, amenity component reduced)

### Supuestos
> Static economy with continuum of workers of measure L
> Log-concave utility: U_{ij} = ε_L ln(w_j) + a_j + v_{ij}
> Type-I EV preference shocks (generating logit demand)
> Perfectly competitive product markets (firms are price takers in output)
> Firms post wages; cannot perfectly discriminate among workers
> Free entry with fixed cost c_e
> Pareto-distributed firm productivity, Uniform-distributed amenities
> Endogenous number of firms J determined by zero-profit condition

### Intuición
The paper shows that labor market power (oligopsony) is a quantitatively important source of cross-country income differences. In poor countries, workers face few competitive alternatives (low ε_L), so firms can pay large markdowns below marginal product. This distorts the allocation of labor: low-productivity, high-amenity firms survive while high-productivity firms cannot attract enough workers. The counterfactual exercise shows that if poor countries had rich-country labor market competitiveness, their GDP per capita would increase by up to 45%.

### Conexiones
- T
- h
- i
- s
-  
- p
- a
- p
- e
- r
-  
- i
- s
-  
- a
- n
-  
- a
- p
- p
- l
- i
- c
- a
- t
- i
- o
- n
-  
- o
- f
-  
- s
- t
- r
- u
- c
- t
- u
- r
- a
- l
-  
- e
- s
- t
- i
- m
- a
- t
- i
- o
- n
-  
- i
- n
-  
- l
- a
- b
- o
- r
- /
- d
- e
- v
- e
- l
- o
- p
- m
- e
- n
- t
-  
- e
- c
- o
- n
- o
- m
- i
- c
- s
- .
-  
- W
- h
- i
- l
- e
-  
- i
- t
-  
- u
- s
- e
- s
-  
- M
- S
- M
-  
- (
- n
- o
- t
-  
- S
- C
-  
- o
- r
-  
- D
- i
- D
- )
- ,
-  
- i
- t
-  
- c
- o
- n
- n
- e
- c
- t
- s
-  
- t
- o
-  
- t
- h
- e
-  
- c
- a
- u
- s
- a
- l
-  
- i
- n
- f
- e
- r
- e
- n
- c
- e
-  
- l
- i
- t
- e
- r
- a
- t
- u
- r
- e
-  
- b
- y
-  
- q
- u
- a
- n
- t
- i
- f
- y
- i
- n
- g
-  
- h
- o
- w
-  
- m
- a
- r
- k
- e
- t
-  
- s
- t
- r
- u
- c
- t
- u
- r
- e
-  
- (
- l
- a
- b
- o
- r
-  
- m
- a
- r
- k
- e
- t
-  
- p
- o
- w
- e
- r
- )
-  
- c
- a
- u
- s
- e
- s
-  
- m
- i
- s
- a
- l
- l
- o
- c
- a
- t
- i
- o
- n
-  
- a
- n
- d
-  
- r
- e
- d
- u
- c
- e
- s
-  
- a
- g
- g
- r
- e
- g
- a
- t
- e
-  
- o
- u
- t
- p
- u
- t
- .
-  
- T
- h
- e
-  
- s
- t
- r
- u
- c
- t
- u
- r
- a
- l
-  
- m
- o
- d
- e
- l
-  
- a
- p
- p
- r
- o
- a
- c
- h
-  
- c
- o
- m
- p
- l
- e
- m
- e
- n
- t
- s
-  
- r
- e
- d
- u
- c
- e
- d
- -
- f
- o
- r
- m
-  
- m
- e
- t
- h
- o
- d
- s
- .
-  
- T
- h
- e
-  
- p
- a
- p
- e
- r
-  
- c
- o
- n
- t
- r
- i
- b
- u
- t
- e
- s
-  
- t
- o
-  
- u
- n
- d
- e
- r
- s
- t
- a
- n
- d
- i
- n
- g
-  
- w
- h
- y
-  
- p
- o
- o
- r
-  
- c
- o
- u
- n
- t
- r
- i
- e
- s
-  
- a
- r
- e
-  
- p
- o
- o
- r
- ,
-  
- a
-  
- c
- e
- n
- t
- r
- a
- l
-  
- q
- u
- e
- s
- t
- i
- o
- n
-  
- i
- n
-  
- d
- e
- v
- e
- l
- o
- p
- m
- e
- n
- t
-  
- e
- c
- o
- n
- o
- m
- i
- c
- s
- .

### Metodología
- **steps:** ['1. Build static oligopsony model with logit labor demand, endogenous entry, strategic interaction', '2. Construct data moments from World Bank Enterprise Surveys for 130+ countries: number of firms, average size, size dispersion, wage dispersion, firm-size wage premium', '3. Create 4 synthetic countries at log GDP p.c. = 8, 9, 10, 11 (plus Colombia)', '4. Estimate 6 parameters (ε_L, L, α, θ, b, c_e) by minimizing distance between model and data moments (MSM)', '5. Verify model fit: check that simulated moments match data moments', '6. Run counterfactuals: set ε_L = 3.14 for all countries, compare GDP per capita', '7. Decompose misallocation: separate amenity-driven vs. strategic interaction-driven effects']

---

## wcms_906617.pdf
**Tema:** Panorama Laboral 2023: Annual labor market overview for Latin America and the Caribbean by the ILO, covering macroeconomic context, employment, informality, wages, gender gaps, youth labor, and social protection with 30-year retrospective analysis

### Conceptos Clave
- **Trabajador Pobre (Working Poor)**: People who live in poverty despite having employment, driven by loss of real income purchasing power, low wages, and growth of informal/low-quality jobs.
- **Tasa de Informalidad Regional**: Regional informality rate for LAC, measured by ILO using household surveys. Stood at 48% in mid-2023, down slightly from 49% in 2019. In half of countries, it exceeds the regional average, reaching 70%+ in some.
- **Empleo Formal vs Informal**: Formal employment = salaried workers with social security registration. Informal employment = self-employed, employers in informal enterprises, and salaried workers without social security. The report uses the ILO's international statistical definition.
- **Recuperación Plena del Empleo**: Full employment recovery meaning the occupation rate has returned to or exceeded pre-pandemic levels, achieved regionally by 2022-2023 despite incomplete labor force participation recovery.
- **Trabajo Decente (Decent Work)**: ILO's overarching concept encompassing employment opportunities, fair income, security in the workplace, social protection for families, freedom of expression, equality of opportunity, and dignity at work.
- **Recuperación Asimétrica Urbano-Rural**: The more intense employment recovery in urban areas compared to rural areas post-pandemic, which amplified the pre-existing urban-rural employment gap.

### Supuestos
> Household surveys are the primary and most reliable source of labor market data
> Informality rates are measured consistently using ILO international definitions
> Regional averages are weighted by population size of countries
> Post-pandemic recovery patterns follow historical crisis-recovery dynamics
> The relationship between macroeconomic growth and employment creation is mediated by structural factors

### Intuición
The Panorama Laboral 2023 tells the story of a region that has achieved quantitative employment recovery from COVID-19 but faces deep qualitative challenges. While unemployment has fallen below pre-pandemic levels (6.5% vs 7.4% in 2022), this masks: (1) incomplete labor supply recovery (participation still -1pp), (2) persistent informality (48%) leading job creation, (3) real wage losses from inflation making workers poorer despite having jobs, and (4) persistent gender and age gaps. The 30-year retrospective shows structural patterns that have not changed much: agriculture declining, services growing, informality persisting around 45-55%, and women/youth consistently disadvantaged. The key policy imperative is not just job creation but quality job creation with formalization.

### Conexiones
- {'topic': 'Trade and Labor Markets', 'description': "International trade decelerated from mid-2022, with volumes contracting especially in developed economies. LAC's export-oriented economies (Brazil, Peru) saw employment boosted by exports. Commodity price reversal negatively impacted South American economies. Dollar appreciation (15% above 20-year average) affected trade flows and commodity prices.", 'page_reference': 'pp.20-26'}
- {'topic': 'Informality and Poverty', 'description': "Persistent informality (48% regional) combined with real wage losses creates the 'working poor' phenomenon. Employment levels may be restored but income hasn't recovered. In half of countries, total real labor income in Q2 2023 hadn't exceeded late 2019 levels. This is especially severe for low-education women and informal workers.", 'page_reference': 'pp.15-17, 73-77'}
- {'topic': 'Gender Economics in LAC Labor Markets', 'description': 'Despite faster female employment recovery post-pandemic, persistent gaps remain: participation 23pp below men, occupation 22.5pp below, informality higher. Low-education women face 32pp occupation gap vs men with similar education. Construction growth favored male recovery. Domestic service contraction disproportionately affected women.', 'page_reference': 'pp.60-72'}
- {'topic': 'Inflation and Real Wages in LAC', 'description': 'Median regional inflation fell from 8.1% (2022) to 4.4% (2023), but real wages in most countries remained below pre-pandemic levels. In 6 of 17 countries, real minimum wage declined 5-16%. This erosion of purchasing power, combined with employment recovery, means more people are employed but poorer.', 'page_reference': 'pp.73-77'}

### Metodología
- **approach:** Descriptive statistical analysis of labor market indicators using harmonized household survey data across LAC countries
- **data_sources:** ['ILO SIALC (Sistema de Información y Análisis Laboral de América Latina y el Caribe) database', 'National household surveys from 18 Latin American and 10 Caribbean countries', 'ILO Labor Statistics Database (ILOSTAT)', 'IMF World Economic Outlook projections', 'CEPAL/ECLAC economic projections', 'CPB Netherlands Bureau for Economic Policy Analysis (trade data)', 'OECD statistics', 'Official national accounts statistics', 'Encuesta Telefónica de Hogares (pandemic period proxy)']
- **empirical_methods:** ['Time series analysis of labor indicators (participation, occupation, unemployment rates)', 'Cross-country comparison using weighted regional averages', 'Decomposition of employment growth by formality status, gender, age, sector', 'Real wage indices normalized to 2012=100 for comparative analysis', 'Urban/rural decomposition of labor indicators', 'Trend analysis over 30-year period (1994-2023) for special topic', 'Descriptive statistics from administrative registers and household surveys']

---

# Econometrics & Methodology

## Local projections.pdf
**Tema:** Local Projections (LPs) - Comprehensive survey by Jordà and Taylor (2024, NBER WP 32822). Estimation of impulse responses, comparison with VARs, inference, smoothing, multipliers, panel data extensions, and nonlinear LP methods.

### Conceptos Clave
- **Impulse Response Function (IRF)**: The effect R_{s→y}(h,δ) = E[y_{t+h}|s_t = s_0+δ; x_t] - E[y_{t+h}|s_t = s_0; x_t] quantifies how an intervention δ at time t affects outcome y at horizon h.
- **Local Projection (LP)**: A sequence of regressions where y_{t+h} is regressed on s_t (and controls x_t) for each horizon h separately, directly estimating the impulse response β_h without specifying the full DGP.
- **LP-OLS**: LP estimated by OLS when the treatment s_t is exogenous, i.e., E(s_t, v_{t+h}) = 0.
- **LP-IV**: LP estimated using instrumental variables z_t for s_t when treatment is endogenous; introduced by Jordà, Schularick, and Taylor (2015).
- **Long-difference specification**: LP specification regressing Δ_h y_{t+h} = y_{t+h} - y_{t-1} on Δy_{t-1} and s_t, which suppresses small-sample bias relative to the levels specification.
- **Cumulative multiplier**: m(h) = R^c_{sy}(h) / R^c_{ss}(h), the ratio of cumulative outcome response to cumulative treatment response, measuring output per unit of policy intervention.
- **Lag-augmented LP**: Adding w_{t-1} as an extra regressor (Montiel Olea and Plagborg-Møller 2021) makes inference uniformly valid across stationary and unit-root processes, with standard White SEs sufficient.
- **Sup-t confidence bands**: Simultaneous confidence bands for the entire impulse response path, constructed via simulation of max_h |σ_h^{-1} V_h| with V ~ N(0, Ω_β).
- **Significance bands**: Error bands straddling the zero line constructed under the null of zero effect; if the IRF strays outside, the response is significantly different from zero.
- **Gaussian basis function smoothing**: Approximating the impulse response as φ(h;Θ) = a·exp[-(h-b)²/c²], where a=height, b=peak timing, c√(ln2)=half-life; reduces dimensionality dramatically.

### Resultados / Teoremas
> **LP-VAR Asymptotic Equivalence (Jordà 2005; Plagborg-Møller and Wolf 2021):** In large samples, impulse responses estimated by LPs and by an infinite-order VAR are asymptotically equivalent under relatively mild conditions when the data are generated by a VAR.
> **Lag-Augmented LP Uniform Normality (Montiel Olea and Plagborg-Møller 2021):** With lag augmentation (adding w_{t-1} as regressor), the distribution of β̂(h) from the feasible lag-augmented LP is uniformly normal in φ ∈ [-1,1], even under unit-root or near-unit-root dynamics.
> **LP Doubly Robust Misspecification Property (Plagborg-Møller, Montiel-Olea, Qian, and Wolf 2024):** LP confidence intervals are surprisingly robust to misspecification: they enjoy lower bias and correct probability coverage even with misspecification that can be detected with probability approaching 1, whereas VAR CIs substantially undercover.

### Fórmulas
- **Impulse Response**: `R_{s→y}(h,δ) = E[y_{t+h}|s_t = s_0+δ; x_t] - E[y_{t+h}|s_t = s_0; x_t]` — Causal effect of a δ-size intervention s at time t on outcome y at horizon h
- **Baseline LP Regression**: `y_{t+h} = α_h + β_h s_t + γ'_h x_t + v_{t+h}, for h = 0,1,...,H` — Each horizon h gets its own regression; β_h estimates R_{sy}(h)
- **VAR(1) IRF in differences**: `R_{j→i}(h,δ) = e_i Φ^h e'_j δ = ϕ_{ij}^{(h)} δ` — Impulse response from shock j to outcome i at horizon h via matrix power of VAR coefficient matrix
- **Cumulative Response**: `R^c_{j→i}(h,δ) = e_i(I + Φ + ... + Φ^h) e'_j δ` — Sum of impulse responses from horizon 0 to h, equivalent to response in levels
- **Cumulative Multiplier**: `m(h) = R^c_{sy}(h) / R^c_{ss}(h)` — Ratio of cumulative outcome response to cumulative treatment response; e.g., fiscal multiplier
- **Multiplier via Direct LP**: `y^c_{t,h} = m(h) s^c_{t,h} + ε_{t+h}` — Regress cumulative outcome on cumulative treatment; the coefficient IS the multiplier, estimated in one step via IV
- **Smoothing Minimum Distance**: `Q(Θ) = (β̂ - φ(Θ))' Ω̂_β^{-1} (β̂ - φ(Θ))` — Fit a smooth parametric shape φ(h;Θ) to raw LP coefficients via minimum distance
- **GMM LP System**: `E[Z'_t(y_t(H) - S_t β)] = 0` — Population moment condition for the system of H+1 local projections, with instruments Z_t
- **Lag-Augmented LP**: `w_{t+h} = β(h)w_t + β(h+1)w_{t-1} + ξ_t(h)` — Adding w_{t-1} makes the effective regressor stationary; allows White SEs instead of HAC
- **Sup-t Band**: `B̂(ĉ) = ∩_{h=0}^{H} [β̂_h - σ̂_h ĉ, β̂_h + σ̂_h ĉ]` — Simultaneous confidence band where ĉ is the (1-α) quantile of max_h |σ_h^{-1} V_h| simulated from N(0, Ω_β)

### Supuestos
> Linearity of conditional expectation (for basic LP)
> Exogeneity or valid instruments: E(Z'_t S_t) ≠ 0 (relevance) and E(Z'_{t+l} v_t(H)) = 0 for all l (lead-lag exogeneity)
> Stationarity for basic asymptotic normality; lag-augmentation relaxes this
> No anticipation and no spillovers for treatment effect interpretation
> For multipliers: correct specification of both outcome and treatment cumulative LPs

### Intuición
LPs are a 'semi-parametric' middle ground: they impose less structure than VARs (no cross-horizon restrictions) so they are more robust to misspecification, but this comes at the cost of less efficiency. The key insight is that each horizon h gets its own regression, so misspecification at one horizon doesn't compound into others. Long-differencing removes the O(T^{-1}) small-sample bias that plagues levels specifications. Lag-augmentation makes inference valid even for unit-root processes by making the effective regressor stationary.

### Conexiones
- L
- P
- s
-  
- b
- r
- i
- d
- g
- e
-  
- m
- a
- c
- r
- o
- e
- c
- o
- n
- o
- m
- i
- c
-  
- I
- R
- F
-  
- e
- s
- t
- i
- m
- a
- t
- i
- o
- n
-  
- w
- i
- t
- h
-  
- m
- i
- c
- r
- o
- e
- c
- o
- n
- o
- m
- i
- c
-  
- p
- o
- l
- i
- c
- y
-  
- e
- v
- a
- l
- u
- a
- t
- i
- o
- n
-  
- (
- D
- i
- D
- ,
-  
- e
- v
- e
- n
- t
-  
- s
- t
- u
- d
- i
- e
- s
- )
- .
-  
- T
- h
- e
- y
-  
- p
- r
- o
- v
- i
- d
- e
-  
- a
- n
-  
- e
- n
- c
- o
- m
- p
- a
- s
- s
- i
- n
- g
-  
- f
- r
- a
- m
- e
- w
- o
- r
- k
-  
- f
- o
- r
-  
- s
- t
- a
- g
- g
- e
- r
- e
- d
-  
- D
- i
- D
-  
- w
- i
- t
- h
-  
- h
- e
- t
- e
- r
- o
- g
- e
- n
- e
- o
- u
- s
-  
- t
- r
- e
- a
- t
- m
- e
- n
- t
-  
- e
- f
- f
- e
- c
- t
- s
-  
- (
- D
- u
- b
- e
- ,
-  
- G
- i
- r
- a
- r
- d
- i
- ,
-  
- J
- o
- r
- d
- à
- ,
-  
- T
- a
- y
- l
- o
- r
-  
- 2
- 0
- 2
- 3
- )
- .
-  
- L
- P
- -
- I
- V
-  
- i
- s
-  
- t
- h
- e
-  
- w
- o
- r
- k
- h
- o
- r
- s
- e
-  
- o
- f
-  
- e
- m
- p
- i
- r
- i
- c
- a
- l
-  
- m
- a
- c
- r
- o
-  
- f
- o
- r
-  
- m
- o
- n
- e
- t
- a
- r
- y
-  
- a
- n
- d
-  
- f
- i
- s
- c
- a
- l
-  
- p
- o
- l
- i
- c
- y
-  
- a
- n
- a
- l
- y
- s
- i
- s
- .
-  
- L
- P
- s
-  
- c
- o
- n
- n
- e
- c
- t
-  
- t
- o
-  
- t
- h
- e
-  
- p
- o
- t
- e
- n
- t
- i
- a
- l
-  
- o
- u
- t
- c
- o
- m
- e
- s
-  
- f
- r
- a
- m
- e
- w
- o
- r
- k
-  
- v
- i
- a
-  
- R
- a
- m
- b
- a
- c
- h
- a
- n
-  
- a
- n
- d
-  
- S
- h
- e
- p
- h
- a
- r
- d
-  
- (
- 2
- 0
- 1
- 9
- )
- .

### Metodología
- **steps:** ['1. Choose outcome y_t and intervention s_t; define horizon range h = 0,...,H', '2. Specify controls x_t (lags of y and s, other exogenous variables)', "3. For each h, estimate: y_{t+h} = α_h + β_h s_t + γ'_h x_t + v_{t+h} (or use long-differences)", '4. If s_t is endogenous, use instruments z_t and estimate via LP-IV (2SLS at each horizon)', '5. For inference: use lag-augmented LP + White robust SEs (preferred), or Newey-West HAC', '6. For simultaneous inference: construct sup-t bands via simulation from N(0, Ω̂_β)', '7. Optionally smooth using Gaussian basis functions or B-splines', '8. For multipliers: estimate cumulative LPs and compute m(h) = β̂^c_h / θ̂^c_h', '9. Report joint significance tests (χ² test that all β_h = 0)']
- **when_to_use_each:** {'LP-OLS': 'When treatment is randomly assigned or conditionally exogenous', 'LP-IV': 'When treatment is endogenous and instruments available (monetary/fiscal policy)', 'Levels specification': 'When small-sample bias is not a concern or T is large', 'Long-difference specification': 'Preferred in most cases; suppresses O(T^{-1}) bias', 'Lag-augmented LP': 'When data may be persistent or unit-root; for valid inference', 'Gaussian basis smoothing': 'When response should be smooth (single-humped); dramatically reduces noise', 'Sup-t bands': 'When testing whether the entire response path is significant'}

---

## sintetic DID.pdf
**Tema:** Synthetic Difference-in-Differences (SDID) by Arkhangelsky, Athey, Hirshberg, Imbens, and Wager (2019/2021, NBER WP 25532). A new estimator combining DID and Synthetic Control methods with unit and time weights, consistency/normality results, and placebo simulations.

### Conceptos Clave
- **Synthetic DID (SDID)**: An estimator that combines DID's additive fixed effects with SC's reweighting: finds unit weights ω to balance pre-exposure trends AND time weights λ to balance pre/post periods, then runs a weighted two-way fixed effects regression.
- **Unit weights (ω̂_sdid)**: Weights on control units chosen to match pre-treatment trends of treated units, with an intercept ω_0 allowing parallel (not identical) trends, and L2 regularization for dispersion/uniqueness.
- **Time weights (λ̂_sdid)**: Weights on pre-treatment periods chosen so weighted pre-period outcomes predict average post-period outcomes for control units, up to a constant.
- **Weighted double-differencing estimator**: τ̂(ω,λ) = ω'_tr Y_{tr,post} λ_post - ω'_co Y_{co,post} λ_post - ω'_tr Y_{tr,pre} λ_pre + ω'_co Y_{co,pre} λ_pre; SDID is a special case with optimal weights.
- **Latent factor model**: Y_{it} = γ_i ν'_t + τ W_{it} + ε_{it}, where γ_i are latent unit factors and ν_t are latent time factors; L = ΓΥ^T captures systematic variation.
- **Oracle weights**: Deterministic weights with similar bias-elimination properties as data-adaptive SDID weights, used to derive asymptotic distribution.
- **Double robustness**: SDID's two-pronged approach (unit weights balance Γ, time weights balance Υ) means if EITHER set of weights succeeds, the dependence on L is approximately removed.
- **Invariance to additive shifts**: SDID (like DID but unlike SC) is invariant to additive unit-level and time-level shifts: modifying L_{it} ← L_{it} + α_i + β_t leaves τ̂_sdid unchanged.
- **Matrix completion (MC) estimator**: An alternative that directly fits both L and τ via nuclear norm regularization; included as a benchmark.
- **DIFP estimator**: Synthetic control applied after centering data by subtracting pre-treatment means; separates benefits of fixed effects from time weights.

### Resultados / Teoremas
> **SDID Consistency (Theorem 1, Arkhangelsky et al. 2021):** Under the latent factor model Y = L + W◦τ + E with block treatment assignment, if the factor model is sufficiently low-rank and the noise E has bounded serial correlation, then τ̂_sdid is consistent for the average treatment effect τ.
> **SDID Asymptotic Normality (Theorem 2):** The SDID estimator is asymptotically normal: √(N_tr T_post)(τ̂_sdid - τ) → N(0, σ²_sdid), where the variance accounts for both the noise and the adaptivity of the weights.

### Fórmulas
- **SDID Estimator**: `(τ̂_sdid, μ̂, α̂, β̂) = argmin_{τ,μ,α,β} Σ_i Σ_t (Y_{it} - μ - α_i - β_t - W_{it}τ)² ω̂_i λ̂_t` — Weighted two-way fixed effects regression with data-driven unit and time weights
- **Unit Weight Optimization**: `(ω̂_0, ω̂_sdid) = argmin ℓ_unit(ω_0, ω) where ℓ_unit = Σ_t (ω_0 + Σ_i ω_i Y_{it} - N_tr^{-1} Σ_{i treated} Y_{it})² + ζ² T_pre ||ω||²` — Find unit weights making weighted control pre-trends match treated pre-trends (up to intercept), with regularization ζ
- **Time Weight Optimization**: `(λ̂_0, λ̂_sdid) = argmin ℓ_time(λ_0, λ) where ℓ_time = Σ_i (λ_0 + Σ_t λ_t Y_{it} - T_post^{-1} Σ_{t post} Y_{it})²` — Find time weights making weighted pre-period outcomes predict post-period outcomes for controls
- **Regularization Parameter**: `ζ = (N_tr T_post)^{1/4} σ̂, where σ̂² = [N_co(T_pre-1)]^{-1} Σ_i Σ_t (Δ_{it} - Δ̄)²` — Regularization scaled to typical one-period outcome changes, multiplied by theoretically motivated factor
- **Weighted Double-Differencing**: `τ̂(ω,λ) = ω'_tr Y_{tr,post} λ_post - ω'_co Y_{co,post} λ_post - ω'_tr Y_{tr,pre} λ_pre + ω'_co Y_{co,pre} λ_pre` — General form encompassing DID (equal weights), SC (no time weights), and SDID (optimal weights)
- **Error Decomposition**: `τ̂(ω,λ) - τ = B(ω,λ) + ε(ω,λ)` — Error splits into bias B (from systematic component L not fully balanced) and noise ε (from idiosyncratic errors E)

### Supuestos
> Block treatment assignment: W_{it} = 1{i > N_co, t > T_pre} (staggered case requires modification)
> Latent factor DGP: Y_{it} = γ_i ν'_t + τ W_{it} + ε_{it} with bounded-rank factor structure
> Homoskedastic errors across units: Var[E_i.] = Σ for all i
> Independent errors across units (but correlation within unit over time allowed)
> Signal-to-noise: factor variation must dominate idiosyncratic noise for weights to identify the correct factors
> No simultaneous shocks to treatment units at treatment time

### Intuición
SDID is 'local DID': it uses SC-type weights to make the DID parallel trends assumption more plausible. Unit weights find control states similar to the treated state; time weights find pre-treatment periods most informative about post-treatment outcomes. The two-way fixed effects then absorb remaining additive differences. The key advantage over plain DID is robustness to non-parallel trends; the key advantage over plain SC is the unit fixed effects and time weights that improve precision and reduce bias.

### Conexiones
- S
- D
- I
- D
-  
- u
- n
- i
- f
- i
- e
- s
-  
- D
- I
- D
-  
- a
- n
- d
-  
- S
- C
-  
- u
- n
- d
- e
- r
-  
- o
- n
- e
-  
- f
- r
- a
- m
- e
- w
- o
- r
- k
- .
-  
- D
- I
- D
-  
- a
- s
- s
- u
- m
- e
- s
-  
- a
- d
- d
- i
- t
- i
- v
- e
-  
- f
- i
- x
- e
- d
-  
- e
- f
- f
- e
- c
- t
- s
-  
- (
- p
- a
- r
- a
- l
- l
- e
- l
-  
- t
- r
- e
- n
- d
- s
- )
- ;
-  
- S
- C
-  
- m
- a
- t
- c
- h
- e
- s
-  
- p
- r
- e
- -
- t
- r
- e
- n
- d
- s
-  
- v
- i
- a
-  
- r
- e
- w
- e
- i
- g
- h
- t
- i
- n
- g
-  
- b
- u
- t
-  
- l
- a
- c
- k
- s
-  
- u
- n
- i
- t
-  
- F
- E
- .
-  
- S
- D
- I
- D
-  
- c
- o
- m
- b
- i
- n
- e
- s
-  
- b
- o
- t
- h
- :
-  
- w
- e
- i
- g
- h
- t
- s
-  
- +
-  
- F
- E
- .
-  
- T
- h
- e
-  
- m
- e
- t
- h
- o
- d
-  
- c
- o
- n
- n
- e
- c
- t
- s
-  
- t
- o
-  
- i
- n
- t
- e
- r
- a
- c
- t
- i
- v
- e
-  
- f
- i
- x
- e
- d
-  
- e
- f
- f
- e
- c
- t
- s
-  
- m
- o
- d
- e
- l
- s
-  
- (
- B
- a
- i
-  
- 2
- 0
- 0
- 9
- )
- ,
-  
- m
- a
- t
- r
- i
- x
-  
- c
- o
- m
- p
- l
- e
- t
- i
- o
- n
-  
- (
- A
- t
- h
- e
- y
-  
- e
- t
-  
- a
- l
- .
-  
- 2
- 0
- 1
- 7
- )
- ,
-  
- a
- n
- d
-  
- a
- u
- g
- m
- e
- n
- t
- e
- d
-  
- S
- C
-  
- (
- B
- e
- n
- -
- M
- i
- c
- h
- a
- e
- l
-  
- e
- t
-  
- a
- l
- .
-  
- 2
- 0
- 1
- 8
- )
- .
-  
- R
- e
- l
- e
- v
- a
- n
- t
-  
- f
- o
- r
-  
- a
- n
- y
-  
- p
- a
- n
- e
- l
-  
- d
- a
- t
- a
-  
- c
- a
- u
- s
- a
- l
-  
- i
- n
- f
- e
- r
- e
- n
- c
- e
-  
- w
- i
- t
- h
-  
- f
- e
- w
-  
- t
- r
- e
- a
- t
- e
- d
-  
- u
- n
- i
- t
- s
-  
- a
- n
- d
-  
- p
- o
- t
- e
- n
- t
- i
- a
- l
-  
- t
- r
- e
- n
- d
-  
- v
- i
- o
- l
- a
- t
- i
- o
- n
- s
- .

### Metodología
- **steps:** ['1. Organize data as N×T panel with binary treatment W_{it}', '2. Compute regularization parameter ζ = (N_tr T_post)^{1/4} σ̂ from pre-treatment outcome differences', '3. Solve for unit weights ω̂ via constrained optimization (2.1) with intercept and L2 penalty', '4. Solve for time weights λ̂ via constrained optimization (2.3) without regularization', '5. Run weighted TWFE regression (1.1) to obtain τ̂_sdid', '6. For inference: use placebo-based SEs (permutation of treatment assignment) or asymptotic bootstrap', '7. Validate by comparing with DID and SC estimates']
- **when_to_use_each:** {'SDID': 'When parallel trends are questionable AND you want robustness from both FE and reweighting', 'DID': 'When you have many treated units and parallel trends are credible', 'SC': 'When you have 1 treated unit and long pre-treatment series', 'Matrix Completion': 'When factor structure is complex and you want direct low-rank estimation'}

---

## Synthetic Controls in Action Abadie VivesiBastida.pdf
**Tema:** Practical guidance for synthetic control methods by Abadie and Vives-i-Bastida (2021). Seven guiding principles for empirical practice, overfitting biases, validation exercises, trimming, and the role of covariates.

### Conceptos Clave
- **Synthetic Control Estimator**: Ŷ^N_{1t} = Σ_{j=2}^{J+1} W_j Y_{jt}, a weighted average of donor pool outcomes serving as counterfactual for the treated unit; weights are non-negative and sum to one.
- **Overfitting bias**: When pre-treatment fit is achieved through variation in transitory shocks ϵ_{jt} rather than matching unobserved factors μ_j; small T_0 or large J increases this risk.
- **Sparsity**: SC weights are typically sparse (few nonzero weights); when X_1 is outside the convex hull of X_0, number of nonzero weights ≤ k (dimension of predictors).
- **Interpolation bias**: Bias from averaging outcomes of untreated units far from the treated unit in predictor space; linear model is only a local approximation.
- **Pre-RMSE**: Root mean squared error of SC fit in pre-treatment periods; key diagnostic but NOT sufficient for good post-treatment performance due to overfitting risk.
- **Grouped factor model**: Y^N_{it} = δ_t + λ_{f(i)t} + ϵ_{it}, where units load on group-specific factors; used as simulation DGP to study SC properties.
- **Out-of-sample validation**: Assessing SC quality by holding out pre-treatment periods, fitting weights on a subset, and evaluating predictive power on the held-out periods.
- **Trimming**: Restricting the donor pool to units with predictor values close to the treated unit to reduce interpolation bias and overfitting.

### Resultados / Teoremas
> **SC Bias Bound (Abadie et al. 2010):** Under the linear factor model Y^N_{jt} = δ_t + θ_t Z_j + λ_t μ_j + ϵ_{jt}, if the SC weights reproduce pre-treatment outcomes and covariates exactly, the bias |E[τ̂_t - τ_t]| is bounded by terms proportional to (i) σ/√T_0, (ii) J, and (iii) dim(μ_j).
> **Sparsity Result (Abadie and L'Hour 2021):** When X_1 is outside the convex hull of columns of X_0 and columns of X_0 are in general position, the SC solution X_0 W* is unique and sparse with at most k nonzero weights (k = dim of X_j).

### Fórmulas
- **SC Weight Selector**: `‖X_1 - X_0 W‖ = [Σ_h v_h(X_{h1} - W_2 X_{h2} - ... - W_{J+1} X_{h,J+1})²]^{1/2}` — Minimize distance between treated predictors X_1 and weighted combination of donor predictors X_0, subject to W_j ≥ 0 and Σ W_j = 1
- **SC Treatment Effect**: `τ̂_t = Y_{1t} - Σ_{j=2}^{J+1} W*_j Y_{jt}` — Difference between observed treated outcome and synthetic control prediction
- **Linear Factor Model**: `Y^N_{jt} = δ_t + θ_t Z_j + λ_t μ_j + ϵ_{jt}` — Outcome = time trend + observed predictors with time-varying coefficients + unobserved factors + noise
- **Pre-RMSE**: `[(1/T_0) Σ_{t=1}^{T_0} (Y_{1t} - Σ_j W_j Y_{jt})²]^{1/2}` — Root mean squared prediction error in pre-treatment period; diagnostic for SC fit quality
- **Grouped Factor DGP**: `Y^N_{it} = δ_t + λ_{f(i)t} + ϵ_{it}` — Simplified factor model where unit i loads exclusively on factor group f(i); used for simulation studies

### Supuestos
> Linear factor model for potential outcomes (Abadie et al. 2010 framework)
> No anticipation: potential outcomes at t depend only on treatment status at t
> No spillovers: unit i's potential outcomes depend only on i's treatment status
> Large T_0 relative to noise σ for bias bound to be tight
> Donor pool units not indirectly affected by treatment

### Intuición
The paper's seven principles distill the bias bound into practical advice: (1) don't overfit volatile series, (2) good pre-treatment fit should persist, (3) smaller, closer donor pools are better, (4) sparsity enables interpretability, (5) include relevant covariates to reduce what's in μ_j, (6) good fit is necessary but not sufficient, (7) always validate out-of-sample. The key warning is that perfect pre-treatment fit can be an illusion created by overfitting noise.

### Conexiones
- T
- h
- i
- s
-  
- p
- a
- p
- e
- r
-  
- p
- r
- o
- v
- i
- d
- e
- s
-  
- t
- h
- e
-  
- p
- r
- a
- c
- t
- i
- c
- a
- l
-  
- c
- o
- m
- p
- a
- n
- i
- o
- n
-  
- t
- o
-  
- t
- h
- e
-  
- t
- h
- e
- o
- r
- e
- t
- i
- c
- a
- l
-  
- S
- C
-  
- l
- i
- t
- e
- r
- a
- t
- u
- r
- e
- .
-  
- T
- h
- e
-  
- p
- r
- i
- n
- c
- i
- p
- l
- e
- s
-  
- d
- i
- r
- e
- c
- t
- l
- y
-  
- i
- n
- f
- o
- r
- m
-  
- a
- p
- p
- l
- i
- c
- a
- t
- i
- o
- n
-  
- o
- f
-  
- S
- C
- ,
-  
- S
- D
- I
- D
- ,
-  
- a
- n
- d
-  
- r
- e
- l
- a
- t
- e
- d
-  
- m
- e
- t
- h
- o
- d
- s
- .
-  
- O
- v
- e
- r
- f
- i
- t
- t
- i
- n
- g
-  
- c
- o
- n
- c
- e
- r
- n
- s
-  
- c
- o
- n
- n
- e
- c
- t
-  
- t
- o
-  
- t
- h
- e
-  
- b
- r
- o
- a
- d
- e
- r
-  
- b
- i
- a
- s
- -
- v
- a
- r
- i
- a
- n
- c
- e
-  
- t
- r
- a
- d
- e
- o
- f
- f
-  
- i
- n
-  
- c
- a
- u
- s
- a
- l
-  
- i
- n
- f
- e
- r
- e
- n
- c
- e
- .
-  
- T
- h
- e
-  
- g
- r
- o
- u
- p
- e
- d
-  
- f
- a
- c
- t
- o
- r
-  
- m
- o
- d
- e
- l
-  
- f
- r
- a
- m
- e
- w
- o
- r
- k
-  
- i
- s
-  
- u
- s
- e
- d
-  
- t
- o
-  
- s
- t
- u
- d
- y
-  
- D
- I
- D
- ,
-  
- S
- C
- ,
-  
- a
- n
- d
-  
- S
- D
- I
- D
-  
- c
- o
- m
- p
- a
- r
- a
- b
- l
- y
- .

### Metodología
- **steps:** ['1. Select donor pool: restrict to units with similar predictor values (trimming)', '2. Choose matching variables X_j: include pre-treatment outcomes and relevant covariates', '3. Compute SC weights W* via constrained minimization of ‖X_1 - X_0 W‖', '4. Check pre-treatment fit (pre-RMSE): must be close for results to be credible', '5. Assess overfitting risk: if T_0 is small or J is large, pre-fit may be misleading', '6. Conduct out-of-sample validation: fit on subset of pre-periods, predict on held-out periods', '7. Examine sparsity: few nonzero weights facilitate interpretation and reduce bias', '8. Plot treated vs. synthetic control trajectories visually', '9. Conduct placebo tests: reassign treatment to each donor unit and re-estimate']
- **when_to_use_each:** {'Standard SC': 'When X_1 is in or near convex hull of X_0; good pre-treatment fit achievable', 'SC with constant shift': 'When trajectories are parallel but offset; helps avoid interpolation bias', "Penalized SC (Abadie-L'Hour)": 'When many donors and risk of overfitting; favors nearby units in predictor space', 'Trimmed donor pool': 'When donors are far from treated unit in predictor space'}

---

## Cattaneo-Feng-Palomba-Titiunik_2025_JSS.pdf
**Tema:** scpi software package for uncertainty quantification in synthetic control methods (Cattaneo, Feng, Palomba, Titiunik 2025, JSS). Prediction intervals under random potential outcomes, multiple estimation methods (simplex, lasso, ridge), and implementation in R/Python/Stata.

### Conceptos Clave
- **Predictand**: The treatment effect τ_T viewed as a random variable (not fixed parameter), since potential outcomes Y_{1T}(0) and Y_{1T}(1) are random.
- **Prediction interval**: Interval [τ̂_T + M_{1,L} - M_{2,U}, τ̂_T + M_{1,U} - M_{2,L}] with conditional coverage ≥ 1-α_1-α_2, combining in-sample and out-of-sample uncertainty.
- **In-sample error**: p'_T(β̂ - β_0) = error from constructing synthetic control weights; bounded via simulation-based method using normal draws from estimated covariance.
- **Out-of-sample error**: e_T = Y_{1T}(0) - p'_T β_0 = error from post-treatment prediction; bounded via sub-Gaussian concentration, location-scale model, or robust methods.
- **Conic optimization**: SC weight computation framed as conic programs (SOCP); solver ECOS used for numerical stability and speed.
- **Multiple features**: Matching M features of treated unit simultaneously: A = (A_1,...,A_M), with separate covariate adjustments C_l per feature.
- **Cointegrated data handling**: When A and B form a cointegrated system, prediction intervals properly account for non-stationarity in both in-sample and out-of-sample uncertainty.
- **Feasible constraint set Δ***: Approximation to infeasible constraint set Δ used in simulation; must satisfy dist(a, Δ*) ≪ ‖a‖ for all a near zero.

### Resultados / Teoremas
> **Prediction Interval Validity (Cattaneo, Feng, Titiunik 2021):** Under the SC framework with random potential outcomes, the prediction interval [τ̂_T + M_{1,L} - M_{2,U}, τ̂_T + M_{1,U} - M_{2,L}] has conditional coverage ≥ 1-α_1-α_2 with high probability over information set H, where M bounds come from simulation (in-sample) and concentration inequalities (out-of-sample).

### Fórmulas
- **SC Optimization**: `β̂ = (ŵ', r̂')' = argmin_{w∈W, r∈R} (A - Bw - Cr)'V(A - Bw - Cr)` — Find weights w and covariate coefficients r minimizing weighted distance between treated features A and donor features B, with covariates C
- **Counterfactual Prediction**: `Ŷ_{1T}(0) = x'_T ŵ + g'_T r̂ = p'_T β̂, where p_T = (x'_T, g'_T)'` — Post-treatment counterfactual = weighted combination of donor outcomes at time T
- **Prediction Error Decomposition**: `τ̂_T - τ_T = e_T - p'_T(β̂ - β_0)` — Prediction error = out-of-sample error e_T minus in-sample estimation error
- **In-Sample Bound (Simulation)**: `M_{1,L/U} = (α_1/2)-quantile of inf/sup{p'_T D^{-1}δ : δ∈Δ*, ℓ*(δ)≤0}` — Simulation-based bounds on estimation error using normal draws G* ~ N(0, Σ̂)
- **Out-of-Sample Bound (Sub-Gaussian)**: `M_{2,L/U} = E[e_T|H] ∓ √(2σ²_H log(2/α_2))` — Concentration inequality bound on prediction error using sub-Gaussian parameter σ_H
- **Feasible Criterion**: `ℓ*(δ) = δ'Q̂δ - 2(G*)'δ, G* ~ N(0, Σ̂)` — Simulation-based criterion function replacing unknown γ with normal draws

### Supuestos
> No spillovers and no anticipation
> Potential outcomes are random (not fixed parameters)
> For sub-Gaussian bounds: e_T is sub-Gaussian conditional on H
> For location-scale bounds: e_T = E[e_T|H] + √(Var[e_T|H]) ε_T with ε_T independent of H
> Feasible constraint set Δ* close to infeasible Δ (condition 7)

### Intuición
The key innovation is treating the treatment effect as a random 'predictand' rather than a fixed parameter. This shifts the goal from confidence intervals to prediction intervals. The interval has two sources of uncertainty: (1) in-sample: how well did we estimate the weights? (2) out-of-sample: how well does the counterfactual predict the future? The simulation-based method for in-sample uncertainty is agnostic about the estimator's distribution—just draw from N(0, Σ̂) and re-optimize.

### Conexiones
- s
- c
- p
- i
-  
- e
- x
- t
- e
- n
- d
- s
-  
- t
- h
- e
-  
- o
- r
- i
- g
- i
- n
- a
- l
-  
- S
- C
-  
- f
- r
- a
- m
- e
- w
- o
- r
- k
-  
- (
- A
- b
- a
- d
- i
- e
-  
- e
- t
-  
- a
- l
- .
-  
- 2
- 0
- 1
- 0
- ,
-  
- 2
- 0
- 1
- 5
- )
-  
- b
- y
-  
- p
- r
- o
- v
- i
- d
- i
- n
- g
-  
- p
- r
- i
- n
- c
- i
- p
- l
- e
- d
-  
- u
- n
- c
- e
- r
- t
- a
- i
- n
- t
- y
-  
- q
- u
- a
- n
- t
- i
- f
- i
- c
- a
- t
- i
- o
- n
- .
-  
- T
- h
- e
-  
- p
- r
- e
- d
- i
- c
- t
- i
- o
- n
-  
- i
- n
- t
- e
- r
- v
- a
- l
-  
- a
- p
- p
- r
- o
- a
- c
- h
-  
- c
- o
- n
- t
- r
- a
- s
- t
- s
-  
- w
- i
- t
- h
-  
- p
- e
- r
- m
- u
- t
- a
- t
- i
- o
- n
- -
- b
- a
- s
- e
- d
-  
- i
- n
- f
- e
- r
- e
- n
- c
- e
-  
- (
- p
- l
- a
- c
- e
- b
- o
-  
- t
- e
- s
- t
- s
- )
- .
-  
- T
- h
- e
-  
- p
- a
- c
- k
- a
- g
- e
-  
- u
- n
- i
- f
- i
- e
- s
-  
- m
- a
- n
- y
-  
- S
- C
-  
- v
- a
- r
- i
- a
- n
- t
- s
-  
- (
- s
- i
- m
- p
- l
- e
- x
- ,
-  
- l
- a
- s
- s
- o
- ,
-  
- r
- i
- d
- g
- e
- ,
-  
- a
- u
- g
- m
- e
- n
- t
- e
- d
- )
-  
- u
- n
- d
- e
- r
-  
- o
- n
- e
-  
- f
- r
- a
- m
- e
- w
- o
- r
- k
- .
-  
- C
- o
- n
- n
- e
- c
- t
- s
-  
- t
- o
-  
- t
- h
- e
-  
- b
- r
- o
- a
- d
- e
- r
-  
- l
- i
- t
- e
- r
- a
- t
- u
- r
- e
-  
- o
- n
-  
- c
- o
- n
- f
- o
- r
- m
- a
- l
-  
- p
- r
- e
- d
- i
- c
- t
- i
- o
- n
-  
- a
- n
- d
-  
- d
- i
- s
- t
- r
- i
- b
- u
- t
- i
- o
- n
- -
- f
- r
- e
- e
-  
- i
- n
- f
- e
- r
- e
- n
- c
- e
- .

### Metodología
- **steps:** ['1. Prepare data with scdata() or scdataMulti(): specify treated/control units, features, pre/post periods', '2. Choose estimation method via w.constr: simplex (canonical SC), lasso, ridge, OLS, L1-L2', '3. Optionally specify covariate adjustment via cov.adj and constant in scdata()', '4. Run scest() for point prediction of counterfactual Ŷ_{1T}(0)', '5. Run scpi() for prediction intervals: specify α_1, α_2 levels and out-of-sample method', '6. For out-of-sample uncertainty: choose sub-Gaussian, location-scale, or robust approach', '7. Conduct sensitivity analysis on σ_H (sub-Gaussian parameter)', '8. Visualize with scplot() or scplotMulti()']
- **when_to_use_each:** {'Simplex (canonical SC)': 'Standard application; non-negative weights summing to 1; interpretable', 'Lasso': 'When J > T_0 or want sparse solutions without non-negativity constraint', 'Ridge': 'When want smooth shrinkage; good when many donors contribute', 'Unconstrained OLS': 'When Hsiao-type regression approach desired', 'L1-L2 (SDID-like)': 'When combining simplex with ridge penalty for regularization'}

---

## Does the World Cup get the economic ball rolling .pdf
**Tema:** Impact of hosting FIFA World Cup on GDP per capita using synthetic control method (Viana, Barbosa, Sampaio 2018, EconomiA). Application of SC to 7 World Cup hosts (1978-2006).

### Conceptos Clave
- **SC application to mega-events**: Using synthetic control to construct counterfactual GDP per capita for World Cup host countries from a donor pool of non-hosting countries.
- **Treatment effect on GDP**: Difference between observed GDP per capita of host country and synthetic control prediction; estimated for Argentina 1978 through Germany 2006.
- **Donor pool selection**: Countries not hosting the World Cup in the relevant period, with similar economic characteristics; used to construct the synthetic counterfactual.
- **Pre-treatment fit assessment**: Evaluating how closely the synthetic control tracks the host country's GDP trajectory before the World Cup event.
- **Placebo tests**: Reassigning the 'treatment' (hosting) to non-host countries and re-estimating to assess statistical significance of effects.

### Fórmulas
- **SC Treatment Effect**: `τ̂_t = Y_{1t} - Σ_{j=2}^{J+1} W*_j Y_{jt}` — For each host country, the estimated effect is the gap between actual GDP and synthetic control GDP in post-treatment periods
- **Average Treatment Effect**: `τ̄ = (1/T_post) Σ_{t=T_pre+1}^{T} τ̂_t` — Average over post-treatment periods of the per-period treatment effect

### Supuestos
> No anticipation: GDP is not affected before the World Cup is awarded
> No spillovers: hosting one World Cup doesn't affect other countries' GDP
> Linear factor model for potential outcomes
> Donor pool countries not affected by the World Cup (no general equilibrium effects)

### Intuición
The paper tests whether mega sporting events boost economic growth. Using SC, it constructs what each host country's GDP 'would have been' without the World Cup. The finding that effects are zero or negative for most hosts challenges the popular narrative that World Cups are good for the host economy. This aligns with broader evidence that mega-events involve large public expenditures that may not generate commensurate returns.

### Conexiones
- T
- h
- i
- s
-  
- i
- s
-  
- a
-  
- s
- t
- r
- a
- i
- g
- h
- t
- f
- o
- r
- w
- a
- r
- d
-  
- a
- p
- p
- l
- i
- e
- d
-  
- S
- C
-  
- p
- a
- p
- e
- r
-  
- d
- e
- m
- o
- n
- s
- t
- r
- a
- t
- i
- n
- g
-  
- t
- h
- e
-  
- m
- e
- t
- h
- o
- d
-  
- i
- n
-  
- a
-  
- r
- e
- a
- l
- -
- w
- o
- r
- l
- d
-  
- s
- e
- t
- t
- i
- n
- g
- .
-  
- I
- t
-  
- c
- o
- n
- n
- e
- c
- t
- s
-  
- t
- o
-  
- t
- h
- e
-  
- b
- r
- o
- a
- d
- e
- r
-  
- l
- i
- t
- e
- r
- a
- t
- u
- r
- e
-  
- o
- n
-  
- m
- e
- g
- a
- -
- e
- v
- e
- n
- t
-  
- e
- c
- o
- n
- o
- m
- i
- c
- s
-  
- (
- B
- F
- r
- a
- n
- c
- i
- s
- ;
-  
- M
- a
- t
- h
- e
- s
- o
- n
- )
-  
- a
- n
- d
-  
- u
- s
- e
- s
-  
- t
- h
- e
-  
- c
- a
- n
- o
- n
- i
- c
- a
- l
-  
- A
- b
- a
- d
- i
- e
-  
- e
- t
-  
- a
- l
- .
-  
- (
- 2
- 0
- 1
- 0
- )
-  
- m
- e
- t
- h
- o
- d
- o
- l
- o
- g
- y
- .
-  
- T
- h
- e
-  
- f
- i
- n
- d
- i
- n
- g
-  
- o
- f
-  
- n
- u
- l
- l
-  
- e
- f
- f
- e
- c
- t
- s
-  
- i
- s
-  
- p
- o
- l
- i
- c
- y
- -
- r
- e
- l
- e
- v
- a
- n
- t
-  
- f
- o
- r
-  
- c
- o
- u
- n
- t
- r
- i
- e
- s
-  
- b
- i
- d
- d
- i
- n
- g
-  
- t
- o
-  
- h
- o
- s
- t
-  
- W
- o
- r
- l
- d
-  
- C
- u
- p
- s
- .

### Metodología
- **steps:** ['1. Select host country as treated unit (e.g., Argentina for 1978 World Cup)', '2. Construct donor pool of never-treated countries with comparable economic structure', '3. Choose predictors: GDP per capita in pre-treatment years, plus covariates (investment, trade, etc.)', '4. Compute SC weights via constrained minimization (synth package in R)', '5. Plot treated vs. synthetic control GDP trajectories pre- and post-treatment', '6. Compute treatment effects as gap between trajectories', '7. Conduct in-space placebo tests: reassign treatment to each donor and re-estimate', '8. Compute p-value from distribution of placebo effects vs. actual effect', '9. Repeat for all 7 World Cup hosts (1978-2006)']

---

## 1-s2.0-S151775801530031X-main.pdf
**Tema:** Duplicate of the World Cup SC paper (Viana, Barbosa, Sampaio 2018, EconomiA). Same content as the World Cup file above—impact of hosting FIFA World Cup on GDP per capita via synthetic control method.

### Conceptos Clave
- **SC application to mega-events**: Using synthetic control to construct counterfactual GDP per capita for World Cup host countries from a donor pool of non-hosting countries.
- **Treatment effect on GDP**: Difference between observed GDP per capita of host country and synthetic control prediction.
- **Placebo-based inference**: Permutation test reassigning hosting status to donor countries to assess significance.

### Fórmulas
- **SC Treatment Effect**: `τ̂_t = Y_{1t} - Σ_{j=2}^{J+1} W*_j Y_{jt}` — Gap between observed and counterfactual outcome for host country

### Supuestos
> No anticipation and no spillovers
> Linear factor model for GDP dynamics
> Donor pool unaffected by treatment

### Intuición
Same as the World Cup paper: mega sporting events do not boost host country GDP. The SC method provides a transparent, data-driven counterfactual for each host country.

### Conexiones
- A
- p
- p
- l
- i
- e
- d
-  
- S
- C
-  
- m
- e
- t
- h
- o
- d
- o
- l
- o
- g
- y
- ;
-  
- p
- a
- r
- t
-  
- o
- f
-  
- t
- h
- e
-  
- b
- r
- o
- a
- d
- e
- r
-  
- l
- i
- t
- e
- r
- a
- t
- u
- r
- e
-  
- o
- n
-  
- e
- v
- e
- n
- t
-  
- h
- o
- s
- t
- i
- n
- g
-  
- e
- c
- o
- n
- o
- m
- i
- c
- s
- .

### Metodología
- **steps:** ['1. Identify host country and donor pool', '2. Choose predictors and compute SC weights', '3. Estimate treatment effects as gaps', '4. Conduct placebo tests for inference']

---

# Finite Mixture Models

## Gaussian Mixture Models in R.pdf
**Tema:** Comprehensive benchmark of Gaussian Mixture Model R packages: EM algorithm, initialisation methods, and estimation performance comparison

### Conceptos Clave
- **Gaussian Mixture Model (GMM)**: A parametric model where the probability density of observed data is expressed as a weighted sum of k Gaussian component densities, each with its own mean and covariance parameters.
- **Mixing Proportions**: Non-negative weights p_j that sum to 1 (unit simplex constraint), representing the prior probability that an observation belongs to component j.
- **Complete vs Incomplete Log-Likelihood**: The complete log-likelihood (when latent labels S are observed) has a closed-form MLE; the incomplete log-likelihood (when S is unobserved) contains a sum-of-logs making direct maximization intractable.
- **EM Algorithm**: An iterative algorithm that alternates between an E-step (computing posterior probabilities of component membership given current parameters) and an M-step (maximizing the auxiliary Q-function to update parameters), guaranteeing non-decreasing likelihood.
- **Overlap Score (OVL)**: A measure of separation between components defined as the integral of the minimum of two component densities; smaller values indicate well-separated components.
- **Entropy-based Imbalance**: A measure of class imbalance computed as H(S) = -sum(p_j * log_k(p_j)), where lower values indicate more unbalanced mixture proportions.
- **REBMIX Initialisation**: An initialisation algorithm that uses kernel density estimation or binned intervals to find distribution modes, then iteratively assigns intervals to components, providing 'rough' then 'enhanced' parameter estimates.
- **Two Classes of EM Packages**: Packages split into: (1) mixtools/Rmixmod yielding less biased but more variable estimates with slower convergence, and (2) mclust/bgmm/EMCluster/GMKMcharlie/flexmix yielding less variable but more biased estimates that are more sensitive to initialisation.

### Resultados / Teoremas
> **MLE Consistency for GMMs:** The MLE of Gaussian mixture model parameters is consistent, asymptotically efficient, and unbiased under regularity conditions (Chen 2016; McLachlan & Peel 2000).
> **EM Convergence Guarantee:** The likelihood function L(theta) is non-decreased after each EM iteration: L(theta^(k+1)) >= L(theta^(k)) for k = 0, 1, 2, .... Convergence is guaranteed because the sequence of likelihood values is bounded above.

### Fórmulas
- **Gaussian Mixture Density (Univariate)**: `f_θ(X) = Σ_{j=1}^{k} p_j * φ_ζj(X), where φ_ζj(x|μ_j,σ_j) = (1/(√(2π)σ_j)) * exp(-(x-μ_j)²/(2σ_j²))` — The marginal density is a weighted sum of k univariate Gaussian densities with means μ_j and standard deviations σ_j, weighted by mixing proportions p_j.
- **Gaussian Mixture Density (Multivariate)**: `f_ζj(X=x) = det(2πΣ_j)^{-1/2} * exp(-(1/2)(x-μ_j)Σ_j^{-1}(x-μ_j)^⊤)` — Each component follows a D-dimensional multivariate Gaussian with mean vector μ_j ∈ R^D and positive-definite covariance matrix Σ_j.
- **Incomplete Log-Likelihood**: `ℓ(θ|x_{1:n}) = Σ_{i=1}^{n} log(Σ_{j=1}^{k} p_j * f_ζj(x_i))` — The log-likelihood when latent component labels are unobserved; the sum-of-logs structure makes direct MLE intractable.
- **E-step: Posterior Probabilities**: `η_i(j) = p_j * f_ζj(x_i) / Σ_{j'=1}^{k} p_{j'} * f_ζj'(x_i)` — The posterior probability that observation i belongs to component j, given current parameter estimates. These are the 'soft assignments'.
- **Auxiliary Q-function**: `Q(θ|θ̂_{q-1}) = Σ_{i=1}^{n} Σ_{j=1}^{k} η_i(j) * [log(p_j) + log(f(X|S=j,θ))]` — Expected complete-data log-likelihood conditioned on observed data and current parameter estimates; maximized in the M-step.
- **Overlap Score**: `OVL(i,j) = ∫ min(f_ζi(x), f_ζj(x)) dx` — Measures pairwise overlap between components; smaller values indicate better separation. Generalised to k components by averaging pairwise overlaps.
- **Entropy of Mixture**: `H(S) = -Σ_{j=1}^{k} p_j * log_k(p_j)` — Measures imbalance of mixture proportions; maximum when all p_j are equal (balanced), minimum when one component dominates.

### Supuestos
> Each component follows a Gaussian distribution (univariate or multivariate)
> Observations are independent and identically distributed (i.i.d.)
> The number of components k is fixed (or selected via criteria)
> Mixing proportions are non-negative and sum to 1 (unit simplex constraint)
> Covariance matrices are positive-definite
> No constraints on means, variances, or covariances unless specified (fully unconstrained model considered)

### Intuición
GMMs model heterogeneous data as arising from multiple Gaussian subpopulations. The EM algorithm handles the missing data problem (unobserved component labels) by iteratively guessing labels (E-step) and re-estimating Gaussian parameters (M-step). Initialization is critical because the likelihood surface has multiple local maxima. For well-separated components, mode-based initialisation (REBMIX) works best; for overlapping components, k-means initialisation is more robust because its homoscedastic/balanced assumptions provide a stable starting point even when violated.

### Conexiones
- Informality detection: GMMs can model the mix of formal/informal sector workers as separate Gaussian components in wage or productivity distributions, with the mixing proportion representing the share of informal workers.
- Firm heterogeneity: Different firm size or productivity distributions within an industry can be modeled as mixture components; BIC/ICL model selection determines the number of distinct firm types.
- Labor market segmentation: Overlapping wage distributions across sectors or skill levels can be decomposed via GMMs; the overlap score quantifies degree of segmentation.
- Policy evaluation: Bootstrap confidence intervals on mixture parameters allow assessing whether component proportions (e.g., informal sector share) change significantly across time periods or regions.

### Metodología
- **estimation:** Maximum Likelihood via EM algorithm with iterative E-step (posterior computation) and M-step (parameter update)
- **initialisation_methods:** ['Random', 'k-means', 'MBHC (hierarchical clustering)', 'Quantile', 'REBMIX']
- **model_selection:** ['BIC', 'ICL', 'AIC']
- **evaluation:** ['Parametric bootstrap for confidence intervals', 'Overlap score (OVL)', 'Entropy', 'Hellinger distance', 'RMSE and bias of parameter estimates']
- **recommended_package_init:** {'well_separated': 'mclust with REBMIX initialisation', 'overlapping': 'mclust with k-means initialisation', 'high_dimensional': 'mclust or GMKMcharlie with k-means initialisation'}

---

## FMM.pdf
**Tema:** Finite Mixture Models: comprehensive theoretical review covering formulation, estimation, EM algorithm, Bayesian analysis, normal/t/skew mixtures, and model selection

### Conceptos Clave
- **Finite Mixture Distribution**: A probability density function expressed as f(y) = Σ_{i=1}^{g} π_i * f_i(y), where π_i are mixing proportions and f_i(y) are component densities.
- **Latent Component Indicator**: A g-dimensional binary vector Z_j where Z_{ij}=1 if observation j belongs to component i, distributed as Multinomial(1, π).
- **Posterior Probability (Responsibility)**: τ(y_j; Θ) = pr{Z_{ij}=1 | Y_j=y_j} = π_i * f(y_j; θ_i) / f(y_j; Θ), the probability that observation j arose from component i given the data and current parameters.
- **Identifiability**: A mixture model is identifiable if distinct parameter values produce distinct mixture densities, up to permutation of component labels. Most finite mixtures of continuous densities are identifiable (exception: mixtures of uniform densities).
- **Complete-Data Log-Likelihood**: log L_c(Θ) = Σ_{i=1}^{g} Σ_{j=1}^{n} z_{ij} * {log π_i + log f(y_j; θ_i)}, linear in the unobservable indicators z_{ij}.
- **Label-Switching Problem**: In Bayesian posterior simulation, the lack of identifiability due to interchange of component labels causes the posterior to be symmetric under permutations, complicating inference.
- **Mixture of Factor Analyzers**: A model where each component covariance has the form Σ_i = B_i B_i^⊤ + D_i, with B_i a p×q loading matrix and D_i diagonal, reducing the number of free parameters when p is large relative to n.
- **Order of a Mixture Model**: The smallest value g_0 such that the g-component model is compatible with the data, with all components distinct and all mixing proportions nonzero.

### Resultados / Teoremas
> **Identifiability of Normal Mixtures:** Finite mixtures of normal distributions are identifiable. Teicher (1960) showed mixtures of Poisson distributions are identifiable, while mixtures of binomial distributions are not identifiable if N < 2g-1.
> **BIC Consistency for Mixture Order:** Under certain conditions, BIC performs consistently in choosing the true number of components in a mixture model (Keribin 2000).
> **LRT Null Distribution for Mixtures:** For testing H_0: g=1 vs H_1: g=2, the asymptotic null distribution of -2 log λ is a 'chi-bar-squared' distribution: it equals 0 with probability 0.5 and is chi-squared(1) with probability 0.5.

### Fórmulas
- **Finite Mixture Density**: `f(y) = Σ_{i=1}^{g} π_i * f_i(y), where f_i(y) = f(y; θ_i)` — The marginal density of Y is a convex combination of g component densities weighted by mixing proportions π_i ≥ 0 summing to 1.
- **Complete-Data Log-Likelihood**: `log L_c(Θ) = Σ_{i=1}^{g} Σ_{j=1}^{n} z_{ij} * {log π_i + log f(y_j; θ_i)}` — Log-likelihood when component labels are observed; linear in z_{ij}, making maximization straightforward.
- **E-step: Expected Complete-Data Log-Likelihood**: `Q(Θ; Θ^{(k)}) = Σ_{i=1}^{g} Σ_{j=1}^{n} τ(y_j; Θ^{(k)}) * {log π_i + log f(y_j; θ_i)}` — The auxiliary function obtained by replacing z_{ij} with their conditional expectations τ(y_j; Θ^{(k)}) under current parameters.
- **M-step: Updated Mixing Proportions**: `π_i^{(k+1)} = (1/n) * Σ_{j=1}^{n} τ(y_j; Θ^{(k)})` — Each observation contributes its posterior probability of membership to the updated proportion estimate.
- **M-step: Updated Component Parameters**: `Σ_{i=1}^{g} Σ_{j=1}^{n} τ(y_j; Θ^{(k)}) * ∂ log f(y_j; θ_i)/∂ξ = 0` — Solving this weighted estimating equation yields updated component parameters; for normal mixtures, closed-form solutions exist.
- **Posterior Probability (Bayes' Theorem)**: `τ(y_j; Θ) = π_i * f(y_j; θ_i) / f(y_j; Θ) for i=1,...,g; j=1,...,n` — The probability that observation j belongs to component i, computed via Bayes' theorem using current parameter estimates.
- **Skew Normal Density**: `f(y; μ, Σ, δ) = 2 * φ_p(y; μ, Ω) * Φ_1(δ'(Ω)^{-1}(y-μ); 0, λ), where Ω = Σ + δδ' and λ = 1 - δ'(Ω)^{-1}δ` — Extends the normal distribution with a p-dimensional skewness vector δ, allowing asymmetric clusters.
- **ICL Criterion**: `ICL = -2 log L(Θ̂) + d log n + EN(τ̂), where EN(τ̂) = -Σ_i Σ_j τ̂_i(y_j) log τ̂_i(y_j)` — BIC penalized by an entropy term measuring cluster overlap; prefers well-separated solutions.

### Supuestos
> Component densities belong to a known parametric family (e.g., normal, t, skew-normal)
> Observations are i.i.d. (or dependent structure is explicitly modeled, e.g., HMM)
> Mixing proportions π_i ≥ 0 and Σ π_i = 1
> Model is identifiable (up to label permutation)
> Number of components g is fixed or selected via information criteria
> Component parameters are distinct (non-degenerate mixtures)

### Intuición
Finite mixture models provide a flexible semi-parametric approach between fully parametric and nonparametric methods. The key insight is that observed heterogeneity in data can be modeled as arising from multiple underlying populations. The EM algorithm exploits the incomplete-data structure: the latent component labels make the complete-data problem easy, while the observed-data problem is hard. By iteratively imputing labels (E-step) and re-estimating parameters (M-step), EM monotonically increases the likelihood. Bayesian approaches use MCMC to sample from the posterior, addressing the label-switching problem through identifiable functions or constraints.

### Conexiones
- Economics applications: Mixture models are used in economics for modeling heterogeneous populations (e.g., different types of firms, workers, or consumers) where the group membership is unobserved.
- Latent class analysis: In labor economics, mixture models identify latent types of workers (formal vs informal) based on observable characteristics.
- Density estimation: BIC-consistent selection of the number of mixture components provides principled density estimation for economic data.
- Skewness: Skew normal/t mixtures accommodate asymmetric wage or income distributions common in economic data.
- Dependent data: HMMs extend mixtures to time-series settings, applicable to business cycle analysis or regime-switching models in macroeconomics.
- High-dimensional data: Factor analyzers reduce dimensionality while preserving cluster structure, useful for high-dimensional economic panel data.

### Metodología
- **estimation:** ['Method of moments (Pearson 1894, historical)', 'Maximum Likelihood via EM algorithm (standard)', 'Minorization-Maximization (MM) algorithm (alternative)', 'Nonparametric ML estimation of mixing distribution', 'Bayesian MCMC (Gibbs sampling, Metropolis-Hastings)']
- **model_selection:** ['BIC (tends to overestimate clusters, good for density estimation)', 'ICL (penalizes overlap, better for clustering)', 'AIC', 'Likelihood ratio test with bootstrap p-values', 'Bayesian model selection with reversible jump MCMC']
- **extensions:** ['t-mixtures (robust to outliers, ν controls robustness)', 'Skew normal/t mixtures (asymmetric clusters)', 'Mixtures of factor analyzers (high-dimensional)', 'HMMs (dependent data)', 'Mixtures of experts (nonlinear regression)']

---

## mclust 5 Clustering, Classification and Density Estimation Using Gaussian Finite Mixture Models.pdf
**Tema:** mclust R package version 5: Gaussian finite mixture modeling for clustering, classification, and density estimation with 14 covariance parameterisations, BIC/ICL selection, bootstrap inference, and dimension reduction

### Conceptos Clave
- **14 Covariance Parameterisations**: Parsimonious models obtained by eigen-decomposition Σ_k = λ_k D_k A_k D_k^⊤, constraining volume (λ), shape (A), and orientation (D) to be equal or variable across clusters, yielding models: EII, VII, EEI, VEI, EVI, VVI, EEE, EVE, VEE, VEV, EEV, EVV, VVE, VVV.
- **Eigen-Decomposition Parameterisation**: Σ_k = λ_k D_k A_k D_k^⊤, where λ_k is a scalar (volume), A_k is diagonal with det(A_k)=1 (shape), and D_k is orthogonal (orientation). This provides geometric interpretation of cluster covariance.
- **BIC for Model Selection**: BIC_{M,G} = 2ℓ_{M,G}(x|Ψ̂) - ν log(n), where ℓ is the log-likelihood at the MLE, ν is the number of estimated parameters, and n is sample size. The model {M,G} maximizing BIC is selected.
- **ICL Criterion**: ICL_{M,G} = BIC_{M,G} + 2 Σ_{i=1}^{n} Σ_{k=1}^{G} c_{ik} log(z_{ik}), where c_{ik} is the hard classification indicator and z_{ik} is the posterior probability. Penalizes BIC by an entropy term measuring cluster overlap.
- **Model-Based Hierarchical Agglomerative Clustering (MBHAC)**: Initialisation method that recursively merges the two clusters providing the smallest decrease in classification likelihood for Gaussian mixture models; shared probabilistic model between initialisation and fitting steps.
- **MclustDR (Dimension Reduction)**: Projects data onto a subspace spanned by linear combinations of features ordered by importance, using both variation on cluster means and (depending on model) variation on cluster covariances.
- **Adjusted Rand Index (ARI)**: A measure of agreement between two partitions, independent of labelling; zero expected value for random partition, bounded above by 1 with higher values representing better accuracy.
- **Weighted Likelihood Bootstrap**: A generalization of nonparametric bootstrap assigning random positive weights (from uniform Dirichlet distribution) to observations; useful when components have small mixture proportions and nonparametric bootstrap may miss them.

### Resultados / Teoremas
> **BIC Approximation to Model Evidence:** BIC is derived as an approximation to the model evidence (marginal likelihood) using the Laplace method. Although regularity conditions do not hold for mixture models in general, consistency results apply (Roeder & Wasserman 1997; Keribin 2000).
> **Bootstrap LRT for Number of Components:** A bootstrap procedure approximates the null distribution of the LRT statistic by generating samples from the fitted model under H_0, computing LRTS* for each, and comparing to the observed LRTS.

### Fórmulas
- **GMM Density**: `f(x; Ψ) = Σ_{k=1}^{G} π_k * f_k(x; θ_k), where Ψ = {π_1,...,π_{G-1}, θ_1,...,θ_G}` — Finite mixture of G Gaussian components with mixing weights π_k and component parameters θ_k = (μ_k, Σ_k).
- **Covariance Eigen-Decomposition**: `Σ_k = λ_k D_k A_k D_k^⊤` — λ_k controls volume, A_k (diagonal, det=1) controls shape, D_k (orthogonal) controls orientation of the k-th cluster ellipsoid.
- **BIC Formula**: `BIC_{M,G} = 2ℓ_{M,G}(x|Ψ̂) - ν log(n)` — Log-likelihood penalized by number of parameters times log(n); larger BIC (less negative) indicates better model.
- **ICL Formula**: `ICL_{M,G} = BIC_{M,G} + 2 Σ_{i=1}^{n} Σ_{k=1}^{G} c_{ik} log(z_{ik})` — BIC penalized by an entropy term; the additional penalty discourages models with overlapping clusters.
- **Bootstrap Standard Error**: `se(Ψ̂) = sqrt(diag(Cov_boot(Ψ̂))), where Cov_boot(Ψ̂) = (1/(B-1)) Σ_{b=1}^{B} (Ψ̂*_b - Ψ̂̄)(Ψ̂*_b - Ψ̂̄)^⊤` — Standard errors estimated from the bootstrap distribution of parameter estimates.
- **LRT Statistic**: `LRTS = -2 log{L(Ψ̂_{G_0})/L(Ψ̂_{G_1})} = 2{ℓ(Ψ̂_{G_1}) - ℓ(Ψ̂_{G_0})}` — Tests H_0: G=G_0 vs H_1: G=G_1; large values provide evidence against H_0. Standard chi-squared approximation does not hold for mixture models.
- **LRT Bootstrap p-value**: `p-value ≈ (1 + Σ_{b=1}^{B} I(LRTS*_b ≥ LRTS_obs)) / (B+1)` — Proportion of bootstrap LRT statistics exceeding the observed value, plus 1, divided by B+1.

### Supuestos
> Each component follows a multivariate Gaussian distribution
> Observations are i.i.d.
> Covariance matrices are positive-definite (regularization available for singular estimates)
> Number of components G and covariance model M are selected (not known a priori)
> 14 possible covariance structures from constraining volume, shape, and orientation
> BIC used by default for model selection (ICL also available)
> EM algorithm initialised via MBHAC (model-based hierarchical agglomerative clustering)

### Intuición
mclust provides a comprehensive, integrated framework for model-based clustering using Gaussian finite mixtures. The key innovation is the eigen-decomposition parameterisation of covariance matrices, which generates 14 geometrically interpretable models (from spherical equal-volume to fully general ellipsoidal). Model selection via BIC simultaneously determines both the number of clusters and the covariance structure. The package's strength lies in its completeness: it handles clustering, classification (discriminant analysis), and density estimation within a unified framework, with bootstrap-based inference for uncertainty quantification and MclustDR for visualisation in reduced dimensions.

### Conexiones
- Informality detection: Apply mclust with BIC to select number of formal/informal worker types; use posterior probabilities for soft classification of workers; bootstrap CIs quantify uncertainty in informal sector share estimates.
- Firm heterogeneity: The 14 covariance structures allow flexible modeling of firm size/productivity distributions; spherical models (EII/VII) for homogeneous sectors, full models (VVV) for heterogeneous ones.
- Labor market segmentation: MclustDR can project multi-dimensional worker characteristics into 2D to visualise labor market segments; uncertainty boundaries show regions of ambiguous classification.
- Policy evaluation: Compare BIC-selected models across time periods to detect structural changes in informality; bootstrap inference on mixing proportions tests whether informal sector share changed significantly.
- Cross-country comparison: Apply mclust to harmonized labor force survey data to identify common or distinct informality patterns across countries using the same covariance structures.

### Metodología
- **package:** mclust version >= 5 (R)
- **core_functions:** {'Mclust': 'Main function for model-based clustering and classification', 'mclustBIC': 'Compute BIC for all models and component numbers', 'mclustICL': 'Compute ICL criterion', 'MclustDR': 'Dimension reduction for visualisation', 'MclustBootstrap': 'Bootstrap inference for parameter uncertainty', 'mclustBootstrapLRT': 'Bootstrap likelihood ratio test for number of components', 'densityMclust': 'Density estimation via Gaussian mixtures', 'classError': 'Misclassification error computation', 'adjustedRandIndex': 'Clustering accuracy evaluation'}
- **model_selection:** BIC by default; ICL for clustering-focused selection; LRT with bootstrap for formal hypothesis testing
- **initialisation:** MBHAC (model-based hierarchical agglomerative clustering) by default; SVD scaling for enhanced separation; randomPairs for stability assessment
- **bootstrap_inference:** {'nonparametric': 'Resample with replacement from empirical distribution', 'weighted_likelihood': 'Random Dirichlet weights (useful for small components)', 'outputs': 'Standard errors, percentile confidence intervals for all parameters'}
- **covariance_models:** 14 structures from Banfield-Raftery/Celeux-Govaert parameterisation: EII, VII, EEI, VEI, EVI, VVI, EEE, EVE, VEE, VEV, EEV, EVV, VVE, VVV

---

# Institutional Reports

## 400080Informal101OFFICIAL0USE0ONLY1.pdf
**Tema:** Informality in Latin America: Exit and Exclusion - A comprehensive World Bank analysis of labor market informality, its causes, consequences, and policy implications across Latin America and the Caribbean

### Conceptos Clave
- **Exit vs Exclusion**: Two complementary analytical frameworks for understanding informality. Exit = voluntary opt-out from formal institutions after cost-benefit analysis (Hirschman 1970). Exclusion = involuntary prevention from participating in the formal economy due to barriers, segmentation, or discrimination.
- **Three Margins of Informality**: The three borders between formal and informal: (1) Labor market segmentation preventing workers from accessing formal jobs; (2) Business entry barriers preventing microfirms from registering (de Soto thesis); (3) Defensive evasion by larger firms facing excessive regulatory/tax burdens.
- **Social Protection Definition of Informality**: A worker is informal if they are a salaried employee not registered with social security. This is the report's primary measurement approach, distinguishing informal salaried (~30% of urban employment) from informal independent/self-employed (~24%).
- **Productive Definition of Informality**: A worker is informal if they are unskilled self-employed, a salaried worker in a small firm, or a zero-income worker. Based on characteristics of the job rather than regulatory compliance.
- **Legalistic Definition of Informality**: A salaried worker is informal if they do not have the right to a pension linked to employment upon retirement. Focuses on the legal/regulatory dimension of the employment relationship.
- **Tax Morale**: A social norm reflecting citizens' willingness to pay taxes. Measured by survey responses about whether tax cheating is justified. Negatively correlated with informality, state capture, and positively correlated with government effectiveness and perceived fairness of public spending.
- **Social Contract**: The implicit agreement between citizens and the state regarding taxation, public service provision, and mutual obligations. In LAC, described as 'broken' or 'dysfunctional' due to poor state performance, inequality, and widespread non-compliance norms.
- **Strong Reciprocity**: Behavior of moral reciprocators who condition their compliance on contributions of others. Applied to tax compliance: individuals are more likely to comply if they believe others comply, creating strategic complementarities and multiple equilibria.
- **State Capture**: A political equilibrium where elites (business, public sector, or labor) interact with the state to maintain rents, excluding broader population. Leads to generalized perception the state serves the few, reinforcing social norms of non-compliance.
- **Culture of Informality**: A pervasive social norm of non-compliance with taxes and regulations, self-reinforcing through: perception that others don't comply, distrust in state effectiveness, weak enforcement, and poor quality/equity of public services.
- **Truncated Welfare Systems**: Social protection systems where those in the formal sector access generous multi-dimensional social security packages, while informal sector workers have much more limited access to benefits or formal risk management instruments.
- **Compensating Differentials**: Non-monetary benefits (flexibility, autonomy, independence) that informal workers receive, which may offset lower cash earnings, explaining why some workers voluntarily choose informality.

### Resultados / Teoremas
> **Hirschman's Exit-Voice-Loyalty Framework:** When individuals are dissatisfied with an organization, they can exit (leave), voice (complain to improve), or remain loyal. Applied to informality: citizens exit formal institutions (state) when they find no benefit in engaging with them.
> **De Soto's Entry Barrier Thesis:** Burdensome entry regulations prohibit small firms from crossing into formality and thriving, creating a large informal sector as entrepreneurs are locked out of the formal economy.

### Fórmulas
- **Informality-Elasticity Relationship (Loayza & Rigolini)**: `Self-employment rate = f(GDP per capita, business flexibility, law & order, government expenditure)` — GDP explains ~80% of cross-country variation in informality. Business flexibility, law & order, and government expenditure (enforcement proxy) all have expected significant signs when replacing GDP.
- **Tax Productivity**: `VAT productivity = VAT revenue / [VAT rate × (GDP - imports + exports)]` — Ratio of actual vs. potential tax collection given existing rates. LAC average: 34% in 2000 (up from 24% in 1985). Chile: 64%, Guatemala: 17%.

### Supuestos
> Workers and firms make rational cost-benefit analyses about formalization
> Informality is multidimensional - different measures capture different phenomena
> Exit and exclusion are complementary, not competing, explanations
> The level of economic development is the most important determinant of informality levels
> Social norms (tax morale, reciprocity) are endogenous to state performance
> Informal sector dynamics closely mirror those in advanced countries (similar entry/exit patterns)

### Intuición
The report's core insight is that informality is not simply a problem of poor people being excluded from formal institutions - it is also a massive vote of no-confidence in the state. When citizens find that formal sector participation costs (taxes, regulations) outweigh benefits (poor-quality services, weak enforcement, unfair treatment), they rationally choose to exit. This creates a vicious cycle: low compliance → low revenue → poor services → lower trust → more exit. Breaking this cycle requires simultaneous improvements in: (1) formal sector productivity (raising the opportunity cost of informality), (2) social protection design (making formality attractive), (3) enforcement (raising cost of informality), and (4) state legitimacy (changing social norms).

### Conexiones
- {'topic': 'Trade and Informality', 'description': 'Trade liberalization had modest or no effects on informality trends in most LAC countries. However, global value chains can incentivize formalization upstream (VAT systems make purchases from informal firms ineligible for tax credits). Dollar appreciation negatively impacts commodity-exporting LAC economies.', 'page_reference': 'Overview p.6, Ch.5 p.151'}
- {'topic': 'Wage Inequality', 'description': 'Inequality is positively correlated with informality (partial correlation coefficient = 0.72 controlling for GDP). High inequality → state capture → poor institutions → low trust → exit from formal system → higher informality. This creates a vicious circle that perpetuates both inequality and informality.', 'page_reference': 'Overview p.13, Ch.8 pp.239-244'}
- {'topic': 'Mexico-Specific Labor Economics', 'description': 'Mexico shows high labor market integration: formal-informal flows are roughly symmetric, suggesting voluntary informality. However, informality increased during 1990s due to labor cost increases and macroeconomic instability. Oportunidades covers 80% of poor but tax collection remains lowest in OECD. VAT productivity only 24%.', 'page_reference': 'Overview pp.5-6, Ch.8 pp.243-244'}
- {'topic': 'Social Protection Reform', 'description': "Traditional contributory social security is poorly designed for LAC's high informality: high payroll taxes, rigid one-size-fits-all packages, long vesting periods that exclude mobile workers. Non-contributory programs compete with formal security, creating perverse incentives. Reform requires de-linking essential coverage from employment status.", 'page_reference': 'Ch.7 pp.179-211'}

### Metodología
- **approach:** Mixed-methods combining econometric analysis of household surveys with institutional analysis
- **data_sources:** ['National household surveys (ENEMDU, PNAD, ENIGH, ECH, etc.) across 18+ LAC countries', 'Special informality modules collected with World Bank support in Argentina (Greater Buenos Aires 2005), Bolivia, Colombia, Dominican Republic', 'Rotating panel data from Argentina, Brazil, Mexico', 'Encuesta Nacional de Micronegocios (Mexico), Pesquisa Economia Informal Urbana (Brazil)', 'Investment Climate Surveys (IFC/World Bank 2006)', 'World Development Indicators, Worldwide Governance Indicators', 'Latinobarometro survey data', 'Cross-country databases: Schneider & Enste MIMIC estimates, Gasparini & Tornarolli measures']
- **empirical_methods:** ['Multinomial logit models for sector choice (formal salaried, informal salaried, self-employed)', 'Propensity score matching for earnings analysis (formal vs informal)', 'Probit/logit regressions for firm formality determinants', 'Gross worker flow analysis (transition matrices between labor market states)', 'Cross-country panel regressions for institutional determinants', 'Decomposition of informality trends across dimensions', 'Partial correlation analysis controlling for GDP per capita', 'Qualitative survey analysis of worker motivations']

---

# Working Papers & Trade Theory

## w21906.pdf
**Tema:** The China Shock: Learning from Labor Market Adjustment to Large Changes in Trade

### Conceptos Clave
- Import competition
- Offshoring
- Labor market adjustment
- Manufacturing employment
- Trade adjustment
- Geographic mobility
- Wage inequality

### Resultados / Teoremas
> The China Shock led to persistent declines in US manufacturing employment, particularly in local labor markets most exposed to import competition from China
> Adjustment mechanisms were surprisingly slow: workers in affected regions experienced long-term unemployment, reduced wages, and reliance on government transfers rather than smoothly relocating or retraining
> Geographic mobility of workers was reduced rather than increased following the China Shock, contrary to standard trade adjustment predictions

### Fórmulas
- `Exposure measure: DeltaChinaImp_j = Sum_i (DeltaChinaImp_ij / L_j) where i = industries, j = commuting zones`
- `Exposure combines industry-level import growth with local employment shares in those industries`
- `Empirical specification: Y_j,t = alpha + beta*DeltaChinaImp_j + gamma*X_j,t + delta_t + epsilon_j,t`

### Supuestos
> Commuting zones are appropriate units for analyzing local labor market effects of trade shocks
> Import penetration from China captures the exogenous component of trade shocks
> Pre-determined industry composition of local economies affects exposure to trade
> Adjustment mechanisms operate over multi-year horizons

### Intuición
When China rapidly expanded exports to the US starting in the late 1990s, local labor markets that happened to have large employment shares in import-competing industries experienced severe and persistent job losses. Rather than workers quickly finding new jobs or moving to other regions, affected workers faced prolonged unemployment, exited the labor force, or took lower-paying jobs. Government transfers (disability, welfare) increased substantially, partly offsetting income losses but not restoring employment. This challenges the standard trade theory prediction of rapid, smooth adjustment to trade shocks.

### Conexiones
- Connects to Melitz (2002) model of intra-industry reallocations (w8881.pdf) as the China Shock disrupted the mix of firms operating in affected industries
- Relates to Artuc and Ortega's discussion of trade adjustment mechanisms in quantitative models
- Provides empirical evidence on the labor market frictions that models like Dix-Carneiro et al. (w28391.rev0.pdf) formalize with informality channels
- Highlights the importance of general equilibrium adjustment costs that are often simplified in trade models

---

## w28391.rev0.pdf
**Tema:** Trade and Informality in the Presence of Labor Market Frictions and Regulations

### Conceptos Clave
- Informality
- Labor market frictions
- Search and matching
- Small open economy
- Trade liberalization
- Worker heterogeneity
- Taxes and regulations
- Formal vs informal employment

### Resultados / Teoremas
> Incorporating labor market frictions with a formal/informal sector distinction is essential for understanding trade liberalization effects in developing countries
> Trade liberalization can have heterogeneous effects on formal and informal employment depending on the interaction between tariffs, tax wedges, and search frictions
> The presence of informality creates a wedge between the effects of trade policy changes on wages and employment, with informality acting as a buffer or amplifier of trade shocks
> Worker sorting across formal and informal sectors depends on productivity, risk aversion, and access to social insurance

### Fórmulas
- `Labor market tightness: theta = M/V where M = job matches, V = vacancies`
- `Matching function: M = M(U, V) with constant returns to scale`
- `Wage determination: w = (1-eta)*z + eta*p*q(theta) where eta = bargaining power, z = outside option, p = productivity, q(theta) = vacancy filling rate`
- `Formal sector tax wedge: tau_f = payroll tax + social contributions - benefits`
- `Informal sector effectively faces tau_i approx 0 but no social protection`
- `Bellman equation for firms: J = p - w + beta*(1-delta)*J`

### Supuestos
> Workers can search for jobs in both formal and informal sectors simultaneously
> Formal sector jobs pay higher wages due to regulations but require tax payments
> Informal sector provides no social insurance but avoids regulatory costs
> Matching frictions prevent instantaneous adjustment of employment
> Small open economy faces world prices for traded goods

### Intuición
In many developing countries, trade liberalization doesn't just affect which goods are produced, but also the formality of employment. When tariffs fall, firms face more competition, which can push them to cut costs including by shifting employment to the informal sector where labor is cheaper (due to lower taxes and regulations). However, informal jobs provide less social protection. The model shows that ignoring this informality margin leads to incorrect predictions about the welfare effects of trade liberalization. The key insight is that trade and labor market regulations interact: the same trade reform can have very different effects depending on the regulatory environment.

### Conexiones
- Directly extends the search-and-matching framework to trade contexts, complementing Melitz (2002) which focuses on firm heterogeneity without labor frictions
- Provides theoretical foundation for the empirical labor market adjustment mechanisms documented in Autor et al. (w21906.pdf)
- Connects to Artuc and Ortega by showing how labor market frictions complicate quantitative trade model calibration
- Offers alternative explanation for persistent employment effects from trade shocks that Autor et al. document empirically

---

## w8881.pdf
**Tema:** The Impact of Trade on Intra-Industry Reallocations and Aggregate Industry Productivity

### Conceptos Clave
- Firm heterogeneity
- Intra-industry reallocation
- Self-selection
- Productivity distribution
- Trade liberalization
- Monopolistic competition
- Iceberg trade costs
- Free entry

### Resultados / Teoremas
> Trade liberalization leads to intra-industry reallocation: more productive firms expand and less productive firms contract or exit
> A selection effect occurs where trade increases the minimum productivity threshold for survival in the domestic market, raising average industry productivity
> Trade liberalization raises aggregate industry productivity without any change in individual firm productivity through this reallocation mechanism
> The gains from trade come primarily from the reallocation of resources toward more productive firms rather than from specialization
> Firms that are large before trade liberalization become even larger, while small firms shrink or exit

### Fórmulas
- `Firm productivity: phi drawn from cumulative distribution G(phi)`
- `Revenue function: r(phi) = tau^(1-sigma) * phi^(sigma-1) * R/P^(1-sigma) where tau = iceberg cost, sigma = elasticity of substitution`
- `Profit function: pi(phi) = r(phi)/sigma - f where f = fixed cost`
- `Free entry condition: integral[phi_bar, infinity] pi(phi) dG(phi) = f_e where f_e = entry cost`
- `Price index: P = [integral n(phi) * (p(phi))^(1-sigma) dphi]^(1/(1-sigma))`
- `Wage: w = [integral n(phi) * r(phi) * phi^(-1) dphi] / [integral n(phi) * l(phi) dphi]`

### Supuestos
> CES preferences with identical elasticity of substitution sigma > 1 across varieties
> Monopolistic competition (Dixit-Stiglitz)
> Each firm produces a unique variety with productivity drawn from a Pareto distribution (or similar)
> Firms face fixed costs of production and entry
> Iceberg trade costs tau > 1
> Labor is the only factor of production

### Intuición
When trade opens up, firms face competition from foreign varieties. The most productive domestic firms are also the most profitable exporters, so they expand and serve both domestic and foreign markets. Less productive firms lose market share to imports and to the expanding efficient firms. If trade costs fall enough, the least productive firms exit entirely. This reallocation of market share from low-productivity to high-productivity firms raises the average productivity of the industry, even though no individual firm's technology changed. This is the key insight: trade acts as a productivity-enhancing mechanism through selection and reallocation.

### Conexiones
- Foundational model for understanding how trade affects within-industry productivity, complementing Autor et al.'s focus on across-industry labor market effects
- The firm selection mechanism described here helps explain the persistent productivity effects that Artuc and Ortega attempt to quantify in their practitioner's guide
- Provides micro-foundation for the aggregate productivity gains from trade that motivate much of the quantitative trade literature
- Contrasts with Dix-Carneiro et al. by assuming perfectly functioning labor markets; their model adds the friction that prevents this smooth reallocation

---

## International Trade Policy and Quantitative Models.pdf
**Tema:** Practitioner's Guide to Quantifying the Effects of Trade Policy

### Conceptos Clave
- Quantitative trade models
- Counterfactual analysis
- Welfare gains from trade
- Trade elasticity
- Armington model
- Ricardian model
- Melitz model
- Multi-sector extensions
- Calibration
- Numerical methods

### Resultados / Teoremas
> The Armington model predicts gains from trade driven by love-of-variety and differences in comparative advantage across countries
> The Melitz model adds firm-level selection, which generates additional gains from trade beyond the Armington model through productivity-enhancing reallocation
> The trade elasticity (how much trade volumes respond to trade costs) is a key parameter determining the quantitative effects of trade policy
> Multi-sector models are necessary to capture general equilibrium effects of sector-specific trade policy changes
> Welfare gains from trade liberalization can be decomposed into variety, selection, and reallocation components depending on the model

### Fórmulas
- `Armington: U_i = [Sum_j n_ij * (c_ij)^((sigma-1)/sigma)]^(sigma/(sigma-1))`
- `Trade share: pi_ij = (tau_ij * w_j / A_j)^((1-sigma)) * Sum_k (tau_ik * w_k / A_k)^((sigma-1))`
- `Melitz selection: Delta_avg = [1 - G(phi_bar)]^(-1) * integral[phi_bar, infinity] (phi/phi_bar)^(sigma-1) dG(phi)`
- `Welfare change: DeltaW = DeltaLambda * (sigma/(sigma-1)) where DeltaLambda is the change in the real wage index`
- `Gravity equation: X_ij = T_i * M_j * tau_ij^(1-sigma)`
- `Welfare in Melitz: W = (R/P) * lambda where lambda captures the selection premium`

### Supuestos
> CES preferences are the workhorse specification across most quantitative models
> Iceberg trade costs capture all frictions to trade
> Countries differ in their technologies, factor endowments, or preferences depending on the model
> Calibration targets include bilateral trade shares, GDP, and sector-level employment shares
> The trade elasticity sigma-1 (or a variant) is typically estimated from gravity regressions

### Intuición
This paper provides a practical guide for researchers who want to quantify the effects of trade policy changes (tariffs, trade agreements, etc.) using modern trade models. The key message is that the choice of model matters for quantitative predictions, but there are common analytical frameworks. The Armington model is simplest, capturing gains from variety and comparative advantage. The Melitz model adds firm heterogeneity, generating additional gains from selection. The guide walks through numerical implementation, calibration strategies, and how to handle multi-sector extensions. The trade elasticity, the responsiveness of trade flows to trade costs, is identified as the crucial parameter governing the magnitude of predicted effects.

### Conexiones
- Provides the quantitative framework that Autor et al. (w21906) evaluate empirically with respect to labor market effects
- The Melitz model section directly builds on w8881 (Melitz 2002) adding quantitative implementation details
- The multi-sector framework extends the small open economy framework used by Dix-Carneiro et al. (w28391.rev0) to multiple countries
- Offers methodological bridge between theoretical models and empirical evaluation of trade policies

---

## Nowcasting World Trade.pdf
**Tema:** Nowcasting World Trade with a Multi-Region Factor Model

### Conceptos Clave
- Nowcasting
- Factor model
- High-frequency trade data
- Multi-region
- Real-time prediction
- Information extraction
- Dynamic factor model

### Resultados / Teoremas
> A multi-region factor model can extract common signals from noisy, high-frequency bilateral trade data to provide timely estimates of world trade
> Common factors capture global trade cycles that are not apparent in individual bilateral trade series
> The factor model outperforms simpler benchmarks (like single-country models) for nowcasting world trade
> Bilateral trade data contain substantial idiosyncratic noise that can be filtered out using the factor structure

### Fórmulas
- `Factor model: x_{ij,t} = Lambda_{ij} * f_t + epsilon_{ij,t} where x = log trade, Lambda = factor loadings, f = common factors, epsilon = idiosyncratic`
- `Dynamic factor: f_t = Phi(L) * f_{t-1} + eta_t where Phi(L) = lag polynomial`
- `Nowcast: f_hat_{T+h|T} based on information set at time T`
- `Signal-to-noise ratio: Var(f_t) / Var(epsilon_{ij,t}) determines how much information the factor captures`
- `RMSE comparison: RMSE_factor < RMSE_benchmark for h-step ahead forecasts`

### Supuestos
> Bilateral trade flows share common global and regional factors
> The number of regions/series is large relative to the number of factors
> Factors follow low-dimensional VAR or AR processes
> Idiosyncratic errors are cross-sectionally uncorrelated (or weakly correlated)
> Trade data at high frequency contain signal about underlying trade trends despite measurement noise

### Intuición
World trade data is published with lags and at varying frequencies across countries. To get a timely picture of what's happening to global trade now, this paper develops a factor model that extracts common signals from many bilateral trade series simultaneously. The idea is that if trade between many country pairs is falling simultaneously, this is more informative about a global trade downturn than any single bilateral series. The factor model separates the common signal (global/regional trade cycles) from country-pair specific noise, providing a timely estimate of world trade conditions.

### Conexiones
- Provides real-time monitoring tools that complement the structural models discussed in Artuc and Ortega
- The global trade factors extracted here capture the aggregate trade movements that drive the labor market effects documented in Autor et al.
- The model's ability to detect trade downturns in real-time is relevant for understanding the timing of trade shocks discussed in Melitz (2002)
- Offers a reduced-form complement to the structural trade models by providing timely measurement of trade movements

---

## Stablecoin Shocks.pdf
**Tema:** Stablecoin Shocks: How Stablecoins Affect Financial Markets

### Conceptos Clave
- Stablecoins
- Cryptocurrency
- Financial stability
- Market liquidity
- Flight to safety
- Payment systems
- Digital currencies
- Systemic risk

### Resultados / Teoremas
> Stablecoin adoption can affect traditional financial markets through liquidity and confidence channels
> Stablecoin shocks (sudden outflows or de-pegging events) can spill over to broader financial markets
> The stablecoin market has grown large enough that disruptions can have systemic implications
> Stablecoins function as a form of private money that interacts with traditional monetary systems

### Fórmulas
- `Stablecoin peg: p_t approx 1 USD (target peg)`
- `Redemption flow: DeltaS_t = S_t - S_{t-1} where S = stablecoin supply`
- `Market impact: Delta r_t = beta * DeltaS_t + controls where r = risk asset returns`
- `Liquidity provision: LP_t = f(S_t, M_t) where M = market maker inventory`
- `Confidence shock: epsilon_t = p_t - 1 (deviation from peg)`

### Supuestos
> Stablecoins maintain a 1:1 peg to the US dollar through reserve backing or algorithmic mechanisms
> Large stablecoin redemptions require selling of reserve assets, potentially affecting those markets
> The stablecoin market is sufficiently integrated with traditional financial markets that shocks can transmit
> Information about stablecoin reserves and backing is relevant for market confidence
> Stablecoin usage is growing and becoming systemically important

### Intuición
Stablecoins have become a massive form of private digital money, with supply exceeding $100 billion. When users redeem stablecoins for dollars, the stablecoin issuers must sell their reserve assets (typically Treasury bills, commercial paper, or other short-term debt). This selling pressure can affect those markets, especially during stress periods when many users try to redeem simultaneously. Additionally, stablecoin de-pegging events can create uncertainty and flight-to-safety dynamics that spill over to broader financial markets. The paper documents these effects empirically and explores the mechanisms through which stablecoin shocks affect traditional financial markets.

### Conexiones
- While distinct from the trade papers, this connects to broader themes of financial globalization and cross-border capital flows that interact with trade
- The liquidity and confidence mechanisms discussed here parallel the financial frictions that can amplify trade shocks in developing economies (relevant to Dix-Carneiro et al.)
- The real-time monitoring approach in this paper is methodologically similar to the nowcasting approach in Jackson and Rivera Greenwood
- Provides evidence on how new financial instruments can create novel channels for systemic risk, relevant to understanding the full range of shocks affecting open economies

---

# Development & Informality

## 86c1fd38-en.pdf
**Tema:** OECD (2025): Expanding Social Protection and Addressing Informality in Latin America

### Conceptos Clave
- **Labour informality**: Workers and firms operating on the margins of relevant laws and regulations, generally not paying contributions to standard social security schemes (pensions, health, unemployment). 48% of workers in 7 LAC OECD/OECD-accession countries are informal; 55% across 27 LAC countries.
- **Vicious circle of informality**: Informality keeps workers in low-productivity activities with few social protections and limited access to training, which perpetuates low skills, low productivity, and low-paid informal work with little chance to transition to better jobs.
- **Social protection fragmentation**: Separate, parallel contributory and non-contributory systems that create coverage gaps, particularly for informal workers who are excluded from contributory schemes (IMSS, ISSSTE in Mexico).
- **Non-wage labour costs**: Employer social security contributions and payroll taxes that increase the cost of formal employment and can incentivise firms to keep workers informal. High non-wage labour costs are a key barrier to formalisation across LAC.
- **Universal basic pension**: Non-contributory pension benefit available to all elderly citizens regardless of employment history, used as a tool to reduce old-age poverty and reduce incentives for informality.
- **Universal healthcare system**: A system detaching health access from job characteristics, where all people are eligible regardless of employment status or contributions. Proposed as a key reform for Mexico with estimated fiscal costs of 5.39-5.90% of GDP.
- **Unified identity number**: A unique identifier linking individuals to healthcare, pension, and tax systems - proposed for Mexico as the institutional foundation to move away from informality. Equivalent to a social security number.
- **Social registry**: Centralized database of beneficiaries of social programmes (e.g., SINIRUBE in Costa Rica) used to improve targeting and reduce leakage to middle/high-income households.
- **Employment subsidies**: Subsidies or reductions in employers' social security contributions to encourage formal hiring of targeted groups (young workers, women, low-income earners). Used in Chile, Colombia, Mexico, Uruguay.

### Supuestos
> Informality arises from burdensome taxes and regulations imperfectly enforced by government
> Smaller, less productive firms face lower costs of informality (fly under radar)
> Formal firms underproduce relative to social optimum; informal firms overproduce
> Financing universal social protection through general taxation rather than payroll taxes preserves formalisation incentives
> Fiscal costs of extending social protection range from 1% to 4% of GDP across the 7 countries studied

### Intuición
The report argues that Latin America is stuck in a vicious circle where high social contribution rates discourage formal employment, which in turn limits social protection coverage, keeping workers in low-productivity informal jobs. Breaking this cycle requires shifting financing from payroll contributions to general taxation while expanding universal basic coverage.

### Conexiones
- Directly covers Mexico's informality challenge (Chapter 9) with specific policy proposals for universal healthcare, pension reform, and tax reform
- Mexico's informality rate (55%) is among the highest in OECD countries and Latin America
- Proposed financing via income tax reform (top bracket from 35% to 47%), VAT increase (16% to 18%), wealth tax (2%), and estate tax
- Universal non-contributory pensions have expanded but fiscal sustainability concerns remain
- Connects to broader LAC patterns: commodity boom reduced informality 2003-2014, but post-2014 stagnation reversed gains
- COVID-19 exposed vulnerability of informal workers - for first time informal employment contracted more than formal (mobility restrictions)
- Social protection spending inefficiencies estimated at 4.2% of GDP across the 7 countries
- Tax revenues average 24% of GDP in these countries vs 34% in OECD countries - significant revenue gap

### Metodología
- **type:** Country case studies with fiscal simulation
- **data_sources:** ['Household surveys (ENO, ENOEN)', 'ILO informality statistics', 'ECLAC/CEPALSTAT', 'National statistical institutes (INEGI, IBGE)', 'CIEP Fiscal Simulator', 'OECD Economic Outlook']
- **approach:** In-depth country analyses of social protection systems, tax structures, and informality drivers, with quantitative fiscal cost estimates for reform proposals using microsimulation models

---

## 8a7c0ac4-en.pdf
**Tema:** OECD Economic Surveys: Mexico 2026

### Conceptos Clave
- **Labour informality (Mexico)**: 55% of employment is informal in Mexico, among the highest in OECD and LAC. Strongly linked to low education levels - workers with lower education are far more likely to end up in informal employment.
- **Skills gap and informality**: Many young people leave school before finishing secondary education and end up in informal jobs with limited training opportunities, creating a vicious cycle of low skills → low productivity → low-paid informal work.
- **Women's barriers to formal employment**: Care responsibilities fall disproportionately on women, often preventing them from taking up formal jobs. Shortage of affordable childcare forces many women into informal work or out of the labour force.
- **Dual vocational education**: Education model combining classroom learning with workplace training, has delivered positive outcomes in Mexico but remains limited in scale. Should be scaled up to improve skills alignment with labour market.
- **Plan Mexico**: Government strategy to boost investment by streamlining regulations, closing infrastructure gaps, and promoting local supply chains. Central pillar includes digitalisation.
- **Fiscal framework reform**: Mexico needs a medium-term fiscal framework to reduce procyclicality, create room for priority spending (education, digitalisation, green transition), and channel revenues into areas with highest returns.
- **USMCA compliance**: Rules of origin require 50-60% regional content (75% for automobiles) for tariff-free access to US market. Currently ~90% compliance; expanding compliance reduces effective tariff rates.

### Supuestos
> GDP growth projected at 0.7% in 2025, 1.4% in 2026, 1.7% in 2027
> Inflation expected to gradually ease toward 3% target
> Two decades of sluggish growth highlight the need for structural reforms
> Education quality is a binding constraint on productivity and formalisation
> Fiscal deficit reached 5% of GDP in 2024 (highest in 35 years), needs consolidation to 3% by 2027
> Mexico has the lowest tax-to-GDP ratio in the OECD

### Intuición
Mexico's economy is stable but growth has been modest for two decades. The Survey argues that reducing informality requires a comprehensive strategy combining better education outcomes, expanded childcare for women, stronger digital skills, and fiscal reforms to mobilise revenues for productivity-enhancing investments.

### Conexiones
- Directly about Mexico - provides the macroeconomic context for the social protection reform proposals in the OECD informality book
- Trade tensions with US: 25% general tariff on non-USMCA Mexican exports; 50% on steel/aluminum; significant risk to growth
- USMCA rules of origin compliance is key to maintaining tariff-free access
- Informality linked to low education: states with higher skill levels tend to display lower informality
- Women's informality particularly high due to care barriers
- Digitalisation as complementary strategy to reduce informality and boost productivity
- Fiscal space needed for social protection expansion but deficit requires consolidation

### Metodología
- **type:** OECD Economic Survey (peer review)
- **data_sources:** ['OECD Economic Outlook', 'INEGI household surveys (ENO/ENOEN)', 'Banxico', 'IMF World Economic Outlook', 'World Bank WDI', 'OECD statistics']
- **approach:** Comprehensive economic assessment combining macroeconomic analysis, structural policy evaluation, and sector-specific recommendations with international comparisons

---

## DGMU_Final_Ecma.pdf
**Tema:** Trade and Domestic Distortions: The Case of Informality (Academic Paper)

### Conceptos Clave
- **Informal sector as misallocation**: Smaller, less productive firms sort into informality facing fewer distortions (evading taxes/regulations), while larger, more productive formal firms face higher distortions. This leads to informal firms overproducing and formal firms underproducing relative to social optimum.
- **Reallocation effect from trade**: Reductions in trade barriers trigger reallocation of resources from less distorted informal firms to more distorted formal firms, amplifying gains from trade beyond what occurs in a distortion-free economy.
- **Unemployment buffer hypothesis**: The informal sector absorbs workers dismissed from formal jobs during negative labor demand shocks, mitigating increases in unemployment. Confirmed empirically by Dix-Carneiro and Kovak (2019) and Ponczek and Ulyssea (2022).
- **Informality as non-real-income buffer**: While informality buffers unemployment, it does NOT buffer real income losses from negative shocks. Resources move from more distorted formal to less distorted informal sector, making reallocation effects more negative.
- **Size-dependent distortion**: Government enforcement of taxes/regulations is imperfect, creating size-dependent distortions: larger firms face higher costs of informality (more visible, higher fines), leading to size-dependent sorting into formal/informal sectors.
- **Mechanical vs reallocation effects of trade**: Mechanical effect: direct price impact from lower trade costs (holding allocations fixed). Reallocation effect: gains from resource reallocation across distorted uses. In high-informality settings, the reallocation effect dominates.
- **Cross-firm wage inequality and trade**: Trade liberalization increases wage inequality in the formal manufacturing sector alone (as found in prior literature), but this result reverses when accounting for the informal sector - overall economy-wide wage inequality decreases.

### Fórmulas
- **Real income decomposition (Baqaee-Farhi)**: `ΔlogY ≈ ΔlogY_ME + ΔReallocation Effect` — Total real income gains from trade = mechanical effect (direct price changes) + reallocation effect (resource reallocation across distorted firms)
- **Firm production function**: `q_k(z,ℓ,ι_k) = zℓ^δ_k ι_k^(1-δ_k)` — Output of firm in sector k with productivity z, labor ℓ, and intermediate input ι_k. Cobb-Douglas with labor share δ_k
- **Productivity process**: `ln z' = ρ ln z + σ_z ε, ε ~ N(0,1)` — Firm productivity follows AR(1) process with persistence ρ and innovation σ_z
- **Informality cost function**: `p_ki(ℓ') = ã_k exp(b̃_k(ℓ'-1))` — Expected cost of informality as fraction of revenues, increasing exponentially with firm size ℓ'
- **Matching function**: `m(υ, L_u) = ϕ υ^ξ L_u^(1-ξ)` — Total matches as function of aggregate vacancies υ and unemployed workers L_u, with matching elasticity ξ
- **Hiring cost function**: `Ch_k(ℓ,υ) = h_k (υ/(γ_k1 ℓ^γ_k2))^γ_k1` — Convex hiring costs depending on firm size and vacancies posted, with convexity γ_k1 and scale economies γ_k2

### Supuestos
> Informal sector arises from burdensome taxes/regulations imperfectly enforced by government
> Firms are heterogeneous in TFP and endogenously sort into formal/informal sectors
> Formal firms cannot switch to informal; informal firms can formalize
> Search and matching frictions generate equilibrium unemployment and wage dispersion
> Two sectors: manufacturing (C, tradeable) and services (S, non-tradeable)
> Minimum wage is binding and affects formal/informal sector incentives
> Government imperfectly enforces regulations: cost of informality increases with firm size
> Convex hiring costs generate wage dispersion (expanding firms pay more)

### Intuición
In economies with large informal sectors, trade liberalization gains are amplified because reducing trade barriers reallocates resources from small, inefficient informal firms to larger, more productive formal firms. The informal sector creates a double distortion: it overproduces (facing fewer distortions) while formal firms underproduce (facing more distortions). Trade openness reduces this misallocation, but even large trade reforms only modestly reduce overall informality rates.

### Conexiones
- Directly relevant to understanding how trade openness interacts with informality in Mexico and Latin America
- Latin America informality ranges from 35% (Chile) to 80% (Peru) - Mexico is around 55%
- Brazil's experience with trade liberalization (early 1990s) shows informal sector as key margin of adjustment
- Findings validate that informal sector absorbs unemployment shocks but worsens real income losses
- Trade gains are amplified in high-informality economies - relevant for Mexico-US trade integration
- Even large trade reforms barely reduce informality (5 pp decline despite 4x increase in trade openness) - explains why informality persists despite globalization
- Wage inequality result: trade reduces economy-wide inequality when informal sector is included (reverses formal-sector-only finding)
- Firing costs, minimum wage, payroll taxes - all contribute to informal sector incentives in LAC including Mexico

### Metodología
- **type:** Quantitative structural model with estimation
- **data_sources:** ['RAIS (matched employer-employee, all formal firms/workers, Brazil 2003-2005)', 'PIA (Manufacturing firm census/survey, IBGE)', 'PAS (Services firm survey, IBGE)', 'PAC (Retail/Commerce firm survey, IBGE)', 'SECEX (Customs records, export/import data)', 'ECINF (Informal economy survey, matched employer-employee, firms ≤5 employees, 2003)', 'PME (Monthly Employment Survey, rotating panel, 6 metropolitan regions)']
- **approach:** Structural model with heterogeneous firms, endogenous formal/informal sorting, search-matching frictions, two sectors (manufacturing/services), estimated targeting 74 data moments with 27 structural parameters. Counterfactual simulations of trade cost changes and enforcement scenarios.
- **key_estimates:** {'sigma_C': 5.0, 'sigma_S': 3.0, 'gamma1_C': 1.7, 'gamma1_S': 5.8, 'gamma2_C': 0.06, 'gamma2_S': 0.13, 'unemployment_disutility': '~80% of real income per capita', 'formal_informal_wage_gap': '0.34-0.43 log points (worker-level, controlling for characteristics)'}

---
