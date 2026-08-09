# Cuaderno de apuntes - Dynamic Macroeconomics II (Felipe Meza, ITAM)

*Generado por /the-reader - 2026-08-09 - 22 archivos - 323 paginas*

> **Como leer este cuaderno.** Cada archivo trae, ademas de los apuntes estandar, cuatro secciones
> anadidas para conectar con la tesis sobre elasticidad de demanda de trabajo:
> **Bloque laboral**, **Instrumentos de politica**, **Metodo computacional** y **Objetivos de calibracion**.

## Indice de temas

- **Macro_Din_II_Topics1.1and1.2.pdf** - *Topic 1: Models of Real Business Cycles (1.1 Stylized Facts & HP Filter; 1.2 Standard RBC Model, Calibration, McGrattan *
- **Macro_Din_II_Topic2.1Basic.pdf** - *Fiscal Policy / Ricardian Equivalence -- Basic Model (pure endowment economy, no government, no production)*
- **NotesDynMacroIITopic2.1.pdf** - *Handwritten companion notes to Topic 2.1 Basic Model: step-by-step derivation of the Natural Debt Limit, the Euler equat*
- **Macro_Din_II_Topic2.1Government.pdf** - *Fiscal Policy / Ricardian Equivalence -- Model with Government (formal statement and proof of the Ricardian Proposition)*
- **NotesMacroDynIITopic2.1Gov.pdf** - *Handwritten companion notes to Topic 2.1 Government: full worked derivation of Step 4 in the proof of the Ricardian Prop*
- **Macro_Din_II_Topic2.2FirstPartFINALVERSION.pdf** - *Fiscal Policies in the Growth Model — First Part: non-stochastic one-sector growth model with distortionary taxes (tau_c*
- **Macro_Din_II_Topic2.2SecondPart.pdf** - *Fiscal Policies in the Growth Model — Second Part: steady state of the capital difference equation, comparative statics,*
- **Macro_Din_II_Topic2.2ThirdPartFINALVERSIONfixlastslide.pdf** - *Fiscal Policies in the Growth Model — Third Part: which taxes are distorting versus non-distorting under inelastic labor*
- **NotesDynMacroIITopic2.2.pdf** - *Handwritten notes, Continuous-Time (Ramsey) Model, Part 1: constructing the phase diagram in (k,c) space from the contin*
- **NotesDynMacroIITopic2.2secondpart.pdf** - *Handwritten notes, Continuous-Time (Ramsey) Model, Part 2: the saddle path/stable arm, off-path (non-equilibrium) trajec*
- **Macro_Din_II_Topic2.3FirstPartFINALVERSIONfixes2.pdf** - *Optimal Fiscal Policy with Commitment — First Part: the Ramsey Problem, Chamley's (dual) approach, and Judd's (1985) het*
- **Macro_Din_II_Topic2.3SecondPartFINALVERSION.pdf** - *Optimal Fiscal Policy with Commitment — Second Part: the primal approach to the Ramsey Problem, the Implementability Con*
- **Macro_Din_II_Agosto_2018Topic3.1FirstPart(1).pdf** - *A Monetary Model — First Part: money demand via a shopping-time transaction technology, the Fisher equation, consolidate*
- **NotesDynMacroIITopic3.1.pdf** - *Handwritten student lecture notes, Topic 3.1 (October 2020): the seigniorage Laffer curve, graphical determination of th*
- **Macro_Din_II_Agosto_2018Topic3.1SecondPartand3.2.pdf** - *Monetary economics — shopping-time money-in-the-utility model (Topic 3.1 Second Part: monetary-policy applications — qua*
- **Macro_Din_II_Agosto_2018Topic4.2CORREGIDO.pdf** - *Exogenous growth in the (deterministic) neoclassical growth model with distortionary taxes — DETRENDING. Model type: rep*
- **Macro_Din_II_Agosto_2019Topic5FirstPart(1).pdf** - *Computational/solution methods for DSGE models — log-linearization (first-order Taylor approximation around the steady s*
- **Macro_Din_II_Agosto_2019Topic5SecondPart(1).pdf** - *Uhlig's Method of Undetermined Coefficients for solving linear (log-linearized) rational-expectations DSGE models. Conti*
- **Macro_Din_II_Agosto_2019Topic5ThirdPart.pdf** - *Computational implementation — using Harald Uhlig's Matlab toolkit (Undetermined Coefficients / log-linearization solver*
- **Topic5Solving_by_hand.pdf** - *Topic 5 (handwritten lecture notes, Prof. Felipe Meza): 'Solving the model by hand' -- the method of undetermined coeffi*
- **Proyecto.pdf** - *Computing Program (Proyecto Computacional), Dynamic Macroeconomics II, ITAM (solution by Coronel, Fernandez & Sabido): R*
- **Midterm_exam_Dynamic_Macro_II_oct2024_251013_052910.pdf** - *Midterm Exam, Dynamic Macroeconomics II, Prof. Felipe Meza, ITAM, October 10, 2024 (100 points, 1:30 hours, multiple cho*

---

## Topic 1: Models of Real Business Cycles (1.1 Stylized Facts & HP Filter; 1.2 Standard RBC Model, Calibration, McGrattan 1994 fiscal extension, Hansen 1985 indivisible labor)

*Fuente: `Macro_Din_II_Topics1.1and1.2.pdf`*

*Secciones: Introduction: definition of business cycles (Lucas 1977), trend vs. cycle | The Hodrick-Prescott (HP) filter: definition, minimization problem, choice of lambda | Procyclical/countercyclical/acyclical definitions; leads and lags | Business Cycle Stylized Facts: United States | Business Cycle Stylized Facts: Mexico | RBC methodology (Kydland & Prescott 1982) | McGrattan (1994) standard model: household problem, firm problem, feasibility, state vector, functional forms | Calibration: definition and implementation (lambda_t, TFP detrending) | Calibrating beta, delta, theta, gamma | Business Cycle Methodology: simulate-filter-compare | Table 1: US data vs. Standard Kydland-Prescott model vs. Hansen extension | Hansen (1985): indivisible labor and lotteries | McGrattan (1994): adding fiscal shocks (distortionary taxes, government spending) | VAR for exogenous shocks (TFP + fiscal variables), Table 2: divisible vs indivisible labor with fiscal shocks | Intuition for results: static and two-period labor supply models, with and without taxes*

### Supuestos

> 0<beta<1, 0<delta<1 (McGrattan standard model)
>
> gamma>0, 0<theta<1 (functional form parameters)
>
> -1<rho_lambda<1 (TFP shock persistence)
>
> Competitive economy: agents take prices and initial capital k_0 as given
>
> Household does all investment, so the firm's problem is static
>
> Calibration principle: never calibrate a parameter to reproduce exactly the fact the model aims to explain (else no explanatory power)
>
> Hansen (1985): consumers work a fixed N hours or 0 (discrete/indivisible choice); non-convex choice set convexified via lotteries
>
> McGrattan fiscal extension: balanced government budget every period (no public debt in this version); taxes/spending follow a VAR known by consumers (no informational asymmetry)
>
> 1<lambda<R type growth conditions do not appear here (that's Topic 2.1); relevant instead: TFP grows geometrically lambda_t=lambda_0(1+g)^t, incompatible with plain stationary AR(1) unless detrended
>

### Conceptos clave

- **Business cycle (Lucas 1977)** - Fluctuations of output around a trend, together with comovement of other economic series with output.
- **Trend/cycle decomposition** - Any time series Y_t is broken into a trend component Y_t^g and a cyclical component Y_t^c: Y_t = Y_t^c + Y_t^g.
- **Hodrick-Prescott (HP) filter** - A two-sided filter that extracts the trend Y_t^g by solving a penalized least-squares problem trading off fit to the data against smoothness (curvature) of the trend.
- **Smoothing parameter lambda** - Penalty weight in the HP filter on the variance of the trend's growth rate; lambda=0 gives Y_t=Y_t^g (all cycle), lambda to infinity gives a linear trend. In practice lambda=1600 (quarterly) and lambda=100 (annual), chosen so the trend absorbs fluctuations at frequencies lower than usual business-cycle frequency (3-5 years, Burns & Mitchell 1946).
- **Procyclical / countercyclical / acyclical** - A variable is procyclical if corr(x,GDP)>0, countercyclical if corr(x,GDP)<0, acyclical if the correlation is near zero.
- **Leading/lagging variables** - Determined by looking at correlation of a variable with GDP at various leads/lags; e.g., past values of money are highly correlated with current output, so money 'leads' the cycle.
- **Extensive vs. intensive margin** - Extensive margin = number of employed workers (employment); intensive margin = average hours worked per employee. US data: extensive margin is more volatile than intensive margin.
- **Total Factor Productivity (TFP), lambda_t** - Multiplicative productivity shifter in the production function y_t = lambda_t f(k_t,n_t); treated as the exogenous driving force of the RBC model.
- **State vector x_t** - Summarizes information about the current position of the system relevant for determining its future; for the standard McGrattan (1994) economy x_t = {k_t, lambda_t}.
- **Competitive equilibrium (static firm problem)** - Agents (households and a representative firm) take prices (w_t, r_t) as given; since the household does all investment, the firm's problem is static (period-by-period profit maximization).
- **Calibration** - Finding parameter values so the model replicates certain features of the economy (typically steady-state/first-moment facts), explicitly NOT calibrating to reproduce exactly what the model aims to explain, or the model would have no explanatory power by construction.
- **Indivisible labor / lotteries (Hansen 1985)** - Because individual work-hour choice is discrete (work N hours or 0), the individual choice set is non-convex; Hansen convexifies it using lotteries (probabilities of working 0 or N hours), which the consumer chooses over, delivering a linear-in-leisure aggregate utility function.
- **Fiscal shocks (McGrattan 1994)** - Extension of the standard RBC model adding distortionary taxes on labor and capital income, government expenditure that may enter utility, and a balanced-budget government financed via endogenous lump-sum transfers.

### Teoremas, lemas y proposiciones

> **RBC model shortfall (Kydland & Prescott 1982) and its resolution**
>
> The standard neoclassical growth model with a single stochastic TFP shock, calibrated to US data, fails to explain the volatility of hours worked, and produces a correlation between labor productivity and hours worked near one, whereas in the data that correlation is close to zero (or negative).
>
> *Supuestos requeridos:* Cobb-Douglas technology k^theta n^(1-theta); divisible labor with log-separable utility ln(c)+gamma ln(l); TFP follows AR(1); competitive equilibrium, representative agent
>
> *Garantiza:* Motivates two documented extensions: Hansen (1985) indivisible labor (lotteries -> linear-in-leisure utility, amplifies hours volatility) and McGrattan (1994) fiscal shocks (distortionary taxes lower the model-implied hours-productivity correlation toward the negative value seen in the data).

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Trend-cycle decomposition | `Y_t = Y_t^c + Y_t^g` | Output equals cyclical plus trend component | Whenever separating a raw series into cycle and trend before computing stylized facts |
| HP filter minimization problem | `\min_{\{Y_t^g\}} \sum_{t=1}^{T}(Y_t-Y_t^g)^2 + \lambda\sum_{t=1}^{T-1}\big[(Y_{t+1}^g-Y_t^g)-(Y_t^g-Y_{t-1}^g)\big]^2` | First term penalizes deviation of the trend from the data (fit), second term penalizes changes in the trend's growth rate (smoothness/curvature) | To extract the trend component Y_t^g for detrending macro time series |
| Log growth-rate approximation | `\log(Y_t/Y_t^g) = \log(Y_t)-\log(Y_t^g) \approx \log(Y_t^c)` | Working in logs, the log difference between actual and trend approximates the percentage cyclical deviation | When computing percentage deviations from trend for volatility/correlation statistics; multiply by 100 to interpret as percent |
| Household objective (McGrattan 1994 standard model) | `\max\ E_0\sum_{t=0}^{\infty}\beta^t\big[u(c_t,\ell_t)\mid x_0\big]` | Consumer maximizes expected discounted utility from consumption and leisure | Setting up the household's dynamic program in the standard RBC model |
| Budget constraint (1) | `c_t+i_t \le r_tk_t+w_tn_t` | Consumption plus investment cannot exceed capital and labor income | Household resource constraint each period |
| Law of motion of capital (2) | `i_t = k_{t+1}-(1-\delta)k_t` | Investment equals net change in capital plus depreciation; net investment k_{t+1}-k_t differs from gross investment k_{t+1}-k_t+\delta k_t | Capital accumulation equation |
| Time constraint (3) | `1 = \ell_t+n_t` | Total time endowment normalized to 1 splits between leisure and labor | Whenever leisure and hours worked must be linked |
| Firm problem and output (4) | `\max\ y_t-w_tn_t-r_tk_t\ \ \text{s.t.}\ \ y_t=\lambda_tf(k_t,n_t)` | Representative competitive firm maximizes static profit given TFP lambda_t | Deriving factor demand/pricing conditions |
| Factor pricing (marginal products) | `w_t=\lambda_tf_{n_t}=MP_{n_t}, \quad r_t=\lambda_tf_{k_t}=MP_{k_t}` | Competitive wages/rental rates equal marginal products | This is the labor demand condition of the model |
| Feasibility | `c_t+i_t = y_t` | Aggregate resource constraint in the baseline model (no government) | Market clearing condition |
| TFP AR(1) process | `\lambda_{t+1} = (1-\rho_\lambda)\bar\lambda+\rho_\lambda\lambda_t+\varepsilon_{t+1}, \quad \varepsilon\sim(0,\sigma_\varepsilon^2)` | TFP follows a first-order autoregressive process with persistence rho_lambda in (-1,1) | Driving stochastic process for simulating the model |
| Functional forms | `u(c_t,\ell_t)=\ln(c_t)+\gamma\ln(\ell_t), \qquad f(k_t,n_t)=k_t^{\theta}n_t^{1-\theta}` | Log-separable utility and Cobb-Douglas production, \gamma>0,\ 0<\theta<1 | Needed to close the model numerically / to compute a competitive equilibrium |
| Measured TFP | `\lambda_t = \dfrac{y_t}{k_t^{\theta}n_t^{1-\theta}}` | Solow-residual style computation of TFP from data given theta | Constructing the empirical TFP series to feed the calibration/AR(1) estimation |
| TFP detrending regression (McGrattan) | `\ln TFP_t = \beta_0+\beta_1 t; \qquad \ln\lambda_t^{consistent} = \ln TFP_t-\beta_1 t` | Because TFP grows geometrically (\lambda_t=\lambda_0(1+g)^t, so \ln TFP_t\approx \ln\lambda_0+gt), incompatible with stationary AR(1); regress log TFP on a linear trend and remove it before estimating the AR(1) | Before estimating rho_lambda and sigma_epsilon |
| Beta calibration via steady-state Euler equation | `\beta=\dfrac{1}{1+r}` | Discount factor pinned down by the real interest rate | Annual real r=4% gives beta=0.96; quarterly gives beta approx 0.99. Choice of period length (month/quarter/year) for t matters. |
| Delta calibration regression | `i_t-(k_{t+1}-k_t) = \delta k_t` | Regression linking investment and capital change to depreciation | McGrattan finds quarterly delta=0.023; annualized via (1-0.023)^4\approx0.91=1-\delta_{annual}, so \delta_{annual}=0.09 |
| Theta calibration via steady-state Euler equation | `1=\beta\Big[\theta\dfrac{y}{k}+(1-\delta)\Big]` | Steady-state condition linking capital share theta to the K/Y ratio | Quarterly K/Y approx 11, annual K/Y approx 3 in developed countries, giving theta approx 1/3 |
| Gamma calibration via consumption-leisure condition | `\dfrac{\gamma c}{1-n} = (1-\theta)\dfrac{y}{n}` | Steady-state MRS between consumption and leisure equals the after-tax wage/marginal product of labor | Targeting US average hours n approx 0.27 gives gamma approx 2 |
| Hansen (1985) linear-in-leisure utility | `u(c_t,\ell_t) = \ln(c_t)+\gamma_2\ell_t` | Result of convexifying the discrete work/no-work choice via lotteries | Indivisible-labor extension of the standard RBC model to amplify hours volatility |
| McGrattan (1994) utility with government spending | `u(c_t+\pi g_t,\ell_t), \quad \pi\ge 0` | Government expenditure enters utility as an imperfect substitute for private consumption, weight pi | Fiscal-shocks extension; McGrattan estimates pi approx 0 |
| Balanced-budget transfer rule | `g_t+T_t = \tau_{k_t}(r_t-\delta)k_t+\tau_{n_t}w_tn_t` | Endogenous lump-sum transfers T_t close the government budget every period given exogenous g_t and tax rates | Government budget constraint in the fiscal RBC model (no public debt) |
| Consumer budget constraint with taxes | `c_t+i_t \le (1-\tau_{n_t})w_tn_t+r_tk_t-\tau_{k_t}(r_t-\delta)k_t+T_t` | Distortionary labor and net-capital-income taxation plus lump-sum transfer | Household problem in the fiscal-shocks extension |
| Exogenous shock VAR | `v_{t+1} = (I-\rho_v)\bar v+\rho_v v_t+\varepsilon_{t+1}, \quad \varepsilon\sim(0,\Sigma), \quad v_t=(\lambda_t,g_t,\tau_{k_t},\tau_{n_t})` | Vector generalization of the AR(1); rho_v is diagonal with entries rho_lambda, rho_g, rho_n, rho_k | Joint stochastic process driving TFP and fiscal variables |
| New feasibility with government | `c_t+i_t+g_t = y_t` | Resource constraint including government purchases | Market clearing once g_t is introduced |
| Static labor supply | `\max\ u=\ln(c)+b\ln(1-n)\ \ \text{s.t.}\ \ c\le wn \ \Rightarrow\ n=\dfrac{1}{1+b}` | In a static economy labor supply depends only on preference parameter b, not on the wage | Baseline intuition building block before adding intertemporal substitution |
| Two-period labor supply FOC | `\dfrac{1-n_1}{1-n_2} = \dfrac{1}{\beta(1+r)}\dfrac{w_2}{w_1}` | Relative labor supply across two periods depends on relative wages and the interest rate (intertemporal substitution in labor supply) | A higher w1/w2 implies n1>n2; a higher r induces working more today to save |
| Two-period labor supply FOC with taxes | `\dfrac{1-n_1}{1-n_2} = \dfrac{1}{\beta(1+r)}\dfrac{w_2}{w_1}\dfrac{1-\tau_2}{1-\tau_1}` | Labor income tax wedge modifies the intertemporal labor-supply condition; equal tax rates across periods leave the condition unchanged (last term vanishes) | Shows that time-varying labor taxes are the channel by which McGrattan's model lowers the hours-productivity correlation |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Production is Cobb-Douglas: f(k_t,n_t)=k_t^theta n_t^(1-theta), 0<theta<1 (theta = capital's share; the CURVATURE parameter governing diminishing marginal product of labor and the elasticity of substitution between capital and labor, which is unity under Cobb-Douglas). The labor demand condition is competitive marginal-product pricing: w_t = lambda_t f_{n_t} = MP_{n_t} = lambda_t(1-theta)k_t^theta n_t^{-theta} (equivalently w_t=(1-theta) y_t/n_t in the government-extended model's steady-state calibration equation). Baseline utility/labor-supply specification is separable and NOT GHH: u(c_t,l_t) = ln(c_t) + gamma ln(l_t) [with l_t=1-n_t], gamma>0 governing the strength of the income effect on labor supply and calibrated (gamma approx 2, or 2.33 with government) to match average hours n approx 0.27; this generates a finite, model-implied Frisch elasticity (no closed-form Frisch elasticity is stated in the slides). Hansen (1985) modifies this to LINEAR-in-leisure utility u(c_t,l_t)=ln(c_t)+gamma_2 l_t via lotteries over an indivisible (work N hours or 0) individual choice -- this is the mechanism that makes AGGREGATE labor supply behave as if the (aggregate) Frisch elasticity were effectively very high/infinite along the extensive margin, amplifying hours volatility. The two-period/intertemporal labor supply FOCs, (1-n1)/(1-n2)=[1/(beta(1+r))](w2/w1) and its tax-augmented version with the wedge (1-tau2)/(1-tau1), show labor supply's curvature also depends on relative (present vs. future) after-tax wages -- i.e., intertemporal substitution in labor supply, directly relevant to how labor demand/supply elasticities are identified.

### [POLICY] Instrumentos de politica

- tau_{k_t}: stochastic capital income tax rate, part of the VAR state v_t; enters the budget constraint as -tau_{k_t}(r_t-delta)k_t (tax on NET capital income) and the transfer-balancing identity
- tau_{n_t}: stochastic labor income tax rate; enters the budget constraint as (1-tau_{n_t})w_t n_t
- g_t: exogenous government expenditure; enters utility as u(c_t+pi g_t, l_t) with pi>=0 (calibrated pi approx 0) and enters feasibility c_t+i_t+g_t=y_t
- T_t: endogenous lump-sum transfer that balances the government budget every period: g_t+T_t = tau_{k_t}(r_t-delta)k_t+tau_{n_t}w_t n_t (no public debt in this version)
- Calibrated long-run fiscal targets: g_bar/y_bar=0.22, tau_k_bar=0.5, tau_n_bar=0.23
- No monetary policy instrument appears (this is a real RBC model)

### [COMPUT] Metodo computacional

Hodrick-Prescott (HP) filter for detrending (lambda=1600 quarterly, lambda=100 annual). Calibration methodology explicitly distinguished from estimation-to-fit (must not calibrate to the very moments being explained). Standard RBC simulation pipeline: (1) calibrate parameters and pick a solution method (value function iteration OR log-linearization plus the method of undetermined coefficients are both mentioned), (2) generate a random shock sequence {lambda_t} (or vector v_t in the fiscal extension), (3) simulate the model for a long T to get equilibrium sequences {c_t,y_t,n_t,i_t,k_{t+1}}, (4) apply the HP filter to the simulated series, (5) compute theoretical/model moments and compare against the analogous HP-filtered US data moments (Tables 1 and 2). Regression-based detrending of ln(TFP) on a linear time trend (since TFP grows geometrically, incompatible with a stationary AR(1)) before estimating rho_lambda and sigma_epsilon. VAR estimated line-by-line for the joint fiscal/TFP shock vector v_t, with residual-based estimation of the covariance matrix Sigma. Perpetual inventory method used to construct a capital stock series from national-accounts investment data when no official capital series exists (e.g., Mexico). Software mentioned generically: Eviews, Matlab.

### [CALIB] Objetivos de calibracion

- lambda_t computed directly as the Solow residual y_t/(k_t^theta n_t^(1-theta)); long-run lambda_bar normalized to 1
- beta calibrated to the real interest rate: annual r=4% -> beta=0.96; quarterly -> beta approx 0.99
- delta calibrated via regression i_t-(k_{t+1}-k_t)=delta k_t: McGrattan's quarterly delta=0.023 implies annual delta approx 0.09
- theta calibrated via the steady-state Euler equation given the observed K/Y ratio (quarterly K/Y approx 11, annual approx 3 in developed countries) -> theta approx 1/3 (0.355 standard model, 0.359 with government/K over Y approx 8.3)
- gamma calibrated via the steady-state consumption-leisure condition targeting US average hours n approx 0.27 -> gamma approx 2 (2.36 standard, 2.33 with government)
- g_bar/y_bar=0.22, tau_k_bar=0.5, tau_n_bar=0.23 set to approximate long-run US fiscal shares
- rho_lambda, rho_g, rho_n, rho_k and Sigma estimated from VAR residuals after removing deterministic trends
- Model-implied second moments (std. dev. of output, consumption, investment, capital, hours, productivity; corr(hours,productivity)) targeted to match 1947:1-1987:4 US data as reported in McGrattan (1994) Tables 1 and 2

### Intuicion general

The HP filter separates a series into trend and cycle by penalizing curvature (the change in the trend's growth rate), with lambda controlling how smooth the trend must be; the standard choices (1600 quarterly, 100 annual) are set so that fluctuations at frequencies below the usual 3-5 year business cycle are assigned to the trend. The baseline RBC model (Kydland-Prescott/McGrattan) is calibrated off steady-state relationships (interest rate -> beta, K/Y -> theta, depreciation regression -> delta, hours target -> gamma) and simulated with an AR(1) TFP shock; it reproduces many second moments reasonably well but badly overstates the correlation between hours and labor productivity relative to the data (near 1 in the model vs. near 0/negative in US data) and understates hours volatility. Hansen's indivisible-labor/lotteries mechanism linearizes leisure in utility, which flattens (and in the aggregate perfectly elasticizes) labor supply and amplifies hours volatility via the extensive margin. McGrattan's fiscal shocks add distortionary labor/capital taxes that move labor supply independently of productivity (a labor-supply-shifting mechanism, as shown in the two-period labor supply FOC with the tax wedge (1-tau2)/(1-tau1)), which is what pulls the model's hours-productivity correlation down toward (though not exactly matching) the data.

### Ejemplos y ejercicios

- McGrattan (1994) Table 1: US data (1947:1-1987:4) vs. Standard divisible-labor model vs. Hansen indivisible-labor extension -- standard deviations of output, consumption, investment, capital, hours, productivity, and corr(hours,productivity)
- McGrattan (1994) Table 2: US data vs. Divisible-labor vs. Indivisible-labor model, both with fiscal shocks added -- shows correlation(hours,productivity) becomes negative (matching sign of data) only once indivisible labor AND fiscal shocks are combined
- Static one-period labor supply example: n=1/(1+b)
- Two-period labor supply example without and with labor income taxes, showing how relative wages/taxes across periods pin down relative labor supply

### Anotaciones a mano (tuyas)

- Slide 5 (HP filter minimization): labels first term as 'min error c.r. datos' (min error relative to data) and second term as 'min variacion suavidad' (min variation/smoothness); a marginal note near lambda that is only partly legible.
- Slide 6: marginal note 'Con esto lambda y calculamos la tend. y eliminamos el componente ciclico que ...' (with this lambda we calculate the trend and eliminate the cyclical component that...); annotation 'higher t' next to the statement about eliminating fluctuations below 8-year frequency.
- Slide 7: student re-derives by hand the log-growth-rate approximation: 'ln(X_{t+1}/X_e) = tasa crecimiento // X_{t+1}/X_e = [algo] ciclo // log(X_{t+1}/X_e - 1) = tasa ciclo'; also notes 'variable coherente / es mas sencillo calcular sus momentos' near the volatility (std. dev.) bullet, and 'interpretacion a las magnitudes del ciclo se determinan' near the lead/lag correlation graph.
- Slide 8: handwritten formulas Corr(C,Y)>0 written next to the procyclical definition; Corr(Delta X, Y)<0 with annotation 'x crisis' next to the countercyclical definition.
- Slide 22 (TFP trend): top-of-slide handwritten header 'Medir de / Quitar tendencia de crecimiento de' and a reminder 'Recall ln(1+g) approx g'.
- Slide 23 (calibrating beta): handwritten annotation '(1+r)=(1+n)(1+n)' and 'beta Euler | son ortodoxo Datos reales -> beta', flagging that the beta formula comes from the steady-state Euler equation and is fed with real (not nominal) interest rate data.
- Slide 26 (calibrating gamma): handwritten derivation at the top, 'ln(l^(1-theta)) => w=(1-theta) y/n', re-deriving the wage/labor-demand relation used to back out gamma.

### Conexiones con otros temas

- Uses the same 'solve forward'/algebraic iteration mindset and Euler-equation apparatus that Topic 2.1 (Basic model, NotesDynMacroIITopic2.1.pdf) develops explicitly for the Natural Debt Limit and Transversality Condition
- McGrattan's (1994) fiscal-shocks extension is a direct precursor/companion to the Ricardian Equivalence discussion in Macro_Din_II_Topic2.1Government.pdf: McGrattan's taxes are distortionary (labor/capital income taxes), which is exactly the case where Ricardian equivalence (lump-sum taxes only) does NOT apply
- The K/theta/n Cobb-Douglas labor demand condition w_t=(1-theta) y_t/n_t derived here is the direct macro-theoretic analogue of the labor demand elasticity object central to the user's thesis on local labor market elasticities

---

## Fiscal Policy / Ricardian Equivalence -- Basic Model (pure endowment economy, no government, no production)

*Fuente: `Macro_Din_II_Topic2.1Basic.pdf`*

*Secciones: Basic model setup: infinite-horizon endowment economy, sequential budget constraint (1) | Endowment sequence assumptions and R*beta=1 | Two possible borrowing restrictions: b_{t+1}>=0 (no borrowing) vs. the Natural Debt Limit (NDL, Aiyagari 1994) | 'Solving Forward' technique and the Transversality Condition | Intuition for the NDL and for the Transversality Condition | Consumer's problem imposing no borrowing (Lagrangian, first-order conditions) | Modified Euler equation with multiplier mu_t; constrained vs. unconstrained cases | Perfect consumption smoothing result | Example 1: alternating endowment {y_h,y_l,...} starting high, b_0=0, unconstrained | Constructing the optimal bond-holding sequence (savings plan), formula (2) | Example 2: alternating endowment {y_l,y_h,...} starting low, constrained only in period 0 | Example 3: geometrically growing endowment y_t=lambda^t, always borrowing-constrained*

### Supuestos

> beta in (0,1)
>
> u(.) strictly increasing, strictly concave, twice differentiable
>
> Inada condition: lim_{c->0} u'(c) = +infinity
>
> No uncertainty in the economy
>
> Single risk-free asset with fixed gross return R>1
>
> {y_t} non-stochastic, y_t>=0, with sum beta^t y_t < infinity
>
> b_0 given exogenously
>
> R*beta=1 (key simplifying assumption throughout)
>
> Either b_{t+1}>=0 (no borrowing) OR the Natural Debt Limit b_{t+1}>=b-tilde_{t+1} is imposed (two alternative, not simultaneous, restrictions)
>
> No default risk
>

### Conceptos clave

- **Infinite-horizon endowment economy** - No production; households receive an exogenous non-stochastic endowment sequence {y_t} and can only smooth consumption via a single risk-free bond.
- **Inada condition** - lim_{c->0} u'(c) = +infinity, ensuring an interior consumption solution.
- **Single risk-free asset** - A bond b_{t+1} bearing a fixed gross one-period return R>1, with no default risk and no uncertainty in this basic version.
- **Natural Debt Limit (NDL)** - (Aiyagari 1994) The tightest possible borrowing limit: the largest debt a household could ever repay even by setting consumption to zero forever, equal to minus the present value of the entire future endowment stream.
- **'Solving forward'** - The technique of substituting the sequential budget constraint at t+1, t+2, ... successively into the constraint at t, to express b_t (or B_t for government) as a function of current and future variables.
- **Transversality Condition (TC)** - lim_{T->infinity} R^{-T} b_{t+T} = 0; economically, the discounted value of the terminal asset position must vanish, ruling out Ponzi schemes.
- **No-Ponzi-scheme condition** - Interpretation of the Transversality Condition: an agent cannot borrow forever, rolling over principal and interest, and never repay.
- **Perfect consumption smoothing** - Under R*beta=1 and no binding borrowing constraint, concavity of u(.) implies the Euler equation forces c_t=c_{t+1} for all t; the household holds a constant consumption plan pinned down by equating PV(income) to PV(consumption).
- **Present value of income/consumption, PV(y), PV(c)** - Discounted sums sum beta^t y_t and sum beta^t c_t used to pin down the constant consumption level under perfect smoothing.

### Teoremas, lemas y proposiciones

> **Perfect consumption smoothing result**
>
> If R*beta=1 and the no-borrowing (or NDL) constraint never binds (mu_t=0 for all t), then u'(c_t)=beta R u'(c_{t+1}) implies c_t=c_{t+1} for all t: the household holds constant consumption c-bar equal to the annuity value of its endowment stream, c-bar = (1-beta) * PV(y).
>
> *Supuestos requeridos:* strictly concave, strictly increasing, twice differentiable u(.); Inada condition; R*beta=1; no uncertainty; borrowing constraint (whichever form) never binds
>
> *Garantiza:* Whether or not the constraint binds depends entirely on the shape/timing of the income path {y_t}, as illustrated by Examples 1-3 (unconstrained, constrained only at t=0, and always constrained, respectively).

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Household objective | `\sum_{t=0}^{\infty}\beta^t u(c_t)` | Discounted lifetime utility from consumption only (no leisure/labor) | Endowment-economy consumer problem |
| Sequential budget constraint (1) | `c_t+\dfrac{b_{t+1}}{R} \le y_t+b_t` | Consumption plus new bond purchases cannot exceed endowment plus maturing bond value | Period-by-period resource constraint |
| Finite PV endowment condition | `\sum_{t=0}^{\infty}\beta^t y_t < \infty` | Technical condition ensuring the household's problem is well defined | Maintained assumption throughout |
| No-borrowing restriction | `c_t \le y_t+b_t-\tfrac{1}{R}b_{t+1}, \quad b_{t+1}\ge 0` | Households can lend but never borrow | First of the two alternative borrowing restrictions considered |
| Natural Debt Limit derivation | `\tilde b_t = -\sum_{j=0}^{\infty}R^{-j}y_{t+j} = -PV(y)` | Obtained by setting c_t=0 for all t and solving forward; the alternative constraint is b_{t+1}\ge \tilde b_{t+1}<0 | Second, looser borrowing restriction alternative to b_{t+1}\ge0 |
| Transversality Condition | `\lim_{T\to\infty} R^{-T}b_{t+T}=0` | Assumed limiting condition needed to close the forward-substitution derivation | Required to rule out Ponzi schemes / pin down a unique intertemporal budget constraint |
| Lagrangian of consumer's problem (no borrowing) | `\mathcal{L}=\sum_{t=0}^{\infty}\Big[\beta^t u(c_t)+\lambda_t\big(y_t+b_t-c_t-\tfrac{b_{t+1}}{R}\big)+\mu_t b_{t+1}\Big]` | lambda_t is the multiplier on the budget constraint (always strictly positive), mu_t on b_{t+1}\ge0 (Kuhn-Tucker) | Deriving optimality conditions under the no-borrowing restriction |
| Modified Euler equation | `u'(c_t) = \beta R\, u'(c_{t+1}) + \dfrac{R\mu_t}{\beta^t}` | Standard Euler equation augmented by the shadow value of the binding borrowing constraint | mu_t\ge0; if mu_t>0 (constraint binds, b_{t+1}=0) then u'(c_t)>\beta R\,u'(c_{t+1}), and with R\beta=1, c_t<c_{t+1}; if mu_t=0, c_t=c_{t+1} |
| Example 1: present value of alternating endowment | `PV(y)=\sum_{t=0}^{\infty}\beta^t y_t = \sum_{t=0}^{\infty}\beta^{2t}(y_h+\beta y_\ell) = \dfrac{y_h+\beta y_\ell}{1-\beta^2}` | Splitting the alternating sequence into 2-period blocks and summing a geometric series in beta^2 | Whenever the endowment alternates between two values with period 2 |
| Example 1: constant consumption level | `\dfrac{\bar c}{1-\beta} = \dfrac{y_h+\beta y_\ell}{1-\beta^2} \ \Rightarrow\ \bar c=\dfrac{y_h+\beta y_\ell}{1+\beta}` | Equating PV(c) to PV(y) under perfect smoothing, c_t=cbar for all t | Solving Example 1 for the level of consumption |
| Example 1: optimal bond-holding sequence (2) | `b_{t+1}=\begin{cases}\dfrac{y_h-y_\ell}{1+\beta} & t=0,2,4,\dots\\[4pt] 0 & t=1,3,5,\dots\end{cases}` | Consumer saves in high-income periods, decumulates in low-income periods, never binds the constraint | Constructing the implied savings plan once cbar is known |
| Multiplier recovery | `\mu_t=\beta^tR^{-1}u'(c_t)-\beta^{t+1}u'(c_{t+1})` | Backing out the Lagrange multiplier from the optimal consumption sequence via the Euler equation | Verifying mu_t=0 (unconstrained) in Example 1 |
| Example 3 growth condition | `1<\lambda<R, \quad \lambda\beta<1` | Endowment grows geometrically, y_t=\lambda^t, growth rate below R ensures PV(y) converges, but \lambda\beta<1 keeps the household wanting to bring income forward | Example 3: consumer is always borrowing-constrained, c_t=y_t=\lambda^t and b_{t+1}=0 \ \forall t |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Not applicable. This is a pure endowment economy with no production, no firm, and no labor/leisure choice; households only choose consumption c_t and bond holdings b_{t+1} each period.

### [COMPUT] Metodo computacional

Purely analytical: (i) the 'solving forward' iterative substitution technique to derive the Natural Debt Limit and the intertemporal budget constraint; (ii) Lagrangian/Kuhn-Tucker first-order-condition method to characterize the constrained optimum (Euler equation plus complementary slackness on the borrowing constraint); (iii) closed-form summation of geometric series to compute present values in Examples 1-3. No numerical, calibration, or simulation methods appear in this file.

### Intuicion general

The Natural Debt Limit says debt can never exceed the present value of all future income, since even driving consumption to zero forever cannot repay more than that. The Transversality Condition is the discrete-time no-Ponzi-scheme requirement: the discounted value of the household's terminal asset position must go to zero, otherwise the household could borrow without limit and never truly repay. Under R*beta=1 and no binding constraint, strict concavity of u(.) alone (not any particular functional form) is enough to force perfectly smoothed consumption; the level of that constant consumption plan is pinned down by a present-value budget-balance condition (PV(consumption)=PV(income)), exactly analogous to the permanent-income hypothesis. Whether the no-borrowing constraint actually binds depends purely on the shape of the income path: front-loaded income (Example 1) leaves the household wanting to save (never constrained); back-loaded income at first (Example 2) makes the household want to borrow in period 0 but it cannot, so c_0=y_0 exactly, after which behavior mirrors Example 1; and a permanently fast-growing income path (Example 3) makes the household always want to borrow against the future, so it is constrained in every single period (b_{t+1}=0 forever, c_t=y_t).

### Ejemplos y ejercicios

- Example 1: b_0=0, y_t={y_h,y_l,y_h,y_l,...} with y_h>y_l, constraint b_{t+1}>=0; consumer wants to save, never constrained, PV(y)=PV(c) gives cbar=(y_h+beta*y_l)/(1+beta), and the savings plan alternates between b_{t+1}=(y_h-y_l)/(1+beta) and 0
- Example 2: b_0=0, y_t={y_l,y_h,y_l,y_h,...} with y_h>y_l>0; optimal plan is c_0=y_l (constrained only in period 0), then follows the same pattern as Example 1 from period 1 onward
- Example 3: b_0=0, y_t=lambda^t with 1<lambda<R and lambda*beta<1; consumer is always borrowing-constrained, optimal plan is c_t=y_t=lambda^t and b_{t+1}=0 for all t

### Anotaciones a mano (tuyas)

- A small comment/speech-bubble icon appears on slide 4 next to 'Assume R*beta = 1', but no legible handwritten text accompanies it in the rendered slide.

### Conexiones con otros temas

- The 'solving forward' technique and the Transversality Condition derived here are reused directly in Macro_Din_II_Topic2.1Government.pdf to derive both the government's intertemporal budget constraint and the proof of the Ricardian Proposition
- NotesDynMacroIITopic2.1.pdf is the handwritten scratch-work for exactly this file's NDL derivation, Euler equation, and Example 1
- Shares the same log-type separable-utility / Euler-equation calibration logic used in the McGrattan (1994) RBC model of Topic 1, though this file has no production or labor -- pure consumption/savings problem

---

## Handwritten companion notes to Topic 2.1 Basic Model: step-by-step derivation of the Natural Debt Limit, the Euler equation with a borrowing-constraint multiplier, and the full worked solution of Example 1

*Fuente: `NotesDynMacroIITopic2.1.pdf`*

*Secciones: 1. How to construct the Natural Debt Limit (NDL) -- forward substitution of the sequential budget constraint | 2. Euler equation -- Lagrangian and first-order conditions | 3. Example 1 -- computing PV(y) via an even/odd geometric-series decomposition | 4. Constructing the sequence of bond holdings {b_t}*

### Supuestos

> R*beta=1 assumed when simplifying the Euler equation
>
> c_t=0 assumed (for all t) specifically to derive the tightest Natural Debt Limit bound -- not assumed to be optimal, just the worst-case repayment scenario
>
> Transversality Condition lim_{T->infinity} R^{-T} b_{t+T}=0 assumed (boxed in red) to close the forward-substitution derivation
>

### Conceptos clave

- **'Solving forward'** - Named explicitly in the notes as the operation of writing b_t as a function of future variables by successive substitution of the budget constraint (excluding the extra step of setting c_t=0).
- **Natural Debt Limit** - The tightest borrowing bound obtained by additionally imposing c_t=0 (zero consumption forever) on the solved-forward expression for b_t.
- **Transversality Condition** - The assumed limit condition lim_{T->infinity} R^{-T} b_{t+T}=0 (boxed in red in the notes) that closes the forward-substitution argument and turns an infinite recursive expression into the explicit present-value formula for b_t.
- **Lagrangian with two multipliers** - lambda_t on the sequential budget constraint, mu_t on the borrowing constraint b_{t+1}>=0; both enter the first-order conditions and combine into the modified Euler equation.
- **Even/odd geometric-series decomposition** - Trick for summing an alternating sequence (y_h,y_l,y_h,y_l,...): group into repeating 2-period blocks (y_h+beta*y_l), factor out a geometric series in beta^2, and solve 'Sum - beta^2*Sum = 1' for Sum=1/(1-beta^2).

### Teoremas, lemas y proposiciones

> **Natural Debt Limit derivation (worked algebra)**
>
> Iteratively substituting the sequential budget constraint c_t+b_{t+1}/R=y_t+b_t forward and imposing the Transversality Condition lim_{T->infinity}R^{-T}b_{t+T}=0 yields b_t=sum_{j=0}^infty R^{-j}(c_{t+j}-y_{t+j}). Setting c_t=0 for all t (the minimum feasible consumption) gives the tightest borrowing bound b-tilde_t = -sum_{j=0}^infty R^{-j}y_{t+j}, i.e., debt can never exceed the present value of the entire future endowment stream.
>
> *Supuestos requeridos:* Transversality Condition holds; c_t=0 is feasible (Inada-type condition rules out negative consumption, not that zero itself is optimal)
>
> *Garantiza:* Even with consumption driven to the lowest feasible level, the consumer cannot repay more than b-tilde_t; this is the loosest possible (Natural) debt limit.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Sequential budget constraint (starting point) | `c_t+\dfrac{b_{t+1}}{R}=y_t+b_t` | Base equation to be iterated forward | Starting point of the NDL derivation |
| First forward-substitution step | `b_t=c_t-y_t+\dfrac{c_{t+1}}{R}+\dfrac{b_{t+2}}{R^2}-\dfrac{y_{t+1}}{R}` | Result of substituting the period t+1 constraint into the period t constraint once | Illustrates the mechanics of 'solving forward' before generalizing |
| General forward solution (after invoking TC) | `b_t=\sum_{j=0}^{\infty}R^{-j}(c_{t+j}-y_{t+j})` | Closed-form present-value expression for b_t once the boxed Transversality term vanishes | Intertemporal budget constraint of the household |
| Natural Debt Limit | `\tilde b_t=-\sum_{j=0}^{\infty}R^{-j}y_{t+j}` | Obtained by setting c_t=0 for all t in the general forward solution | Tightest feasible borrowing limit |
| Lagrangian | `\mathcal L=\sum_{t=0}^{\infty}\Big(\beta^t u(c_t)+\lambda_t(y_t+b_t-c_t-\tfrac{b_{t+1}}{R})+\mu_t b_{t+1}\Big)` | Constrained optimization setup for the household's problem under the no-borrowing restriction | Deriving the Euler equation with a borrowing-constraint multiplier |
| FOC w.r.t. c_t | `\beta^t u'(c_t)-\lambda_t=0` | Marginal utility of consumption equals the shadow price of resources | Step toward the Euler equation |
| FOC w.r.t. b_{t+1} | `-\dfrac{\lambda_t}{R}+\lambda_{t+1}+\mu_t=0` | Marginal cost of saving equals its discounted marginal benefit plus the shadow value of relaxing the borrowing constraint | Step toward the Euler equation |
| Euler equation (with multiplier) | `u'(c_t)=\beta R\,u'(c_{t+1})+\dfrac{\mu_t R}{\beta^t}` | Combining the two FOCs; reduces to the standard Euler equation under R\beta=1 when \mu_t=0: u'(c_t)=u'(c_{t+1})+\dfrac{\mu_t R}{\beta^t} | Characterizing optimal consumption with a possibly-binding borrowing constraint |
| Example 1: PV(y) via even/odd split | `PV(y)=y_h+\beta y_\ell+\beta^2 y_h+\dots=(y_h+\beta y_\ell)(1+\beta^2+\beta^4+\dots)=\dfrac{y_h+\beta y_\ell}{1-\beta^2}` | Sum-\beta^2 Sum = 1 telescoping trick applied to Sum=1+\beta^2+\beta^4+\dots | Computing present value of a 2-period alternating endowment sequence |
| Bond sequence recursion (Example 1) | `c_0+\dfrac{b_1}{R}=y_0+b_0; \quad \bar c+\dfrac{b_1}{R}=y_h+0 \Rightarrow b_1=R(y_h-\bar c); \quad c_1+\dfrac{b_2}{R}=y_1+b_1 \Rightarrow \bar c+\dfrac{b_2}{R}=y_\ell+b_1` | Period-by-period recursive construction of the optimal bond-holding sequence once cbar is known | Building the explicit savings plan {b_t} implementing the optimal constant-consumption plan |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Not applicable -- pure endowment economy; no labor or production appears anywhere in these notes.

### [COMPUT] Metodo computacional

'Solving forward' (iterative substitution) technique, worked out step by step by hand; Lagrangian method for constrained optimization (two multipliers, complementary slackness implied for mu_t); geometric-series summation technique (even/odd decomposition) to compute present values in Example 1. No numerical or software methods.

### Intuicion general

This file is the scratch-work behind the printed Basic-model slides: it shows mechanically how 'solving forward' works (substitute the t+1 constraint into the t constraint, repeat, and take a limit), why the Natural Debt Limit specifically uses c_t=0 (it is the absolute loosest borrowing bound achievable, since the consumer literally cannot repay more than that even by starving), and how the Lagrange multiplier mu_t on the no-borrowing constraint modifies the standard Euler equation -- mu_t is strictly positive exactly when the household is currently borrowing-constrained.

### Ejemplos y ejercicios

- Worked computation of PV(y) for an alternating endowment sequence {y_h,y_l,y_h,y_l,...} using the even/odd geometric-series decomposition trick (grouping into a repeating 2-period block and solving Sum - beta^2*Sum = 1)

### Anotaciones a mano (tuyas)

- Page 1: circled step number (1) labels the section 'How to construct the Natural Debt Limit (NDL)'; steps are numbered (1) through (7) in the margin tracking each substitution.
- Page 1: the recursive term is boxed in red just before the note 'Look at term in red: Assume lim_{T->infinity} R^{-T} b_{t+T}=0. This is a Transversality Condition.' -- the critical assumption is explicitly flagged in red ink.
- Page 2: bracketed self-authored gloss: '[The operation we did (excluding setting c_t=0) is called "to solve forward" for b_t]', defining the technique in the student's own words.
- Page 2: note 'Even with very low consumption, c_t=0, the consumer cannot repay more than b-tilde_t' as an interpretive summary of the NDL result.
- Pages 3-5: circled numbers (2), (3), (4) mark the Euler equation, Example 1, and the bond-holdings construction sections respectively; small hat/caret marks and circled sub-steps track substitution order in the Example 1 derivation.

### Conexiones con otros temas

- Direct handwritten derivation underlying slides 5-6, 8-9, and 11-13 of Macro_Din_II_Topic2.1Basic.pdf -- matches the printed formulas for the NDL, the Transversality Condition, the Euler equation with multiplier, and Example 1's closed-form cbar and PV(y)
- Plays the same 'worked scratch-paper' role for the Basic model that NotesMacroDynIITopic2.1Gov.pdf plays for the Government model's Ricardian Proposition proof (Step 4)

---

## Fiscal Policy / Ricardian Equivalence -- Model with Government (formal statement and proof of the Ricardian Proposition)

*Fuente: `Macro_Din_II_Topic2.1Government.pdf`*

*Secciones: Model with government: purchases {g_t}, lump-sum taxes {tau_t}, government sequential budget constraint | Solving forward for B_t: the government's intertemporal budget constraint | Changes to the consumer's problem: budget constraint with taxes, new Natural Debt Limit using disposable income | Definition of equilibrium (consumer optimization + government budget balance) | Ricardian Equivalence: does the timing of taxes matter? | The Ricardian Proposition (formal statement) | Proof, Step 1: household's optimal consumption plan depends only on the present value of taxes | Proof, Step 2: constructing the adjusted borrowing plan b-bar_t | Proof, Step 3: showing the new debt sequence satisfies the Natural Debt Limit | Proof, Step 4: showing the Transversality Condition holds for the adjusted sequence (solve backward) | Proof, Step 5: showing the government still satisfies its budget constraint under the new tax plan*

### Supuestos

> Government purchases g_t do not enter the household's utility and are not productive (not public investment)
>
> Taxes tau_t are lump-sum (not distortionary) -- essential for Ricardian equivalence
>
> Sign convention: B_t>0 denotes public debt (opposite convention from the household's b_t)
>
> Equilibrium requires (1) household optimization given taxes and (2) government budget balance every period, given (b_0,B_0)
>
> Natural Debt Limit imposed on the household (carried from the Basic model)
>
> Alternative tax sequence {tau-bar_t} must have identical present value to {tau_t} for Ricardian equivalence to hold
>
> No uncertainty, no default risk (carried over from the Basic model)
>

### Conceptos clave

- **Government debt B_t** - One-period debt outstanding at t, denominated in consumption goods; B_t>0 means the government is a net debtor (sign convention opposite to the household's bond holdings b_t).
- **Lump-sum tax tau_t** - A tax levied on the household that does not depend on any economic choice (not distortionary); the necessary condition for Ricardian equivalence to hold.
- **Non-productive government purchases g_t** - Government spending stream that does not enter the household's utility function and is not productive (e.g., not public investment).
- **Equilibrium** - A plan for the consumer {c_t,b_{t+1}} and a government policy {g_t,tau_t,B_{t+1}} such that, given initial conditions (b_0,B_0): (1) the consumer solves her problem given the tax sequence, and (2) the government satisfies its budget constraint every period.
- **Ricardian Equivalence** - The proposition that the timing of lump-sum taxes (financed by adjusting government debt) is irrelevant for the household's consumption plan and for the equilibrium, as long as the present value of taxes is unchanged -- because the household perceives current debt-financed tax cuts as future tax liabilities.
- **Disposable income** - y_t - tau_t; income net of lump-sum taxes, the relevant resource in the household's (new) Natural Debt Limit.

### Teoremas, lemas y proposiciones

> **Ricardian Proposition**
>
> Suppose the Natural Debt Limit is imposed. Given initial conditions (b_0,B_0), let {c_t,b_{t+1}} and {g_t,tau_t,B_{t+1}} be an equilibrium. Consider any other tax sequence {tau-bar_t} such that sum_{t=0}^infty R^{-t} tau_t = sum_{t=0}^infty R^{-t} tau-bar_t (same present value). Then {c_t, b-bar_{t+1}} and {g_t, tau-bar_t, B-bar_{t+1}} also constitute an equilibrium, where b-bar_t=sum_{j=0}^infty R^{-j}(c_{t+j}+tau-bar_{t+j}-y_{t+j}) and B-bar_t=sum_{j=0}^infty R^{-j}(tau-bar_{t+j}-g_{t+j}).
>
> *Supuestos requeridos:* Natural Debt Limit imposed on the household; same government expenditure path {g_t}; alternative tax sequence has identical present value to the original; no uncertainty, no default risk, single bond market (carried over from the Basic model); taxes are purely lump-sum (not distortionary)
>
> *Garantiza:* Proved in 5 steps: (1) household's optimal consumption is unchanged because it depends on taxes only through their present value (via the solved-forward budget constraint for b_0); (2)-(3) the adjusted borrowing sequence b-bar_t is constructed and shown to satisfy the Natural Debt Limit (since consumption stays non-negative); (4) the adjusted sequence is shown to satisfy the Transversality Condition, by solving backward and taking k to infinity, using that the original sequence satisfies TC and that the tax sequences have equal present value; (5) the government's budget constraint at t=0 depends only on the present value of taxes, so it can finance the same {g_t} plan. QED.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Government sequential budget constraint | `B_t+g_t = \tau_t+\dfrac{B_{t+1}}{R}` | Government debt plus spending financed by current taxes and new borrowing | Period-by-period government resource constraint |
| Government intertemporal budget constraint | `B_t=\sum_{j=0}^{\infty}R^{-j}(\tau_{t+j}-g_{t+j})` | Obtained by solving forward and imposing the Transversality Condition \lim_{T\to\infty}R^{-T}B_{t+T}=0 | Government's present-value budget constraint |
| Consumer's modified sequential budget constraint | `c_t+\dfrac{b_{t+1}}{R}\le y_t+b_t-\tau_t` | Household resource constraint net of lump-sum taxes | Consumer's problem once a government/tax sequence is introduced |
| Consumer's intertemporal constraint (solve forward) | `b_t=\sum_{j=0}^{\infty}R^{-j}(c_{t+j}+\tau_{t+j}-y_{t+j})` | Present-value form of the household budget constraint including taxes | Building block for the Ricardian Proposition proof, Step 1 |
| New Natural Debt Limit (disposable income) | `\tilde b_t=-\sum_{j=0}^{\infty}R^{-j}(y_{t+j}-\tau_{t+j})` | Household can never borrow more than the present value of its disposable (after-tax) income | Borrowing limit once taxes are present |
| Equal-present-value tax condition | `\sum_{t=0}^{\infty}R^{-t}\tau_t=\sum_{t=0}^{\infty}R^{-t}\bar\tau_t` | Definition of a Ricardian-equivalent alternative tax sequence | Hypothesis of the Ricardian Proposition |
| Adjusted debt sequences | `\bar b_t=\sum_{j=0}^{\infty}R^{-j}(c_{t+j}+\bar\tau_{t+j}-y_{t+j}), \qquad \bar B_t=\sum_{j=0}^{\infty}R^{-j}(\bar\tau_{t+j}-g_{t+j})` | New equilibrium bond/debt levels implied by keeping the same {c_t},{g_t} but using the alternative tax sequence | Constructed in Step 2 of the proof |
| Step 1: solve forward for b_0 | `b_0=\sum_{t=0}^{\infty}R^{-t}(c_t-y_t)+\sum_{t=0}^{\infty}R^{-t}\tau_t` | Shows the optimal consumption plan depends on the tax sequence only through its present value | Core step establishing that consumption is unaffected by tax timing |
| Step 3: NDL check | `\bar b_t=\sum_{j=0}^{\infty}R^{-j}(c_{t+j}+\bar\tau_{t+j}-y_{t+j}) \ge \tilde b_t=-\sum_{j=0}^{\infty}R^{-j}(y_{t+j}-\bar\tau_{t+j})` | Holds automatically because the consumption stream {c_t} is non-negative | Verifying the adjusted sequence respects the Natural Debt Limit |
| Step 4: solve backward for b-bar_k | `\bar b_k=\sum_{j=1}^{k}R^{j}\big[y_{k-j}-\bar\tau_{k-j}-c_{k-j}\big]+R^{k}b_0` | Backward substitution (from period k down to 0) of the sequential budget constraint | Needed to compare b_k and b-bar_k directly since both share the same b_0 |
| Step 4: difference equation | `b_k-\bar b_k=\sum_{j=1}^{k}R^{j}\big[\bar\tau_{k-j}-\tau_{k-j}\big]` | Difference between original and adjusted debt at k depends only on discounted tax differences | Core algebraic step of Step 4 |
| Step 4: rescaled difference | `R^{1-k}(b_k-\bar b_k)=R\sum_{t=0}^{k-1}R^{-t}\big[\bar\tau_t-\tau_t\big]` | As k\to\infty, since \{b_{t+1}\} satisfies the Transversality Condition and the tax sequences have equal present value, \{\bar b_{t+1}\} must too | Concludes Step 4 of the proof |
| Step 5: government budget solved forward at t=0 | `B_0=\sum_{t=0}^{\infty}R^{-t}\tau_t-\sum_{t=0}^{\infty}R^{-t}g_t` | Government's initial debt depends on taxes and spending only through present values | Shows unchanged present value of taxes finances the identical {g_t} plan |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Not applicable. Like the Basic model, this is an endowment/no-production economy; households only choose consumption and bond holdings, and taxes are lump-sum (not levied on labor or capital income), so there is no labor-supply or labor-demand margin in this file.

### [POLICY] Instrumentos de politica

- g_t: exogenous government purchases, does not enter utility, appears in the government budget constraint B_t+g_t=tau_t+B_{t+1}/R
- tau_t: lump-sum tax on the household, appears in both the government budget constraint and (subtracted from disposable income) in the consumer's budget constraint c_t+b_{t+1}/R<=y_t+b_t-tau_t
- B_t: one-period government debt outstanding at t (B_t>0 = government is net debtor; opposite sign convention to household bond holdings b_t)
- R: common gross risk-free interest rate faced by both the household and the government (single bond market)
- No distortionary taxes, subsidies, or monetary instruments appear -- taxes are strictly lump-sum, the key condition needed for the Ricardian Proposition

### [COMPUT] Metodo computacional

Purely analytical/proof-based: 'solving forward' and 'solving backward' algebraic substitution techniques to derive intertemporal budget constraints for both the government and the household; the Transversality Condition applied as a limiting argument (k -> infinity); a constructive proof technique (build an alternative bond-holding sequence and verify it satisfies the budget constraint, the Natural Debt Limit, and the Transversality Condition). No numerical, simulation, or calibration methods appear.

### Intuicion general

Ricardian Equivalence hinges on the fact that only the present value of taxes -- not their timing -- enters the household's intertemporal budget constraint (Step 1): a tax cut financed by more government debt today, offset by higher taxes tomorrow, leaves the household's lifetime budget set unchanged, so a rational, forward-looking household with access to the same borrowing/lending technology as the government simply adjusts its own asset holdings to exactly offset the government's, and consumption is unaffected. The proof is a two-fold reapplication of the 'solving forward' / 'solving backward' / Transversality-Condition machinery built in the Basic model: once to show the household's plan is invariant (Steps 1-4), and once to show the government's budget still balances (Step 5). The subtlety is Step 4, which needs to solve BACKWARD (not forward) to directly compare the original and adjusted debt sequences at a finite horizon k and then take a limit, exploiting that the two tax sequences have the same present value so their discounted difference vanishes appropriately.

### Anotaciones a mano (tuyas)

- Slide 9 (Proof, Step 1): handwritten line at the bottom of the slide re-deriving the budget constraint algebra by hand, roughly 'c+b<=y+(1+r)b => c+b'/(1+r)<=y+b', confirming the rearrangement used to go from the per-period constraint to the solved-forward form.

### Conexiones con otros temas

- Direct sequel to Macro_Din_II_Topic2.1Basic.pdf: reuses that file's Natural Debt Limit construction and Transversality Condition (solved both forward and backward) essentially unchanged
- The handwritten backward-solving algebra of Proof Step 4 is worked out in full in NotesMacroDynIITopic2.1Gov.pdf
- Establishes the theoretical debt-neutrality benchmark against which McGrattan's (1994) fiscal RBC extension (Topic 1) is a deviation: McGrattan uses distortionary capital/labor income taxes (tau_k, tau_n), not lump-sum taxes, so Ricardian equivalence does NOT apply there -- exactly the condition (lump-sum-only taxation) required by this file's proposition

---

## Handwritten companion notes to Topic 2.1 Government: full worked derivation of Step 4 in the proof of the Ricardian Proposition (extending the Transversality Condition from the original to the adjusted debt sequence)

*Fuente: `NotesMacroDynIITopic2.1Gov.pdf`*

*Secciones: 1. Solve backward for b_k / b-bar_k using disposable income y-hat_t = y_t - tau_t | 2. Finishing the proof: the difference equation b_k - b-bar_k and its behavior as k -> infinity*

### Supuestos

> b_0 is identical and exogenous across the original and the adjusted asset sequences (carried from Step 3 of the printed proof)
>
> The original {tau_t} and the alternative {tau-bar_t} have equal present value (the defining hypothesis of the Ricardian Proposition)
>

### Conceptos clave

- **Disposable income y-hat_t** - Boxed definition y-hat_t = y_t - tau_t, the endowment net of the (original) lump-sum tax, used as the effective resource in the backward-solved budget identity.
- **'Solving backward'** - The complementary technique to 'solving forward': starting from a known b_0, iterate the sequential budget constraint forward in index but expressed to isolate b_k at a fixed future date k, i.e., express b_k in terms of b_0 and the discounted history y_{k-j}-tau_{k-j}-c_{k-j} for j=1,...,k.
- **Telescoping tax-difference sum** - The discounted sum sum_{t=0}^{k-1} R^{-t}(tau-bar_t - tau_t), which is a partial sum of a series whose infinite sum is zero because the two tax sequences share the same present value; this is what lets the Transversality Condition transfer from the original to the adjusted debt sequence.

### Teoremas, lemas y proposiciones

> **Step 4 of the Ricardian Proposition proof (Transversality transfer)**
>
> If the original bond sequence {b_{t+1}} satisfies the Transversality Condition, and the alternative tax sequence {tau-bar_t} has the same present value as {tau_t}, then the adjusted bond sequence {b-bar_{t+1}} also satisfies the Transversality Condition, because R^{1-k}(b_k - b-bar_k) = R * sum_{t=0}^{k-1} R^{-t}(tau-bar_t - tau_t), and the right-hand side is a partial sum converging to zero as k -> infinity (since the full infinite sum of discounted tax differences is zero by the equal-present-value hypothesis).
>
> *Supuestos requeridos:* b_0 is identical and exogenous in both the original and the adjusted asset sequences; original {tau_t} and alternative {tau-bar_t} have equal present value; the original sequence {b_{t+1}} already satisfies the Transversality Condition (carried from Step 3/earlier equilibrium)
>
> *Garantiza:* Closes the equivalence argument on the household side: the adjusted debt sequence is a valid equilibrium object (satisfies both the Natural Debt Limit, shown in Step 3, and now the Transversality Condition), so consumption is unaffected by the change in tax timing.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Disposable income definition | `\hat y_t = y_t-\tau_t` | Endowment net of the original lump-sum tax | Substituted into the backward-solved budget identity |
| Backward recursion base step | `c_{k-1}+\dfrac{b_k}{R}=\hat y_{k-1}+\bar b_{k-1} \ \Rightarrow\ b_k=R(\hat y_{k-1}-c_{k-1}+\bar b_{k-1})` | Isolating b_k from the constraint at period k-1 | First step of solving backward from a fixed horizon k |
| Iterated backward solution | `b_k=\sum_{j=1}^{k}R^{j}(\hat y_{k-j}-c_{k-j})+R^{k}b_0=\sum_{j=1}^{k}R^{j}(y_{k-j}-\tau_{k-j}-c_{k-j})+R^{k}b_0` | Closed-form expression for b_k (or b-bar_k under the alternative tax plan) purely in terms of b_0 and the history of disposable income minus consumption | Comparing the original and adjusted debt levels at a common finite horizon k |
| Difference of debt sequences | `b_k-\bar b_k=\sum_{j=1}^{k}R^{j}(\bar\tau_{k-j}-\tau_{k-j})` | Because b_0 and {c_t} are identical across the two plans, the entire difference collapses to discounted tax differences | Core simplification enabling the limiting argument |
| Rescaled difference | `R^{1-k}(b_k-\bar b_k)=R\sum_{t=0}^{k-1}R^{-t}(\bar\tau_t-\tau_t)` | Re-indexing and rescaling the previous formula into a form directly comparable to the Transversality Condition's R^{-T}b_{t+T} object | Final step before concluding via k -> infinity that Transversality transfers from b to b-bar |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Not applicable -- no labor or production; same endowment-economy-with-lump-sum-taxes structure as the printed Government file.

### [POLICY] Instrumentos de politica

- tau_t: original lump-sum tax sequence, embedded in the disposable-income term y-hat_t = y_t - tau_t
- tau-bar_t: alternative lump-sum tax sequence with identical present value to tau_t -- the object of the Ricardian equivalence argument
- y-hat_t = y_t - tau_t: disposable income, the effective endowment net of taxes entering the backward-solved budget identity

### [COMPUT] Metodo computacional

'Solving backward' (iterative backward substitution of the sequential budget constraint from a fixed future period k down to period 0), presented as the explicit complement to the 'solving forward' technique used elsewhere; a telescoping-sum / limit argument to establish convergence and thereby verify the Transversality Condition for the adjusted debt sequence. No numerical or software methods.

### Intuicion general

This page is the 'engine room' behind Step 4 of the Ricardian Proposition proof: to show the alternative bond sequence b-bar_t also satisfies the Transversality Condition, the student solves BACKWARD (from a fixed future date k down to the known initial b_0) rather than forward, which directly relates b_k and b-bar_k to the accumulated discounted difference between the alternative and original tax sequences. Because the alternative tax sequence was constructed to have exactly the same present value as the original, this discounted difference is precisely a partial sum of a series that sums to zero overall -- so it stays appropriately bounded/vanishing as k grows, which is exactly what is needed to transfer the Transversality Condition from the known-good original sequence {b_t} to the new one {b-bar_t}. This closes the household side of the equivalence argument: the government can finance the identical expenditure plan with any tax timing that preserves the present value of taxes, without disturbing any equilibrium condition.

### Anotaciones a mano (tuyas)

- Page 1: circled step marker (1) labels 'To solve backward for b-bar_k'; the definition y-hat_t = y_t - tau_t is boxed and highlighted in pink ink to flag it as the key substitution.
- Page 1: small pencil numbering '1, 2' next to the budget constraint terms, apparently indicating which term corresponds to which time subscript during the backward substitution.
- Page 2: circled step marker (2) labels 'Finishing the proof', separating the backward-solution algebra from the limiting argument.
- Page 3: closing freehand remark 'Then you can show that b-bar satisfies Transversality', written as the informal conclusion tying back to the printed slide's earlier deferred claim ('we will prove it later').

### Conexiones con otros temas

- This is the handwritten derivation underlying slides 12-13 of Macro_Din_II_Topic2.1Government.pdf ('Step 4: show that Transversality Condition holds'), filling in the algebra that the printed slide leaves compressed
- Plays the same role for the Government file that NotesDynMacroIITopic2.1.pdf plays for the Basic model file -- worked scratch algebra behind compressed slide bullets
- Explicitly introduces and uses 'solving backward' as the technique complementary to the 'solving forward' technique introduced in the Basic model notes (NotesDynMacroIITopic2.1.pdf)

---

## Fiscal Policies in the Growth Model — First Part: non-stochastic one-sector growth model with distortionary taxes (tau_c, tau_k, tau_n, tau_h) and an investment subsidy (tau_i) plus exogenous government spending g; defines a price system, a Budget Feasible Fiscal Policy, and a Competitive Equilibrium with Distortionary Taxes (CEDT); derives government and consumer intertemporal budget constraints, the No-Arbitrage Condition, the Transversality Condition, and the User Cost of Capital; ends by deriving the second-order difference equation for capital under exogenous (inelastic) labor supply.

*Fuente: `Macro_Din_II_Topic2.2FirstPartFINALVERSION.pdf`*

*Secciones: Objective | Model (primitives) | Competitive equilibrium (timing / Arrow-Debreu equivalence) | Definition: Price system | Definition: Budget Feasible Fiscal Policy (BFFP) | Government's intertemporal budget constraint | Consumer's intertemporal budget constraint | Household's and firm's problems | Equilibrium: Definition of CEDT | Two formulas: no-arbitrage rewriting of household budget constraint | No Arbitrage Condition (NAC) | Transversality Condition (TVC) | User Cost of Capital (UCC) | Effects of exogenous variables on UCC | Choices of consumer (household FOCs) | Choices of the firm (Euler's theorem, zero profit) | Solving the model (system to be solved) | A particular case: exogenous labor supply | Obtaining a second-order difference equation for capital*

### Supuestos

> Model is non-stochastic (perfect foresight).
>
> Taxes are distorting: tau_c (consumption), tau_k (capital earnings), tau_n (labor earnings), tau_h (lump-sum), and a subsidy tau_i on investment, all exogenous sequences.
>
> Government spending {g_t} is exogenous.
>
> U(c,1-n) is strictly increasing in both arguments, twice continuously differentiable, and strictly concave.
>
> F(k,n) is homogeneous of degree one with positive and decreasing marginal products of capital and labor.
>
> Initial government assets are zero when constructing the government's intertemporal budget constraint.
>
> All trades take place at t=0 (equivalent to sequential trading; Arrow-Debreu under uncertainty).
>
> Free entry among firms (zero-profit condition).
>
> Households can short-sell capital (borrow it), invoked in deriving the NAC.
>
> In the particular case: labor supply is exogenous/inelastic, n_t=1 for all t.
>

### Conceptos clave

- **Distorting taxes** - Taxes that break the equivalence between the competitive equilibrium and the Planner's Problem, so the First Welfare Theorem fails; the model must be solved as a Competitive Equilibrium directly rather than via a planner's problem.
- **Price system** - A triple of sequences {q_t, r_t, w_t}: q_t is the time-0 pretax price of one unit of investment/consumption at t; r_t and w_t are analogous time-0 (intertemporal) prices of a unit of capital and of labor. All trades are assumed to take place at t=0, equivalent to sequential trading under certainty (would be Arrow-Debreu equilibrium under uncertainty).
- **Budget Feasible Fiscal Policy (BFFP)** - A sequence of government spending, taxes, and the investment subsidy that satisfies the government's intertemporal budget constraint. The set of competitive equilibria is indexed by alternative BFFPs.
- **Competitive Equilibrium with Distortionary Taxes (CEDT)** - A budget-feasible government policy, a feasible allocation for the consumer, and a price system such that, given the price system and government policy, the allocation solves both the household's and the firm's problems.
- **No Arbitrage Condition (NAC)** - For all t>=1, the bracketed term multiplying k_t in the rearranged household budget constraint must equal zero; otherwise the consumer could earn unbounded profit buying capital cheap in t-1 and selling expensive in t, or the reverse via short-selling.
- **Transversality Condition (TVC)** - lim_{T->infinity} (1-tau_iT) q_T k_{T+1} = 0; rules out holding positive capital forever (wasteful) or negative capital forever (unfinanceable as T grows).
- **User Cost of Capital (UCC)** - A one-period-forward rewriting of the NAC expressing r_{t+1} as the cost of owning (rather than selling) a unit of capital -- what a firm gives up by keeping a plant instead of selling it.

### Teoremas, lemas y proposiciones

> **Euler's theorem on homogeneous functions of degree one (applied to the firm's problem)**
>
> For F(k,n) homogeneous of degree one, F(k,n) = F_k(k,n) k + F_n(k,n) n.
>
> *Supuestos requeridos:* F is homogeneous of degree one; F has positive and decreasing marginal products of capital and labor
>
> *Garantiza:* The firm's discounted profit sum sum_t [q_t F(k_t,n_t) - r_t k_t - w_t n_t] can be rewritten as sum_t [(q_t F_kt - r_t) k_t - (q_t F_lt - w_t) n_t]; with free entry, zero profit requires each bracket to vanish termwise, giving r_t = q_t F_kt and w_t = q_t F_nt.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Utility function | `\sum_{t=0}^{\infty}\beta^t U(c_t,1-n_t),\quad 0<\beta<1` | Lifetime utility over consumption and leisure; U strictly increasing in both arguments, twice continuously differentiable, strictly concave. | Household's objective function. |
| Production function | `y_t = F(k_t,n_t)` | Homogeneous of degree one, positive and decreasing marginal products of capital and labor. | Firm's technology; basis for factor prices via Euler's theorem. |
| Law of motion for capital | `k_{t+1} = (1-\delta)k_t + x_t` | Capital accumulates from gross investment x_t net of depreciation delta. | Defines feasible allocations. |
| Feasibility condition | `y_t = c_t + x_t + g_t` | Output splits between private consumption, investment, and government purchases. | Resource constraint; used to build both intertemporal budget constraints and the final second-order difference equation. |
| Government's intertemporal budget constraint | `\sum_{t=0}^{\infty} q_t g_t \le \sum_{t=0}^{\infty}\{\tau_{ct}q_tc_t - \tau_{it}q_t[k_{t+1}-(1-\delta)k_t] + r_t\tau_{kt}k_t + w_t\tau_{nt}n_t + q_t\tau_{ht}\}` | Present value of government purchases cannot exceed present value of net tax/subsidy revenue. | Defines BFFP; constructed assuming zero initial government assets and imposing a transversality condition. |
| Consumer's intertemporal budget constraint | `\sum_{t=0}^{\infty}\{q_t(1+\tau_{ct})c_t + (1-\tau_{it})q_t[k_{t+1}-(1-\delta)k_t]\} \le \sum_{t=0}^{\infty}\{r_t(1-\tau_{kt})k_t + w_t(1-\tau_{nt})n_t - q_t\tau_{ht}\}` | Present value of after-tax consumption plus after-subsidy net investment cannot exceed present value of after-tax factor income minus lump-sum taxes. | Household's constraint in the utility-maximization problem. |
| Firm's problem | `\max_{\{k_t,n_t\}_{t=0}^{\infty}} \sum_{t=0}^{\infty}[q_tF(k_t,n_t) - r_tk_t - w_tn_t]` | Firm chooses capital and labor sequences to maximize present-value profit given the price system. | Yields zero-profit / factor-price conditions via Euler's theorem. |
| Household FOCs | `\beta^t U_{1t} = \mu q_t(1+\tau_{ct}), \qquad \beta^t U_{2t} = \mu w_t(1-\tau_{nt})` | Marginal utility of consumption (leisure) equated to multiplier mu times the after-tax price of consumption (after-tax wage). | Household's first-order conditions from maximizing intertemporal utility subject to its unique intertemporal constraint (multiplier mu). |
| Zero profit conditions | `r_t = q_tF_{kt}, \qquad w_t = q_tF_{nt}` | With free entry and constant-returns technology, factor prices equal the value of marginal products. | Firm's optimality conditions. |
| No Arbitrage Condition (NAC) | `r_t(1-\tau_{kt}) + (1-\tau_{it})q_t(1-\delta) - q_{t-1}(1-\tau_{it-1}) = 0,\quad t\ge1` | Equates the after-tax return from holding capital one period to its after-tax purchase price the previous period; prevents arbitrage. | Derived by collecting k_t terms in the household budget constraint; core equilibrium condition. |
| Transversality Condition | `\lim_{T\to\infty}(1-\tau_{iT})q_Tk_{T+1} = 0` | Present value of the terminal capital stock (net of investment subsidy) must vanish asymptotically. | Terminal condition (with initial k_0) needed to solve the difference-equation system; q_t is linked to marginal utility of consumption. |
| User Cost of Capital (UCC) | `r_{t+1} = \left(\frac{1}{1-\tau_{k,t+1}}\right)\left[q_t(1-\tau_{it}) - q_{t+1}(1-\tau_{i,t+1}) + \delta q_{t+1}(1-\tau_{i,t+1})\right]` | One-period-forward rewriting of the NAC giving the cost of owning (not selling) one unit of capital for one more period, as a function of taxes/subsidy, depreciation, and prices. | Comparative statics: effects of tau_k, delta, q, and tau_i on the cost of capital (e.g., a firm deciding whether to keep or sell a plant). |
| Particular case: exogenous labor (n=1) | `U(c,1-n)=u(c),\; n=1;\quad f(k)=F(k,1);\quad F_k=f'(k),\; F_n=f(k)-f'(k)k;\quad f(k_t)=c_t+g_t+k_{t+1}-(1-\delta)k_t` | Simplification with inelastic labor supply reduces the model to a single control (consumption/capital) using intensive-form production. | Setting up the second-order difference equation when the labor margin is shut down. |
| Second-order nonlinear difference equation for capital | `u'(c_t) = \beta u'(c_{t+1})\frac{1+\tau_{ct}}{1+\tau_{ct+1}}\left[\frac{1-\tau_{k,t+1}}{1-\tau_{it}}f'(k_{t+1}) + \frac{1-\tau_{i,t+1}}{1-\tau_{it}}(1-\delta)\right]` | Euler equation with prices substituted out (using q_t = beta^t u'(c_t) / [mu(1+tau_ct)]) and consumption replaced via feasibility, yielding a second-order difference equation purely in k_t, k_{t+1}, k_{t+2}. | Core equation solved numerically (via shooting, developed in Part 2) given k_0 and the transversality condition as boundary conditions. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Part 1 keeps the production function fully general: F(k,n), homogeneous of degree one with positive and decreasing marginal products (no explicit Cobb-Douglas or CES form given). Labor demand emerges from the firm's zero-profit condition via Euler's theorem: w_t = q_t F_nt (wage equals price times marginal product of labor); since F is only assumed homogeneous of degree 1 here, the curvature of labor demand is whatever curvature F_nn has -- it is not pinned down numerically in this file. Utility is general U(c_t,1-n_t) (strictly increasing, strictly concave, twice differentiable) -- not GHH, not explicitly separable/CES in leisure; no Frisch elasticity is derived. The household's labor-supply FOC is beta^t U_2t = mu w_t (1-tau_nt), so combined with the consumption FOC, labor supply satisfies U_2t/U_1t = w_t(1-tau_nt) / [q_t(1+tau_ct)], i.e. MRS(leisure,consumption) equals the after-tax wage relative to the after-tax consumption price. However, the 'particular case' used to derive the tractable second-order difference equation SHUTS DOWN the labor margin entirely: U(c,1-n)=u(c) with n=1 fixed, i.e. inelastic labor supply, Frisch elasticity = 0 by construction. No curvature parameter (alpha, elasticity of substitution) for capital-labor substitution is specified in Part 1; F is left generic.

### [POLICY] Instrumentos de politica

- g_t -- government purchases/spending (exogenous sequence); enters feasibility y_t=c_t+x_t+g_t and the government's IBC.
- tau_ct -- consumption tax; enters consumer IBC as q_t(1+tau_ct)c_t, household FOC beta^t U_1t = mu q_t(1+tau_ct), and the pricing equations (q_t, R_{t+1}).
- tau_kt -- capital-earnings tax; enters as r_t(1-tau_kt) in the consumer IBC, NAC, UCC, and the second-order difference equation.
- tau_nt -- labor-earnings tax; enters as w_t(1-tau_nt) in the consumer IBC and household labor FOC beta^t U_2t = mu w_t(1-tau_nt).
- tau_ht -- lump-sum tax; enters both government IBC (+q_t tau_ht) and consumer IBC (-q_t tau_ht).
- tau_it -- subsidy to investment; enters as (1-tau_it) multiplying net investment terms in both budget constraints, in the NAC, and in the UCC formula.

### [COMPUT] Metodo computacional

None implemented yet; this file sets up the theoretical equilibrium system (feasibility, NAC, consumer FOCs, zero-profit conditions) as a system of nonlinear difference equations with initial condition k_0 and terminal Transversality Condition, which is the exact system later solved numerically (via the Shooting algorithm) in Part 2.

### Intuicion general

Because taxes are distortionary, the competitive equilibrium no longer coincides with the solution to a social planner's problem, so the model must be solved directly as a competitive equilibrium (First Welfare Theorem fails). Rearranging the household's constraint to collect all terms multiplying k_t isolates a no-arbitrage requirement: if the after-tax return to holding capital one more period differed from its price, someone could make unbounded riskless profit buying/selling or short-selling capital across periods, which cannot happen in equilibrium. The transversality condition rules out both hoarding capital forever (wasteful) and running unbounded debt forever (unfinanceable). The user cost of capital reframes the same no-arbitrage logic from a firm's perspective (keep vs. sell a unit of capital), making transparent how tau_k, delta, and the price of capital each raise or lower the effective cost of capital.

### Ejemplos y ejercicios

- Comparative statics on UCC (page 20): a higher capital tax raises the cost of operating capital; a higher depreciation rate raises the cost of capital; a higher price of capital reduces the (relative) cost; an investment subsidy reduces the cost of capital in steady state.

### Anotaciones a mano (tuyas)

- Page 4 ('Model'): entire bullet list highlighted in green with a hand-drawn bracket in the left margin, emphasizing 'distorting taxes and exogenous government spending', the full list of tax instruments {tau_ct,tau_kt,tau_nt,tau_ht} plus subsidy tau_it, and 'Distorting taxes prevent a competitive equilibrium from solving a Planner's Problem' / 'First Welfare Theorem does not hold.'
- Page 7 (Price system definition): green highlighting over the definitions of q_t, r_t, w_t as intertemporal (time-0) prices -- flagged as a key definition.
- Page 8 (BFFP definition): entire definition block highlighted in green.
- Page 14: student hand-copied the capital law of motion at the top of the slide as 'k_{t+1} = (1-delta)k_t + i' (using i for investment instead of the slide's x_t), and highlighted in orange/tan the concluding sentence 'Consumer would buy capital cheap in t-1, sell it expensive in t, make a profit.'
- Page 15: orange highlighting on the short-selling arbitrage explanation.
- Page 22: a small comment/sticky-note icon placed next to the Euler's-theorem rewriting of the firm's profit sum (no legible text extracted from the icon itself).

### Conexiones con otros temas

- Directly followed by Macro_Din_II_Topic2.2SecondPart.pdf, which solves the second-order difference equation for capital derived on the last slide here (page 25) using the Shooting algorithm.
- The particular case with inelastic labor supply (page 24) is exactly the simplification later flagged explicitly in Macro_Din_II_Topic2.2ThirdPartFINALVERSIONfixlastslide.pdf (page 4), and is relaxed in that same file's final two slides ('Implementing Shooting for economy with endogenous labor supply').
- The discrete-time Euler equation and NAC are the discrete-time analog of the continuous-time Euler equation (c-dot/c = (1/sigma)(f'(k)-delta-rho)) developed in NotesDynMacroIITopic2.2.pdf and NotesDynMacroIITopic2.2secondpart.pdf.

---

## Fiscal Policies in the Growth Model — Second Part: steady state of the capital difference equation, comparative statics, the discrete-time Shooting algorithm for solving the nonlinear difference equation, reconstructing the rest of the equilibrium allocation, the intertemporal elasticity of substitution under CRRA utility, and a transition into continuous-time (Ramsey) phase-diagram dynamics and saddle-path stability.

*Fuente: `Macro_Din_II_Topic2.2SecondPart.pdf`*

*Secciones: Title / 'Second Part' | Setup: vector z_t of exogenous variables, difference equation H(...)=0 | Calculating the steady state | Effects of parameters and taxes on steady-state capital | Numerical solution method: Shooting algorithm (goal, requirement S>T) | Steps of the Shooting algorithm | Updating the guess for c_0 (bisection between c^low and c^high) | Constructing the rest of the equilibrium allocation once the k-path is known | Gross real after-tax interest rate; CRRA example; Intertemporal Elasticity of Substitution (IES) | Comments on solution method (advantages/disadvantages) | Continuous-time dynamics (Ramsey set-up) | Phase diagram (saddle path) | Explaining phase diagram on the blackboard (study checklist) | Bonus handwritten page: annotated phase diagram with quadrant dynamics and Golden Rule note*

### Supuestos

> lim_{t->infinity} z_t = z-bar (exogenous fiscal variables converge to constants).
>
> Shooting requires S>T, where T is the period after which exogenous variables are constant.
>
> Model has a single endogenous state variable (capital), needed for Shooting to be tractable.
>
> Continuous-time block: inelastic labor supply n=1; f(k)=k^alpha; CRRA utility with curvature sigma; discount rate rho.
>
> Model exhibits saddle-point stability.
>

### Conceptos clave

- **Steady state of a difference equation** - The fixed point k-bar solving H(k-bar,k-bar,k-bar;z-bar,z-bar)=0 once the exogenous vector z_t converges to z-bar.
- **Shooting algorithm** - A numerical method that guesses an initial control (c_0), simulates the nonlinear difference-equation system forward, and updates the guess (by bisection) until the simulated terminal state matches the known steady state.
- **Intertemporal Elasticity of Substitution (IES)** - Under CRRA utility u(c)=(c^{1-sigma}-1)/(1-sigma), the derivative of the log of the consumption growth factor with respect to the log real interest rate, equal to 1/sigma.
- **Saddle-point stability** - Property of the phase diagram/dynamic system whereby only a single stable trajectory (the stable arm) converges to the steady state; all other paths diverge.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Exogenous state vector | `z_t = [g_t\ \tau_{it}\ \tau_{kt}\ \tau_{ct}]'` | Collects the exogenous fiscal variables relevant to the capital difference equation under inelastic labor supply (tau_n and tau_h drop out). | Compact notation for the difference equation H. |
| Difference equation / steady state | `H(k_t,k_{t+1},k_{t+2},z_t,z_{t+1})=0,\quad \lim_{t\to\infty}z_t=\bar z,\quad H(\bar k,\bar k,\bar k;\bar z,\bar z)=0` | General second-order difference equation for capital and its steady state given convergent exogenous variables. | Abstract statement of the equation solved by Shooting. |
| Steady-state Euler condition | `1=\beta\left[\frac{1-\tau_k}{1-\tau_i}f'(\bar k)+(1-\delta)\right]` | Steady-state version of the Euler equation from Part 1: after-tax marginal product of capital net of depreciation equals the inverse discount factor. | Solving for steady-state capital k-bar. |
| Closed-form steady-state capital (Cobb-Douglas) | `\bar k = \left(\frac{1-\tau_k}{1-\tau_i}\cdot\frac{\alpha A}{\frac{1}{\beta}-1+\delta}\right)^{\frac{1}{1-\alpha}}\quad \text{if } f(k)=Ak^\alpha` | Explicit solution for steady-state capital under Cobb-Douglas technology. | Quick calculation of k-bar once functional form and parameters are set. |
| Shooting: period-0 feasibility step | `f(k_0)=c_0+g_0+k_1-(1-\delta)k_0` | Given k_0 and a guess c_0, solve for k_1. | Step 2 of the Shooting algorithm. |
| Shooting: Euler forward step | `u'(c_0)=\beta u'(c_1)\frac{1+\tau_{c0}}{1+\tau_{c1}}\left[\frac{1-\tau_{k1}}{1-\tau_{i1}}f'(k_1)+\frac{1-\tau_{i1}}{1-\tau_{i0}}(1-\delta)\right]` | Solve for c_1 given k_1 and the tax sequence. | Step 3 of the Shooting algorithm, repeated to build {k_0,...,k_S}. |
| Bisection bounds on c_0 | `c^{\ell}=0,\qquad c^{h}=f(k_0)+(1-\delta)k_0\ (\text{equivalent to }k_1=0);\qquad c_0=\tfrac12(c^{\ell}+c^{h})` | Low bound is zero consumption; high bound consumes everything (drives k_1 to zero). New guess is the midpoint, with the relevant bound updated depending on whether k_S over- or undershoots k-bar. | Updating c_0 between Shooting iterations. |
| Rest of the equilibrium allocation | `c_t=f(k_t)+(1-\delta)k_t-k_{t+1}-g_t,\quad q_t=\frac{\beta^tu'(c_t)}{1+\tau_{ct}},\quad r_t=q_tf'(k_t),\quad w_t=q_t(f(k_t)-k_tf'(k_t))` | Once the capital path is known, consumption, prices, and factor payments follow algebraically (q_t normalized by setting q_0=1, since it carries the intertemporal budget-constraint multiplier). | Final reconstruction step after Shooting converges. |
| Gross real after-tax interest rate | `u'(c_t)=\beta u'(c_{t+1})R_{t+1},\qquad R_{t+1}=\frac{1+\tau_{ct}}{1+\tau_{ct+1}}\left[\frac{1-\tau_{it+1}}{1-\tau_{it}}(1-\delta)+\frac{1-\tau_{kt+1}}{1-\tau_{it}}f'(k_{t+1})\right]` | Defines the after-tax gross real return R_{t+1} implicit in the Euler equation. | Computing implied interest rates along the equilibrium path. |
| CRRA utility and IES | `u(c_t)=\frac{c_t^{1-\sigma}-1}{1-\sigma},\ \sigma>0,\sigma\ne1;\qquad \ln\left(\frac{c_{t+1}}{c_t}\right)=\frac1\sigma\ln\beta+\frac1\sigma\ln R_{t+1}` | With CRRA utility the Euler equation implies log consumption growth is linear in the log gross real rate with slope 1/sigma; that slope is, by definition, the intertemporal elasticity of substitution. | Any time CRRA is used and the response of consumption growth to interest-rate changes is needed. |
| Continuous-time utility and feasibility | `\int_0^{\infty}\frac{c^{1-\sigma}-1}{1-\sigma}e^{-\rho t}dt;\qquad \dot k=\frac{\partial k}{\partial t};\qquad y=c+\dot k+\delta k;\qquad f(k)=k^\alpha,\ n=1` | Continuous-time analog of the model: CRRA flow utility discounted at rate rho, capital accumulation as a time derivative, feasibility, and Cobb-Douglas-in-k production with inelastic labor. | Setting up the continuous-time (Ramsey) version to build the phase diagram. |
| Continuous-time Euler equation | `\frac{\dot c}{c}=\frac1\sigma(f_k-\delta-\rho)` | Consumption growth rate equals (1/sigma) times the gap between the net-of-depreciation marginal product of capital and the discount rate. | Core equation for the phase diagram (loci and dynamics), given directly without deriving the Hamiltonian. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

The discrete-time part of this file keeps labor supply exogenous/suppressed (inherited from Part 1's 'particular case'); production is written in intensive form f(k) with no separate n. The 'Continuous-time dynamics' section explicitly assumes inelastic labor supply (n=1) with production f(k)=k^alpha -- i.e. labor is fixed and absorbed into the function; no separate labor demand condition or wage equation is derived. No utility-of-leisure term and no Frisch elasticity appear anywhere in this file. The curvature/substitution parameter that IS pinned down is sigma, the CRRA coefficient governing intertemporal (not labor) substitution: IES=1/sigma, entering directly in the continuous-time Euler equation c-dot/c=(1/sigma)(f'(k)-delta-rho).

### [POLICY] Instrumentos de politica

- g_t -- government purchases, collected in z_t; enters the feasibility/Shooting steps.
- tau_it -- investment subsidy, collected in z_t; higher subsidy increases steady-state capital.
- tau_kt -- capital-earnings tax, collected in z_t; higher tax on payment to capital reduces steady-state capital.
- tau_ct -- consumption tax, collected in z_t; appears in R_{t+1} and in q_t.
- Note: tau_nt (labor tax) and tau_ht (lump-sum tax) are dropped from z_t here, since with inelastic labor they do not affect the capital difference equation (consistent with Part 3's finding).

### [COMPUT] Metodo computacional

Shooting algorithm (discrete-time nonlinear difference-equation solver): (1) compute steady state k-bar (closed form under Cobb-Douglas, or numerically) from the steady-state Euler condition; (2) given k_0 and a guess c_0, iterate forward using feasibility to get k_1 and the Euler equation to get c_1, repeating to generate {k_0,...,k_S} for S>T; (3) compare k_S to k-bar and update c_0 by bisection between c^low=0 and c^high=f(k_0)+(1-delta)k_0; (4) once the capital path is found, back out c_t, q_t, r_t, w_t algebraically (q_t normalized by q_0=1). Advantages noted: fast, more precise than linear/perturbation methods for a single-state-variable model under certainty. Disadvantages noted: cannot handle uncertainty (multiple paths) and is difficult to extend beyond one state variable. Reference: Barro and Sala-i-Martin (1995) for the continuous-time (phase-diagram) analog.

### [CALIB] Objetivos de calibracion

- No explicit calibration targets stated; steady-state capital k-bar is solved analytically from parameters (A, alpha, beta, delta, tau_k, tau_i) rather than matched to a data moment in this file.

### Intuicion general

The steady state equates the after-tax net marginal product of capital to the consumer's rate of time preference, adjusted by the relative capital-tax/investment-subsidy wedge. The Shooting algorithm exploits monotonicity: there is a unique initial consumption c_0 consistent with reaching k-bar (the stable arm), so bisecting on c_0 between 'consume nothing' and 'consume everything' (drive k_1 to zero), and checking whether the simulated k_S over- or undershoots k-bar, must converge. The continuous-time phase diagram (elaborated with far more graphical detail in the two handwritten notes files) explains why this works: departures from the unique stable arm diverge, so exactly one c(0) per k(0) is consistent with equilibrium -- precisely what Shooting searches for.

### Ejemplos y ejercicios

- Cobb-Douglas closed form for steady-state capital (page 4).
- CRRA utility example used to derive IES = 1/sigma (page 10).

### Anotaciones a mano (tuyas)

- Page 10: green highlighting over the CRRA utility formula and over the phrase 'intertemporal elasticity of substitution (IES) is 1/sigma.'
- Page 11 ('Comments on solution method'): blue highlighting over 'Useful method when solving nonlinear dynamic model with certainty and single endogenous state variable (e.g. capital)' and over 'continuous-time dynamics.'
- Page 12 ('Continuous-time dynamics'): a handwritten marginal note (partially legible, reads approximately 'has a subscript') near the discount factor e^{-rho t}; a handwritten reformulation of the feasibility condition beside the printed continuous one, written as 'k_{t+1}=k_t(1-delta)+i_t' and '(k_{t+1}-k_t)+delta k_t = i_t' -- apparently the student translating the continuous k-dot=y-c-delta k back into discrete notation; and a handwritten question near the Euler equation reading approximately 'Cand Euler-Lagrange??' with multiple question marks, reflecting uncertainty about the (explicitly skipped) Hamiltonian/Lagrangian approach.
- Bonus final page (unnumbered, tan background): a full hand-drawn, color-coded reconstruction of the phase diagram (orange k-dot=0 curve, blue arrows, pink vertical c-dot=0 line), with region labels (approximately) 'C>Css -> k-dot<0' (top-left), 'C<Css -> k-dot>0' (bottom-left), 'K>Kss -> C>0' (bottom axis); a circled region on the declining part of the hump labeled '(k>Kss -> C<0)' with a green note reading approximately 'No alcanzamos K_GR pq somos impacientes' (Spanish: 'We don't reach K_GR because we are impatient') and 'rho>0' written at far right; a green note '\exists una unica trayectoria' ('there exists a unique trajectory') pointing at the declining segment of the k-dot=0 locus; and a small inset box reproducing 'max_k {c=f(k)-delta k}, F.O.C. f'(k)=delta' marking the Golden Rule capital K_GR on the hump. Below the diagram the student re-derives c-dot/c=(1/sigma)(f'(k)-delta-rho), sets c-dot=0 => f'(k)=delta+rho, and restates k-dot=f(k)-c-delta k, c=f(k)-delta k.

### Conexiones con otros temas

- Solves numerically the second-order difference equation derived at the end of Part 1 (Macro_Din_II_Topic2.2FirstPartFINALVERSION.pdf, page 25).
- The 'Continuous-time dynamics' slides and bonus handwritten phase-diagram page are elaborated step by step in NotesDynMacroIITopic2.2.pdf and NotesDynMacroIITopic2.2secondpart.pdf.
- Part 3 (ThirdPartFINALVERSION) extends the Shooting algorithm to endogenous labor supply by adding an fsolve step for the static consumption-leisure equation.
- Cites Barro and Sala-i-Martin (1995) as the reference for continuous-time neoclassical growth dynamics.

---

## Fiscal Policies in the Growth Model — Third Part: which taxes are distorting versus non-distorting under inelastic labor supply; impulse-response versus transition experiments with an application to Mexico's 2014 fiscal reform; and extending the Shooting algorithm to an economy with endogenous labor supply.

*Fuente: `Macro_Din_II_Topic2.2ThirdPartFINALVERSIONfixlastslide.pdf`*

*Secciones: Title (Third Part, reviewed September 9, 2019) | Effects of taxes: system of equations (c_t, q_t, r_t, w_t, Euler, R_{t+1}) | Distorting vs. non-distorting taxes under inelastic labor supply | Experiments: impulse-response vs. transition; application to Mexico 2014 fiscal reform | Implementing Shooting for an economy with endogenous labor supply (utility, feasibility, production, Euler, consumption-leisure equation) | Algorithm to solve the equilibrium with a consumption-leisure decision (extra fsolve step)*

### Supuestos

> Labor supply is inelastic in the 'effects of taxes' analysis (baseline case).
>
> No government (g_t=0, no taxes) when introducing endogenous labor supply, 'for simplicity.'
>
> Utility separable log-log in consumption and leisure with weight psi on leisure.
>
> Cobb-Douglas production k^alpha n^{1-alpha}.
>

### Conceptos clave

- **Non-distorting vs. distorting tax (under inelastic labor)** - A tax is non-distorting here if it does not alter the intertemporal margin captured by R_{t+1}; a constant tau_c and any tau_n are non-distorting under inelastic labor, while tau_i and tau_k always distort, and a time-varying tau_c also distorts.
- **Impulse-response experiment** - Starting from steady state, change one exogenous variable for one period only and observe the economy's response; analogous to taking a derivative.
- **Transition experiment** - Initialize state variables from data for a given year, then feed in the observed sequence of exogenous shocks; dynamics combine capital's convergence to steady state with the direct effect of the shocks.
- **Consumption-leisure (static labor-supply) equation** - The intratemporal first-order condition equating the marginal rate of substitution between leisure and consumption to the (after-tax) marginal product of labor / wage, solved period-by-period as a nonlinear equation once labor is endogenous.
- **fsolve** - Matlab's nonlinear equation solver, used at each period of the Shooting algorithm to solve the static consumption-leisure equation for n_t.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Equilibrium system (baseline, inelastic labor) | `c_t = f(k_t) + (1-\delta)k_t - k_{t+1} - g_t;\quad q_t=\frac{\beta^tu'(c_t)}{1+\tau_{ct}};\quad r_t=q_tf'(k_t);\quad w_t=q_t(f(k_t)-k_tf'(k_t));\quad u'(c_t)=\beta u'(c_{t+1})R_{t+1};\quad R_{t+1}=\frac{1+\tau_{ct}}{1+\tau_{ct+1}}\left[\frac{1-\tau_{it+1}}{1-\tau_{it}}(1-\delta)+\frac{1-\tau_{kt+1}}{1-\tau_{it}}f'(k_{t+1})\right]` | Reprints, in one block, the full pricing/allocation system from Parts 1-2, used to read off which taxes appear where. | Classifying which taxes are distorting. |
| Utility with leisure (endogenous labor case) | `u(c_t,1-n_t) = \ln(c_t) + \psi\ln(1-n_t)` | Additively separable log utility in consumption and leisure with leisure weight psi. | Extending the model to endogenous labor supply. |
| Feasibility (no government) | `c_t + k_{t+1} - (1-\delta)k_t = y_t` | Resource constraint with government purchases set to zero for simplicity. | Endogenous-labor Shooting example. |
| Cobb-Douglas production | `y_t = f(k_t,n_t) = k_t^{\alpha} n_t^{1-\alpha}` | Two-factor constant-returns technology with capital share alpha. | Endogenous-labor Shooting example. |
| Euler equation with endogenous labor | `\frac{c_{t+1}}{c_t} = \beta[\alpha k_{t+1}^{\alpha-1}n_{t+1}^{1-\alpha} + 1 - \delta]` | Intertemporal consumption-savings condition, now with labor n_{t+1} entering the marginal product of capital. | Forward step of the endogenous-labor Shooting algorithm. |
| Consumption-leisure equation | `\frac{\psi c_t}{1-n_t} = (1-\alpha)k_t^{\alpha} n_t^{-\alpha}` | Static intratemporal condition: MRS between leisure and consumption equals the marginal product of labor (real wage, since q_0 is normalized). | Solved via fsolve for n_t at every period of the Shooting algorithm. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

This file is the one place in the chunk where both sides of the labor block are made fully explicit. (1) In the baseline 'Effects of taxes' system, labor supply is still inelastic (restated explicitly on page 4); under that assumption tau_n literally disappears from the system of equations, and a constant tau_c is also non-distorting -- only tau_i and tau_k always distort. A handwritten annotation on page 4 derives what the marginal condition WOULD be if labor entered: 'Umgc/Umgh = w(1-tau_n)' (marginal utility of consumption over marginal utility of leisure equals the after-tax wage), with the note 'No hay en el modelo' (not present in the model) because n is fixed. (2) The final two slides DO switch on endogenous labor supply, using additively separable log utility u(c,1-n)=ln(c)+psi*ln(1-n) -- NOT GHH (GHH would remove the wealth effect on labor supply; here it is fully separable, so a wealth effect on labor supply IS present). Production is Cobb-Douglas y=k^alpha n^{1-alpha}, so alpha (equivalently 1-alpha, labor's share) is the curvature parameter governing the marginal product of labor: F_n=(1-alpha)k^alpha n^{-alpha}, F_nn=-alpha(1-alpha)k^alpha n^{-alpha-1}<0. The implicit labor demand condition (from the same zero-profit/Euler's-theorem logic as Part 1, specialized to Cobb-Douglas) is w_t=q_t(1-alpha)k_t^alpha n_t^{-alpha}; combined with the household's static FOC this yields the printed consumption-leisure equation psi*c_t/(1-n_t) = (1-alpha)k_t^alpha n_t^{-alpha}, i.e. MRS(leisure,c)=wage. The implied Frisch elasticity under log-log separable utility is finite (not infinite as under GHH with linear disutility of labor) and depends on the steady-state labor share n-bar, though it is not computed explicitly in the slides.

### [POLICY] Instrumentos de politica

- g_t -- government spending; present in the baseline system but set to zero ('assume no government for simplicity') once labor supply is made endogenous.
- tau_ct -- consumption tax; non-distorting if constant, distorting if time-varying, under inelastic labor.
- tau_kt -- capital-earnings tax; always distorting (enters R_{t+1}).
- tau_nt -- labor-earnings tax; literally absent from the system of equations under inelastic labor supply (flagged with a handwritten 'check' annotation).
- tau_ht -- lump-sum tax; not explicitly discussed in this file's tax-effects table.
- tau_it -- investment subsidy; always distorting (enters R_{t+1}), constant or time-varying.

### [COMPUT] Metodo computacional

Two model 'experiments' once solved on the computer: (1) impulse-response -- perturb one exogenous variable for a single period from steady state and trace the response, likened to a numerical derivative; (2) transition -- initialize state variables from real data for a given year and feed in the actual observed sequence of exogenous shocks, so simulated dynamics reflect both capital's convergence to steady state and the shocks' direct effects; applied to Mexico's 2014 fiscal reform. Also: extension of the discrete-time Shooting algorithm (from Part 2) to endogenous labor supply -- at each iteration, after guessing c_0, solve the static consumption-leisure equation for n_t using fsolve in Matlab, then proceed with feasibility to get k_{t+1} and the Euler equation to get c_{t+1}.

### Intuicion general

With inelastic labor supply, a constant tau_c and any tau_n are non-distorting: tau_c cancels as a constant ratio inside R_{t+1}, and tau_n never enters the system at all because labor cannot respond to it, so there is no margin left for it to distort. A time-varying tau_c becomes distorting because the ratio (1+tau_ct)/(1+tau_ct+1) no longer cancels to a constant. tau_i and tau_k always distort R_{t+1}, constant or not, because they enter asymmetrically across today's and tomorrow's terms. Impulse-response experiments isolate the pure comparative-dynamics effect of a single instrument (like a derivative), while transition experiments feed in real historical shock sequences from real initial conditions, mixing endogenous convergence with the shocks' direct effects -- exactly the design used to study Mexico's 2014 fiscal reform. Turning on endogenous labor supply adds one unknown (n_t) and one static equation per period, solved via fsolve, before the rest of the Shooting steps (feasibility, Euler) proceed as before.

### Ejemplos y ejercicios

- Mexico's 2014 fiscal reform as the transition-experiment application (page 5).
- Full Shooting algorithm with endogenous labor supply (pages 6-7): guess c_0 -> solve the static consumption-leisure equation for n_0 via fsolve -> get k_1 from feasibility -> get c_1 from Euler -> repeat -> compare k_S to k-bar -> adjust c_0.

### Anotaciones a mano (tuyas)

- Page 4: a blue-ink 'check' with an arrow pointing toward R_{t+1}/the 'not distorting' claim; handwritten note 'No hay en el modelo' ('not [there] in the model') next to 'The tax on labor income does not appear in system of equations,' with a compact handwritten formula 'Umgc/Umgh = w(1-tau_n)' underneath -- the marginal-rate-of-substitution condition the student wrote out to verify why tau_n would matter if labor were endogenous; the whole passage is highlighted in blue.
- Page 6 title: hand-drawn blue highlight over the word 'endogenous' in 'Implementing Shooting for economy with endogenous labor supply.'
- Page 7: a yellow sticky-note/comment icon placed over the word 'generate' in step 5 (no legible text content extracted from the icon).

### Conexiones con otros temas

- Builds directly on the pricing system first derived at the end of Part 1 (page 25) and used throughout Part 2's Shooting algorithm; reprints the same {c_t,q_t,r_t,w_t,Euler,R_{t+1}} system verbatim.
- Extends Part 2's Shooting steps (page 7 of Part 2) by adding the fsolve sub-step for n_t.
- The distorting/non-distorting tax classification is the payoff of carrying tau_c, tau_k, tau_n, tau_h, tau_i symbolically through Parts 1-2.
- The Mexico-2014 application and the endogenous-labor Shooting extension are the two pieces of this course closest to the user's own thesis project on estimating the labor demand elasticity in Mexican local labor markets: the consumption-leisure equation here is the model-consistent labor supply/demand-clearing condition whose curvature (alpha) is exactly the kind of parameter a shift-share/enclave design would need to be consistent with structurally.

---

## Handwritten notes, Continuous-Time (Ramsey) Model, Part 1: constructing the phase diagram in (k,c) space from the continuous-time Euler and feasibility equations, identifying the c-dot=0 and k-dot=0 loci and the dynamics in each of the four regions, and setting up the logic behind the Shooting Method.

*Fuente: `NotesDynMacroIITopic2.2.pdf`*

*Secciones: Framing: a phase diagram is a locus of points representing the behavior of a differential equation, constructed in (k,c) space | Deriving the c-dot=0 locus from the Euler equation | Deriving the k-dot=0 locus from feasibility | Dynamics away from each locus (region-by-region sign analysis) | Combined phase diagram: regions I-IV and convergence to steady state | Why a specific c(0) is needed for a given k(0): the rationale for the Shooting Method*

### Supuestos

> Continuous-time primitives as in the companion slides: production f(k), inelastic labor supply, discount rate rho, depreciation delta, CRRA curvature sigma.
>
> f'(k) is strictly decreasing (diminishing marginal returns to capital), used to sign the dynamics in each region.
>

### Conceptos clave

- **Phase diagram / locus** - A set of points in (k,c) space representing the behavior (zero-locus) of a differential equation, used to characterize the qualitative dynamics of the system.
- **c-dot=0 locus** - The vertical line k=k_ss in (k,c) space, obtained by setting the continuous-time Euler equation to zero; depends only on k, not on c.
- **k-dot=0 locus** - The hump-shaped curve c=f(k)-delta*k in (k,c) space, obtained by setting the feasibility condition (k-dot=0) to zero.
- **Steady state (k_ss)** - The intersection of the c-dot=0 and k-dot=0 loci; the value of capital at which the economy stops moving.
- **Four dynamic regions (I-IV)** - The (k,c) plane split by the two loci into four regions, each with its own combination of signs for c-dot and k-dot, summarized with directional arrows.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Continuous-time Euler equation | `\frac{\dot c}{c} = \frac{1}{\sigma}(f'(k)-\delta-\rho)` | Growth rate of consumption as a function of the gap between the net marginal product of capital and the discount rate, scaled by 1/sigma. | Deriving the c-dot=0 locus and the sign of consumption dynamics off that locus. |
| c-dot=0 locus | `f'(k)=\delta+\rho` | Equation depending only on k; its solution is the steady-state capital k_ss, shown as a vertical line in the (k,c) plane. | Locating k_ss and drawing the vertical locus. |
| Continuous-time feasibility | `\dot k = f(k) - c - \delta k` | Capital accumulation net of consumption and depreciation. | Deriving the k-dot=0 locus. |
| k-dot=0 locus | `c = f(k) - \delta k` | Hump-shaped curve: rises while extra output from more capital exceeds extra depreciation, eventually falls once depreciation dominates diminishing returns. | Plotting the second locus of the phase diagram. |
| Sign of dynamics off the loci | `k>k_{ss} \Rightarrow f'(k)<\delta+\rho \Rightarrow \dot c<0;\qquad k<k_{ss} \Rightarrow \dot c>0;\qquad \text{fixed } k,\ \text{higher } c \Rightarrow \dot k<0;\ \text{lower } c \Rightarrow \dot k>0` | Direction of movement in each region, derived from diminishing marginal returns (f' decreasing) and from the feasibility identity. | Drawing arrows in each of the four regions of the phase diagram. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Same continuous-time set-up as SecondPart.pdf page 12: inelastic labor supply (n=1, not modeled as a choice); Cobb-Douglas-in-capital-only intensive production f(k)=k^alpha is implicit (inherited from the companion slide, not re-derived here). No separate labor demand or labor supply equation appears; labor is entirely absent from the phase-diagram derivation, consistent with the 'particular case' simplification carried over from the discrete-time slides. No Frisch elasticity, no CES/GHH specification, no wage equation.

### [COMPUT] Metodo computacional

Phase-diagram / graphical shooting-method reasoning (no numbers, no code): identify the c-dot=0 and k-dot=0 loci, sign the dynamics in each region, and argue graphically that a unique trajectory from a given k(0) reaches the steady state -- presented explicitly as the reason the (numerical) Shooting Method works.

### Intuicion general

Constructing a phase diagram means finding, for each of the two differential equations (Euler and feasibility), the locus of (k,c) pairs that make that equation's time-derivative zero, then using the sign of the derivative just off that locus to draw direction arrows. Because the Euler equation only involves k once set to zero, the c-dot=0 locus is a vertical line at k_ss regardless of c. Because the feasibility zero-locus c=f(k)-delta*k is a genuine function of k with the concave shape of f(k) net of a linear depreciation drain, it first rises then eventually falls -- a single-peaked curve. Combining both sign patterns partitions the (k,c) plane into four regions whose arrows point toward or away from the steady state; regions II and III converge toward it, the two-dimensional realization of saddle-path stability. Since only a knife-edge starting c(0) for a given k(0) lands exactly on that convergent path, finding it numerically is precisely what the Shooting Method does.

### Anotaciones a mano (tuyas)

- Entirely handwritten (blue and black ink) notes dated August 2020; later additions appear layered in a different (blue) ink on top of the original black-ink derivation -- e.g. on page 3 the blue text 'We can show (below...) that the maximum of (k-dot=0) is located to the right of k_ss' is a follow-up remark foreshadowing the Golden Rule result proved in the second part.
- Page 4 uses blue ink specifically to state the mirror-image case ('The behavior is the opposite with k<k_ss; i.e. c-dot>0'), visually distinguishing the k>k_ss case (black ink) from the k<k_ss case (blue ink).
- Page 5 again marks the symmetric case in blue ink ('If c is smaller, then k-dot increases over time, i.e. k-dot>0'), continuing the same black/blue convention.
- Greek letters are rendered in a personal cursive shorthand that could be misread on a later pass: delta (depreciation) is written like a cursive 'S', and rho (discount rate) like an 'e' or script letter -- this recurs identically across both handwritten files.
- Page 6 overlays red and blue arrows on the same axes to show c-dot dynamics (red, vertical) and k-dot dynamics (blue, horizontal) separately before merging them into the four-region (I-IV) summary diagram directly below.

### Conexiones con otros temas

- Handwritten companion to Macro_Din_II_Topic2.2SecondPart.pdf's 'Continuous-time dynamics' and 'Phase Diagram' slides (pages 12-14), with a more step-by-step derivation of the loci and quadrant arrows than the slides show.
- Continued directly in NotesDynMacroIITopic2.2secondpart.pdf ('2nd Part'), which picks up with the saddle path, off-path divergence, and the Golden Rule.

---

## Handwritten notes, Continuous-Time (Ramsey) Model, Part 2: the saddle path/stable arm, off-path (non-equilibrium) trajectories and why they are ruled out by the Euler equation and the Transversality Condition, and the Golden Rule capital k_GR versus the (modified-golden-rule) steady state k_ss.

*Fuente: `NotesDynMacroIITopic2.2secondpart.pdf`*

*Secciones: Redrawing the phase diagram with the stable arm from k(0) to steady state | Boundary features of the k-dot=0 locus (k=0 => c=0; high k => locus turns down) | What happens off the stable arm: too-high c(0) (green path) vs. too-low c(0) (purple path) | The Golden Rule: k_GR defined as the maximizer of steady-state consumption | Comparing k_ss (from f'(k)=delta+rho) and k_GR (from f'(k)=delta): k_GR>k_ss because f' is decreasing | Why the (impatient) planner/competitive economy never reaches k_GR*

### Supuestos

> f'(k) is strictly decreasing (diminishing marginal returns to capital).
>
> rho>0 (positive discounting / impatience).
>
> Off-path behavior is ruled out by two separate optimality conditions: the Euler equation rules out consumption 'jumps'; the Transversality Condition rules out perpetual over-accumulation.
>

### Conceptos clave

- **Stable arm / saddle path** - The unique trajectory through the steady state along which both the c-dot and k-dot dynamics point inward; the only path consistent with equilibrium for a given k(0).
- **Off-equilibrium divergence** - Paths starting from a c(0) not on the stable arm either hit the c-axis (capital collapses to zero, forcing consumption to jump discontinuously -- violating the Euler equation) or run out along the declining part of the k-dot=0 locus (over-accumulating capital and permanently losing consumption -- violating the Transversality Condition).
- **Golden Rule capital (k_GR)** - The capital stock that maximizes steady-state consumption c=f(k)-delta*k, found from the F.O.C. f'(k)=delta.
- **Modified Golden Rule steady state (k_ss) vs. Golden Rule (k_GR)** - k_ss (from f'(k)=delta+rho) is strictly smaller than k_GR (from f'(k)=delta) whenever rho>0, because f'(k) is strictly decreasing.

### Teoremas, lemas y proposiciones

> **k_GR > k_ss**
>
> Given that f'(k) is decreasing (diminishing marginal returns) and delta+rho > delta (since rho>0), the capital level solving f'(k)=delta (k_GR) must exceed the capital level solving f'(k)=delta+rho (k_ss).
>
> *Supuestos requeridos:* f'(k) strictly decreasing; rho>0
>
> *Garantiza:* k_GR > k_ss; illustrated by a declining f'(k) curve mapping delta+rho to k_ss and delta to k_GR, with k_ss to the left of k_GR.

> **The economy does not reach k_GR**
>
> In the Planner's Problem or in the Competitive Equilibrium (where the Welfare Theorems hold), the consumer does not reach k_GR because she is impatient (rho>0).
>
> *Supuestos requeridos:* rho>0
>
> *Garantiza:* Equilibrium capital converges to k_ss < k_GR, not to the Golden Rule level.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| k-dot=0 locus boundary behavior | `k=0 \Rightarrow c=0\ (\text{from feasibility with } \dot k=0);\quad \text{for sufficiently high } k,\ \delta k \text{ dominates the marginal increase in } f(k)` | The k-dot=0 locus passes through the origin and eventually turns down and returns toward the k-axis at high capital levels. | Sketching the full shape of the k-dot=0 hump, including its endpoints. |
| Golden Rule problem | `k_{GR} = \arg\max_{k}\{c = f(k) - \delta k\},\qquad \text{F.O.C. } f'(k)=\delta` | Capital level maximizing steady-state consumption, ignoring impatience. | Comparing the technologically best steady state to the one actually reached in equilibrium. |
| Modified Golden Rule (actual steady state) | `k_{ss}:\ f'(k)=\delta+\rho` | Capital level actually reached in equilibrium, accounting for the discount rate rho. | Comparing to k_GR to show k_ss<k_GR. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Same as NotesDynMacroIITopic2.2.pdf -- continuous-time Ramsey model with inelastic labor supply; no labor margin appears anywhere in this file. Not applicable.

### [COMPUT] Metodo computacional

Purely graphical/phase-diagram reasoning (no numerical algorithm executed here), but it supplies the economic justification for why the Shooting Method's convergence criterion is well posed: any guess off the stable arm produces one of exactly two disqualifying outcomes (Euler-violating jump to the origin, or Transversality-violating over-accumulation), which is why bisecting on c(0) between those two failure modes (as in SecondPart.pdf's Shooting steps) must converge to the unique correct path.

### Intuicion general

The stable arm is the unique curve through the steady state along which both loci's dynamics point inward; for a given k(0), only the point on that arm is consistent with equilibrium. If c(0) is guessed too high (green path), capital runs down to zero while consumption is still positive, forcing consumption to collapse discontinuously to zero when capital hits zero -- inconsistent with the Euler equation, which describes smooth, jump-free behavior. If c(0) is guessed too low (purple path), the economy keeps accumulating capital past k_ss along the declining part of the k-dot=0 locus, over-accumulating capital and permanently sacrificing consumption -- violating the Transversality Condition. The Golden Rule is the purely technological benchmark that ignores impatience: since f' is decreasing, requiring a smaller marginal product (f'=delta, versus f'=delta+rho for the actual steady state) implies a strictly larger capital stock, so k_GR>k_ss. But no impatient agent (rho>0) would ever choose to sit at k_GR: equilibrium always converges to the smaller, modified-golden-rule k_ss, trading off extra future consumption at k_GR against the impatience cost of getting there.

### Ejemplos y ejercicios

- The two colored (green/purple) off-equilibrium trajectories are worked 'what if' examples of wrong initial guesses for c(0), directly illustrating why the Shooting Method's bisection search must converge -- any c(0) not exactly on the stable arm produces one of these two self-evidently invalid outcomes.

### Anotaciones a mano (tuyas)

- Extensive color-coding as an annotation device: green ink traces the 'too much initial consumption' trajectory with a Spanish-language explanation reading approximately 'Al tocar eje de c, como k=0, economia se colapsa, y salta al origen. Viola Euler, que describe comportamiento sin saltos' ('On touching the c-axis, since k=0, the economy collapses and jumps to the origin. This violates the Euler equation, which describes behavior without jumps'); purple/magenta ink traces the 'too little initial consumption' trajectory with its own note reading approximately 'Acumulamos demasiado capital. Perdemos consumo. Viola Transversalidad' ('We accumulate too much capital. We lose consumption. Violates Transversality'). The student explicitly apologizes inline for switching to Spanish ('Oops sorry for the Spanish').
- Blue instructional aside on page 2: 'Put the point on the graph, let arrows determine the path' -- a self-reminder of the graphical method for tracing any candidate trajectory.
- Page 3: a magenta/purple box explicitly labels the maximizer as 'K_GR -- Golden Rule capital,' visually distinct from the black-ink main derivation, suggesting it was added as a follow-up emphasis.
- Page 4 closes with an underlined 'rho>0' as the one-line justification for why k_GR is never reached, visually set apart as the key takeaway of the two-part notes.

### Conexiones con otros temas

- Direct continuation of NotesDynMacroIITopic2.2.pdf (same phase diagram, picked up mid-derivation).
- The Golden Rule result here is the same result foreshadowed in blue ink on page 3 of NotesDynMacroIITopic2.2.pdf ('the maximizer is called K_GR').
- Matches and elaborates on the bonus hand-annotated final page of Macro_Din_II_Topic2.2SecondPart.pdf, which contains the identical note 'No alcanzamos K_GR pq somos impacientes.'

---

## Optimal Fiscal Policy with Commitment — First Part: the Ramsey Problem, Chamley's (dual) approach, and Judd's (1985) heterogeneous-agent extension

*Fuente: `Macro_Din_II_Topic2.3FirstPartFINALVERSIONfixes2.pdf`*

*Secciones: Introduction: the Ramsey Problem (dynamic optimal taxation, commitment, no uncertainty) | Model: household utility, technology, capital accumulation, feasibility | Government: tax instruments, bonds, sequential budget constraint | Households: budget constraint, FOCs, Euler equation, consumption-leisure condition, no-arbitrage condition | Households: present-value budget constraint and transversality conditions | Firms: profit maximization, FOCs | The Ramsey Problem: feasible allocation, price system, government policy, competitive equilibrium | Chamley's approach: after-tax prices, government revenue as a residual, Lagrangian | Calculation of steady-state optimal tax on capital (tau_k = 0 result) | Judd (1985): heterogeneous agents, social welfare function, redistribution limits | Judd's extreme two-class case: workers vs. capitalists*

### Supuestos

> 0 < beta < 1 (household discount factor)
>
> u strictly increasing in c_t and 1-n_t, twice continuously differentiable, strictly concave
>
> F(k_t,n_t) homogeneous of degree one, positive and diminishing marginal returns in both inputs
>
> No uncertainty
>
> Government commits to future tax rates and will not deviate from the announced plan
>
> Government can issue public debt b_t (positive or negative)
>
> tau_k0 restricted to be a small number (essentially zero) so that taxing only the initial, inelastically-supplied capital stock is not a trivial solution to the Ramsey Problem
>
> Lump-sum taxes are ruled out (otherwise the Ramsey Problem is trivial: set all distortionary taxes to zero)
>
> Government expenditures g_t constant after some period T; Ramsey Problem's solution converges to a steady state (used for the tau_k=0 derivation)
>
> Judd's extension: all N agents share the SAME discount factor beta (critical — result fails if beta_i != beta_j)
>
> Judd's extension: government budget balanced in the baseline (stated as inessential — result is the same if relaxed)
>
> Two-class case: alpha_1 > alpha_2 = 0 (planner cares only about workers), workers do not save, capitalists do not work
>

### Conceptos clave

- **Ramsey Problem** - Dynamic optimal taxation problem: choose sequences of distortionary taxes (and implicitly the resulting competitive equilibrium allocation) that maximize household welfare, given that the government commits today to never deviate from the announced tax plan and may issue debt; no uncertainty.
- **Ramsey plan** - The solution (tax sequence and associated allocation) to the Ramsey Problem.
- **Competitive equilibrium (in this context)** - A feasible allocation, a price system, and a government policy such that (1) given prices and policy, the allocation solves both the household's and firm's problems, and (2) given the allocation and prices, the government policy satisfies the government's budget constraint.
- **Chamley's approach** - Formulate the Ramsey Problem as if the government directly chooses after-tax prices (tilde r_t, bar w_t) rather than taxes, expressing government revenue as the wedge between before- and after-tax factor payments; this is the 'dual' approach, contrasted with the 'primal' approach in the Second Part.
- **Walras' Law (used implicitly)** - Because feasibility and the government's budget constraint hold, the consumer's budget constraint is not an independent constraint and need not be imposed separately in the Ramsey Lagrangian.
- **Judd's redistribution question** - Whether the zero-long-run-capital-tax result survives if the Ramsey planner cares only about workers (who do not own capital) rather than about all agents equally.

### Teoremas, lemas y proposiciones

> **Chamley–Judd zero capital tax (steady state, representative agent)**
>
> If a steady-state allocation solving the Ramsey Problem exists, the associated tax rate on capital earnings must be zero: tau_k = 0.
>
> *Supuestos requeridos:* Neoclassical growth model with F(k,n) homogeneous of degree 1, positive and diminishing marginal returns; No uncertainty, government commits to tax plan; Lump-sum taxes ruled out (tau_k0 restricted to be small, not confiscatory); Government expenditures g_t constant after some period T; Ramsey Problem's solution converges to a steady state
>
> *Garantiza:* tilde r = r (after-tax rental rate equals before-tax rental rate) ⇒ tau_k = 0; result is robust to eliminating government debt (b_{t+1}=b_t=0).

> **Judd (1985) extension with heterogeneous agents**
>
> Even when the government's social welfare function places different Pareto weights alpha_i on different agents (all with the same discount factor beta), the steady-state Ramsey tax on capital is still zero.
>
> *Supuestos requeridos:* N agents i=1,...,N with distinct utilities u_i(c_it,1-n_it); All agents share the SAME discount factor beta; Lump-sum transfers S_it >= 0 allowed, government budget balanced (result unchanged if relaxed); Steady-state equilibrium exists
>
> *Garantiza:* r = tilde r (tau_k=0) again in steady state; result breaks down if discount factors differ across agents (beta_i != beta_j), because the steady-state Euler equation used in the proof would then hold for only one agent.

> **Two-class special case (workers vs. capitalists)**
>
> In the extreme case with class 1 = workers (who do not save, c_1t = bar w_t n_1t + S_1t) and class 2 = capitalists (who do not work, c_2t + k_2,t+1 - (1-delta)k_2t = tilde r_t k_2t + S_2t), with Ramsey weight alpha_1 > alpha_2 = 0 (planner cares only about workers), the result is still that capital is not taxed in the long run; government spending is financed entirely via the labor tax.
>
> *Supuestos requeridos:* alpha_1 > alpha_2 = 0; Same beta for both classes
>
> *Garantiza:* tau_k = 0 even though the planner is maximizing only the utility of the non-capital-owning class.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Household lifetime utility | `\sum_{t=0}^{\infty}\beta^t u(c_t,1-n_t),\ 0<\beta<1` | Utility over consumption and leisure (1-n_t); u strictly increasing, twice continuously differentiable, strictly concave. | Household's objective in the underlying competitive equilibrium. |
| Euler's theorem decomposition | `F(k_t,n_t)=F_k(t)k_t+F_n(t)n_t` | Since F is homogeneous of degree one (CRS), output exactly exhausts factor payments at marginal products. | Used to express firm profits are zero in equilibrium and to write government revenue as residual F(k,n)-tilde r k-bar w n. |
| Capital accumulation | `k_{t+1}=(1-\delta)k_t+x_t` | Law of motion for capital given gross investment x_t and depreciation delta. | Feasibility/resource constraint. |
| Feasibility | `y_t=c_t+x_t+g_t` | Output splits into consumption, investment and government purchases. | Constraint in Ramsey Lagrangian (theta_t multiplier). |
| Government sequential budget constraint | `g_t=\tau_{kt}r_tk_t+\tau_{nt}w_tn_t+\frac{b_{t+1}}{R_t}-b_t` | Government purchases financed by capital tax revenue, labor tax revenue, and net bond issuance. | Defines admissible government policy; combined with feasibility via Chamley's after-tax-price trick. |
| Household sequential budget constraint | `c_t+k_{t+1}-(1-\delta)k_t+\frac{b_{t+1}}{R_t}-b_t=(1-\tau_{nt})w_tn_t+(1-\tau_{kt})r_tk_t` | Consumption plus net capital accumulation plus net bond purchases equals after-tax labor and capital income. | Household optimization problem. |
| Household FOCs | `c_t:\ u_c(t)=\lambda_t;\quad n_t:\ u_l(t)=\lambda_t(1-\tau_{nt})w_t;\quad k_{t+1}:\ \lambda_t=\beta\lambda_{t+1}[(1-\tau_{k,t+1})r_{t+1}+1-\delta];\quad b_{t+1}:\ \lambda_t\frac{1}{R_t}=\beta\lambda_{t+1}` | Standard consumer optimality conditions with Lagrange multiplier beta^t lambda_t. | Derive Euler equation, labor supply condition and no-arbitrage condition. |
| Euler equation | `u_{ct}=\beta u_{ct+1}[(1-\tau_{k,t+1})r_{t+1}+(1-\delta)]` | Intertemporal consumption smoothing given after-tax return on capital. | Core dynamic optimality condition used to pin down the steady state. |
| Consumption-leisure (labor supply) condition | `u_{lt}=u_{ct}(1-\tau_{nt})w_t` | Marginal rate of substitution between leisure and consumption equals the after-tax wage. | Static intratemporal optimality condition; embeds the labor tax wedge. |
| No-arbitrage condition | `R_t=(1-\tau_{kt})r_{t+1}+(1-\delta)` | Bonds and capital must offer the same after-tax return in equilibrium (note: slide 7 writes tau_kt while the FOC on the previous slide uses tau_{k,t+1} — a possible notational inconsistency in the source that the student did not flag). | Links bond return R_t to the after-tax capital return; used to build present-value budget constraint. |
| Present-value household budget constraint | `\sum_{t=0}^{\infty}\left(\prod_{i=0}^{t-1}R_i^{-1}\right)c_t=\sum_{t=0}^{\infty}\left(\prod_{i=0}^{t-1}R_i^{-1}\right)(1-\tau_{nt})w_tn_t+[(1-\tau_{k0})r_0+1-\delta]k_0+b_0` | Intertemporal budget after eliminating capital/bond terms via NAC, obtained by iterating and consolidating consecutive period budget constraints. | Basis for defining the Ramsey problem's implementability restriction (fully developed in the Second Part). |
| Transversality conditions | `\lim_{T\to\infty}\left(\prod_{i=0}^{T-1}R_i^{-1}\right)k_{T+1}=0;\qquad \lim_{T\to\infty}\left(\prod_{i=0}^{T-1}R_i^{-1}\right)\frac{b_{T+1}}{R_T}=0` | Rules out Ponzi schemes / ensures the consolidated present-value budget constraint is valid. | Needed to justify going from sequential to present-value budget constraint. |
| Firm's problem | `\Pi_t=F(k_t,n_t)-r_tk_t-w_tn_t;\quad F_k(t)=r_t,\ F_n(t)=w_t;\quad \Pi=0` | Competitive firms take prices as given; profits are zero in equilibrium by CRS. | Determines factor prices used throughout. |
| Chamley's after-tax prices | `\tilde r_t=(1-\tau_{kt})r_t;\qquad \bar w_t=(1-\tau_{nt})w_t` | Redefine the problem in terms of net-of-tax prices that the government effectively 'chooses'. | Core trick of the Chamley (dual) approach. |
| Government revenue as residual | `\tau_{kt}r_tk_t+\tau_{nt}w_tn_t=F(k_t,n_t)-\tilde r_tk_t-\bar w_tn_t` | Tax revenue equals output minus what households actually receive net of taxes. | Rewrites government budget without explicit tax rates. |
| Ramsey Lagrangian (representative agent) | `\mathcal{L}=\sum_{t=0}^{\infty}\beta^t\{U(c_t,1-n_t)+\psi_t[F(k_t,n_t)-\tilde r_tk_t-\bar w_tn_t+\tfrac{b_{t+1}}{R_t}-b_t-g_t]+\theta_t[F(k_t,n_t)-c_t-k_{t+1}+(1-\delta)k_t-g_t]+\mu_{1t}[u_l(t)-u_c(t)\bar w_t]+\mu_{2t}[u_c(t)-\beta u_c(t+1)(\tilde r_{t+1}+1-\delta)]\}` | Government maximizes utility subject to its own budget constraint (psi_t), feasibility (theta_t), and household optimality conditions (mu_1t, mu_2t) with R_t=\tilde r_{t+1}+1-\delta (no arbitrage). | Central object of Chamley's dual approach; differentiate w.r.t. k_{t+1} to get the steady-state result. |
| FOC w.r.t. capital | `\theta_t=\beta\{\psi_{t+1}[F_{k,t+1}-\tilde r_{t+1}]+\theta_{t+1}[F_{k,t+1}+1-\delta]\}` | theta_t and psi_t are positive multipliers: marginal value of an extra unit of production and of an extra unit of government revenue, respectively. | Take steady state to solve for tau_k. |
| Steady-state capital-tax result | `\theta=\beta\{\psi[r-\bar r]+\theta[r+1-\delta]\};\quad 1=\beta(\bar r+1-\delta);\quad (\theta+\psi)(r-\bar r)=0\ \Rightarrow\ \bar r=r\ \Rightarrow\ \tau_k=0` | Combining the steady-state FOC for capital with the consumer's steady-state Euler equation forces the after-tax and before-tax rental rates to coincide. | Main derivation of the Chamley-Judd result. |
| Household budget with net taxes (Judd, agent i) | `c_{it}+k_{it+1}-(1-\delta)k_{it}=\bar w_tn_{it}+\tilde r_tk_{it}+S_{it}` | Each agent i faces the same prices/taxes but receives individual lump-sum transfer S_it. | Multi-agent extension of the household budget constraint. |
| Social welfare function | `\sum_{i=1}^{N}\alpha_iu_i(c_{it},1-n_{it}),\quad \alpha_i\ge0,\ \sum_{i=1}^N\alpha_i=1` | Ramsey planner's objective is a weighted average of individual utilities. | Defines the Ramsey Problem when agents are heterogeneous. |
| Aggregate notation | `x_t\equiv\sum_{i=1}^Nx_{it},\ x=c,n,k,S` | Shorthand for economy-wide aggregates. | Used in government budget constraint g_t+S_t=... |
| N-agent Ramsey Lagrangian | `\mathcal{L}=\sum_{t=0}^{\infty}\beta^t\Big\{\sum_{i=1}^N\alpha_iu_i(c_{it},1-n_{it})+\psi_t[F(k_t,n_t)-\tilde r_tk_t-\bar w_tn_t-g_t-S_t]+\theta_t[F(k_t,n_t)-c_t-k_{t+1}+(1-\delta)k_t-g_t]+\sum_i\mu_{i1t}[u_{ilt}-u_{ict}\bar w_t]+\sum_i\mu_{i2t}[u_{ict}-\beta u_{ict+1}(\tilde r_{t+1}+1-\delta)]+\sum_i\varepsilon_{it}[\bar w_tn_{it}+\tilde r_tk_{it}+S_{it}-c_{it}-k_{it+1}+(1-\delta)k_{it}]\Big\}` | Adds individual budget constraints (multipliers epsilon_it) because, unlike the representative-agent case, aggregate feasibility + government budget do not imply each individual budget holds. | Multi-agent Ramsey Problem. |
| N-agent FOC w.r.t. k_{i,t+1} | `\theta_t+\varepsilon_{it}=\beta\{\psi_{t+1}[F_{k,t+1}-\tilde r_{t+1}]+\theta_{t+1}[F_{k,t+1}+1-\delta]+\varepsilon_{i,t+1}(\tilde r_{t+1}+1-\delta)\}` | Same structure as the one-agent FOC, plus terms from each individual's budget constraint. | Steady-state derivation for the heterogeneous-agent case. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Production is a generic CRS function F(k_t,n_t) (not specified as Cobb-Douglas or CES in this file) with Euler's theorem F(k,n)=F_k k+F_n n. Labor demand comes from the firm's static profit-maximization FOC F_n(t)=w_t (competitive wage = marginal product of labor). Labor supply/consumption-leisure margin: u_l(t)=u_c(t)(1-\tau_{nt})w_t, derived from a generic period utility u(c_t,1-n_t) (twice differentiable, strictly concave) — no GHH form and no explicit Frisch elasticity is assumed or computed; the curvature of labor demand is left implicit in F_n and its cross-partial F_{nk} rather than pinned to a specific parameter such as a capital share alpha. The labor tax tau_nt enters as a simple multiplicative wedge on the wage in the consumption-leisure condition. Judd's heterogeneous-agent case adds a second labor-supply margin per agent type i, u_ilt/u_ict=(1-tau_nt)w_t, still with generic utility.

### [POLICY] Instrumentos de politica

- tau_kt: capital income tax rate, enters household return (1-tau_kt)r_t k_t and government revenue tau_kt r_t k_t
- tau_nt: labor income tax rate, enters household labor income (1-tau_nt)w_t n_t and government revenue tau_nt w_t n_t
- g_t: exogenous government purchases stream, held fixed throughout (feasibility constraint and government budget)
- b_t / b_{t+1}: one-period government bonds, gross return R_t (debt instrument)
- tau_k0: initial capital tax, restricted to be small/near zero to keep the Ramsey Problem nontrivial
- S_it / S_t: lump-sum transfers to individual agents in Judd's heterogeneous-agent extension (S_it >= 0), aggregated as S_t, entering government budget g_t+S_t = tax revenue

### [COMPUT] Metodo computacional

None — purely analytical derivation via Lagrangian methods and steady-state characterization; no numerical solution, calibration, or software mentioned in this file.

### Intuicion general

Capital is the reproducible factor of production: extra investment today raises output — and hence consumption and wages — for everyone in the future, including workers who own no capital, because the marginal product of labor rises with the capital stock. Because a capital tax distorts the intertemporal margin cumulatively (compounding via the Euler equation), and because the government would like to exploit this margin as much as possible in the short run, the only way this is consistent with the household's own steady-state Euler equation is if the long-run distortion vanishes entirely — hence tau_k = 0 in the steady state. The multipliers theta_t (value of an extra unit of resources) and psi_t (value of an extra unit of government revenue) formalize this trade-off. Judd's contribution is to show that this conclusion is not an artifact of a representative agent: even a purely redistributive planner (caring only about non-capital-owning workers) still finds it optimal not to tax capital in the long run, financing all government spending from labor income taxes instead — provided all agents discount the future at the same rate.

### Ejemplos y ejercicios

- Judd's extreme two-class economy: workers (no savings, c_1t = bar w_t n_1t + S_1t) versus capitalists (no labor, c_2t + k_2,t+1 - (1-delta)k_2t = tilde r_t k_2t + S_2t), with the Ramsey planner weighting only workers (alpha_1 > alpha_2 = 0); shown to be a special case of the general N-agent framework and to deliver the same tau_k = 0 result.

### Anotaciones a mano (tuyas)

- Slide 3 (Ramsey Problem bullets): highlighted 'dynamic optimal taxation', 'Ramsey Problem', 'No uncertainty', 'the government commits...will not deviate from tax plan announced today', and 'capital should not be taxed in long run'.
- Slide 6 (Households budget constraint): marginal handwritten note in Spanish next to the b_{t+1}/R_t - b_t term: 'Intercambio entre personas y gob[ierno]' (exchange/trade between people and the government).
- Slide 12 (Competitive equilibrium definition): highlighted the two defining conditions of competitive equilibrium (household/firm optimization given prices and policy; government budget satisfied given allocation and prices).
- Slide 15 (Ramsey Lagrangian): handwritten marginal notes including 'Quiero resolver un EC con t*' (I want to solve a CE with t*), a sticky-note icon, and a partly illegible note near the capital FOC about how the derivation would change under a different solution concept ('Solo...','Planif[icador]').
- Slide 16 (Interpretation): highlighted that theta_t and psi_t are positive multipliers representing the marginal value of an extra unit of production and of an extra unit of government revenue, respectively.
- Slides 17-18 (steady-state derivation): highlighted the key assumptions (g_t constant after T; Ramsey solution converges to steady state) and the final conclusion 'tax rate on capital earnings must be zero' plus 'result robust to eliminating government debt'.
- Slide 19 (Judd 1985): highlighted 'explores limits to redistribution', 'same discount factor (below: what would happen otherwise?)', and 'balanced budget (can change that, result same)'.
- Slide 20 (households, net taxes): highlighted 'All households face same prices and taxes'; sticky-note icon on the net-tax budget constraint; partly illegible marginal note about 'majoro' costs/imports near the definition.
- Slide 24 (N-agent steady state): highlighted 'derivative has same structure as with one agent, plus two terms that come from individual budget constraint' and the final 'r = tilde r, which again implies tau_k = 0'.
- Slide 25 (two-class case): highlighted the full worked special case and the caveat, with a handwritten question mark next to 'Result breaks down if discount factors different for each agent (beta_i != beta_j), as Euler equation would hold for only 1 agent.'

### Conexiones con otros temas

- Directly continues in the Second Part with the 'primal' approach (eliminating prices and taxes entirely) to re-derive the same tau_k=0 result via a different, more general method.
- The closing 'Comments' about an untaxed, non-reproducible factor (land-like) sets up the Correia (1996) extension worked out fully in the Second Part, where tau_k=0 breaks down.
- Foundational reference: Chamley (1986) and Judd (1985) — the classic zero-capital-income-tax result in dynamic optimal taxation.

---

## Optimal Fiscal Policy with Commitment — Second Part: the primal approach to the Ramsey Problem, the Implementability Condition, and Correia's (1996) incomplete-taxation extension

*Fuente: `Macro_Din_II_Topic2.3SecondPartFINALVERSION.pdf`*

*Secciones: Before we continue: why lump-sum taxes are ruled out | Why is it Ramsey-optimal to have tau_k=0? (intuition) | Primal approach to the Ramsey Problem (definition, contrast with Chamley's dual approach) | Intertemporal budget constraint via consolidation of sequential constraints; No-Arbitrage Condition; Transversality Conditions | Household's present-value budget constraint with Arrow-Debreu prices q_t | Steps of the Primal approach (Steps 0-3 overview) | Step 1: household FOCs restated in terms of q_t; NAC in intertemporal-price form; firm FOCs | Step 2: Implementability Condition (IC) derivation | Step 3: the V(c,n,Phi) function and the Ramsey Lagrangian J; first-order conditions | Step 4: steady-state derivation of tau_k=0 via the primal approach | Comments: interpretation of the multiplier Phi as the welfare cost of distortionary taxation | An example where tau_k=0 breaks down: Incomplete taxation (Correia 1996) — the untaxed factor z_t | Derivation of the steady-state formula for tau_k under incomplete taxation | Closing comments: what is the empirical counterpart of the untaxed factor Z?*

### Supuestos

> Same underlying economy as in Chamley's (First Part) setup; government can issue debt
>
> Lump-sum taxes ruled out (recap from First Part) — otherwise the Ramsey Problem is trivially solved by setting all distortionary taxes to zero
>
> Correia (1996): production F(k_t,n_t,z_t) has constant returns to scale with strictly positive, decreasing marginal returns
>
> Correia (1996): z_t is inelastically supplied, z_t = Z (fixed) for all t
>
> Correia (1996): factor z priced competitively, p_zt = F_zt (profit maximization)
>
> Ramsey Problem's solution assumed to converge to a steady state (both in the baseline primal model and in the Correia extension)
>
> tau_k0 fixed/given as in the First Part
>

### Conceptos clave

- **Primal approach** - Eliminate all prices and taxes from the Ramsey Problem; the government instead chooses a feasible allocation directly, subject to a constraint (the Implementability Condition) that guarantees the existence of supporting prices and taxes consistent with a competitive equilibrium.
- **Arrow-Debreu price** - q_t = prod_{i=0}^{t-1} R_i^{-1}, with q_0=1; the intertemporal price of one unit of the consumption good delivered at date t, relative to date 0.
- **Implementability Condition (IC)** - The single intertemporal restriction sum_t beta^t (u_ct c_t - u_lt n_t) - A = 0 obtained by substituting the household's and firm's first-order conditions (which express prices and taxes as functions of allocations) into the household's present-value budget constraint.
- **V(c_t,n_t,Phi)** - Auxiliary function V = u(c_t,1-n_t) + Phi(u_c(t)c_t - u_l(t)n_t) used so that maximizing the discounted sum of V subject to feasibility (ignoring the constant A) is equivalent to maximizing utility subject to the IC.
- **Phi (multiplier on IC)** - Nonnegative Lagrange multiplier on the Implementability Condition; measures the utility cost to the household of the government having to raise revenue via distortionary taxes. Phi=0 makes the Ramsey Problem equivalent to the (undistorted) Planner's Problem / competitive equilibrium.
- **Incomplete taxation (Correia 1996)** - An extension in which production uses an additional factor z_t that is inelastically supplied (z_t=Z fixed) and whose competitive rental price p_zt=F_zt cannot be taxed by the government; this breaks the standard zero-capital-tax result.

### Teoremas, lemas y proposiciones

> **Primal-approach confirmation of tau_k=0**
>
> Using the primal approach (Steps 1-4), assuming the solution converges to a steady state, the steady-state FOC for capital 1=beta[F_k+(1-delta)] combined with the steady-state No-Arbitrage Condition 1/beta=(1-tau_k)F_k+1-delta implies tau_k=0.
>
> *Supuestos requeridos:* Same underlying neoclassical growth economy as Chamley's setup (govt can issue debt); Steady state exists
>
> *Garantiza:* tau_k = 0, confirming the Chamley/Judd result via an alternative (primal) method.

> **Correia (1996): steady-state capital tax under incomplete taxation**
>
> When an inelastically supplied, untaxed factor Z enters production, the steady-state optimal capital tax is tau_k = Phi u_c F_zk Z / (theta F_k), where F_zk is the cross-partial derivative of F with respect to z and k.
>
> *Supuestos requeridos:* F(k,n,z) constant returns to scale, strictly positive and decreasing marginal returns; z_t = Z fixed (inelastically supplied); Factor z priced competitively at p_zt = F_zt; Steady state exists
>
> *Garantiza:* tau_k is generally nonzero; its sign is determined entirely by the sign of F_zk (since Z>0, u_c>0, Phi>0, theta>0, F_k>0). tau_k = 0 only when F_zk = 0. For Cobb-Douglas technology, F_zk > 0, so tau_k > 0.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Consolidated intertemporal budget (illustrative, before iterating) | `c_t+\frac{c_{t+1}}{R_t}+\frac{k_{t+2}}{R_t}+\frac{b_{t+2}}{R_tR_{t+1}}=b_t+\ldots` | Two consecutive sequential budget constraints combined, eliminating debt one period at a time. | Building block for the full present-value budget constraint via iteration. |
| Transversality conditions | `\lim_{T\to\infty}\left(\prod_{i=0}^{T-1}R_i^{-1}\right)k_{T+1}=0;\qquad \lim_{T\to\infty}\left(\prod_{i=0}^{T-1}R_i^{-1}\right)\frac{b_{T+1}}{R_T}=0` | Standard no-Ponzi / optimality conditions ensuring the consolidated constraint is valid as T -> infinity. | Used to eliminate all terms related to the choice of capital tomorrow when iterating the budget constraint. |
| Household present-value budget constraint (Arrow-Debreu form) | `\sum_{t=0}^{\infty}q_tc_t=\sum_{t=0}^{\infty}q_t(1-\tau_{nt})w_tn_t+[(1-\tau_{k0})r_0+1-\delta]k_0+b_0,\qquad q_t=\prod_{i=0}^{t-1}R_i^{-1},\ q_0=1` | The household's entire lifetime budget expressed with Arrow-Debreu prices q_t, having imposed the No-Arbitrage Condition to eliminate k_{t+1} terms. | Starting point (Step 0) of the primal approach. |
| Step 1: household FOCs (present-value form) | `\beta^tu_{ct}=\lambda q_t;\quad \beta^tu_{lt}=\lambda q_t(1-\tau_{nt})w_t\ \Rightarrow\ q_t=\beta^t\frac{u_{ct}}{u_{c0}};\quad (1-\tau_{nt})w_t=\frac{u_{lt}}{u_{ct}}` | Household FOCs w.r.t. c_t, n_t for the present-value problem with multiplier lambda; evaluated at t=0 with q_0=1 gives lambda=u_c0. | Express prices q_t and after-tax wages as functions of allocations only. |
| No-arbitrage in intertemporal prices | `\frac{q_t}{q_{t+1}}=(1-\tau_{k,t+1})r_{t+1}+1-\delta` | Rewritten version of the original NAC R_t=(1-tau_kt+1)r_t+1+1-delta using Arrow-Debreu prices. | Combined with firm FOCs to price capital income taxes. |
| Firm FOCs | `F_{kt}=r_t;\quad F_{nt}=w_t` | Competitive factor pricing. | Substituted together with household FOCs into the present-value budget constraint. |
| Step 2: substituted intertemporal budget constraint | `\sum_{t=0}^{\infty}\beta^t\frac{u_{ct}}{u_{c0}}c_t=\sum_{t=0}^{\infty}\beta^t\frac{u_{ct}}{u_{c0}}\frac{u_{lt}}{u_{ct}}n_t+\{[(1-\tau_{k0})F_{k0}+1-\delta]k_0+b_0\}=0` | Budget constraint with all prices/taxes replaced by allocation-based expressions. | Intermediate step toward the Implementability Condition. |
| Definition of A | `A\equiv u_{c0}\{[(1-\tau_{k0})F_{k0}+1-\delta]k_0+b_0\}` | Collects all initial-condition terms (k_0, b_0, tau_k0) into a single constant. | Simplifies the Implementability Condition. |
| Implementability Condition (IC) | `\sum_{t=0}^{\infty}\beta^t(u_{ct}c_t-u_{lt}n_t)-A=0` | The single constraint (obtained by multiplying the Step-2 budget by u_c0) that the primal-approach Ramsey Problem must respect in place of individually tracking prices and taxes. | Core constraint of the primal Ramsey Problem, together with feasibility. |
| V(c,n,Phi) and Ramsey Lagrangian | `V(c_t,n_t,\Phi)\equiv u(c_t,1-n_t)+\Phi(u_c(t)c_t-u_l(t)n_t);\qquad \mathcal{J}=\sum_{t=0}^{\infty}\beta^t\{V(c_t,n_t,\Phi)+\theta_t[F(k_t,n_t)-c_t-k_{t+1}+(1-\delta)k_t-g_t]\}-\Phi A` | Reformulates the primal Ramsey Problem: maximize J over {c_t,n_t,k_{t+1}} and Phi, given k_0, b_0, tau_k0. | Step 3 of the primal approach. |
| First-order conditions of J | `c_t:\ V_{ct}=\theta_t;\quad n_t:\ V_{nt}=-\theta_tF_{nt};\quad k_{t+1}:\ \theta_t=\beta\theta_{t+1}[F_{k,t+1}+1-\delta];\quad c_0:\ V_{c0}=\theta_0+\Phi A_c;\quad n_0:\ V_{n0}=-\theta_0F_{n0}+\Phi A_n` | System of FOCs (six equations) determining {c_0,n_0,{c_t,n_t,k_t}_{t=1}^{\infty},\Phi}. Capital FOC can be rewritten as V_{ct}=\beta V_{c,t+1}[F_{k,t+1}+1-\delta]. | Solve the primal Ramsey Problem. |
| Step 4: steady-state tau_k derivation | `1=\beta[F_k+(1-\delta)]\ \text{(FOC)};\qquad \frac{q_t}{q_{t+1}}=(1-\tau_{k,t+1})F_{k,t+1}+1-\delta\ \text{(NAC, steady state:}\ 1/\beta=(1-\tau_k)F_k+1-\delta)\ \Rightarrow\ \tau_k=0` | Comparing the steady-state capital FOC with the steady-state NAC pins down tau_k=0, matching Chamley's dual-approach result. | Final result of the baseline primal-approach model. |
| Correia (1996): Implementability Condition with extra factor | `\sum_{t=0}^{\infty}\beta^t\{u_{ct}c_t-u_{lt}n_t-u_{ct}F_{zt}Z\}-A=0` | IC augmented with the revenue stream from the untaxed factor Z, sum_t q_t p_zt Z, converted to allocation terms via u_ct F_zt Z. | Primal Ramsey Problem in the incomplete-taxation extension. |
| V(c,n,k,Phi) with untaxed factor | `V(c_t,n_t,k_t,\Phi)=u(c_t,1-n_t)+\Phi(u_{ct}c_t-u_{lt}n_t-u_{ct}F_{zt}Z)` | Now depends explicitly on k_t (through F_zt=F_z(k_t,n_t,Z)), unlike the baseline V(c,n,Phi). | Reformulated Lagrangian for the Correia extension. |
| Lagrangian and capital FOC (Correia extension) | `\mathcal{J}=\sum_{t=0}^{\infty}\beta^t\{V(c_t,n_t,k_t,\phi)+\theta_t[F(k_t,n_t)-c_t-k_{t+1}+(1-\delta)k_t-g_t]\}-\phi A;\qquad \theta_t=\beta V_{k,t+1}+\beta\theta_{t+1}[F_{k,t+1}+1-\delta]` | Because V now depends on k_t, an extra term V_{k,t+1} appears in the FOC for k_{t+1} relative to the baseline model. | Derive the steady-state formula for tau_k. |
| Steady-state derivation of tau_k under incomplete taxation | `\theta=\beta V_k+\beta\theta[F_k+(1-\delta)]\ \Rightarrow\ 1=\beta[F_k+(1-\delta)]+\frac{\beta}{\theta}V_k;\qquad \text{NAC steady state: } 1=\beta[(1-\tau_k)F_k+(1-\delta)];\qquad \Rightarrow\ \frac{\beta}{\theta}V_k=-\beta\tau_kF_k\ \Rightarrow\ \tau_k=-\frac{V_k}{\theta F_k}` | Combines the steady-state FOC and NAC to isolate tau_k as a function of V_k. | Final formula derivation step. |
| V_k and final tau_k formula | `\frac{\partial V}{\partial k_t}=-\Phi u_{ct}F_{zkt}Z\quad\Rightarrow\quad \tau_k=\frac{\Phi u_cF_{zk}Z}{\theta F_k}` | The steady-state optimal capital tax under incomplete taxation, expressed in terms of the cross-partial F_zk, the untaxed factor endowment Z, and the multipliers Phi and theta. | Sign and magnitude of tau_k in the presence of an untaxed factor; tau_k=0 iff F_zk=0; for Cobb-Douglas, F_zk>0 so tau_k>0. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Production remains a generic function F(k_t,n_t) in the baseline primal model (no Cobb-Douglas/CES specified), extended to F(k_t,n_t,z_t) with constant returns to scale in the Correia extension (Cobb-Douglas invoked only at the very end, as an example, to sign F_zk). Labor demand: firm FOC F_nt=w_t (unchanged from First Part). The labor-supply/consumption-leisure margin is embedded inside the Implementability Condition and the V(c,n,Phi) function: V = u(c,1-n) + Phi(u_c c - u_l n) — the multiplier Phi re-weights marginal utilities of consumption and labor in the planner's effective objective, which is the primal-approach mechanism for encoding the labor-tax distortion, but no specific functional form (GHH, separable CRRA, etc.) or Frisch elasticity value is assumed; u(c,1-n) stays fully generic. The parameter that explicitly governs a factor-substitution/curvature margin in this file is F_zk (the cross-partial between the untaxed factor Z and capital) — analogous in role to a labor-demand curvature parameter but for the Z-k margin rather than the k-n margin; it is what determines whether the derived tau_k is positive, negative, or zero.

### [POLICY] Instrumentos de politica

- tau_kt, tau_nt: capital and labor income tax rates (same instruments as First Part, now eliminated from the problem by the primal approach until Step 4, where tau_k is backed out for the steady state)
- b_t: government bonds/debt
- g_t: exogenous government purchases
- Phi: Lagrange multiplier on the Implementability Condition — not a literal tax instrument, but the central object summarizing the shadow cost of all distortionary taxation combined
- p_zt = F_zt: the (implicit, competitive) rental price of the untaxed factor Z in the Correia extension — explicitly NOT taxable by the government, which is the whole point of the exercise

### [COMPUT] Metodo computacional

None — purely analytical Lagrangian/primal-approach derivation of steady-state results; no numerical solution method, calibration, or software is mentioned in this file.

### Intuicion general

The primal approach reduces the entire household optimization problem to one summary constraint (the Implementability Condition), because equilibrium prices and taxes can always be recovered ex post from the allocation via the household's and firm's first-order conditions — there is no need to carry them explicitly. The multiplier Phi on the IC is the shadow price, in utility terms, of financing government spending through distortionary rather than lump-sum taxes; Phi=0 collapses the Ramsey Problem to the frictionless Planner's Problem. In the baseline model the only distortable intertemporal margin is capital, and eliminating it in steady state removes the residual scope for that distortion, giving tau_k=0. Once an untaxed, inelastically supplied factor Z exists (e.g., land), the government gains an indirect way to tax the return to Z's fixed rents by taxing capital, precisely when capital and Z are not additively separable in production (F_zk != 0); this reopens a channel that makes taxing capital welfare-improving even in steady state, restoring tau_k != 0.

### Ejemplos y ejercicios

- Correia (1996) example with an inelastically supplied factor Z (interpreted as land-like) added to production F(k,n,z), yielding tau_k = Phi u_c F_zk Z/(theta F_k); Cobb-Douglas technology is invoked to sign F_zk > 0 and conclude tau_k > 0.

### Anotaciones a mano (tuyas)

- Slide 3 ('Before we continue'): highlighted 'Recall that to make Ramsey Problem interesting we rule out lump-sum taxes', 'Those taxes do not affect marginal decisions, i.e. they are not distortionary', and 'In real world governments use distortionary taxes.'
- Slide 4 ('Why tau_k=0?'): highlighted 'Capital is the reproducible factor of production' and 'Marginal product of labor increases with capital', with a handwritten marginal insertion clarifying '/labor, i.e. w(K/L)'.
- Slide 5 (Primal approach): highlighted 'Primal approach: now, we eliminate all prices and taxes' and 'Government chooses a feasible allocation subject to constraints that ensure the existence of prices and taxes...consistent with a competitive equilibrium'; a stray handwritten word 'particular' appears near the bottom, likely a partial annotation.
- Slide 6: highlighted 'We use same economy as with Chamley; government can issue debt' and 'All terms related to the choice of capital tomorrow disappear as we impose the No-arbitrage Condition'.
- Slide 7: highlighted the definition 'q_t is the Arrow-Debreu price'.
- Slide 8 (Steps of Primal approach): highlighted throughout; a compressed handwritten shorthand fragment appears near Step 1A (partially legible, resembling multiplier notation); highlighted 'This is how we get the Implementability Condition (IC)' and 'Solve Ramsey Problem by maximizing household's utility subject to feasibility and IC.'
- Slide 12 (Step 3, V and Lagrangian): handwritten annotation reproducing/reworking the Lagrangian by hand, including the boxed word 'FACT' next to a rewritten multiplier expression.
- Slide 15 (Comments on Phi): highlighted the full interpretation of Phi as 'the utility cost of raising government revenue through distorting taxes' and that 'Phi=0 makes the Ramsey Problem equivalent to...the Planner's Problem, and to an undistorted Competitive Equilibrium'; a handwritten shorthand note below (partially legible) reading roughly 'RPI, CNA + CPO-CI'.
- Slide 16 (Correia 1996 intro): highlighted 'Correia (1996) introduces an additional production factor z_t, which is inelastically supplied', 'constant returns to scale, strictly positive decreasing marginal returns', and 'Price of factor z_t is p_zt=F_zt'.
- Slide 17: highlighted rhetorical prompt 'Now k_t appears. Why?' left as a reflection question.
- Slides 19-20 (final derivation): highlighted the full derivation and conclusions 'Tax rate depends on Z>0, u_c>0, Phi>0, theta>0, F_k>0', 'The sign of tau_k is determined by F_zk', 'tau_k is zero only when F_zk=0', and 'For Cobb-Douglas technology, F_zk>0 => tau_k>0 (check)'.
- Final 'Comments' slide (p.21/21): highlighted 'We assumed a factor that cannot be taxed', 'Here we cannot do this. Therefore capital may be taxed.', and the open questions 'What is the empirical counterpart of factor Z? Is it something like land (which is also inelastic)? In the real world there are taxes on land ownership.'

### Conexiones con otros temas

- Direct continuation of the First Part: re-derives the Chamley-Judd tau_k=0 result using the primal method instead of Chamley's dual (after-tax-prices) method.
- The closing 'Comments' explicitly ask what the real-world empirical counterpart of the untaxed factor Z might be, suggesting land (also inelastically supplied) and noting that real-world tax systems do tax land ownership — an open question left for discussion.
- Connects to the broader optimal-taxation literature on why capital taxation might be positive in the long run when some factors cannot be taxed (a qualification to the canonical zero-capital-tax result).

---

## A Monetary Model — First Part: money demand via a shopping-time transaction technology, the Fisher equation, consolidated government budget (fiscal + monetary), and the seigniorage/inflation-tax equilibrium (Sargent-Wallace style)

*Fuente: `Macro_Din_II_Agosto_2018Topic3.1FirstPart(1).pdf`*

*Secciones: Introduction: the transaction-cost motive for holding money | The Model: endowment economy, time allocation between leisure and shopping, utility | Shopping-time technology H(c_t, m_{t+1}/p_t) | Households: sequential budget constraint, consolidation of two periods, no-arbitrage condition | Fisher equation and the real return on money R_mt | Households' Lagrangian and first-order conditions (1)-(4) | Derived relations (5)-(9): shadow price, real interest rate, cost-of-holding-money condition, implicit money demand function | Government: consolidated fiscal + monetary sequential budget constraint (Sargent-Wallace 1981) | Equilibrium definition (price system, allocations, debt, money supply) | Short run vs. long run distinction | Stationary equilibrium characterization | Equilibrium in the long run: the seigniorage/inflation-tax equation and the Laffer curve in R_m | Equilibrium in the short run: determination of the initial price level p_0 | Equilibrium determination procedure (long run first, then short run) | Worked example with CRRA-type utility and a specific H function*

### Supuestos

> Endowment economy with no uncertainty
>
> Representative household has one unit of time, split between leisure and shopping: 1 = l_t + s_t
>
> Single good, divided between private consumption {c_t} and government purchases {g_t}
>
> u_c, u_l > 0; u_cc, u_ll < 0; u_cl >= 0
>
> H >= 0, H_c, H_cc >= 0, H_{m/p} <= 0, H_{m/p,m/p} >= 0, H_{c,m/p} <= 0
>
> b_{t+1} can be positive or negative (government bonds); tau_t is a lump-sum tax; y > 0 constant endowment
>
> m_{t+1} >= 0 (nonnegativity of nominal money holdings), given initial stocks m_0, b_0
>
> No-arbitrage requires i_t >= 0, i.e., R_t >= R_mt
>
> M_0 = m_0, {g_t, tau_t} exogenous
>
> Government budget constraint follows from consolidating the fiscal and monetary branches, per Sargent and Wallace (1981)
>
> Assumed fiscal deficit in the long run: g - tau + B(R-1)/R > 0
>
> tau_0 != tau and B_0 != B allowed at t=0 (short run can differ from the t>=1 stationary values)
>

### Conceptos clave

- **Transaction-cost motive for money** - Money is valued only instrumentally: holding more real balances reduces the time cost (shopping time) needed to acquire consumption goods.
- **Shopping time s_t** - Time devoted to acquiring consumption, s_t = H(c_t, m_{t+1}/p_t), which together with leisure l_t exhausts the unit time endowment: 1 = l_t + s_t.
- **Transaction technology H** - Function mapping consumption and real balances into required shopping time, with H>=0, H_c,H_cc>=0 (more consumption requires more/increasingly more shopping time), H_{m/p}<=0, H_{m/p,m/p}>=0 (more real balances reduce shopping time at a decreasing rate), and H_{c,m/p}<=0 (real balances and consumption are complements in reducing shopping time).
- **Real gross return on money** - R_mt = p_t/p_{t+1}, the inverse of the gross inflation factor; the real return earned by holding a unit of money from t to t+1.
- **Fisher equation** - 1 + i_t = R_t/R_mt: decomposes the gross nominal interest rate into a real return component R_t and an inflationary component 1/R_mt.
- **Money demand function** - Implicit function m_{t+1}/p_t = F(c_t, R_mt/R_t) derived from the household's FOCs (via the Implicit Function Theorem), increasing in both consumption and the (inverse) opportunity cost of holding money.
- **Consolidated government budget constraint (Sargent-Wallace, 1981)** - The government's overall budget combines a fiscal branch (lump-sum taxes tau_t, bonds B_t) and a monetary branch (money stock M_t issuance), as in Sargent and Wallace's classic 1981 'Unpleasant Monetarist Arithmetic' framework.
- **Seigniorage / inflation tax** - Revenue the government raises by printing money, f(R_m)(1-R_m): the tax base is real balances f(R_m), the tax rate is the inflation tax rate (1-R_m), increasing in inflation.
- **Laffer curve for seigniorage** - Seigniorage revenue f(R_m)(1-R_m) is a concave (hump-shaped) function of R_m (equivalently of the inflation rate), implying two values of R_m can generate the same seigniorage revenue — analogous to the standard Laffer curve for conventional tax rates.
- **Stationary equilibrium** - An equilibrium in which inflation p_t/p_{t+1}, the real interest rate R_t=R, consumption c_t=c, and shopping time s_t=s are all constant over time; in this case R = 1/beta from the Euler equation.

### Teoremas, lemas y proposiciones

> **No-arbitrage / Fisher-equation derivation**
>
> Boundedness of household consumption requires 1 - p_t/(p_{t+1}R_t) >= 0, equivalently i_t/(1+i_t) >= 0, i.e., R_t >= R_mt (i_t >= 0).
>
> *Supuestos requeridos:* m_{t+1} >= 0 (nonnegativity of nominal balances)
>
> *Garantiza:* The gross real return on bonds must be at least as large as the gross real return on money; otherwise households could achieve unbounded consumption via unbounded nominal money holdings.

> **Stationary real interest rate**
>
> In a stationary equilibrium with constant lambda_t, the Euler equation R_t = (1/beta)(lambda_t/lambda_{t+1}) collapses to R = 1/beta.
>
> *Supuestos requeridos:* Stationary equilibrium (constant inflation, constant c, constant s)
>
> *Garantiza:* R = 1/beta; consumption is pinned down directly by c = y - g since y,g are exogenous in the endowment economy.

> **Long-run equilibrium determination (Laffer curve equation)**
>
> The long-run consolidated government budget constraint reduces to g - tau + B(R-1)/R = f(R_m)(1-R_m) for all t>=1; given (g,tau,B), this equation determines R_m.
>
> *Supuestos requeridos:* Stationary equilibrium for t>=1; f'(R_m) >= 0 (money demand increasing in R_m); Assumed deficit: g - tau + B(R-1)/R > 0
>
> *Garantiza:* Because the seigniorage function is hump-shaped (Laffer curve), the equation generically has two solutions for R_m; the model/slide states 'we will work with the classic one' without further specifying selection criteria here (elaborated with economic reasoning in the companion handwritten notes, Topic 3.1).

> **Short-run price level determination**
>
> Given R_m (determined in the long run) and M_0 exogenous, the initial price level solves M_0/p_0 = f(R_m) - (g+B_0-tau_0) + B/R.
>
> *Supuestos requeridos:* M_0 = m_0 given; {g_t,tau_t} exogenous
>
> *Garantiza:* p_0 is pinned down residually after R_m is found; the equilibrium is solved in two stages: long run first (find R_m), then short run (find p_0).

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Household utility | `\sum_{t=0}^{\infty}\beta^tu(c_t,l_t),\ 0<\beta<1,\quad u_c,u_l>0,\ u_{cc},u_{ll}<0,\ u_{cl}\ge0` | Lifetime utility over consumption and leisure in the endowment economy. | Household's objective. |
| Time constraint | `1=l_t+s_t` | One unit of time split between leisure and shopping time. | Constraint in household's Lagrangian (multiplier mu_t). |
| Shopping-time technology (example) | `s_t=H\left(c_t,\frac{m_{t+1}}{p_t}\right);\qquad H=\frac{c_t}{m_{t+1}/p_t}\cdot\varepsilon,\ \varepsilon>0` | General transaction technology and a specific parametric example. | Determines the household's demand for real balances. |
| Household sequential budget constraint | `c_t+\frac{b_{t+1}}{R_t}+\frac{m_{t+1}}{p_t}=y-\tau_t+b_t+\frac{m_t}{p_t}` | Consumption plus bond purchases plus new money holdings equals endowment net of lump-sum tax plus existing bond and money holdings. | Household budget in each period; y>0 constant endowment, tau_t lump-sum tax, b_{t+1} can be positive or negative. |
| No-arbitrage condition (bonds vs money) | `1-\frac{p_t}{p_{t+1}}\cdot\frac{1}{R_t}\ge0` | Required for a bounded consumption set; if violated, households could achieve unbounded consumption by holding unbounded nominal balances. | Derivation of the Fisher equation. |
| Real return on money and Fisher equation | `R_{mt}\equiv\frac{p_t}{p_{t+1}};\qquad 1+i_t\equiv\frac{R_t}{R_{mt}};\qquad 1-\frac{p_t}{p_{t+1}R_t}=1-\frac{R_{mt}}{R_t}=1-\frac{1}{1+i_t}=\frac{i_t}{1+i_t}\ge0` | Decomposes the nominal rate into real and inflation components; equivalent no-arbitrage condition requires i_t>=0. | Central pricing relation linking bonds, money and inflation. |
| Household Lagrangian | `L=\sum_{t=0}^{\infty}\beta^t\Big\{u(c_t,l_t)+\lambda_t\Big(y-\tau_t+b_t+\frac{m_t}{p_t}-c_t-\frac{b_{t+1}}{R_t}-\frac{m_{t+1}}{p_t}\Big)+\mu_t\Big(1-l_t-H\big(c_t,\tfrac{m_{t+1}}{p_t}\big)\Big)\Big\}` | Household maximizes utility subject to budget constraint and the time/shopping constraint. | Source of FOCs (1)-(4). |
| FOCs (1)-(4) | `c_t:\ u_{ct}-\lambda_t-\mu_tH_{ct}=0\ (1);\quad l_t:\ u_{lt}-\mu_t=0\ (2);\quad b_{t+1}:\ -\lambda_t\tfrac{1}{R_t}+\beta\lambda_{t+1}=0\ (3);\quad m_{t+1}:\ -\lambda_t\tfrac{1}{p_t}-\mu_tH_{m/pt}\tfrac{1}{p_t}+\beta\lambda_{t+1}\tfrac{1}{p_{t+1}}=0\ (4)` | Interior-solution first-order conditions. | Derive shadow price of wealth, real interest rate, and money demand. |
| Shadow price of wealth | `\lambda_t=u_{ct}-u_{lt}H_{ct}\ (5)` | Marginal utility of consumption net of the marginal disutility of the extra shopping time that consumption requires. | Combine with (3) for the real interest rate. |
| Real interest rate | `R_t=\frac{1}{\beta}\frac{\lambda_t}{\lambda_{t+1}}=\frac{1}{\beta}\frac{u_{ct}-u_{lt}H_{ct}}{u_{ct+1}-u_{lt+1}H_{ct+1}}\ (6)` | Depends on the discount factor and shopping-adjusted marginal utilities. | Determines bond pricing. |
| Cost-of-holding-money condition | `\frac{R_t-R_{mt}}{R_t}\lambda_t=-\mu_tH_{m/p}(t)\ (7);\qquad \left(1-\frac{R_{mt}}{R_t}\right)\left[\frac{u_{ct}}{u_{lt}}-H_c(t)\right]+H_{m/pt}=0\ (8)` | The opportunity cost of holding money (R_t-R_mt) equals the marginal benefit of real balances in reducing shopping time. | Implicitly defines money demand; equation (8) evaluated at l_t=1-H(c_t,m_{t+1}/p_t). |
| Implicit money demand function | `\frac{m_{t+1}}{p_t}=F(c_t,R_{mt}/R_t)\ (9)` | Real balances demanded increase in both consumption and R_mt/R_t (via the Implicit Function Theorem); since R_mt/R_t=1/(1+i_t), real balances fall with the nominal interest rate. | Money demand equation used throughout the equilibrium characterization. |
| Government sequential budget constraint | `g_t=\tau_t+\frac{B_{t+1}}{R_t}-B_t+\frac{M_{t+1}-M_t}{p_t}` | Consolidated fiscal (tau_t,B_t) and monetary (M_t) branches financing government purchases; B_0, M_0>0 given, {g_t,\tau_t} exogenous. | Government budget in equilibrium; cf. Sargent and Wallace (1981). |
| Stationary-equilibrium relations | `p_t/p_{t+1}=R_m,\ \forall t;\quad R_t=R=1/\beta;\quad c_t=c=y-g;\quad m_{t+1}/p_t=F(c,R_m/R)\equiv f(R_m),\ f'(R_m)\ge0` | Definition and implications of a stationary equilibrium. | Reduces the dynamic system to two static equations (long run, short run). |
| Long-run government budget (Laffer-curve equation) | `g-\tau+\frac{B(R-1)}{R}=f(R_m)(1-R_m),\quad \forall t\ge1` | The gross-of-interest deficit g-\tau+B(R-1)/R must equal seigniorage revenue f(R_m)(1-R_m); g-\tau is the primary deficit, f(R_m)(1-R_m) is a concave ('Laffer') function of R_m. | Determine R_m given fiscal stance (g,\tau,B). |
| Short-run government budget (initial price level) | `\frac{M_0}{p_0}=f(R_m)-(g+B_0-\tau_0)+\frac{B}{R}` | Given R_m from the long run and M_0 exogenous, this pins down p_0. | Final step of equilibrium determination. |
| Example functional forms | `u(c_t,l_t)=\frac{c_t^{1-\delta}}{1-\delta}+\frac{l_t^{1-\alpha}}{1-\alpha};\qquad H(c_t,m_{t+1}/p_t)=\frac{c_t}{1+m_{t+1}/p_t}` | CRRA-type utility over consumption and leisure and a specific shopping-time function used for the graphical worked example. | Explicit example to solve the model graphically; no numeric parameter values are assigned. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Not applicable in the standard production sense: this is a pure endowment economy (y fixed, no firms, no production function, no wage, no labor demand). The only 'time allocation' margin is between leisure l_t and shopping time s_t (1=l_t+s_t), where shopping time s_t=H(c_t,m_{t+1}/p_t) is a transaction-cost technology, not a labor-supply/demand relationship. Utility u(c_t,l_t) is left generic (u_c,u_l>0, u_cc,u_ll<0, u_cl>=0 — cross-partial allowed to be nonnegative, not necessarily additively separable); no GHH functional form and no Frisch elasticity are specified or computed. There is no capital-labor substitution parameter (no alpha/CES share) since there is no production function in this file at all — this file is a useful contrast case (a monetary/endowment model with no firms) rather than a source of labor-demand-curvature information.

### [POLICY] Instrumentos de politica

- tau_t: lump-sum tax (fiscal branch), enters household budget (y-tau_t) and government budget g_t=tau_t+B_{t+1}/R_t-B_t+(M_{t+1}-M_t)/p_t
- B_t (or b_t): government bonds/debt, real value, gross return R_t (fiscal branch)
- M_t: nominal money stock (monetary branch), M_0 given exogenously as initial condition
- g_t: government purchases, exogenous stream
- Seigniorage f(R_m)(1-R_m): revenue from money creation, i.e., the inflation tax, with implicit 'tax rate' (1-R_m) and 'tax base' f(R_m) (real money demand)
- Consolidated government budget constraint per Sargent and Wallace (1981), combining fiscal (tau,B) and monetary (M) branches into a single financing constraint

### [COMPUT] Metodo computacional

Graphical/geometric solution method explicitly invoked ('let's solve the equilibrium using a graph. Take notes.'); no numerical software, loglinearization, or calibration procedure is used — the model is solved analytically/graphically via the Implicit Function Theorem (to sign the money demand function) and via inspection of the seigniorage Laffer curve. Explicitly notes the model has two solutions and states the convention of working with the 'classic' one.

### Intuicion general

Money is demanded purely because it saves shopping time; the nominal interest rate is exactly the opportunity cost of holding money (Fisher equation), so money demand falls as this opportunity cost rises. When the fiscal and monetary arms of the government are consolidated into one budget constraint, any structural (primary plus interest) deficit must ultimately be financed by seigniorage — revenue from money creation, an implicit tax on real balances. Because seigniorage revenue is a hump-shaped (Laffer) function of the real return on money R_m, financing a given deficit is generically consistent with two different steady-state inflation rates; the initial price level p_0 is then determined residually, after R_m is pinned down, from the period-0 budget constraint given the historically given nominal money stock M_0.

### Ejemplos y ejercicios

- Worked example with CRRA-type utility u(c,l)=c^{1-delta}/(1-delta)+l^{1-alpha}/(1-alpha) and shopping-time function H=c_t/(1+m_{t+1}/p_t), solved graphically (no explicit numeric parameter values given); the slide flags that the model generically has two solutions for R_m and states the class will work with the 'classic' one, elaborated further in the companion handwritten notes.

### Anotaciones a mano (tuyas)

- No substantive handwritten text annotations or highlighting are visible in the rendered pages of this file (unlike Files 1 and 2); only small unlabeled sticky-note-style icons appear on a few slides (e.g., near the interest-rate/no-arbitrage condition on slide 9, and near equations (7)-(8) on slide 12), with no legible additional content to transcribe.

### Conexiones con otros temas

- Sets up directly the handwritten companion notes 'NotesDynMacroIITopic3.1.pdf', which work out the graphical Laffer-curve equilibrium determination in detail and cover the monetary 'doctrines' (Quantitative Theory, deficits-cause-inflation, fiscal prerequisite of zero inflation, unpleasant monetarist arithmetic) plus Friedman's Optimum Quantity of Money.
- Explicitly cites Sargent and Wallace's classic 1981 paper ('Some Unpleasant Monetarist Arithmetic') as the source of the consolidated government budget constraint.
- Contrasts with the real, non-monetary Ramsey taxation models of Files 1-2 (Topic 2.3): here there is no capital, no labor/firm side — money and government debt/deficits replace capital taxation as the central margin.

---

## Handwritten student lecture notes, Topic 3.1 (October 2020): the seigniorage Laffer curve, graphical determination of the monetary equilibrium, monetary 'doctrines' (Quantitative Theory, deficits-cause-inflation, fiscal prerequisite of zero inflation, unpleasant monetarist arithmetic), and Friedman's Optimum Quantity of Money — a worked graphical companion to the 'Monetary Model' slide deck

*Fuente: `NotesDynMacroIITopic3.1.pdf`*

*Secciones: (1) Seigniorage is a Laffer curve | (2) Graphic solution of the model: government budget for t>=1 and at t=0 | (3) Choosing between the two equilibrium values of R_m | Graphical illustration: moving along the seigniorage curve as the deficit changes | Monetary 'doctrines': (1) Quantitative Theory | Monetary 'doctrines': (2) Deficits cause inflation | Monetary 'doctrines': (3) Fiscal prerequisite of zero inflation (heading only, no graph) | Monetary 'doctrines': (4) Unpleasant [monetarist] arithmetic | Worked example: central bank sells bonds (open-market operation), Spanish annotation | (5) Optimum Quantity of Money (Friedman) | Implementing the Friedman rule: condition on the surplus needed | Graph of the shopping-time function H versus real balances (satiation point psi(c))*

### Supuestos

> Government budget for t>=1 assumed to represent a deficit: g-\tau+B(R-1)/R>0 (boxed/labeled assumption in the notes)
>
> f'(R_m) >= 0 (seigniorage/money-demand function increasing in R_m) taken into account when drawing the t=0 diagram
>
> Example assumes -(g+B_0-\tau_0)+B/R>0, otherwise M_0/p_0 could be negative, contradicting the assumed M_0>0, p_0>=0
>
> There may exist an R_m such that f(R_m)=0 'as in the example in the book' (referenced but not derived here)
>
> At R_m=1, seigniorage=0; for R_m>1, seigniorage<0
>
> To implement the Friedman rule, need g-\tau+B(R-1)/R<0, i.e., a sufficiently large fiscal surplus
>
> An 'extra assumption' on H is needed to generate the kinked/satiated shape shown on the last page (H flat beyond psi(c))
>

### Conceptos clave

- **Seigniorage Laffer curve** - Tax revenue from money creation, plotted as a function of the tax rate (or equivalently of R_m), rises then falls — there exists a tax rate that maximizes seigniorage revenue, exactly analogous to a conventional Laffer curve, and this shape can be derived 'with basic microfoundations' (student's own added remark).
- **Government budget diagram (t>=1)** - Graphical device plotting f(R_m)(1-R_m) (seigniorage, hump-shaped in R_m) against a horizontal line at height g-\tau+B(R-1)/R (the gross-of-interest deficit, assumed positive); the equilibrium R_m values are the intersections.
- **Government budget diagram (t=0)** - A second, upward-sloping diagram plotting M_0/p_0 = f(R_m)-(g+B_0-\tau_0)+B/R against R_m, used together with the t>=1 diagram to determine first R_m and then p_0.
- **Equilibrium selection rule (two R_m roots)** - Because the Laffer-shaped seigniorage curve generically crosses a horizontal deficit line twice, there are two admissible steady-state values of R_m; the student's notes argue (informal economic reasoning, not a formal theorem) for selecting the higher R_m (lower steady inflation) root because it has the 'plausible dynamic' that an increase in the gross deficit requires higher seigniorage — which only holds on the upward-sloping (high-R_m) branch of the Laffer curve.
- **Quantitative Theory (doctrine 1)** - In this framework, the money stock M_0 does NOT determine the steady-state real return on money R_m (which is pinned down by the long-run fiscal/seigniorage condition alone); M_0 instead determines the price level p_0, and a proportional change in M_0 produces the same proportional (percentage) change in p_0 — the classic quantity-theoretic neutrality result.
- **Deficits cause inflation (doctrine 2)** - A permanent increase in government debt (B' > B) shifts the required-deficit line up along the seigniorage Laffer curve, generically lowering the equilibrium R_m and thus raising steady-state inflation (since R_m = p_t/p_{t+1}, a lower R_m means higher inflation).
- **Fiscal prerequisite of zero inflation (doctrine 3)** - Heading noted with no accompanying graph or derivation in these notes; flags that achieving zero (or Friedman-optimal) inflation requires a specific fiscal stance.
- **Unpleasant [monetarist] arithmetic (doctrine 4)** - Sargent-Wallace-style result: with higher debt B'>B, satisfying the government budget can require the price level (and money growth path) to adjust in a way that is 'unpleasant' for monetary control — illustrated by both the long-run Laffer diagram and the short-run M_0/p_0 diagram shifting together.
- **Optimum Quantity of Money (Friedman)** - Friedman's welfare argument: since the marginal cost of creating (additional) money is zero, welfare is maximized by driving the opportunity cost of holding money (the nominal interest rate i) to zero — the 'Friedman rule' — because any i>0 imposes a deadweight loss (fall in consumer surplus) relative to the i=0 benchmark.
- **Satiation point psi(c) in the shopping-time function H** - Under an extra assumption on H, the transaction-cost function decreases in real balances m_{t+1}/p_t only up to a threshold psi(c), beyond which H is flat (or slightly increasing more generally) — i.e., there is a satiation level of real balances beyond which extra money holdings no longer reduce shopping time, consistent with implementing the Friedman rule.

### Teoremas, lemas y proposiciones

> **Two-root selection heuristic (student's own informal argument)**
>
> Of the two R_m values solving the steady-state government budget (Laffer curve = deficit line), the higher R_m is chosen because only on that (downward-sloping/high-R_m) branch does an increase in the gross deficit (including interest payments) require higher seigniorage — a 'plausible dynamic'.
>
> *Supuestos requeridos:* Deficit line lies below the peak of the Laffer curve (two intersections exist)
>
> *Garantiza:* Equilibrium selection convention: pick the higher-R_m (lower-inflation) intersection as the relevant steady state.

> **Friedman rule implementation condition**
>
> To implement the Friedman rule R_m = 1/beta (equivalently i=0), the government needs g-\tau+B(R-1)/R < 0, i.e., a sufficiently large fiscal surplus (net of interest).
>
> *Supuestos requeridos:* 1/beta > 1 lies beyond the peak of the seigniorage Laffer curve, on its downward-sloping segment where seigniorage revenue is negative
>
> *Garantiza:* The intersection of the deficit line with the Laffer curve at R_m=1/beta requires the deficit line itself to lie below zero, i.e. a primary-plus-interest surplus, not a deficit.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Long-run government budget identity | `g-\tau+\frac{B(R-1)}{R}=f(R_m)(1-R_m)` | Same long-run equation as in the slide deck (File 3), re-derived graphically here; region '>0' above the horizontal axis corresponds to a deficit (assumption), '<0' below corresponds to R_m>1 giving negative seigniorage. | Core graphical device for all doctrine discussions (1)-(4). |
| Short-run (t=0) government budget | `\frac{M_0}{p_0}=f(R_m)-(g+B_0-\tau_0)+\frac{B}{R}` | Upward-sloping in R_m (given f'(R_m)>=0); example assumes -(g+B_0-\tau_0)+B/R>0 so that M_0/p_0>0 is guaranteed (consistent with M_0>0, p_0>=0). | Determines p_0 once R_m is known from the long-run diagram. |
| Quantity-theory proportionality | `\Delta M_0 \Rightarrow \text{same } \%\Delta \text{ in } p_0` | A given percentage change in the initial money stock produces an equal percentage change in the initial price level, holding R_m fixed (R_m determined independently in the long-run diagram). | Illustrates the Quantitative Theory doctrine. |
| Friedman-rule implementation condition | `R_m=\frac{1}{\beta};\qquad \text{need } g-\tau+\frac{B(R-1)}{R}<0` | To hit the Friedman-optimal R_m=1/beta on the seigniorage Laffer curve (where seigniorage is negative, i.e., beyond the curve's zero-crossing at R_m=1), the government budget line must lie below zero — a sufficiently large fiscal surplus. | Condition for implementing the Optimum Quantity of Money. |
| Inflation rate in terms of R_m | `R_m=\frac{p_t}{p_{t+1}};\qquad \text{inflation rate}=\frac{1}{R_m}-1` | Relates the model's real-return-on-money object R_m to the conventional inflation rate. | Used throughout doctrines (1)-(4) to translate R_m comparisons into inflation comparisons. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Not applicable — this file (entirely about seigniorage, the government budget constraint, monetary doctrines, and the Friedman rule) contains no production function and no labor demand/supply content.

### [POLICY] Instrumentos de politica

- tau, tau_0: lump-sum tax (fiscal branch), tau_0 distinguished from steady-state tau
- B, B_0, B': government bond stock, with B' denoting a higher-debt scenario used in the 'deficits cause inflation' and 'unpleasant arithmetic' examples
- M_0: initial money stock; explicit open-market-operation example where the central bank sells bonds, reducing M_0 and raising B
- R_m: real return on money (equivalently, 1/R_m - 1 = inflation rate) — the key state variable/instrument determined jointly by fiscal stance and monetary policy
- g: government spending, held fixed throughout
- Seigniorage f(R_m)(1-R_m): revenue instrument (inflation tax), tax rate (1-R_m), tax base f(R_m)
- Implicit interest-rate instrument i (Friedman-rule discussion): setting i=0 (R_m=1/beta) is the welfare-maximizing monetary policy stance, feasible only with sufficiently large fiscal surplus

### [COMPUT] Metodo computacional

Purely graphical/diagrammatic solution method — hand-drawn Laffer curves and their intersections with horizontal or upward-sloping 'deficit'/'budget' lines are used to solve for R_m and p_0 in sequence; no numerical computation, calibration, or software is used. This file is explicitly a worked graphical companion to the algebra in File 3 ('Take notes' instruction on that slide deck).

### Intuicion general

The government budget constraint, once seigniorage is plotted as a Laffer curve against R_m, generically intersects any given (positive) deficit line twice; picking between the two roots is an economic judgment call, not a mathematical necessity — the notes argue for the higher-R_m root because it displays the economically sensible comprovative-static property that a bigger deficit requires more seigniorage. Because R_m is pinned down purely by the long-run fiscal stance, the level of the money stock M_0 has no effect on R_m (and hence no real effects) — it only rescales the price level proportionally (Quantitative Theory). Higher government debt (B'>B) shifts the deficit line up, generically lowering the equilibrium R_m and raising long-run inflation ('deficits cause inflation' / 'unpleasant arithmetic'), and can also require an adjustment in the initial price level p_0. Friedman's Optimum Quantity of Money argument treats the nominal interest rate as a pure distortionary 'tax' on real balances relative to their zero marginal cost of creation, so welfare (consumer surplus) is maximized by deflating at the rate of time preference (R_m=1/beta) — but this is fiscally feasible only if the government runs a large enough underlying surplus, since operating on the falling side of the Laffer curve means seigniorage revenue is actually negative.

### Ejemplos y ejercicios

- Central-bank open-market operation, annotated by the student in Spanish: 'Banco Central vende bonos => downarrow M_0, uparrow B' (the central bank sells bonds, reducing money supply and increasing government debt), worked through both the long-run Laffer diagram (B'>B shifts the deficit line up, R_m moves along the curve) and the short-run M_0/p_0 diagram, concluding (circled in red) that in this example the initial price level ends up lower: p_0' < p_0.
- Friedman's graph: nominal interest rate i on the vertical axis against real balances M/p on the horizontal axis, with the area between the i>0 line and the downward-sloping money-demand curve shaded as the 'fall in consumer surplus' (deadweight loss) relative to the i=0 (Friedman-rule) benchmark, where the marginal cost of creating money is zero.

### Anotaciones a mano (tuyas)

- Page 1: blue boxed aside, the student's own added remark: 'We can construct Laffer curve with basic microfoundations.'
- Page 3: handwritten note 'Take into account that f'(R_m) >= 0' and explanatory note about why the example assumes -(g+B_0-\tau_0)+B/R>0 (otherwise M_0/p_0 could be negative, contradicting M_0>0, p_0>=0).
- Page 4: self-posed question and answer, entirely in the student's own words: 'Which one do we choose? The value to the right, with a higher value for R_m, has a plausible dynamic: an increase in the gross deficit (including interest payments) leads to a need for higher seigniorage.'
- Page 9: blue annotation 'Depends on B! => it has to shift', clarifying how the unpleasant-arithmetic diagram responds to a change in debt.
- Page 10: Spanish-language worked example added by the student: 'Banco Central vende bonos => downarrow M_0, uparrow B' (an open-market operation), with numbered steps '(1) B'>B shifts curve upwards' and '(2) R_m' > R_m: movement on curve', concluding with a red-circled result: 'In this example: M_0/p_0' > M_0/p_0 => p_0' < p_0.'
- Page 11: blue annotation clarifying 'inflation rate is 1/R_m - 1' and 'In this example, price level is initially lower, and "inflation" 1/R_m is higher.'
- Page 12 (Friedman's graph): blue annotation labeling the shaded region under the money-demand curve above i>0 as 'Fall in consumer surplus', and a handwritten note 'Marginal cost of creating money = 0' at the base of the diagram.
- Page 13: underlined handwritten conclusion: 'To implement Friedman need R_m=1/beta. Need g-\tau+B(R-1)/R<0. I.e. need a sufficiently large surplus.'
- Page 14: cross-referencing note 'Graph for p.14 in the slides (extra assumption for H)' and '(More generally, H: ...)' tying this handwritten page directly back to the transaction-technology graph in the companion slide deck (File 3).

### Conexiones con otros temas

- Direct graphical/worked-example companion to 'Macro_Din_II_Agosto_2018Topic3.1FirstPart(1).pdf' ('A Monetary Model — First Part'): reuses the same long-run and short-run government budget equations and the same shopping-time function H(c,m'/p), including an explicit cross-reference on the last page ('Graph for p.14 in the slides, extra assumption for H').
- Introduces Friedman's Optimum Quantity of Money and the classic monetary-policy 'doctrines' (Quantitative Theory, deficits-cause-inflation, fiscal prerequisite of zero inflation, unpleasant monetarist arithmetic) associated with Sargent and Wallace (1981), building directly on that paper cited in File 3.
- The satiation-point graph of H versus real balances on the final page operationalizes the Friedman-rule discussion by showing what property of the transaction-cost technology is needed for the marginal benefit of money to vanish at a finite level of real balances.

---

## Monetary economics — shopping-time money-in-the-utility model (Topic 3.1 Second Part: monetary-policy applications — quantitative theory of money, deficits/seigniorage, unpleasant monetarist arithmetic, optimal quantity of money/Friedman rule; Topic 3.2: Ramsey-optimal monetary policy with labor supply and distortionary taxation in the shopping-time model). Representative-agent, deterministic monetary model — not RBC/New Keynesian/SOE/heterogeneous-agent/search.

*Fuente: `Macro_Din_II_Agosto_2018Topic3.1SecondPartand3.2.pdf`*

*Secciones: Monetary ideas (roadmap) | Quantitative Theory of Money | QTM in the shopping-time model (long-run/short-run graphs) | Deficits cause inflation | Fiscal prerequisites of zero inflation | Unpleasant Monetarist Arithmetic (Sargent & Wallace 1981) | Open-market operation in the shopping-time model | Optimum quantity of money (Friedman rule) | Implementation of Friedman's rule in the shopping-time model | Phelps' critique to Friedman | Model with labor supply (household, firm/technology, feasibility, time constraint) | Household's sequential and present-value budget constraints | Ramsey Problem setup (elimination of prices/taxes, Implementability Condition) | Ramsey plan: Lagrangian and FOCs | Proof that Friedman's rule is Ramsey-optimal (cases on nu)*

### Supuestos

> B>0 (real value of public debt must equal PV of net-of-interest government surplus)
>
> Extra assumption: for all c there exists m_{t+1}/p_t=\psi(c) such that H_{\widehat m_{t+1}}=0 for m_{t+1}/p_t \ge \psi(c) (existence of a satiation point)
>
> \nu \ge 0 (degree of homogeneity of shopping technology H)
>
> u_c,u_l>0;\ u_{cc},u_{ll}<0;\ u_{cl}\ge 0 (utility curvature/cross-partial used in the Friedman-rule proof)
>
> b_0=m_0=0 (initial conditions for the Ramsey plan)
>
> Transversality conditions: \lim_{T\to\infty} q_T \frac{b_{T+1}}{R_t}=0 and \lim_{T\to\infty} q_T \widehat m_{T+1}=0
>

### Conceptos clave

- **Quantitative Theory of Money** - P_t = v_t M_t / Y_t; if velocity v_t and real expenditure Y_t are constant and independent of the quantity of money, a change in money supply leads to a proportional change in the price level.
- **Seigniorage / inflation tax** - Revenue the government raises by creating money. Higher deficits must be financed with higher seigniorage, higher seigniorage requires more inflation, and the resulting inflation tax more than compensates the reduction in real money demand it causes.
- **Fiscal prerequisites of zero inflation** - The fiscal stance (spending, debt, taxes) consistent with R_m=1 (pi=0): real government debt must equal the present value of primary (net-of-interest) surpluses, B = sum_t R^{-t}(tau-g).
- **Unpleasant Monetarist Arithmetic (Sargent & Wallace 1981)** - Paradox in which a contractionary open-market sale (lower M, higher B) can raise the permanent/stationary inflation rate, because the extra debt burden requires more future seigniorage even though it can lower the price level today.
- **Optimum quantity of money / Friedman rule** - Optimal monetary policy sets the nominal interest rate to zero (satiates real money balances), because the marginal social cost of printing money is near zero while the marginal private cost of holding money (i>0) is positive.
- **Satiation point** - Level of real balances m-hat >= psi(c) beyond which the marginal product of money in the shopping technology, H_m-hat, is zero (extra assumption needed for a well-defined Friedman-rule allocation).
- **Ramsey Problem (primal approach)** - The planner chooses allocations directly, subject to an Implementability Condition (household optimality embedded as a single intertemporal constraint) and to resource feasibility, instead of choosing tax/policy instruments directly.
- **Arrow-Debreu price q_t** - Date-0 price of one unit of the consumption good delivered at date t: q_t = prod_{i=0}^{t-1} R_i^{-1}, q_0=1.

### Teoremas, lemas y proposiciones

> **Ramsey-optimality of Friedman's rule in the shopping-time model with homogeneous transaction technology**
>
> If the shopping-time technology H(c,m-hat) is homogeneous of degree nu>=0 and, for every consumption level c, there exists a finite satiation point m-hat=psi(c) at which H_m-hat=H=0, then the unique solution to the Ramsey planner's first-order condition for real balances is H_{m-hat,t+1}=0 for all t — the economy is satiated with real balances and the Friedman rule (R_m=1/beta, i=0) is optimal.
>
> *Supuestos requeridos:* nu >= 0 (degree of homogeneity of H); u_c, u_l > 0; u_cc, u_ll < 0; u_cl >= 0 (curvature/cross-partial assumption used in the proof); existence, for every c, of a finite satiation point psi(c)
>
> *Garantiza:* Proved by exhaustive cases on nu: nu>1 forces multipliers phi and theta_t to be zero or of opposite sign, but phi>0 and theta_t>0 by insatiability — contradiction unless H_m-hat=0; nu=1 forces theta_t=0, contradicting theta_t>0; nu in [0,1) leads, after substitution, to a contradiction with u_c,u_l>0, u_cc,u_ll<0, u_cl>=0 unless H_m-hat=0. Hence Friedman's rule is Ramsey-optimal for any nu>=0 in this economy — the professor stresses this optimality is an example, not a fully general result across all monetary models.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Quantitative theory of money | `P_t = \frac{v_t M_t}{Y_t}` | price level as a function of velocity, money supply and real expenditure | long-run neutrality-of-money analysis; effect of a change in M on P |
| Fiscal prerequisites of zero inflation (govt. budget constraint, t>=1) | `g - \tau + \frac{B(R-1)}{R} = f(R_m)(1-R_m)` | government budget constraint relating primary deficit, real debt service, and seigniorage revenue f(R_m)(1-R_m) | finding fiscal policy consistent with a given long-run inflation/R_m |
| Present-value debt condition for pi=0 | `B = \frac{R}{R-1}(\tau-g) = \sum_{t=0}^{\infty} R^{-t}(\tau-g)` | real government debt equals present value of primary surpluses when R_m=1 | checking fiscal prerequisites for a zero-inflation steady state (assumes B>0) |
| Money's rate of return vs nominal rate | `\frac{R_m}{R} = \frac{1}{1+i}` | relation linking the real return on money R_m, the real interest rate R and the nominal interest rate i | translating between R_m and i in the shopping-time model |
| Fisher equation and Friedman rule | `1+i=(1+r)(1+\pi) \;\Longrightarrow\; \pi=-r \text{ when } i=0` | under the Friedman rule (i=0), the optimal inflation rate equals minus the real interest rate (deflation) | deriving the inflation implication of the Friedman rule |
| Friedman-rule value of R_m | `R_m=\frac{1}{\beta} > 1` | the gross return on money that implements the Friedman rule | target value the government must attain via fiscal policy |
| Government surplus condition to attain any R_m in (1,1/beta) | `g-\tau+\frac{B(R-1)}{R} < 0` | a sufficiently large gross-of-interest fiscal surplus is required (low spending, low debt, high taxes) | implementing an arbitrarily high R_m, in particular the Friedman-rule value |
| Shopping technology homogeneity | `s_t=H(c_t,\widehat m_{t+1})=c_t^{\nu} H\!\left(1,\frac{\widehat m_{t+1}}{c_t}\right) \ \forall c_t>0` | shopping time as a homogeneous-of-degree-nu function of consumption and real balances | deriving the money-demand/shopping-time relation and its role in the Ramsey proof |
| Euler's theorem applied to H | `\nu H(c,\widehat m) = H_c c + H_{\widehat m}\widehat m` | decomposition of H implied by its homogeneity degree | simplifying the Implementability Condition |
| Household sequential budget constraint | `c_t+\frac{b_{t+1}}{R_t}+\frac{m_{t+1}}{p_t}=(1-\tau_t)(1-l_t-s_t)+b_t+\frac{m_t}{p_t}` | period budget constraint with real wage normalized to 1 and labor tax tau_t | deriving the household's present-value budget constraint |
| Household present-value budget constraint (eq. 1) | `\sum_{t=0}^{\infty} q_t\left(c_t+\frac{i_t}{1+i_t}\widehat m_{t+1}\right)=\sum_{t=0}^{\infty} q_t(1-\tau_t)(1-l_t-s_t)+b_0+\widehat m_0` | lifetime budget constraint after substituting s_t=H(c_t,\widehat m_{t+1}) | setting up the Ramsey/primal approach |
| FOCs of household problem (2)-(4) | `(2)\ \beta^t u_{c_t}-\lambda q_t[(1-\tau_t)H_{c_t}+1]=0;\quad (3)\ \beta^t u_{l_t}-\lambda q_t(1-\tau_t)=0;\quad (4)\ -\lambda q_t\left[(1-\tau_t)H_{\widehat m_{t+1}}+\frac{i_t}{1+i_t}\right]=0` | first-order conditions with respect to c_t, l_t, m-hat_{t+1} | eliminating prices and taxes from the budget constraint to build the Implementability Condition |
| Consumption-leisure equation | `\frac{u_{l_t}}{1-\tau_t}=u_{c_t}-u_{l_t}H_{c_t}` | intratemporal optimality condition combining (2) and (3) | eliminating tau_t from the household problem |
| Implementability Condition | `\sum_{t=0}^{\infty}\beta^t\Big[(u_{c_t}-u_{l_t}H_{c_t})c_t-u_{l_t}H_{\widehat m_{t+1}}\widehat m_{t+1}-u_{l_t}\big(1-l_t-H(c_t,\widehat m_{t+1})\big)\Big]=0` | single intertemporal constraint summarizing all household optimality + budget conditions, price/tax-free | replacing individual household FOCs in the Ramsey problem |
| Ramsey problem | `\max \sum_{t=0}^{\infty}\beta^t u(c_t,l_t) \text{ s.t. Implementability Condition (mult. }\phi\text{) and } 1-l_t-H(c_t,\widehat m_{t+1})=c_t+g_t \text{ (mult. }\theta_t\text{)}` | planner's problem choosing allocations to maximize utility subject to implementability and feasibility | deriving optimal (Ramsey) monetary/fiscal policy |
| Feasibility / technology | `y_t=c_t+g_t,\qquad y_t=n_t` | output equals consumption plus government spending; output equals labor input (linear technology, no capital) | closing the resource constraint of the model |
| Time constraint | `1=l_t+s_t+n_t` | time is allocated between leisure, shopping time and labor | defining the household's time-use restriction |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Labor enters only through a linear technology y_t=n_t (output equals labor input directly; no capital, no Cobb-Douglas/CES production function in this model). There is no separate 'labor demand' condition of the W=(1-alpha)Y/N type because the real wage is normalized to 1 and there is no diminishing marginal product of labor here. The household allocates time 1=l_t+s_t+n_t among leisure l_t, shopping time s_t=H(c_t,m-hat_{t+1}), and labor n_t; income is (1-tau_t)(1-l_t-s_t) at wage 1, net of labor tax tau_t. Utility u(c_t,l_t) is left in general (not necessarily separable) form with only sign/curvature assumptions (u_c,u_l>0; u_cc,u_ll<0; u_cl>=0) — not GHH, no explicit Frisch elasticity computed. The one parameter that governs curvature/substitution in this model is nu, the degree of homogeneity of the shopping-time technology H(c,m-hat) in consumption and real balances; it determines how shopping time and money demand respond to consumption, and it is exactly the parameter for which the Friedman-rule optimality proof is shown to hold for any nu>=0.

### [POLICY] Instrumentos de politica

- tau_t — proportional tax on labor/time income (1-tau_t)(1-l_t-s_t), the sole tax in the household budget constraint
- g, g_t — government spending (exogenous)
- B — real government debt/bonds; b_{t+1} sequential bond holdings
- R_t — gross real interest rate on bonds
- R_m, R_{mt} — gross real return on money
- M_t, M_0, M_0' — money supply/monetary base (moved by open-market operations)
- i_t — nominal interest rate; Fisher relation 1+i_t=(1+r_t)(1+pi_t)
- Seigniorage / inflation tax (implicit instrument via money creation)
- tau_0, tau — tax-rate levels referenced in the fiscal-prerequisite and Ramsey conditions
- Extension flagged but not modeled here: distortionary (vs lump-sum) taxation — Phelps / Mulligan & Sala-i-Martin

### [COMPUT] Metodo computacional

Primarily analytical/graphical: long-run and short-run graph analysis of the shopping-time model (shifting curves to trace the effects of changes in M_0, B, R_m); the Ramsey optimal-policy result is derived purely analytically via a Lagrangian and a case-by-case algebraic proof — no numerical/computational solution method is used in this chunk.

### [CALIB] Objetivos de calibracion

- Mulligan & Sala-i-Martin (1997, JMCB): under distortionary taxation, the Ramsey-optimal inflation rate is small but strictly positive, around 1% — cited as an illustrative quantitative finding, not a calibration performed in these slides.

### Intuicion general

The shopping-time model nests classic quantity-theory logic (long-run money neutrality) but also captures fiscal-monetary interaction: because the government budget constraint links debt, deficits and seigniorage, a fiscal authority running primary deficits forces the monetary authority into inflationary finance ('deficits cause inflation'), and a debt-financed contraction of money today can paradoxically raise long-run inflation ('unpleasant monetarist arithmetic') because it raises the future financing burden. On the normative side, since printing money is nearly costless for the government but costly for households to hold at i>0, welfare is maximized by satiating money demand — the Friedman rule — unless the revenue needed for g must be raised with distortionary (not lump-sum) taxes, in which case Phelps' critique implies a strictly positive (but small, ~1%) optimal inflation rate.

### Ejemplos y ejercicios

- Two countries with identical fiscal parameters (tau_0,tau,g,B,B_0) but different initial money M_0'=lambda*M_0, lambda>0: because R_m does not depend on M_0, the long-run graph is unchanged and P_0'=lambda*P_0 (pure QTM scaling of the short-run graph).
- Open-market sale at t=0 (decrease in M_1, increase in B, fiscal variables tau_0,tau held constant): analyzed first in the long-run graph (stationary inflation unambiguously rises) then in the short-run graph (two offsetting effects on M_0/p_0; class exercise: draw the case where p_0 falls, illustrating the 'paradox').

### Anotaciones a mano (tuyas)

- Slide 6 ('Deficits cause inflation'): all three bullets highlighted in teal — 'Higher deficit needs to be financed with higher seigniorage', 'Higher seigniorage requires more inflation', 'Higher inflation tax more than compensates reduction in demand for real balances.'
- Slide 7 ('Fiscal prerequisites of zero inflation'): the '(check)' derivation prompt and the bottom bullets ('Assume B>0…', 'Government renounces to seignorage and has to have a primary surplus') partly highlighted, with a small scribble/doodle in the bottom-left margin.
- Slide 8 ('Unpleasant Monetarist Arithmetic'): nearly every bullet highlighted in teal, emphasizing the open-market purchase vs. sale mechanics and their opposite effects on money supply.
- Slide 9 ('Open-market operation in the shopping-time model'): heavy highlighting on the definition of the t=0 open-market sale and on the long-run result that stationary inflation unambiguously rises.
- Slide 10: highlighting on 'the lower R_m is a downward movement along the curve', 'the higher B shifts the curve upwards', the paradox statement ('a lower price level today can be accompanied by permanent higher inflation'), and the intuition line about asset sales requiring more resources to pay debt; a small handwritten mark in the left margin.
- Slide 11 ('Optimum quantity of money'): highlighted — marginal cost of printing money ~0 (Friedman 1969), nominal interest rate as the marginal cost of holding money, equating private/social marginal costs implies i=0, and the Fisher-equation implication pi=-r.
- Slide 12: highlighted the statement that the government can attain any value of R_m, and the gross-of-interest surplus condition; 'Needs a combination of low spending, low debt, high taxes' also highlighted.
- Slide 13: highlighted 'it is optimal to supply a large amount of real money balances, and minimize time spent shopping' and the y=c+g feasibility line.
- Slide 14: heavy highlighting throughout, including the extra-assumption box (for all c there exists a satiation point psi(c)); a handwritten blue question mark '?' in the bottom-left margin flags this slide as a point of confusion/review.
- Slide 15 ('Phelps' critique'): highlighted 'Optimal inflation rate could be strictly positive', 'Optimal inflation rate is small but positive, around 1%', and 'distortionary taxation'.
- Slide 23 (Lagrangian FOCs): a highlighted box and a hand-drawn arrow mark the u_{c_t} coefficient term inside the FOC for c_t, flagging that specific term for review.

### Conexiones con otros temas

- Sargent & Wallace (1981) 'Some Unpleasant Monetarist Arithmetic'
- Friedman (1969) The Optimum Quantity of Money
- Mulligan & Sala-i-Martin (1997, JMCB) — optimal inflation under distortionary taxation
- Phelps (1973) critique of the Friedman rule
- Fiscal theory of the price level / government budget constraint literature
- Introduces the tax notation (tau^k, tau^l, etc.) reused in Topic 4's neoclassical growth model with distortionary taxes

---

## Exogenous growth in the (deterministic) neoclassical growth model with distortionary taxes — DETRENDING. Model type: representative-agent Ramsey/neoclassical growth model (no uncertainty in this deck) extended with population growth g_n and labor-augmenting technological progress g_z, plus a full set of distortionary taxes (tau^c, tau^x, tau^k, tau^l) and lump-sum transfers, following McGrattan (2006)'s presentation. The lecture's purpose is purely technical: showing how to detrend a growing economy so that solution methods requiring a bounded steady state (shooting, log-linearization, dynamic programming) can be applied.

*Fuente: `Macro_Din_II_Agosto_2018Topic4.2CORREGIDO.pdf`*

*Secciones: Exogenous sources of growth and computational issues | Notation (population N_t, labor-augmenting technology Z_t, per-capita vs. detrended variables) | Model: household problem with taxes and transfers | Capital accumulation equation rewritten in per-capita/detrended form | Firm's problem and government budget constraint; feasibility conditions | Transforming the model: Kaldor's facts as motivation for detrending | Detrended household utility (modified discount factor beta-tilde) | Detrended budget constraint and detrended capital accumulation | Detrended firm problem (intensive-form production f(k-hat,l)) | Lagrangian and static consumption-leisure condition | Detrended Euler equation | Firm FOCs (detrended factor prices) | Ready to use computational methods (reduced system of 3 equations / 3 unknowns)*

### Supuestos

> Total Factor Productivity and/or population grow at exogenous rates (some variables display growth so a steady state in levels does not exist)
>
> F is homogeneous of degree 1 (constant returns to scale in K and effective labor ZL)
>
> Utility multiplicatively separable, U(c,1-l)=c^{1-sigma}v(l)/(1-sigma) (KPR-type, balanced-growth consistent)
>
> beta-tilde=beta(1+g_n)(1+g_z)^{1-sigma}<1 required for convergence of detrended intertemporal utility
>
> G_t (government spending) is exogenous
>
> c_t,x_t>=0
>

### Conceptos clave

- **Detrending** - Dividing a growing aggregate variable by N_t(1+g_z)^t so the transformed ('hat') variable is stationary in the long run — a prerequisite for shooting, log-linearization and dynamic programming, all of which require a well-defined bounded steady state.
- **Kaldor's facts** - Long-run stylized facts (GDP, consumption and investment per capita, and the real wage, all grow at the same rate; labor per worker and the real interest rate are stationary/trendless) that the neoclassical growth model is built to replicate, motivating why growth must be removed before applying standard solution techniques.
- **Labor-augmenting (Harrod-neutral) technological change** - Z_t enters production as F(K_t,Z_tL_t) with Z_t=(1+g_z)^t; the form required for a balanced growth path to exist with a constant (non-trending) labor supply.
- **Modified/detrended discount factor** - beta-tilde = beta(1+g_n)(1+g_z)^{1-sigma}; must satisfy beta-tilde<1 for the detrended intertemporal utility sum to be well-defined (converge).

### Teoremas, lemas y proposiciones

> **Well-posedness of the detrended household problem**
>
> If U(c,1-l)=c^{1-sigma}v(l)/(1-sigma) (a multiplicatively separable, balanced-growth-consistent form) and beta-tilde=beta(1+g_n)(1+g_z)^{1-sigma}<1, then the detrended lifetime utility sum_{t=0}^{infty} beta-tilde^t c-hat_t^{1-sigma}v(l_t)/(1-sigma) is well defined (bounded).
>
> *Supuestos requeridos:* multiplicatively separable utility of KPR type, c^{1-sigma}v(l)/(1-sigma); beta(1+g_n)(1+g_z)^{1-sigma}<1
>
> *Garantiza:* Guarantees the household's detrended optimization problem is well posed, i.e. the model can be solved as a stationary dynamic program/Euler-equation system after removing trend.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Population and technology growth | `N_t=N_0(1+g_n)^t,\ N_0=1; \qquad Y_t=F(K_t,Z_tL_t),\ Z_t=(1+g_z)^t` | exogenous population growth rate g_n and labor-augmenting technology growth rate g_z | defining the sources of long-run growth in the model |
| Per-capita and detrended variable definitions | `v_t=\frac{V_t}{N_t}; \qquad \widehat v_t=\frac{V_t}{N_t(1+g_z)^t}` | per-capita variable v_t and detrended variable v-hat_t for any aggregate V_t | transforming trending aggregates into stationary objects before solving the model |
| Household problem (levels) | `\max_{\{c_t,x_t,l_t\}} \sum_{t=0}^{\infty}\beta^t[U(c_t,1-l_t)]N_t \ \text{s.t.}\ (1+\tau_t^c)c_t+(1+\tau_t^x)x_t=(1-\tau_t^k)r_tk_t+(1-\tau_t^l)w_tl_t+\tau_t^k\delta k_t+tr_t,\quad N_{t+1}k_{t+1}=[(1-\delta)k_t+x_t]N_t,\quad c_t,x_t\ge0` | household maximizes discounted utility over consumption, investment and leisure subject to a budget constraint with consumption/investment/capital/labor taxes and transfers, and per-capita capital accumulation | starting point of the neoclassical growth model with taxes |
| Capital accumulation rewritten | `K_{t+1}=(1-\delta)K_t+X_t \;\Longrightarrow\; (1+g_n)k_{t+1}=(1-\delta)k_t+x_t` | aggregate capital law of motion converted to per-capita form using N_{t+1}/N_t=1+g_n | deriving the per-capita/detrended capital accumulation equation |
| Firm's problem | `\max_{K_t,L_t} F(K_t,Z_tL_t)-w_tL_t-r_tK_t` | representative firm chooses capital and labor to maximize profit given effective-labor-augmenting technology | deriving factor price (labor demand/capital rent) conditions |
| Government budget constraint | `G_t+N_ttr_t=\tau_t^k(r_t-\delta)N_tk_t+\tau_t^lw_tl_tN_t+\tau_t^cN_tc_t+\tau_t^xN_tx_t` | government spending plus transfers financed by capital, labor, consumption and investment tax revenue (G_t exogenous) | closing the model / checking fiscal balance |
| Feasibility conditions | `N_t(c_t+x_t)+G_t=F(K_t,Z_tL_t); \qquad N_tk_t=K_t; \qquad N_tl_t=L_t` | aggregate resource constraint and market-clearing for capital and labor | equilibrium definition |
| Utility functional form (KPR-type) | `U(c_t,1-l_t)=\frac{c_t^{1-\sigma}}{1-\sigma}\cdot v(l_t)` | multiplicatively separable utility, consumption CRRA times a decreasing function v of labor | specification consistent with a balanced growth path |
| Detrended intertemporal utility | `c_t=(1+g_z)^t\widehat c_t \;\Rightarrow\; \sum_{t=0}^{\infty}\big(\beta(1+g_n)(1+g_z)^{1-\sigma}\big)^t \frac{\widehat c_t^{1-\sigma}}{1-\sigma}v(l_t)` | lifetime utility rewritten in terms of the stationary variable c-hat_t and a modified discount factor | defining beta-tilde and checking convergence |
| Modified discount factor | `\widetilde\beta=\beta(1+g_n)(1+g_z)^{1-\sigma}, \quad \text{need } \widetilde\beta<1` | combines time discounting with population/technology growth | convergence condition for the detrended objective |
| Detrended household budget constraint | `(1+\tau_t^c)\widehat c_t+(1+\tau_t^x)\widehat x_t=(1-\tau_t^k)r_t\widehat k_t+(1-\tau_t^l)\widehat w_tl_t+\tau_t^k\delta\widehat k_t+\widehat{tr}_t` | budget constraint with all quantity variables replaced by their detrended counterparts | setting up the stationary household problem |
| Detrended capital accumulation | `(1+g_z)(1+g_n)\widehat k_{t+1}=(1-\delta)\widehat k_t+\widehat x_t` | law of motion for detrended capital | state equation of the stationary recursive problem |
| Intensive-form production function | `F\!\left(\frac{K_t}{N_tZ_t},\frac{Z_tL_t}{N_tZ_t}\right)=\frac{F(K_t,Z_tL_t)}{N_tZ_t}\equiv f(\widehat k_t,l_t)` | production function per unit of effective labor, using homogeneity of degree 1 of F | rewriting the firm's problem and feasibility in detrended form |
| Detrended feasibility | `\widehat y_t=\widehat c_t+\widehat x_t+\widehat g_t` | detrended resource constraint (with g_t growing at rate g_z in the long run so g-hat_t is stationary) | equilibrium condition in the stationary system |
| Lagrangian (household) | `\mathcal L=\sum_{t=0}^{\infty}\Big\{\widetilde\beta^t U(\widehat c_t,1-l_t)+\lambda_t[(1-\tau_t^k)r_t\widehat k_t+(1-\tau_t^l)\widehat w_tl_t+\tau_t^k\delta\widehat k_t+\widehat{tr}_t-(1+\tau_t^c)\widehat c_t-(1+\tau_t^x)\widehat x_t]+\mu_t[(1-\delta)\widehat k_t+\widehat x_t-(1+g_z)(1+g_n)\widehat k_{t+1}]\Big\}` | Lagrangian for the detrended household optimization problem | deriving static and Euler first-order conditions |
| Consumption-leisure condition | `\frac{U_2(\widehat c_t,1-l_t)}{U_1(\widehat c_t,1-l_t)}=\frac{1-\tau_t^l}{1+\tau_t^c}\widehat w_t` | static intratemporal labor-supply/leisure condition, wedge driven by labor and consumption taxes | determining labor supply given after-tax detrended wage |
| Detrended Euler equation | `\frac{1+\tau_t^x}{1+\tau_t^c}U_1(\widehat c_t,1-l_t)=\widehat\beta\Big\{\frac{U_1(\widehat c_{t+1},1-l_{t+1})}{1+\tau_{t+1}^c}\big[(1-\tau_{t+1}^k)r_{t+1}+\delta\tau_{t+1}^k+(1-\delta)(1+\tau_{t+1}^x)\big]\Big\}, \quad \widehat\beta=\frac{\widetilde\beta}{(1+g_z)(1+g_n)}=\beta(1+g_z)^{-\sigma}` | intertemporal optimality condition in detrended variables, with an extra step relative to the standard Euler equation because of investment taxes | pinning down the dynamics of consumption/capital |
| Firm FOCs (detrended) | `r_t=f_1(\widehat k_t,l_t); \qquad \widehat w_t=f_2(\widehat k_t,l_t)` | factor prices equal marginal products of the intensive-form production function | closing the equilibrium system with factor-price determination |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Production is a generic constant-returns function F(K_t,Z_tL_t) (homogeneous of degree 1 in K and effective labor ZL — not restricted to Cobb-Douglas in this deck), transformed into intensive form f(k-hat_t,l_t)=F(K_t,Z_tL_t)/(N_tZ_t). The firm's detrended FOCs give the labor-demand and capital-rent conditions: r_t=f_1(k-hat_t,l_t) and w-hat_t=f_2(k-hat_t,l_t) — factor prices equal marginal products of the intensive-form production function (the familiar Cobb-Douglas special case W=(1-alpha)Y/N would follow only if F were specialized, which is not done here). On the household side, utility is U(c_t,1-l_t)=c_t^{1-sigma}v(l_t)/(1-sigma) — a multiplicatively separable, KPR-type (balanced-growth-consistent) specification with v(.) left generic, so no explicit Frisch elasticity is pinned down; the curvature in consumption is governed by sigma, and the curvature/substitutability of labor supply is governed by the (unspecified) shape of v(l). The labor-leisure optimality condition is U_2(c-hat_t,1-l_t)/U_1(c-hat_t,1-l_t) = [(1-tau_t^l)/(1+tau_t^c)]*w-hat_t, so the labor tax tau^l and the consumption tax tau^c jointly wedge the labor-supply margin, and the after-tax detrended wage w-hat_t is exactly the firm's f_2(k-hat,l) — the closest analogue here to a 'labor demand = labor supply' condition. No explicit CES/elasticity-of-substitution parameter between K and L appears since F is left generic (homogeneous of degree 1).

### [POLICY] Instrumentos de politica

- tau_t^c — consumption tax, multiplies c_t / c-hat_t in the budget constraint
- tau_t^x — investment tax, multiplies x_t / x-hat_t
- tau_t^k — capital income tax, applied to (r_t-delta)k_t (net-of-depreciation capital income), with depreciation allowance tau_t^k*delta rebated
- tau_t^l — labor income tax, applied to w_t l_t
- tr_t — lump-sum government transfers to households
- G_t — government spending, exogenous, enters feasibility and the government budget constraint
- Government budget constraint: G_t+N_t tr_t = tau_t^k(r_t-delta)N_tk_t + tau_t^l w_t l_t N_t + tau_t^c N_t c_t + tau_t^x N_t x_t

### [COMPUT] Metodo computacional

The lecture itself IS a computational-method prerequisite: 'detrending' — transforming trending aggregate/per-capita variables into stationary detrended variables v-hat_t=V_t/(N_t(1+g_z)^t) — so that shooting algorithms, log-linearization, and dynamic programming (all of which require a well-defined bounded steady state / bounded capital grid) can subsequently be applied. After detrending, the model reduces to a system of 3 unknowns (c-hat_t, l_t, k-hat_{t+1}) and 3 equations (Euler equation, static consumption-leisure condition, feasibility, after substituting in firm FOCs and the capital accumulation equation), ready for standard solution methods. Presentation follows McGrattan (2006), 'without uncertainty.'

### [CALIB] Objetivos de calibracion

- Kaldor's facts as qualitative matching targets for the model class: GDP per capita, consumption per capita, investment per capita and the real wage should all grow at a common rate on the balanced growth path; labor per worker and the real interest rate should be trendless (stationary) in the long run.

### Intuicion general

The neoclassical growth model is calibrated to match long-run US/UK growth facts (Kaldor's facts), which means several variables (output, consumption, investment, wages per capita) grow without bound and have no steady state in levels — but the standard toolbox (shooting algorithms, log-linearization, dynamic programming with a bounded capital grid) all require a stationary steady state to operate. The fix is a pure change of variables: divide every trending aggregate by N_t(1+g_z)^t (detrending) so the transformed system has a genuine bounded steady state, then solve the detrended system with familiar methods. The key technical subtlety is that household utility must be multiplicatively separable in a particular way (c^{1-sigma}v(l)/(1-sigma)) so that, after substituting c_t=(1+g_z)^t c-hat_t, the growth terms collapse into a single modified discount factor beta-tilde, which must be <1 for the infinite utility sum to converge — i.e. population and technology cannot grow so fast that they overwhelm time discounting.

### Conexiones con otros temas

- McGrattan (2006) — 'without uncertainty' presentation followed here
- Kaldor's stylized facts of growth
- Reuses the tax notation (tau^c, tau^x, tau^k, tau^l) introduced in the monetary/Ramsey-taxation lecture (Topic 3), now extended into a growth model with capital
- Sets up Topic 5 (log-linearization / Uhlig's method), which requires exactly this kind of detrended, stationary system to operate

---

## Computational/solution methods for DSGE models — log-linearization (first-order Taylor approximation around the steady state) and a taxonomy of solution methods (Blanchard-Kahn, Uhlig's Undetermined Coefficients, Uribe & Schmitt-Grohe for linear systems; system-of-equations solvers, shooting, dynamic programming for nonlinear systems; McGrattan's Weighted Residuals for nonlinear stochastic models). Illustrated on the standard stochastic Real Business Cycle (RBC) model with indivisible labor (linear labor disutility), i.e. Hansen (1985) as presented by Uhlig (1999) — a stochastic neoclassical growth model with a single AR(1) TFP shock and no government/taxes.

*Fuente: `Macro_Din_II_Agosto_2019Topic5FirstPart(1).pdf`*

*Secciones: Computational problems in macro (DSGE, uncertainty) | A categorization of problems and solution methods (deterministic/stochastic x linear/nonlinear) | Black-boxes versus flexibility: Dynare vs. hand-coded methods | What matters most: the policy function and what can be computed from it | Plan: log-linearize, then apply Uhlig's Undetermined Coefficients by hand | Example model: Hansen (1985)/Uhlig (1999) stochastic growth model | Uhlig's notation for capital timing (K_{t-1} given, K_t chosen) | System of equations for the example (FOC, labor condition, capital return, production, feasibility, Euler, TFP process) | Log-linearization: Taylor approximation, log-deviations x_t=log(X_t)-log(X-bar), X_t=X-bar*e^{x_t} | Steady-state simplifying relations (1=beta*R-bar, R-bar=rho*Y-bar/K-bar+(1-delta)) | Worked log-linearization of each equation of the system*

### Supuestos

> Uncertainty about future exogenous productivity (stochastic TFP)
>
> Log utility in consumption, linear (indivisible-labor) disutility of labor: log(C_t)-AN_t
>
> Cobb-Douglas production with capital share rho
>
> Linearization performed around the deterministic steady state
>
> Uhlig's timing convention: at time t, capital K_{t-1} is given and K_t is chosen (different from the more common convention of K_t given, K_{t+1} chosen — explicitly flagged: 'keep difference in mind')
>

### Conceptos clave

- **DSGE model** - General term for the class of dynamic stochastic general equilibrium models macro uses to answer quantitative questions; usually not solvable by hand except in special cases.
- **Log-linearization** - First-order Taylor approximation of a nonlinear system of equations around the steady state, after substituting each variable X_t=X-bar*e^{x_t}, where x_t is the log-deviation from steady state (approximately the percent deviation when multiplied by 100).
- **Uhlig's 'building blocks'** - An algebraic shortcut Uhlig proposes as an alternative to explicit partial differentiation when log-linearizing (referenced, not detailed, in this deck; see Uhlig's chapter p. 34).
- **Indivisible labor / Hansen (1985) preferences** - Utility linear in hours, log(C_t)-A*N_t, which via the lottery interpretation rationalizes aggregate employment fluctuations at the extensive margin.
- **Policy function** - The object every solution method ultimately seeks: endogenous variables expressed as functions of state variables. Once known, impulse responses, model-implied moments, transitions, historical simulations, welfare and parameter estimation are all straightforward to compute.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Categorization of solution methods | `Table: {Deterministic-Linear: Blanchard-Kahn, Uhlig's Undetermined Coefficients, Uribe & Schmitt-Grohe; Stochastic-Linear: same as Deterministic-Linear; Deterministic-Nonlinear: system-of-equations solver, Shooting, Dynamic Programming; Stochastic-Nonlinear: Dynamic Programming (slow), McGrattan's Weighted Residuals}` | classification of solution methods by model class (linear/nonlinear, deterministic/stochastic) | choosing a solution algorithm given the properties of the model at hand |
| Household problem | `\max E_0\sum_{t=0}^{\infty}\beta^t[\log(C_t)-AN_t]` | expected discounted utility, log consumption minus linear disutility of labor (indivisible labor) | defining preferences of the Hansen/Uhlig RBC example |
| Feasibility / budget constraint | `C_t+K_t=Y_t+(1-\delta)K_{t-1}` | resource constraint of the closed-economy RBC model | equilibrium condition of the example |
| Production function | `Y_t=Z_tK_{t-1}^{\rho}N_t^{1-\rho}` | Cobb-Douglas production with capital share rho | technology of the RBC example |
| TFP process | `\log(Z_t)=(1-\psi)\log(\bar Z)+\psi\log(Z_{t-1})+\varepsilon_t,\ \varepsilon\sim(0,\sigma_\varepsilon^2)` | AR(1) process in logs for total factor productivity | source of uncertainty/business cycle fluctuations |
| System of equations | `\frac{1}{C_t}=\Lambda_t;\quad A=\Lambda_t(1-\rho)\frac{Y_t}{N_t};\quad R_t=\rho\frac{Y_t}{K_{t-1}}+(1-\delta);\quad Y_t=Z_tK_{t-1}^{\rho}N_t^{1-\rho};\quad C_t+K_t=Y_t+(1-\delta)K_{t-1};\quad \Lambda_t=\beta E_t[\Lambda_{t+1}R_{t+1}];\quad \log(Z_t)=(1-\psi)\log(\bar Z)+\psi\log(Z_{t-1})+\varepsilon_t` | complete nonlinear equilibrium system (7 equations) prior to log-linearization | starting point for solving the model |
| Log-deviation definition | `x_t\equiv\log(X_t)-\log(\bar X), \qquad X_t=\bar X e^{x_t}` | log-deviation of a variable from its steady-state value | substitution step before Taylor-expanding each equation |
| First-order Taylor approximation | `f(x)\approx f(x_0)+f'(x_0)(x-x_0)` | generic linearization formula, applied around steady state x_0 | deriving the log-linearized version of each equilibrium equation |
| Steady-state simplifications | `1=\beta\bar R; \qquad \bar R=\rho\frac{\bar Y}{\bar K}+(1-\delta)` | steady-state relations used to simplify log-linearized coefficients | cleaning up algebra after Taylor-expanding |
| Log-linearized FOC for consumption/multiplier | `c_t=-\lambda_t` | from 0=1/C_t-\Lambda_t linearized | reduced system building block |
| Log-linearized labor condition | `n_t=\lambda_t+y_t` | from A=\Lambda_t(1-\rho)Y_t/N_t linearized | reduced system building block |
| Log-linearized capital-return definition | `\bar R r_t=\rho\frac{\bar Y}{\bar K}(y_t-k_{t-1})` | linearized rental-rate definition | reduced system building block |
| Log-linearized production function | `y_t=z_t+\rho k_{t-1}+(1-\rho)n_t` | linearized Cobb-Douglas production function | reduced system building block |
| Log-linearized feasibility | `y_t=\frac{\bar C}{\bar Y}c_t+\frac{\bar K}{\bar Y}\big(k_t-(1-\delta)k_{t-1}\big)` | linearized resource constraint | reduced system building block |
| Log-linearized Euler equation | `\lambda_t=E_t(\lambda_{t+1}+r_{t+1})` | linearized intertemporal optimality condition | reduced system building block, links present and expected future multiplier/return |
| AR(1) TFP (kept in levels) | `z_t=\psi z_{t-1}+\varepsilon_t` | the technology process is already log-linear, no Taylor expansion needed | closing the log-linearized system |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Utility is log(C_t)-AN_t: additively separable and LINEAR in hours N_t (Hansen 1985 indivisible-labor specification), which implies via the standard lottery/indivisible-labor argument an effectively infinite Frisch elasticity of aggregate labor supply — a deliberate modeling choice to generate large employment volatility. Production is Cobb-Douglas, Y_t=Z_tK_{t-1}^rho*N_t^{1-rho}: the curvature/substitution parameter is rho (capital's share), which pins the elasticity of substitution between capital and labor at 1 (Cobb-Douglas) and governs the diminishing-marginal-product curvature of the (implicit) labor demand relation. There is no separate 'labor demand=(1-alpha)Y/N' equation written explicitly (no posted wage in this closed RBC model), but it is implicit: combining the static FOCs A=Lambda_t(1-rho)Y_t/N_t and 1/C_t=Lambda_t gives A*C_t=(1-rho)Y_t/N_t, i.e. the marginal rate of substitution between consumption and leisure equals the marginal product of labor (1-rho)Y_t/N_t. In log-linearized form this collapses to n_t=lambda_t+y_t.

### [COMPUT] Metodo computacional

Log-linearization by hand: (1) substitute X_t=X-bar*e^{x_t} into every equation of the nonlinear system; (2) apply a first-order Taylor expansion around x_t=y_t=0 (the steady state); (3) use steady-state simplifications (1=beta*R-bar, R-bar=rho*Y-bar/K-bar+(1-delta)) to simplify coefficients; Uhlig's 'building blocks' offered as a shortcut to explicit differentiation. Positioned within a broader taxonomy: Blanchard-Kahn, Uhlig's Undetermined Coefficients, and Uribe & Schmitt-Grohe for linear (deterministic or stochastic) systems; system-of-equations solvers, shooting, and dynamic programming for deterministic nonlinear systems; dynamic programming (slow) and McGrattan's Weighted Residuals for nonlinear stochastic systems. Dynare mentioned as an automated (black-box) alternative that performs log-linearization internally.

### Intuicion general

Because most DSGE models cannot be solved in closed form, and many macro questions require uncertainty, the field has developed a menu of solution methods organized along two dimensions: linear vs. nonlinear, and deterministic vs. stochastic. Dynare automates log-linearization (a black box: convenient but opaque about what is happening under the hood, e.g. choices like 1st vs. 2nd order approximation), whereas this lecture teaches the underlying technique by hand on Hansen's (1985) indivisible-labor RBC model so students understand exactly what a 'policy function' is and how it is obtained — because once the policy function is known, essentially everything else (impulse responses, moments, transitions, simulations, welfare, estimation) follows.

### Ejemplos y ejercicios

- Hansen (1985)/Uhlig (1999) indivisible-labor RBC model worked end-to-end: every equation of the nonlinear system is log-linearized by hand (FOC, labor condition, capital-return definition, production function, feasibility, Euler equation), leaving the TFP AR(1) process unlinearized since it is already log-linear.

### Anotaciones a mano (tuyas)

- Slide 6 ('What matters most'): 'policy function' and 'state variables' highlighted in yellow, marking the central object of the whole lecture.
- Slide 7 ('Plan'): 'log-linearize the nonlinear system of equations that gives us the solution of a model' and 'Uhlig's Method of Undetermined Coefficients' highlighted in yellow.
- Slide 8 ('Here we go'): 'uncertainty' highlighted with a hand-drawn arrow/underline pointing to 'productivity', flagging where stochasticity enters the model.
- Slide 9 ('Uhlig's notation'): heavy yellow highlighting on the non-standard timing convention — 'every period t, capital K_{t-1} is given, and capital K_t is chosen' — with the professor's own added remark 'we are used to take K_t as given, choose K_{t+1}. Keep difference in mind,' underscoring this as a common source of confusion.
- Slide 10 (system of equations): three equations bullet-highlighted in yellow (production function, budget/feasibility, TFP AR(1) process).
- Slide 11 (Taylor approximation / log-deviation definitions): extensive yellow highlighting including the Taylor formula, the definition x_t=log(X_t)-log(X-bar), and the interpretation note ('multiply x_t by 100 gives us the % distance from steady state').
- Slide 12 (steady-state simplifications): the two steady-state equations 1=beta*R-bar and R-bar=rho*Y-bar/K-bar+(1-delta) highlighted in yellow.
- Slide 13 ('Log-linearizing', FOC for consumption/multiplier): a genuine HANDWRITTEN worked derivation fills the left margin and center of the slide — labels like 'tlb of ss' (Taylor around steady state), 'on ss' pointing at F-bar(0,0), '1/C=-Lambda' circled, arrows pointing to F_{c_t}(0), F_{lambda_t}(0) marking which partial derivatives are being evaluated, and the final boxed/highlighted result (1/C-bar)c_t=-Lambda-bar*lambda_t leading to c_t=-lambda_t — the student's own step-by-step re-derivation of the printed result, done live in class.
- Slide 14 (consumption-leisure log-linearization): handwritten labels F_{lambda_t}, F_{y_t}, F_{n_t} written above the corresponding terms, plus F(0,0,0) noted under the zero-order term, and the final result n_t=lambda_t+y_t highlighted in yellow with a hand-drawn arrow tracing the derivation.
- Slide 15 (capital-return log-linearization): terms rho*(Y-bar/K-bar)*y_t and rho*(Y-bar/K-bar)*k_{t-1} highlighted in purple, with an arrow connecting the two lines of the derivation.

### Conexiones con otros temas

- Uhlig (1999), chapter in Marimon & Scott (eds.), Computational Methods for the Study of Dynamic Economies
- Hansen (1985) indivisible-labor RBC model
- Blanchard & Kahn (1980) method for linear rational-expectations models
- Uribe & Schmitt-Grohe perturbation/log-linearization approach
- Dynare software (contrasted as a 'black box')
- McGrattan-Sargent parameter estimation methods (mentioned as a further use of the policy function)
- Directly continues into Topic 5 Second Part (Undetermined Coefficients solves the very system log-linearized here)

---

## Uhlig's Method of Undetermined Coefficients for solving linear (log-linearized) rational-expectations DSGE models. Continues the same example model as Topic 5 First Part — the Hansen (1985)/Uhlig (1999) stochastic RBC model (Cobb-Douglas production, indivisible-labor utility, AR(1) TFP) — now solved by hand for its policy functions.

*Fuente: `Macro_Din_II_Agosto_2019Topic5SecondPart(1).pdf`*

*Secciones: Undetermined Coefficients: motivation and Uhlig's two-group organization of equations (static vs. dynamic/expectational) | General notation: state vector x_t, other endogenous variables y_t, exogenous z_t; matrices A-N; policy functions P,Q,R,S | Example: identifying endogenous/exogenous state variables for the Hansen/Uhlig model (x_t=k_t, z_t, y_t=[c_t,y_t,n_t,lambda_t,r_t]) | Filling matrices A,B,C,D,F,G,H,J,K,L,M,N for the example | Analytical (by-hand) solution: reducing the system to two variables (multiplier lambda_t and capital k_t) | Deriving alpha_1..alpha_6 coefficients and the reduced two-equation system (eqs. 9-10) | Guessing linear policy functions k_t=eta_KK*k_{t-1}+eta_Kz*z_t, lambda_t=eta_lambdaK*k_{t-1}+eta_lambdaz*z_t | Matching coefficients on k_{t-1}: quadratic equation for eta_KK, stability/saddle-path selection of the root <1 | Matching coefficients on z_t: linear system for eta_lambdaz, eta_Kz | Summary: policy function coefficients obtained by hand; segue to using Uhlig's code in general*

### Supuestos

> Same underlying RBC model assumptions as Topic 5 First Part (log utility, linear/indivisible labor disutility, Cobb-Douglas production, AR(1) TFP)
>
> Guessed functional form: policy functions are linear in the (single) state variables k_{t-1} and z_t
>
> Both matched equations must hold for ALL values of k_{t-1} and z_t simultaneously, so all coefficients multiplying them must independently equal zero (identification argument underlying Undetermined Coefficients)
>

### Conceptos clave

- **Undetermined Coefficients method** - Solves a linear rational-expectations system by guessing that the policy functions are linear in the state variables, then matching coefficients on each state variable across all periods to pin down the unknown ('undetermined') coefficients.
- **Uhlig's general notation** - Partitions equations into 'static' (no expectations; matrices A,B,C,D) and 'dynamic/expectational' (matrices E through M) blocks; endogenous state variables x_t, other endogenous y_t, exogenous z_t following an AR(1) with matrix N.
- **Policy functions** - x_t=Px_{t-1}+Qz_t (law of motion for states), y_t=Rx_{t-1}+Sz_t (other endogenous variables as functions of lagged states and current shocks); Uhlig's codes solve for P,Q,R,S numerically given matrices A-N.
- **Saddle-path stability / root selection** - The quadratic equation for eta_KK has two roots whose product equals R-bar=1/beta>1; exactly one root is <1 (stable) and is selected so the policy function delivers a bounded, convergent solution — a defining property of the neoclassical growth model.

### Teoremas, lemas y proposiciones

> **Reciprocal-roots / saddle-path uniqueness result for eta_KK**
>
> The quadratic characteristic equation 0=\eta_{KK}^2-\left(\alpha_1-\frac{\alpha_2}{\alpha_5}\alpha_4+\frac{1}{\alpha_5}\right)\eta_{KK}+\frac{\alpha_1}{\alpha_5} has two roots eta_{KK,1}, eta_{KK,2} satisfying eta_{KK,1}*eta_{KK,2}=alpha_1/alpha_5=R-bar=1/beta>1, and the roots are 'almost reciprocal' except for beta: eta_{KK,1}=1/(beta*eta_{KK,2}).
>
> *Supuestos requeridos:* log-linearized Hansen/Uhlig RBC system; guessed linear policy-function form for k_t and lambda_t
>
> *Garantiza:* At most one root is stable (modulus <1); this stable root is the economically relevant/selected solution, ensuring a unique bounded (non-explosive) policy function for capital — a characteristic feature of the neoclassical growth model (cf. Ljungqvist & Sargent 2004; Stokey, Lucas & Prescott 1989).

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| General Uhlig system — static block | `0=Ax_t+Bx_{t-1}+Cy_t+Dz_t` | equations not involving expectations | classifying model equations before applying Undetermined Coefficients |
| General Uhlig system — dynamic/expectational block | `0=E_t\big[Fx_{t+1}+Gx_t+Hx_{t-1}+Jy_{t+1}+Ky_t+Lz_{t+1}+Mz_t\big]` | equations involving conditional expectations of future variables | classifying model equations before applying Undetermined Coefficients |
| Exogenous process | `z_{t+1}=Nz_t+\varepsilon_{t+1}, \qquad 0=E_t[\varepsilon_{t+1}]` | law of motion of exogenous state(s) | closing the system |
| Policy functions (general) | `x_t=Px_{t-1}+Qz_t; \qquad y_t=Rx_{t-1}+Sz_t` | endogenous state and other endogenous variables as linear functions of lagged states and current shocks | the object solved for by Uhlig's method / codes |
| Reduced two-variable relation (eq. 8) | `y_t=\frac{1}{\rho}z_t+k_{t-1}+\frac{1-\rho}{\rho}\lambda_t` | output expressed in terms of state k_{t-1}, shock z_t, and multiplier lambda_t (after eliminating n_t via the labor condition) | step toward reducing the system to (k_t, lambda_t) only |
| Coefficients alpha_1..alpha_6 | `\alpha_1=\frac{\bar Y}{\bar K}+(1-\delta);\ \alpha_2=\frac{\bar C}{\bar K}+\frac{1-\rho}{\rho}\frac{\bar Y}{\bar K};\ \alpha_3=\frac{\bar Y}{\rho\bar K};\ \alpha_4=0;\ \alpha_5=1+(1-\rho)\frac{\bar Y}{\bar R\bar K};\ \alpha_6=\frac{\bar Y}{\bar R\bar K}` | steady-state ratios combined into shorthand coefficients for the reduced system | writing feasibility and Euler equations compactly in (k,lambda,z) only |
| Reduced feasibility equation (eq. 9) | `0=-k_t+\alpha_1k_{t-1}+\alpha_2\lambda_t+\alpha_3z_t` | capital law of motion in terms of lagged capital, multiplier and shock | one of the two equations defining the reduced system |
| Reduced Euler equation (eq. 10) | `0=E_t\big[-\lambda_t+\alpha_4k_t+\alpha_5\lambda_{t+1}+\alpha_6z_{t+1}\big]` | Euler equation in terms of the multiplier and shock only (alpha_4=0 in this example) | second equation defining the reduced system |
| Guessed linear policy functions | `k_t=\eta_{KK}k_{t-1}+\eta_{Kz}z_t; \qquad \lambda_t=\eta_{\lambda K}k_{t-1}+\eta_{\lambda z}z_t` | conjectured form of the solution, linear in the state variables | starting point of Undetermined Coefficients |
| Coefficient-matching equations on k_{t-1} | `0=-\eta_{KK}+\alpha_1+\alpha_2\eta_{\lambda K}; \qquad 0=-\eta_{\lambda K}+\alpha_4\eta_{KK}+\alpha_5\eta_{\lambda K}\eta_{KK}` | conditions obtained because eqs. (9)-(10) must hold for all k_{t-1} | deriving the quadratic equation for eta_KK |
| Quadratic equation for eta_KK | `0=\eta_{KK}^2-\left(\alpha_1-\frac{\alpha_2}{\alpha_5}\alpha_4+\frac{1}{\alpha_5}\right)\eta_{KK}+\frac{\alpha_1}{\alpha_5}` | characteristic equation whose roots are the candidate values of eta_KK | solving for the capital policy-function coefficient |
| Closed-form solution for eta_KK | `\eta_{KK}=\frac12\left[\left(\alpha_1-\frac{\alpha_2}{\alpha_5}\alpha_4+\frac1{\alpha_5}\right)\pm\sqrt{\left(\alpha_1-\frac{\alpha_2}{\alpha_5}\alpha_4+\frac1{\alpha_5}\right)^2-4\frac{\alpha_1}{\alpha_5}}\right]` | quadratic formula applied to the characteristic equation | computing the two candidate roots, then selecting the stable one |
| z_t-coefficient equations | `0=-\eta_{Kz}+\alpha_2\eta_{\lambda z}+\alpha_3; \qquad 0=-\eta_{\lambda z}+\alpha_4\eta_{Kz}+\alpha_5\eta_{\lambda K}\eta_{Kz}+(\alpha_5\eta_{\lambda z}+\alpha_6)\psi` | conditions obtained because eqs. (9)-(10) must hold for all z_t | deriving the (now linear, since eta_KK and eta_lambdaK are already known) system for eta_Kz, eta_lambdaz |
| Closed-form solutions for eta_lambdaz, eta_Kz | `\eta_{\lambda z}=\frac{\alpha_4\alpha_3+\alpha_5\eta_{\lambda K}\alpha_3+\alpha_6\psi}{1-\alpha_4\alpha_2-\alpha_5\eta_{\lambda K}\alpha_2-\alpha_5\psi}; \qquad \eta_{Kz}=\alpha_2\eta_{\lambda z}+\alpha_3` | completes the policy function coefficients on the exogenous shock | final step of the by-hand Undetermined Coefficients solution |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Same model as Part 1: n_t is among the 'other endogenous variables' y_t=[c_t,y_t,n_t,lambda_t,r_t] (note: this y_t is Uhlig's generic vector notation, distinct from output y_t — a labeling collision the slides do not resolve explicitly). The consumption-leisure/labor equation 0=-n_t+y_t+lambda_t (a row of matrix C) is one of the 'static' equations used to eliminate n_t, c_t, r_t and reduce the system to the two dynamic variables k_t and lambda_t (eq. 8: y_t=(1/rho)z_t+k_{t-1}+((1-rho)/rho)lambda_t). The curvature parameter rho (Cobb-Douglas capital share) reappears throughout the alpha_1..alpha_6 coefficients that determine the policy function — in particular alpha_3=Y-bar/(rho*K-bar) and the (1-rho)/rho term multiplying lambda_t in eq. (8) — so rho continues to govern how strongly labor/output respond to the multiplier (shadow value of wealth) and to capital.

### [COMPUT] Metodo computacional

Uhlig's Method of Undetermined Coefficients, done fully by hand for the example: (1) write the log-linearized system in Uhlig's general matrix form 0=Ax_t+Bx_{t-1}+Cy_t+Dz_t and 0=E_t[Fx_{t+1}+Gx_t+Hx_{t-1}+Jy_{t+1}+Ky_t+Lz_{t+1}+Mz_t] with z_{t+1}=Nz_t+epsilon_{t+1}; (2) reduce algebraically to a 2-equation system in (k_t, lambda_t) using alpha_1..alpha_6; (3) guess linear policy functions k_t=eta_KK*k_{t-1}+eta_Kz*z_t, lambda_t=eta_lambdaK*k_{t-1}+eta_lambdaz*z_t; (4) match coefficients on k_{t-1} to get a quadratic in eta_KK, select the stable (<1) root; (5) match coefficients on z_t to get a linear system for eta_Kz, eta_lambdaz. Uhlig's Matlab codes solve for P,Q,R,S automatically from matrices A-N (previewed here, implemented in Part 3).

### Intuicion general

Once the model is log-linearized (Part 1), 'solving' it means finding the policy functions — expressing every endogenous variable as a function of the state variables (lagged capital k_{t-1} and the TFP shock z_t). Uhlig's trick is to first collapse the whole system down to just two variables (capital and the Lagrange multiplier lambda_t, since consumption, output, labor and the capital return can all be written in terms of these two plus the state), then GUESS the solution is linear in the states with unknown ('undetermined') coefficients eta, and finally exploit that the resulting equations must hold for every possible realization of k_{t-1} and z_t — which is only possible if each coefficient is exactly right. This turns solving a dynamic stochastic model into solving one quadratic equation (for eta_KK) plus two linear equations (for eta_Kz, eta_lambdaz) entirely by hand for this example — exactly what Uhlig's Matlab code automates in general.

### Ejemplos y ejercicios

- Full worked example: filling in Uhlig's A-N matrices for the Hansen/Uhlig RBC model (5x1 A,B,D vectors; 5x5 matrix C; 1x1 F,G,H,M; 1x5 J,K,L; 1x1 N=psi), then solving by hand for eta_KK (selecting the stable root <1), eta_lambdaK, eta_Kz, eta_lambdaz, i.e. the complete policy function of the model.

### Anotaciones a mano (tuyas)

- Slide 3 ('Undetermined Coefficients'): 'x_t' highlighted purple and 'endogenous state variables' underlined/highlighted purple in the general-notation bullet.
- Slide 5 (matrix C, filling matrices): small handwritten column headers 'c, y, n, lambda, r' penciled in above matrix C to label which column corresponds to which variable — the student's own annotation for keeping track of Uhlig's abstract matrix notation.
- Slide 10 (analytical solution, eqs. 1-7): highlighting in yellow/green/purple across several terms of equation (5), e.g. 'Y-bar*y_t' and '(1-delta)K-bar*k_{t-1}' highlighted, and a purple mark over 'K-bar*k_t', apparently tracking which terms get substituted where.
- Slide 11 ('Uhlig writes the system as a function of only two variables'): a faint handwritten note in the blank space below the bullets, roughly 'use (5),(6); y divided (both entries) on K-bar' — the student's shorthand recording how equations (5) and (6) are combined and divided through by K-bar to eliminate c_t, y_t, r_t.
- A full HANDWRITTEN page inserted between the printed slides (corresponding to the y_t=(1/rho)z_t+k_{t-1}+((1-rho)/rho)lambda_t derivation and eqs. 9-10): the student re-derives the reduction to two variables step by step, reproducing 0=-k_t+alpha_1*k_{t-1}+alpha_2*lambda_t+alpha_3*z_t and 0=E_t[-lambda_t+alpha_4*k_t+alpha_5*lambda_{t+1}+alpha_6*z_{t+1}] with color-coded highlighting (green/yellow/blue) tying each alpha coefficient back to the term it replaces (e.g. Y-bar/K-bar+(1-delta) highlighted and linked to alpha_1), and writes out r_{t+1}=rho*(Y-bar/K-bar)*(y_t-k_{t-1}) substituted into the Euler equation — a complete independent re-derivation of the printed result, suggesting the student worked through the algebra live rather than just copying it.
- Slide 13 (guessed policy functions): 'k_t' and 'lambda_t' guesses both highlighted (blue/yellow) and a faint handwritten annotation resembling 'psi*z_t + phi' penciled near the E_t(z_{t+1})=psi*z_t substitution, marking that step.

### Conexiones con otros temas

- Direct continuation of Topic 5 First Part (uses the log-linearized equations derived there)
- Uhlig (1999) in Marimon & Scott (eds.), Computational Methods for the Study of Dynamic Economies — general notation and Matlab toolbox
- Ljungqvist & Sargent (2004) Recursive Macroeconomic Theory — saddle-path/stability discussion
- Stokey, Lucas & Prescott (1989) — recursive methods, uniqueness of the stable solution
- Sets up Topic 5 Third Part, where Uhlig's actual Matlab code (solve.m) automates exactly this hand computation

---

## Computational implementation — using Harald Uhlig's Matlab toolkit (Undetermined Coefficients / log-linearization solver, version 4.3) to solve, simulate, and analyze the Hansen (1985)/Uhlig (1999) RBC model that was log-linearized and solved by hand in Topic 5 First and Second Parts. Purely a software/implementation session, no new theory. (Note: the internal slide metadata reads 'Fall 2023' / 'Version: October 31, 2023', despite the filename indicating 'Agosto 2019' — transcribed as-is; likely a reused/updated template across course years.)

*Fuente: `Macro_Din_II_Agosto_2019Topic5ThirdPart.pdf`*

*Secciones: Title/roadmap slide | Matlab programs: downloading Uhlig's toolkit (version 4.3) | Description of exampl1.m (Hansen's model as coded by Uhlig: declares parameters, computes steady state, solves the model) | Description of solve.m (the routine that solves the model) and sol_out.m (displays the solution) | Computing impulse-response functions, second moments, and correlations | Class plan: review an accompanying PDF on Uhlig's example, run the code, interpret the solution, program impulse-response functions*

### Conceptos clave

- **exampl1.m** - Uhlig toolkit script that declares model parameters, computes steady-state values, and calls the solver for Hansen's (1985) RBC model.
- **solve.m** - The toolkit's core routine; takes the filled A-N matrices (Uhlig's general notation) and returns the policy function matrices P,Q,R,S via the Method of Undetermined Coefficients.
- **sol_out.m** - Displays/reports the computed solution (policy function coefficients).
- **Impulse-response functions / second moments / correlations** - Standard outputs computed from the policy function once solved, used to characterize the model's business-cycle properties and compare with data.

### [COMPUT] Metodo computacional

Harald Uhlig's Matlab toolkit for solving linear rational-expectations models via the Method of Undetermined Coefficients (version 4.3, downloadable from Uhlig's website). Key files: exampl1.m (declares parameters, computes steady state, sets up and calls the solver for Hansen's 1985 model), solve.m (the main solver routine computing policy-function matrices P,Q,R,S), sol_out.m (displays the solution). The toolkit is also used to calculate impulse-response functions, second moments, and correlations of the solved model.

### Intuicion general

This session closes the log-linearization/Uhlig's-method sequence by moving from pencil-and-paper derivation (Parts 1-2) to Uhlig's actual Matlab implementation: the same Hansen (1985) RBC model, the same A-N matrices, but now solved automatically by solve.m instead of by hand, so students can check their hand-derived eta coefficients against the code's output and then use the toolkit to generate impulse-response functions and second moments — the standard quantitative outputs of any RBC exercise.

### Ejemplos y ejercicios

- exampl1.m — Uhlig's own coded version of the Hansen (1985) model, used as the running example for the whole log-linearization/Undetermined-Coefficients sequence (Parts 1-3).

### Conexiones con otros temas

- Direct continuation of Topic 5 First and Second Parts (same Hansen/Uhlig RBC model, now solved computationally instead of by hand)
- Uhlig's toolkit page: https://voices.uchicago.edu/haralduhlig/code-and-material/
- Contrasts with Dynare, described in Part 1 as a more automated 'black-box' alternative to Uhlig's more transparent, hand-inspectable toolkit

---

## Topic 5 (handwritten lecture notes, Prof. Felipe Meza): 'Solving the model by hand' -- the method of undetermined coefficients applied to a two-equation loglinearized system in capital k_t and the multiplier lambda_t, deriving the quadratic in eta_kk, choosing the stable root |eta_kk| < 1, and then solving a 2x2 linear system for the coefficients on the TFP shock z_t.

*Fuente: `Topic5Solving_by_hand.pdf`*

*Secciones: Set-up: equations (9) and (10) from p.12 of the Presentation | Conjecturing the policy functions (a) and (b) | Substituting the guesses into (9) and factoring k_{t-1} and z_t | Substituting the guesses into (10), handling lambda_{t+1} (must substitute k_t inside) and E_t z_{t+1} = psi z_t | Matching coefficients: both equations must hold for any (k_{t-1}, z_t), so each bracketed sum must be zero | Coefficients on k_{t-1}: two equations -> the quadratic in eta_kk | Root selection: the stable root |eta_kk| < 1; recovering eta_lambda_k | Coefficients on z_t: a 2x2 linear system for eta_kz and eta_lambda_z*

### Supuestos

> The full non-linear model has ALREADY been loglinearized and algebraically reduced to the two equations (9) and (10) in (k_t, lambda_t, z_t) -- the notes explicitly say 'assume by now you have done algebra to get equation (9) and (10) in the Presentation, p.12'.
>
> The equilibrium is a linear (first-order) function of the minimal state (k_{t-1}, z_t) -- i.e. a linear rational-expectations solution exists and is unique after imposing stability.
>
> z_t follows an AR(1): z_{t+1} = psi z_t + epsilon_{t+1} with E_t epsilon_{t+1} = 0.
>
> alpha_2 =/= 0 and alpha_5 =/= 0 (needed to divide).
>
> The two equations must hold for ANY possible value of (k_{t-1}, z_t), which is what licenses coefficient matching.
>
> Exactly one root of the quadratic satisfies |eta_kk| < 1 (saddle-path stability).
>

### Conceptos clave

- **Method of undetermined coefficients** - Guess that the endogenous variables are linear functions of the state (k_{t-1}, z_t), substitute the guesses everywhere in the loglinearized equilibrium conditions, collect terms, and impose that the coefficient multiplying each state variable be zero (since the equations must hold for ANY value of the state).
- **Policy (decision) functions** - k_t = eta_kk k_{t-1} + eta_kz z_t and lambda_t = eta_lambda_k k_{t-1} + eta_lambda_z z_t. eta_kk is the scalar analogue of Uhlig's P and is what 'links k_t to k_{t-1}', i.e. the endogenous persistence of capital.
- **Forward substitution of the guess** - Where lambda_{t+1} appears, substitute lambda_{t+1} = eta_lambda_k k_t + eta_lambda_z z_{t+1}; then k_t must ITSELF be replaced by its own policy function eta_kk k_{t-1} + eta_kz z_t. The professor flags this in red: 'alpha_5 lambda_{t+1}, need to substitute k_t!'
- **Law of iterated expectations on the AR(1)** - E_t(psi z_t + epsilon_{t+1}) = psi z_t, since E_t epsilon_{t+1} = 0. Written in magenta on the notes and used to eliminate z_{t+1}.
- **Stable root selection** - The quadratic in eta_kk has two roots eta_kk,1 and eta_kk,2; keep the one with |eta_kk| < 1 (written in red: 'the stable one: |eta_kk| < 1'), which delivers a convergent capital path.

### Teoremas, lemas y proposiciones

> **Quadratic characterization of the capital autoregressive coefficient**
>
> Given 0 = -k_t + alpha_1 k_{t-1} + alpha_2 lambda_t + alpha_3 z_t (eq. 9) and 0 = E_t[-lambda_t + alpha_4 k_t + alpha_5 lambda_{t+1} + alpha_6 z_{t+1}] (eq. 10), the coefficient on k_{t-1} in both equations must vanish: (i) -eta_kk + alpha_1 + alpha_2 eta_lambda_k = 0 and (ii) -eta_lambda_k + alpha_4 eta_kk + alpha_5 eta_lambda_k eta_kk = 0. Solving (i) for eta_lambda_k = -alpha_1/alpha_2 + eta_kk/alpha_2 and substituting into (ii), then multiplying every term by alpha_2/alpha_5, yields 0 = eta_kk^2 - eta_kk( alpha_1 - (alpha_2/alpha_5) alpha_4 + 1/alpha_5 ) + alpha_1/alpha_5.
>
> *Supuestos requeridos:* alpha_2 =/= 0 and alpha_5 =/= 0; the two loglinear equations (9) and (10) hold for every possible value of (k_{t-1}, z_t); z_t follows z_{t+1} = psi z_t + epsilon_{t+1} with E_t epsilon_{t+1} = 0
>
> *Garantiza:* eta_kk is a root of a scalar quadratic; take the root with |eta_kk| < 1 and recover eta_lambda_k = -alpha_1/alpha_2 + eta_kk/alpha_2. This is the by-hand version of Uhlig's Ftilde P^2 + Gtilde P + Htilde = 0 with the P < 1 stability selection.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Equation (9) (Presentation p.12) | `0 = -k_t + \alpha_1 k_{t-1} + \alpha_2 \lambda_t + \alpha_3 z_t` | The deterministic (intratemporal + resource) block reduced to one equation relating capital today, capital yesterday, the multiplier and TFP. | Starting point; assumes the algebra reducing the full loglinear system has already been done. |
| Equation (10) (Presentation p.12) | `0 = E_t\left[-\lambda_t + \alpha_4 k_t + \alpha_5 \lambda_{t+1} + \alpha_6 z_{t+1}\right]` | The expectational (Euler) block. | Starting point. |
| Conjectured policy function for capital (a) | `k_t = \eta_{kk} k_{t-1} + \eta_{kz} z_t` | Capital is a linear function of the two states. | Substitute wherever k_t appears. |
| Conjectured policy function for the multiplier (b) | `\lambda_t = \eta_{\lambda k} k_{t-1} + \eta_{\lambda z} z_t` | The costate/multiplier is a linear function of the same two states. | Substitute wherever lambda_t appears; and lambda_{t+1} = eta_lambda_k k_t + eta_lambda_z z_{t+1}. |
| Equation (9) after substitution and factoring | `0 = \left(-\eta_{kk} + \alpha_1 + \alpha_2 \eta_{\lambda k}\right) k_{t-1} + \left(-\eta_{kz} + \alpha_2 \eta_{\lambda z} + \alpha_3\right) z_t` | Both bracketed coefficients must be zero. | Gives one restriction on the k-coefficients and one on the z-coefficients. |
| Equation (10) after substitution and factoring | `0 = k_{t-1}\left(-\eta_{\lambda k} + \alpha_4 \eta_{kk} + \alpha_5 \eta_{\lambda k}\eta_{kk}\right) + z_t\left(-\eta_{\lambda z} + \alpha_4 \eta_{kz} + \alpha_5 \eta_{\lambda z}\psi + \alpha_6 \psi + \alpha_5 \eta_{\lambda k}\eta_{kz}\right)` | Same logic; note the product terms alpha_5 eta_lambda_k eta_kk and alpha_5 eta_lambda_k eta_kz arising from substituting k_t inside lambda_{t+1}. | Gives the second restriction on the k-coefficients and the second on the z-coefficients. |
| Expectation of the AR(1) | `E_t\left(\psi z_t + \varepsilon_{t+1}\right) = \psi z_t` | Removes z_{t+1} and epsilon_{t+1} from the expectational equation. | Every time z_{t+1} appears inside E_t. |
| Restriction on k_{t-1} from (9) | `-\eta_{kk} + \alpha_1 + \alpha_2 \eta_{\lambda k} = 0 \;\Longrightarrow\; \eta_{\lambda k} = -\frac{\alpha_1}{\alpha_2} + \frac{\eta_{kk}}{\alpha_2}` | Expresses the multiplier's loading on capital in terms of eta_kk. | Substitute into the second restriction to eliminate eta_lambda_k. |
| Restriction on k_{t-1} from (10) | `-\eta_{\lambda k} + \alpha_4 \eta_{kk} + \alpha_5 \eta_{\lambda k}\eta_{kk} = 0` | The second equation in the two unknowns (eta_kk, eta_lambda_k). | Combine with the previous one. |
| Intermediate substitution | `+\frac{\alpha_1}{\alpha_2} - \frac{\eta_{kk}}{\alpha_2} + \alpha_4\eta_{kk} - \alpha_5\frac{\alpha_1}{\alpha_2}\eta_{kk} + \alpha_5\frac{\eta_{kk}}{\alpha_2}\eta_{kk} = 0` | After plugging eta_lambda_k out; then multiply every term by alpha_2/alpha_5. | Algebra step towards the quadratic. |
| After multiplying by alpha_2/alpha_5 | `\frac{\alpha_1}{\alpha_5} - \eta_{kk}\frac{1}{\alpha_5} + \eta_{kk}\alpha_4\frac{\alpha_2}{\alpha_5} - \alpha_1 \eta_{kk} + \eta_{kk}^{2} = 0` | Same equation normalized so that the coefficient on eta_kk^2 is 1. | Immediately before boxing the quadratic. |
| THE QUADRATIC IN eta_kk (boxed in the notes) | `0 = \eta_{kk}^{2} - \eta_{kk}\left(\alpha_1 - \frac{\alpha_2}{\alpha_5}\alpha_4 + \frac{1}{\alpha_5}\right) + \frac{\alpha_1}{\alpha_5}` | The central result of the note: a monic scalar quadratic whose roots are the candidate autoregressive coefficients of capital. | Apply the quadratic formula; keep the root with \|eta_kk\| < 1. |
| Recovering eta_lambda_k | `\eta_{\lambda k} = -\frac{\alpha_1}{\alpha_2} + \frac{\eta_{kk}}{\alpha_2}` | Once the stable eta_kk is chosen, eta_lambda_k follows directly. | After root selection. (The handwriting shows a '2' in the denominator of the second term; the correct denominator is alpha_2.) |
| Restriction on z_t from (9) | `-\eta_{kz} + \alpha_2 \eta_{\lambda z} + \alpha_3 = 0` | First of the two linear equations in the z-loadings. | Once eta_kk and eta_lambda_k are known. |
| Restriction on z_t from (10) | `-\eta_{\lambda z} + \alpha_4 \eta_{kz} + \alpha_5 \eta_{\lambda k}\eta_{kz} + \left(\alpha_5 \eta_{\lambda z} + \alpha_6\right)\psi = 0` | Second linear equation; eta_lambda_k is already known so the only unknowns are eta_kz and eta_lambda_z. | Solve the 2x2 linear system; 'the result is in the Presentation'. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Labor does not appear explicitly in these notes: the system has already been reduced to two equations in capital k_t and the multiplier lambda_t, with hours substituted out. Implicitly, hours n_t (and consumption, output, investment) are recovered afterwards from the static equations as linear functions of (k_{t-1}, z_t), exactly as y_t = R x_{t-1} + S z_t does in the project. Hence any labor-demand curvature parameter (alpha in Cobb-Douglas) and labor-supply curvature parameter (v) are buried inside the reduced-form coefficients alpha_1,...,alpha_6.

### [COMPUT] Metodo computacional

Method of undetermined coefficients, done by hand: (1) start from the reduced loglinear pair (9)-(10); (2) conjecture linear policy functions (a) and (b) in the state (k_{t-1}, z_t); (3) substitute (a) and (b) everywhere, remembering to substitute k_t inside lambda_{t+1}; (4) use E_t(psi z_t + epsilon_{t+1}) = psi z_t; (5) factor k_{t-1} and z_t and set each coefficient to zero; (6) from the two k_{t-1} coefficients derive and solve the quadratic in eta_kk, keeping the root with |eta_kk| < 1; (7) recover eta_lambda_k = -alpha_1/alpha_2 + eta_kk/alpha_2; (8) from the two z_t coefficients solve the resulting 2x2 linear system for eta_kz and eta_lambda_z.

### [RECETA] Solucion paso a paso

1. STEP 1 - Take as given the two reduced loglinear equations: (9) 0 = -k_t + alpha_1 k_{t-1} + alpha_2 lambda_t + alpha_3 z_t; (10) 0 = E_t[-lambda_t + alpha_4 k_t + alpha_5 lambda_{t+1} + alpha_6 z_{t+1}].
2. STEP 2 - Conjecture (a) k_t = eta_kk k_{t-1} + eta_kz z_t and (b) lambda_t = eta_lambda_k k_{t-1} + eta_lambda_z z_t.
3. STEP 3 - Substitute (a) wherever k_t appears and (b) wherever lambda_t appears. For lambda_{t+1}, write lambda_{t+1} = eta_lambda_k k_t + eta_lambda_z z_{t+1} AND THEN replace k_t by (a) -- this second substitution is what produces the products eta_lambda_k eta_kk and eta_lambda_k eta_kz.
4. STEP 4 - Use E_t(psi z_t + epsilon_{t+1}) = psi z_t to remove all t+1 shock terms.
5. STEP 5 - Factor out k_{t-1} and z_t in each equation, obtaining (9): 0 = (-eta_kk + alpha_1 + alpha_2 eta_lambda_k) k_{t-1} + (-eta_kz + alpha_2 eta_lambda_z + alpha_3) z_t and (10): 0 = (-eta_lambda_k + alpha_4 eta_kk + alpha_5 eta_lambda_k eta_kk) k_{t-1} + (-eta_lambda_z + alpha_4 eta_kz + alpha_5 eta_lambda_z psi + alpha_6 psi + alpha_5 eta_lambda_k eta_kz) z_t.
6. STEP 6 - Because these must hold for every (k_{t-1}, z_t), set all four bracketed coefficients to zero.
7. STEP 7 - k_{t-1} block: from (9), eta_lambda_k = -alpha_1/alpha_2 + eta_kk/alpha_2. Substitute into (10)'s k-coefficient, multiply through by alpha_2/alpha_5, and obtain the quadratic 0 = eta_kk^2 - eta_kk(alpha_1 - (alpha_2/alpha_5)alpha_4 + 1/alpha_5) + alpha_1/alpha_5.
8. STEP 8 - Apply the quadratic formula to get eta_kk,1 and eta_kk,2; SELECT THE STABLE ROOT |eta_kk| < 1. Then compute eta_lambda_k = -alpha_1/alpha_2 + eta_kk/alpha_2.
9. STEP 9 - z_t block: with eta_lambda_k known, solve the linear system -eta_kz + alpha_2 eta_lambda_z + alpha_3 = 0 and -eta_lambda_z + alpha_4 eta_kz + alpha_5 eta_lambda_k eta_kz + (alpha_5 eta_lambda_z + alpha_6) psi = 0 for the two unknowns eta_kz and eta_lambda_z (2 equations, 2 unknowns).
10. STEP 10 - The resulting closed-form expressions are reported in the Topic 5 Presentation; with all four etas in hand the model is solved and can be simulated or used for IRFs.

### Intuicion general

This is the pencil-and-paper version of what Matlab does in the project. The logic is: if you believe the solution is linear in the state, then the equilibrium conditions become polynomials in the state variables that must vanish identically -- and a polynomial that is zero for every value of its argument must have all coefficients zero. That converts an infinite-dimensional functional equation into a handful of algebraic equations in the unknown loadings eta. Two subtleties are flagged in colour in the notes. First, when you substitute lambda_{t+1}, you must remember it is a function of k_t, which is itself a function of (k_{t-1}, z_t) -- forgetting this second-level substitution is the classic mistake and is what generates the QUADRATIC (the product eta_lambda_k * eta_kk). Second, expectations of the future shock collapse to psi z_t. The quadratic having two roots is not a defect: it reflects that the Euler equation alone does not pin down the path -- the transversality/stability condition does, and it selects |eta_kk| < 1. Once the capital block is solved, the shock block is only a linear 2x2 system because eta_lambda_k is already known.

### Ejemplos y ejercicios

- The worked example IS the RBC/neoclassical growth model of the Presentation (Topic 5), whose equations (9) and (10) on p.12 are taken as given; the final closed-form answers for eta_kz and eta_lambda_z are said to be 'in the Presentation'.

### Anotaciones a mano (tuyas)

- These pages are ENTIRELY handwritten by the professor (they are the lecture note itself), with a deliberate colour code rather than student marks; the colours carry the pedagogical content.
- p.1 (blue underline): 'Presentation, p.12' underlined -- the source of equations (9) and (10).
- p.1 (blue braces): under the substituted terms in (9), '-eta_kk k_{t-1} - eta_kz z_t' is braced and labelled '-k_t'; 'alpha_2 eta_lambda_k k_{t-1} + alpha_2 eta_lambda_z z_t' is braced and labelled 'alpha_2 lambda_t' -- showing which guess replaced which term.
- p.2 (blue box): the factored version of (9) is boxed and labelled '(9):' -- 0 = (-eta_kk + alpha_1 + alpha_2 eta_lambda_k)k_{t-1} + (-eta_kz + alpha_2 eta_lambda_z + alpha_3)z_t.
- p.2 (RED warning): next to 'alpha_5 eta_lambda_k k_t + alpha_5 eta_lambda_z z_{t+1}' the note reads 'alpha_5 lambda_{t+1}; need to substitute k_t!' -- an explicit CHECK/warning that the guess must be applied recursively.
- p.2 (magenta box): 'alpha_5 eta_lambda_z E_t(psi z_t + epsilon_{t+1})' boxed in magenta.
- p.3 (magenta box and note): 'alpha_6 E_t(psi z_t + epsilon_{t+1})' boxed; below, in magenta, 'where we used E_t(psi z_t + epsilon_{t+1}) = psi z_t' with the equals sign double-underlined.
- p.3 (blue box labelled '(10):'): the factored version of (10), 0 = k_{t-1}(-eta_lambda_k + alpha_4 eta_kk + alpha_5 eta_lambda_k eta_kk) + z_t(-eta_lambda_z + alpha_4 eta_kz + alpha_5 eta_lambda_z psi + alpha_6 psi + alpha_5 eta_lambda_k eta_kz), with the magenta sub-box highlighting the two psi terms.
- p.3 (bottom): 'Next: These 2 equations must hold simultaneously for any possible value of (k_{t-1}, z_t)'.
- p.4 (top): 'this requires that each coefficient (the sums in parentheses) must be 0.'
- p.4 (red/blue underlines): 'Let us work with the coefficients for k_{t-1}. There is one in (9), and one in (10)'; and 'We want to compute eta_kk, as it links k_t to k_{t-1}' (underlined in red).
- p.5 (blue box): the boxed quadratic 0 = eta_kk^2 - eta_kk(alpha_1 - (alpha_2/alpha_5)alpha_4 + 1/alpha_5) + alpha_1/alpha_5.
- p.5 (RED, circled): next to eta_lambda_k = -alpha_1/alpha_2 + eta_kk/alpha_2, eta_kk is circled in red with the note 'the stable one: |eta_kk| < 1'. NOTE: the handwritten denominator of the second term looks like '2' but must be alpha_2.
- p.5 (blue): 'At this point we are done with the coefficients for k_{t-1}. Now let us calculate the coefficients for z_t' and 'We collect its coefficients, one from (9) and one from (10)'.
- p.6: 'We just calculated eta_lambda_k => the unknowns are: eta_kz, eta_lambda_z'; 'It is a linear system of 2 equations and 2 unknowns, which we can solve'; 'The result is in the Presentation.'

### Conexiones con otros temas

- Direct hand-computed analogue of Proyecto.pdf's matrix method: eta_kk <-> P, eta_kz <-> Q, and (eta_lambda_k, eta_lambda_z) <-> (R, S) for the costate. The quadratic 0 = eta_kk^2 - eta_kk(alpha_1 - (alpha_2/alpha_5)alpha_4 + 1/alpha_5) + alpha_1/alpha_5 is the scalar special case of 0 = Ftilde P^2 + Gtilde P + Htilde, and '|eta_kk| < 1' is exactly the 'choose P < 1' rule.
- The root-selection rule is the Blanchard-Kahn condition in its simplest one-state form; it is the same logic as the transversality condition used in Topic 2 to rule out explosive debt/capital paths.
- Relies on the loglinearization step done in Topic 4 / the project; without the reduction to (9)-(10) the method cannot start.
- For empirical work: eta_kk is precisely the model-implied persistence one would compare with the autoregressive coefficient of detrended capital or investment in the data.

---

## Computing Program (Proyecto Computacional), Dynamic Macroeconomics II, ITAM (solution by Coronel, Fernandez & Sabido): RBC / stochastic neoclassical growth model with endogenous labor and GHH-type preferences. Full pipeline: planner's Lagrangian -> FOCs -> non-linear system -> non-stochastic steady state -> loglinearization -> mapping into Uhlig's matrices A,B,C,D,F,G,H,J,K,L,M,N -> undetermined-coefficient solution P,Q,R,S -> Matlab program (exampl1modifv1.m) -> impulse response functions.

*Fuente: `Proyecto.pdf`*

*Secciones: Q0. Why do we assume nu > 1? (convexity of the disutility of work) | Q1. Lagrangian of the Planner's Problem | Q2. First order conditions (C_t, N_t, K_{t+1}, lambda_t) | Q3. Rewriting the system with factor payments as functions of the ratios Y_t/N_t and Y_t/K_t; the six-equation non-linear system (Leisure-consumption, Capital accumulation, Technology, Feasibility, Euler, TFP) | Q4. Evaluation at the non-stochastic steady state (bar-X notation) | Q5. Loglinearization equation by equation (lowercase = log deviations from steady state) | Q6. Matlab program starting from exampl1modifv1.m (Canvas) | Q6.1 Calibration equation for the parameter tau | Q6.2 Identification of the Uhlig vectors x_t, y_t, z_t | Q6.3 Filling in the matrices A, B, C, D, F, G, H, J, K, L, M, N | Q6.4 Computing the solution (recursive law of motion) matrices P, Q, R, S | Q6.5 Programming the impulse response function (1% shock, T = 150, plot t = -1 to t = 33) | Q6.6 Report by hand the first five values of output y_t in response to the shock (left blank in this copy)*

### Supuestos

> Representative agent, closed economy, no government, no taxes and no distortions: the planner's allocation equals the competitive equilibrium.
>
> Period utility is GHH: ln(C_t - tau N_t^v / v). Consumption enters logarithmically inside the composite, and there is no wealth effect on labor supply.
>
> v > 1, so the disutility of labor is strictly convex (increasing marginal disutility of hours).
>
> tau > 0 is a preference weight on the disutility of work (NOT a tax).
>
> Technology is Cobb-Douglas with constant returns to scale, Y_t = Z_t K_t^alpha N_t^{1-alpha}, 0 < alpha < 1.
>
> Capital depreciates at a constant rate 0 < delta < 1 and takes one period to build (K_{t+1} chosen at t).
>
> Discount factor 0 < beta < 1, constant.
>
> TFP is an AR(1) in logs with persistence 0 < psi < 1 and iid innovations with mean 0 and variance sigma^2 (distribution D unspecified beyond its first two moments -- certainty equivalence of the loglinear solution means only sigma matters).
>
> The economy is close enough to the non-stochastic steady state that a first-order (log)linear approximation is accurate; e^x approx 1 + x.
>
> The matrix C is invertible (there are exactly as many equations in the deterministic block as control variables).
>
> Only one root of the quadratic in P satisfies |P| < 1 (saddle-path stability / Blanchard-Kahn holds).
>

### Conceptos clave

- **Social planner's problem** - The Pareto problem chosen instead of the decentralized equilibrium: the planner maximizes E_t sum_j beta^j u(C_{t+j}, N_{t+j}) subject to the resource constraint Z_t K_t^alpha N_t^{1-alpha} + (1-delta)K_t = C_t + K_{t+1}. By the welfare theorems its allocation coincides with the competitive equilibrium (no distortions in this model).
- **GHH-type (Greenwood-Hercowitz-Huffman) preferences** - Period utility ln(C_t - tau N_t^v / v): consumption and labor enter through the single composite C_t - tau N_t^v/v. This eliminates the wealth effect on labor supply, so the intratemporal condition collapses to tau N_t^{v-1} = W_t (labor supply depends only on the wage), which is why the leisure-consumption equation becomes tau N_t^v = (1-alpha) Y_t with no C_t in it.
- **Convexity of the disutility of work (nu > 1)** - With disutility tau N_t^v / v, the first derivative in N is positive and the second derivative (v-1)N^{v-2} is positive iff v > 1; thus marginal disutility of working is increasing, matching the real-world idea that each extra hour hurts more than the previous one.
- **Factor payments written as ratios** - Using constant returns to scale, W_t = (1-alpha) Z_t (K_t/N_t)^alpha = (1-alpha) Y_t/N_t and the gross return R_{t+1} = alpha Z_t (N_t/K_t)^{1-alpha} + (1-delta) = alpha Y_t/K_t + (1-delta). This trick removes Z_t, K_t and N_t separately from the Euler equation and leaves only the observable ratios Y/N and Y/K.
- **Non-stochastic steady state** - The fixed point of the deterministic system with Z_t = Zbar, all variables constant, no shocks: tau N^v = (1-alpha)Y, I = delta K, Y = Z K^alpha N^{1-alpha}, Y = C + I, 1/beta = alpha Y/K + (1-delta).
- **Loglinearization** - Write X_t = Xbar e^{x_t} and use e^{x} approx 1 + x for x near zero, so x_t = ln(X_t/Xbar) is the percent (log) deviation from steady state. Applied equation by equation to the six non-linear equations.
- **Uhlig's (1999) toolkit notation** - Partition the loglinear model into endogenous states x_t, other endogenous ('jump'/control) variables y_t, and exogenous states z_t, and write it as (1) 0 = A x_t + B x_{t-1} + C y_t + D z_t (deterministic block), (2) 0 = E_t[F x_{t+1} + G x_t + H x_{t-1} + J y_{t+1} + K y_t + L z_{t+1} + M z_t] (expectational block), (3) z_{t+1} = N z_t + epsilon_{t+1}, (4) E_t[epsilon_{t+1}] = 0.
- **Recursive law of motion** - The guessed and verified solution x_t = P x_{t-1} + Q z_t, y_t = R x_{t-1} + S z_t. P governs endogenous persistence, Q the impact of the shock on the state, R and S the response of the controls.
- **Method of undetermined coefficients** - Substitute the conjectured policy functions into (1) and (2), collect terms in x_{t-1} and z_t, and impose that each coefficient block be zero, which yields a matrix-quadratic in P and a linear equation in Q.
- **Stability / saddle-path selection** - The quadratic in P has two roots; only the one with |P| < 1 delivers a non-explosive (stable) path consistent with the transversality condition. The other root is discarded.
- **Impulse response function (IRF)** - The deterministic path of the loglinear system after a one-time 1% innovation to z at date 0 and no further shocks; computed by iterating x_t = P x_{t-1} + Q z_t, y_t = R x_{t-1} + S z_t with z_t = psi^t z_0.

### Teoremas, lemas y proposiciones

> **Convexity criterion for the labor-disutility exponent**
>
> For the disutility term N_t^v / v, d/dN (N^v/v) = N^{v-1} > 0 and d^2/dN^2 (N^v/v) = (v-1) N^{v-2} > 0 if and only if v > 1.
>
> *Supuestos requeridos:* N_t > 0; tau > 0
>
> *Garantiza:* v > 1 is exactly what makes the disutility of work convex (increasing marginal disutility), which is required for an interior, well-behaved labor choice. Note the document's typo: it prints d/dN (N^v/v) = N_t^v when it should be N_t^{v-1}.

> **Uhlig's undetermined-coefficient characterization of P and Q**
>
> Eliminate y_t from (1) as y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t) and substitute into (2). Defining Ftilde = F - J C^{-1} A, Gtilde = G - J C^{-1} B - K C^{-1} A, Htilde = H - K C^{-1} B, Ltilde = L - J C^{-1} D, Mtilde = M - K C^{-1} D, the coefficient restrictions are 0 = Ftilde P^2 + Gtilde P + Htilde and 0 = Ltilde N + Mtilde + Ftilde Q N + Ftilde P Q + Gtilde Q.
>
> *Supuestos requeridos:* C is square and invertible (here 4x4, one equation of the deterministic block per control variable); the expectational block has as many equations as endogenous states (here 1); z_t is AR(1) with matrix N
>
> *Garantiza:* Since P is a scalar here, P = (-Gtilde +/- sqrt(Gtilde^2 - 4 Ftilde Htilde)) / (2 Ftilde); choose the root with P < 1 for stability. Then Q solves the second (linear) equation, and R = -C^{-1}(A P + B), S = -C^{-1}(A Q + D).

> **Steady-state modified golden rule with depreciation**
>
> 1/beta = alpha Y/K + (1 - delta), hence Y/K = (1/beta - 1 + delta)/alpha and alpha beta Y/K = 1 - beta(1-delta).
>
> *Supuestos requeridos:* Cobb-Douglas technology; constant discount factor beta; no taxes, no growth
>
> *Garantiza:* Pins down the steady-state capital-output ratio from beta, delta, alpha alone; the identity alpha beta Y/K = 1 - beta(1-delta) is precisely the simplification the student writes over the loglinear Euler equation and over G.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Planner's Lagrangian | `\mathcal{L} = E_t \sum_{j=0}^{\infty} \beta^{j}\left\{ \ln\!\left(C_{t+j} - \tau \frac{N_{t+j}^{v}}{v}\right) + \lambda_{t+j}\left[ Z_{t+j}K_{t+j}^{\alpha}N_{t+j}^{1-\alpha} + K_{t+j}(1-\delta) - C_{t+j} - K_{t+j+1} \right]\right\}` | Planner maximizes expected discounted GHH utility subject to the period resource constraint; lambda_{t+j} is the multiplier on feasibility. | Step 1 of every project of this type: write the Lagrangian before differentiating. |
| FOC for consumption | `\frac{1}{C_t - \tau \frac{N_t^{v}}{v}} = \lambda_t` | Marginal utility of the GHH composite equals the shadow value of resources. | To substitute lambda out of the Euler and labor conditions. |
| FOC for labor | `\frac{\tau N_t^{v-1}}{C_t - \tau \frac{N_t^{v}}{v}} = \lambda_t (1-\alpha) Z_t \left(\frac{K_t}{N_t}\right)^{\alpha}` | Marginal disutility of an extra hour (in utils) equals the marginal product of labor times the shadow value of resources. | This is the labor-market equilibrium condition of the model; combined with the C-FOC it collapses to tau N^{v-1} = W_t. |
| FOC for capital (Euler in multiplier form) | `E_t\left[\beta \lambda_{t+1}\left( \alpha Z_{t+1}\left(\frac{N_{t+1}}{K_{t+1}}\right)^{1-\alpha} + (1-\delta)\right) - \lambda_t\right] = 0` | Intertemporal optimality: giving up one unit of consumption today buys the gross return on capital tomorrow. | Basis of the Euler equation and of the steady-state condition 1/beta = alpha Y/K + 1 - delta. |
| FOC for the multiplier (feasibility) | `Z_t K_t^{\alpha} N_t^{1-\alpha} + K_t(1-\delta) - C_t - K_{t+1} = 0` | Resource constraint holds with equality. | Splits into Y_t = C_t + I_t and I_t = K_{t+1} - (1-delta)K_t. |
| Wage (marginal product of labor) | `W_t = (1-\alpha) Z_t \left(\frac{K_t}{N_t}\right)^{\alpha} = (1-\alpha)\frac{Y_t}{N_t}` | Competitive real wage = labor share times average product of labor. | This IS the labor demand curve of the model; use it to write the labor condition in terms of Y/N. |
| Gross return to capital | `R_{t+1} = \alpha Z_t \left(\frac{N_t}{K_t}\right)^{1-\alpha} + (1-\delta) = \alpha \frac{Y_t}{K_t} + (1-\delta)` | Rental rate plus undepreciated capital. | To rewrite the Euler equation with only the ratio Y/K. |
| Ratio of multipliers | `\frac{\lambda_{t+1}}{\lambda_t} = \frac{C_t - \tau \frac{N_t^{v}}{v}}{C_{t+1} - \tau \frac{N_{t+1}^{v}}{v}}` | Stochastic discount factor written in terms of the GHH composite. | Substituted into the capital FOC to obtain the consumption Euler equation. |
| Leisure-consumption (intratemporal) equation | `\tau N_t^{v} = (1-\alpha) Y_t` | Labor supply = labor demand. Obtained by multiplying tau N^{v-1} = W_t by N_t and using W_t N_t = (1-alpha)Y_t. Note that C_t has dropped out: GHH kills the wealth effect. | Equation 1 of the non-linear system AND the equation used to calibrate tau. |
| Capital accumulation | `I_t = K_{t+1} - (1-\delta)K_t` | Law of motion of capital. | Equation 2 of the non-linear system. |
| Technology | `Y_t = Z_t K_t^{\alpha} N_t^{1-\alpha}` | Cobb-Douglas production with capital share alpha and TFP Z_t. | Equation 3. |
| Feasibility | `Y_t = C_t + I_t` | Closed economy, no government: output is consumed or invested. | Equation 4. |
| Euler equation | `\frac{1}{C_t - \tau \frac{N_t^{v}}{v}} = \beta E_t\left[\frac{1}{C_{t+1} - \tau \frac{N_{t+1}^{v}}{v}}\left(\alpha \frac{Y_{t+1}}{K_{t+1}} + (1-\delta)\right)\right]` | Intertemporal condition in terms of the GHH composite and the ratio Y/K. | Equation 5; the only expectational equation of the system. |
| TFP process | `\ln Z_t = (1-\psi)\ln \overline{Z} + \psi \ln Z_{t-1} + \epsilon_t,\quad \epsilon_t \overset{iid}{\sim} D(0,\sigma^2)` | AR(1) in logs for total factor productivity with persistence psi and long-run mean Zbar. | Equation 6; in log-deviations it becomes z_{t+1} = psi z_t + epsilon_{t+1}. |
| Steady state system | `\tau N^{v} = (1-\alpha) Y;\quad I = \delta K;\quad Y = Z K^{\alpha} N^{1-\alpha};\quad Y = C + I;\quad \frac{1}{\beta} = \alpha\frac{Y}{K} + (1-\delta)` | Five equations for the five steady-state unknowns (given parameters and a normalization). | Step 4; must be solved numerically/analytically before loglinearizing because the loglinear coefficients depend on steady-state ratios C/Y, I/Y, Y/K, tau N^v. |
| Steady-state capital-output ratio | `\frac{Y}{K} = \frac{\frac{1}{\beta} - 1 + \delta}{\alpha}\quad\Longleftrightarrow\quad \alpha\beta\frac{Y}{K} = 1 - \beta(1-\delta)` | Implied by the steady-state Euler equation. | Used to simplify G = -alpha beta Y/K = beta(1-delta) - 1 and the coefficient in the loglinear Euler (this is exactly the student's handwritten simplification). |
| Steady-state great ratios | `\frac{I}{Y} = \delta\frac{K}{Y} = \frac{\delta\alpha}{\frac{1}{\beta}-1+\delta},\qquad \frac{C}{Y} = 1 - \frac{I}{Y}` | Investment and consumption shares of output at the steady state. | These are the entries C/Y and I/Y that appear in the C matrix; they are implied by the steady-state block, not calibrated independently. |
| Loglinear leisure-consumption | `(1-\alpha) Y\, y_t = \tau v N^{v} n_t \quad\text{(from } 0 = (1-\alpha)Y e^{y_t} - \tau (N e^{n_t})^{v})` | Percent change in output must equal v times the percent change in hours scaled by the steady-state weights; using tau N^v = (1-alpha)Y this is simply y_t = v n_t. | Row 1 of the Uhlig deterministic block. IMPORTANT for labor: it says n_t = y_t / v, i.e. the (Frisch) labor-supply elasticity is 1/(v-1) in wage terms and hours move one-for-v with output. |
| Loglinear capital accumulation | `0 = K e^{k_{t+1}} - (1-\delta) K e^{k_t} - I e^{i_t} \;\Rightarrow\; 0 \approx K k_{t+1} - (1-\delta)K k_t - \delta K i_t \;\Rightarrow\; k_{t+1} = (1-\delta)k_t + \delta i_t` | Log-deviation law of motion; note I = delta K was used to cancel levels. | Row 2 of the deterministic block. |
| Loglinear technology | `0 = Y e^{y_t} - Z e^{z_t}(K e^{k_t})^{\alpha}(N e^{n_t})^{1-\alpha} \;\Rightarrow\; y_t = z_t + \alpha k_t + (1-\alpha) n_t` | Exact in logs for Cobb-Douglas (the approximation is not even needed). | Row 3. |
| Loglinear feasibility | `0 = Y e^{y_t} - C e^{c_t} - I e^{i_t} \;\Rightarrow\; y_t = \frac{C}{Y}c_t + \frac{I}{Y}i_t` | Output deviation is the share-weighted average of consumption and investment deviations. | Row 4. (The printed text has a typo: 'y_t = + C/Y c_t + I/Y i_t'.) |
| Loglinear Euler (project's printed version) | `\frac{\tau N^{v} n_t - C c_t}{C - \tau\frac{N^{v}}{v}} = E_t\left[\frac{\tau N^{v} n_{t+1} - C c_{t+1}}{C - \tau\frac{N^{v}}{v}}\right] + \alpha\frac{Y}{K}\beta E_t\left[y_{t+1} - k_{t+1}\right]` | Loglinearized intertemporal condition. Intermediate step: 0 approx E_t[tau N^v n_{t+1} - C c_{t+1}] + alpha (Y/K)(C - tau N^v/v) beta E_t[y_{t+1}-k_{t+1}] - (tau N^v n_t - C c_t). | The single expectational equation; it defines F, G, H, J, K, L, M. |
| Loglinear Euler (student's simplified version, page 5 '(*)') | `\frac{1}{C - \tau\frac{N^{v}}{v}}\, E_t\!\left[C(c_{t+1}-c_t) - \tau N^{v}(n_{t+1}-n_t)\right] = \left(1 - \beta(1-\delta)\right) E_t\!\left[y_{t+1} - k_{t+1}\right]` | Same equation after using the steady-state relation alpha Y/K = 1/beta - (1-delta), so that beta alpha Y/K = 1 - beta(1-delta). This is the cleanest form to program. | Use this form to sanity-check the signs of J, K and G in the Matlab code. |
| Loglinear TFP | `z_{t+1} = \psi z_t + \epsilon_{t+1}` | AR(1) in log-deviations, so N (Uhlig) = psi. | Row (3) of Uhlig's system. |
| Uhlig's system | `0 = A x_t + B x_{t-1} + C y_t + D z_t;\;\; 0 = E_t[F x_{t+1} + G x_t + H x_{t-1} + J y_{t+1} + K y_t + L z_{t+1} + M z_t];\;\; z_{t+1} = N z_t + \varepsilon_{t+1};\;\; 0 = E_t[\varepsilon_{t+1}]` | General canonical form of a loglinearized DSGE model. | Always the target format before calling Uhlig's Matlab routines (solve.m / do_it.m). |
| Uhlig vectors in this model | `x_t = [k_{t+1}]_{1\times 1},\quad y_t = [c_t,\, y_t,\, n_t,\, i_t]_{4\times 1},\quad z_t = [z_t]_{1\times 1}` | One endogenous state (next-period capital), four controls/jumps, one exogenous state. | Q6.2. WARNING on notation: the symbol y_t is overloaded -- Uhlig's y_t is the 4x1 control vector, while the scalar y_t inside it is log output. |
| Matrix A | `A = \begin{bmatrix}0\\1\\0\\0\end{bmatrix}` | Coefficient on x_t = k_{t+1}; only the capital-accumulation row involves k_{t+1}. | Row order is: (1) leisure-consumption, (2) capital accumulation, (3) technology, (4) feasibility. |
| Matrix B | `B = \begin{bmatrix}0\\-(1-\delta)\\-\alpha\\0\end{bmatrix}` | Coefficient on x_{t-1} = k_t: -(1-delta) in the accumulation equation and -alpha in the production function. | Same row order. |
| Matrix C | `C = \begin{bmatrix} 0 & (1-\alpha)Y & -\tau v N^{v} & 0\\ 0 & 0 & 0 & -\delta\\ 0 & 1 & -(1-\alpha) & 0\\ -\frac{C}{Y} & 1 & 0 & -\frac{I}{Y}\end{bmatrix}` | Coefficients on the controls, columns ordered (c_t, y_t, n_t, i_t) -- the student annotated these column labels by hand. | Must be invertible; it is (4x4, full rank) which is why the elimination y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t) works. |
| Matrix D | `D = \begin{bmatrix}0\\0\\-1\\0\end{bmatrix}` | z_t only enters the production function, with coefficient -1 as written (0 = y_t - z_t - alpha k_t - (1-alpha)n_t). | Row 3 only. |
| Matrices F, G, H | `F = [0],\qquad G = \left[-\alpha\beta\frac{Y}{K}\right] = [\beta(1-\delta)-1] = [-(1-\beta(1-\delta))],\qquad H = [0]` | The expectational equation has no k_{t+2} and no k_t (in Uhlig indexing, no x_{t+1} and no x_{t-1}); it only contains k_{t+1} = x_t with coefficient -alpha beta Y/K. | Because F = 0, the 'quadratic' in P degenerates to Ftilde P^2 + Gtilde P + Htilde with Ftilde = -J C^{-1} A. |
| Matrix J | `J = \left[\; \frac{-C}{C-\tau\frac{N^{v}}{v}} \quad \alpha\beta\frac{Y}{K} \quad \frac{\tau N^{v}}{C-\tau\frac{N^{v}}{v}} \quad 0 \;\right]` | Coefficients on E_t y_{t+1} = (c_{t+1}, y_{t+1}, n_{t+1}, i_{t+1}). Note alpha beta Y/K = 1 - beta(1-delta). | Q6.3; the student annotated the column labels c_{t+1}, y_{t+1}, n_{t+1}, i_{t+1} and rewrote alpha beta Y/K as (1 - beta(1-delta)). |
| Matrix K | `K = \left[\; \frac{C}{C-\tau\frac{N^{v}}{v}} \quad 0 \quad \frac{-\tau N^{v}}{C-\tau\frac{N^{v}}{v}} \quad 0 \;\right]` | Coefficients on the date-t controls in the Euler equation; exactly minus the c and n entries of J (no y_t, no i_t). | Q6.3. |
| Matrices L, M, N | `L = [0],\qquad M = [0],\qquad N = [\psi]` | z does not appear directly in the Euler equation (it enters only through y and k); N is the AR(1) persistence. | Q6.3. |
| Tilde matrices (elimination of y_t) | `\tilde F = F - JC^{-1}A;\;\; \tilde G = G - JC^{-1}B - KC^{-1}A;\;\; \tilde H = H - KC^{-1}B;\;\; \tilde L = L - JC^{-1}D;\;\; \tilde M = M - KC^{-1}D` | What is left of the expectational equation once controls are substituted out with y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t). | Step before solving for P and Q. |
| Quadratic for P | `0 = \tilde F P^{2} + \tilde G P + \tilde H \;\Longrightarrow\; P = \frac{-\tilde G \pm \sqrt{\tilde G^{2} - 4\tilde F\tilde H}}{2\tilde F}` | P is a scalar here, so the standard quadratic formula applies. | Choose the root with P < 1 (in absolute value) to ensure stability / non-explosive capital. |
| Linear equation for Q | `0 = \tilde L N + \tilde M + \tilde F Q N + \tilde F P Q + \tilde G Q \;\Longrightarrow\; Q = \frac{-(\tilde L N + \tilde M)}{\tilde F N + \tilde F P + \tilde G}` | Once P is known, Q follows from the z_t coefficient block. | Immediately after P. |
| Solution matrices R and S | `R = -C^{-1}(A P + B),\qquad S = -C^{-1}(A Q + D)` | Obtained by plugging x_t = P x_{t-1} + Q z_t into y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t) and matching coefficients with y_t = R x_{t-1} + S z_t. | Final step; R and S give the responses of c, y, n, i to capital and to TFP. |
| Recursive law of motion (solution) | `x_t = P x_{t-1} + Q z_t,\qquad y_t = R x_{t-1} + S z_t` | The policy functions of the loglinearized economy. | Simulation and IRF computation. |
| Calibration of tau | `\tau = (1-\alpha)\frac{Y}{N^{v}}` | Solve the steady-state leisure-consumption condition tau N^v = (1-alpha)Y for tau, given a target for steady-state hours N (typically a normalization such as N = 1 or N = 1/3) and the implied steady-state Y. | Q6.1; must be inserted in the Matlab program so that tau is not a free parameter but is implied by the hours target. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

PRODUCTION: Cobb-Douglas Y_t = Z_t K_t^alpha N_t^{1-alpha}, constant returns to scale, labor share (1-alpha). LABOR DEMAND: the marginal product condition W_t = (1-alpha) Z_t (K_t/N_t)^alpha = (1-alpha) Y_t/N_t. Inverting, ln N_t = (1/alpha)[ln(1-alpha) + ln Z_t + alpha ln K_t - ln W_t], so with capital predetermined the (short-run, partial-equilibrium) labor demand elasticity is d ln N_t / d ln W_t = -1/alpha. THE CURVATURE OF LABOR DEMAND IS GOVERNED SOLELY BY alpha (the capital share); under Cobb-Douglas the elasticity of substitution between K and N is 1, so -1/alpha is exactly the conditional labor demand elasticity holding K fixed, and it becomes perfectly elastic (horizontal) once K adjusts fully in the long run. In loglinear form labor demand is w_t = y_t - n_t = z_t + alpha k_t - alpha n_t. UTILITY / LABOR SUPPLY: GHH period utility ln(C_t - tau N_t^v / v). The intratemporal FOC is tau N_t^{v-1} / (C_t - tau N_t^v/v) = lambda_t W_t, and with 1/(C_t - tau N_t^v/v) = lambda_t it collapses to tau N_t^{v-1} = W_t, hence ln N_t = (1/(v-1))(ln W_t - ln tau). FRISCH ELASTICITY OF LABOR SUPPLY = 1/(v-1). Because preferences are GHH there is NO wealth effect: the Frisch, Marshallian and Hicksian labor-supply elasticities all coincide at 1/(v-1). The parameter v > 1 governs the curvature (convexity) of labor supply; v -> 1 gives infinitely elastic labor supply, v -> infinity gives inelastic labor supply. EQUILIBRIUM: multiplying by N_t gives tau N_t^v = W_t N_t = (1-alpha)Y_t, so in loglinear form (1-alpha)Y y_t = tau v N^v n_t, i.e. n_t = y_t / v: hours are output divided by v. Combining supply (n_t = (1/(v-1))w_t) with demand (w_t = z_t + alpha k_t - alpha n_t) gives the equilibrium hours response n_t = z_t/(v-1+alpha) + alpha k_t/(v-1+alpha) -- the standard identification problem: only the intersection is observed, so alpha (demand curvature) and v (supply curvature) cannot be separated from the equilibrium (w, n) pair alone; one needs a shifter of supply (or of demand) to trace out the other curve. The relevant natural experiment in this model is the TFP shock z_t, which is a pure LABOR DEMAND shifter and therefore traces out the labor SUPPLY curve, not the demand curve.

### [COMPUT] Metodo computacional

(1) Write the planner's Lagrangian with GHH utility and the resource constraint. (2) Take FOCs w.r.t. C_t, N_t, K_{t+1}, lambda_t. (3) Substitute lambda out using lambda_t = 1/(C_t - tau N_t^v/v) and rewrite factor payments as W = (1-alpha)Y/N and R = alpha Y/K + 1 - delta, obtaining a 6-equation non-linear system in (C, N, Y, I, K, Z). (4) Impose constancy and E[epsilon]=0 to get the non-stochastic steady state; solve it for the ratios Y/K, I/Y, C/Y and for the level of N (normalized) and hence tau. (5) Loglinearize each equation with X_t = Xbar e^{x_t}, e^x approx 1 + x, keeping only first-order terms. (6) Cast the loglinear system into Uhlig's canonical form (1)-(4) with x_t = k_{t+1}, y_t = (c,y,n,i), z_t = z; build A,B,C,D (deterministic block, 4 rows) and F,G,H,J,K,L,M,N (expectational block, 1 row). (7) Eliminate y_t via y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t) to form Ftilde, Gtilde, Htilde, Ltilde, Mtilde. (8) Solve the scalar quadratic Ftilde P^2 + Gtilde P + Htilde = 0, keep the stable root P < 1; solve the linear equation for Q. (9) Recover R = -C^{-1}(AP+B) and S = -C^{-1}(AQ+D). (10) Implement all of this in Matlab starting from exampl1modifv1.m (Uhlig toolkit), with tau calibrated inside the code from tau = (1-alpha)Y/N^v. (11) Compute IRFs by iterating the recursive law of motion after a 1% innovation to z at date 0, over T = 150 periods, and plot t = -1 (zero) through t = 33.

### [CALIB] Objetivos de calibracion

- tau: calibrated (not estimated) from the steady-state leisure-consumption condition, tau = (1-alpha) Y / N^v, i.e. it is chosen so that steady-state hours N hit their target (typically a normalization of the time endowment) given the steady-state level of output. This is the only calibration equation the project explicitly asks for (Q6.1) and it must be coded inside the Matlab program.
- Y/K: implied by the steady-state Euler 1/beta = alpha Y/K + (1-delta), so Y/K = (1/beta - 1 + delta)/alpha (equivalently alpha beta Y/K = 1 - beta(1-delta)). Not a free parameter.
- I/Y: implied by I = delta K, so I/Y = delta K/Y = delta alpha / (1/beta - 1 + delta).
- C/Y: implied by Y = C + I, so C/Y = 1 - I/Y.
- alpha, beta, delta, psi, sigma, v: taken as given/inherited from the standard RBC calibration (alpha = capital share, beta from the real interest rate, delta from depreciation, psi and sigma from the AR(1) fitted to the Solow residual, v from the target labor-supply elasticity 1/(v-1)). The project does not restate these but they are required inputs to the steady-state block.

### [RECETA] Solucion paso a paso

1. STEP 1 - Planner's problem and Lagrangian. Primitives: period utility u(C_t,N_t) = ln(C_t - tau N_t^v / v) (GHH), discount factor beta in (0,1), technology Y_t = Z_t K_t^alpha N_t^{1-alpha}, depreciation delta, resource constraint Z_t K_t^alpha N_t^{1-alpha} + (1-delta)K_t = C_t + K_{t+1}, TFP AR(1) in logs. The Lagrangian is L = E_t sum_{j=0}^{infty} beta^j { ln(C_{t+j} - tau N_{t+j}^v / v) + lambda_{t+j}[ Z_{t+j}K_{t+j}^alpha N_{t+j}^{1-alpha} + K_{t+j}(1-delta) - C_{t+j} - K_{t+j+1} ] }. (Student's note: run the sum from t = 0 with E_0.)
2. STEP 2 - First order conditions. (a) C_t: 1/(C_t - tau N_t^v/v) = lambda_t. (b) N_t: tau N_t^{v-1}/(C_t - tau N_t^v/v) = lambda_t (1-alpha) Z_t (K_t/N_t)^alpha. (c) K_{t+1}: E_t[ beta lambda_{t+1}( alpha Z_{t+1}(N_{t+1}/K_{t+1})^{1-alpha} + (1-delta) ) - lambda_t ] = 0. (d) lambda_t: Z_t K_t^alpha N_t^{1-alpha} + K_t(1-delta) - C_t - K_{t+1} = 0.
3. STEP 3 - Rewrite factor payments as ratios. W_t = (1-alpha)Z_t(K_t/N_t)^alpha = (1-alpha)Y_t/N_t and R_{t+1} = alpha Z_t (N_t/K_t)^{1-alpha} + (1-delta) = alpha Y_t/K_t + (1-delta). Substituting, the labor FOC becomes tau N_t^{v-1}/(C_t - tau N_t^v/v) = lambda_t (1-alpha) Y_t/N_t and the capital FOC becomes E_t[ beta lambda_{t+1}( alpha Y_{t+1}/K_{t+1} + (1-delta) ) - lambda_t ] = 0. Use lambda_{t+1}/lambda_t = (C_t - tau N_t^v/v)/(C_{t+1} - tau N_{t+1}^v/v).
4. STEP 4 - The full non-linear system (six equations). (i) Leisure-consumption: tau N_t^v = (1-alpha) Y_t. (ii) Capital accumulation: I_t = K_{t+1} - (1-delta)K_t. (iii) Technology: Y_t = Z_t K_t^alpha N_t^{1-alpha}. (iv) Feasibility: Y_t = C_t + I_t. (v) Euler: 1/(C_t - tau N_t^v/v) = beta E_t[ (1/(C_{t+1} - tau N_{t+1}^v/v)) ( alpha Y_{t+1}/K_{t+1} + (1-delta) ) ]. (vi) TFP: ln Z_t = (1-psi) ln Zbar + psi ln Z_{t-1} + epsilon_t, epsilon_t iid D(0, sigma^2).
5. STEP 5 - Non-stochastic steady state (bar notation dropped for readability). tau N^v = (1-alpha) Y; I = delta K; Y = Z K^alpha N^{1-alpha}; Y = C + I; 1/beta = alpha Y/K + (1-delta). Solve in this order: Y/K = (1/beta - 1 + delta)/alpha; K/Y = alpha/(1/beta - 1 + delta); I/Y = delta K/Y; C/Y = 1 - I/Y; normalize N (or target it) and get Y from the production function; then tau = (1-alpha)Y/N^v. Key identity for later: alpha beta Y/K = 1 - beta(1-delta).
6. STEP 6 - Loglinearize equation by equation (X_t = Xbar e^{x_t}, e^x approx 1 + x). (i) Leisure-consumption: 0 = (1-alpha)Y e^{y_t} - tau (N e^{n_t})^v  =>  0 approx (1-alpha)Y y_t - tau v N^v n_t, i.e. (1-alpha)Y y_t = tau v N^v n_t (equivalently n_t = y_t / v). (ii) Capital accumulation: 0 = K e^{k_{t+1}} - (1-delta)K e^{k_t} - I e^{i_t}  =>  0 approx K k_{t+1} - (1-delta)K k_t - delta K i_t  =>  k_{t+1} = (1-delta) k_t + delta i_t. (iii) Technology: 0 = Y e^{y_t} - Z e^{z_t}(K e^{k_t})^alpha (N e^{n_t})^{1-alpha}  =>  0 approx Y y_t - Y z_t - alpha Y k_t - (1-alpha) Y n_t  =>  y_t = z_t + alpha k_t + (1-alpha) n_t. (iv) Feasibility: 0 = Y e^{y_t} - C e^{c_t} - I e^{i_t}  =>  y_t = (C/Y) c_t + (I/Y) i_t. (v) Euler: expanding both sides around the steady state gives 0 approx E_t[tau N^v n_{t+1} - C c_{t+1}] + alpha (Y/K)(C - tau N^v/v) beta E_t[y_{t+1} - k_{t+1}] - (tau N^v n_t - C c_t), i.e. (tau N^v n_t - C c_t)/(C - tau N^v/v) = E_t[(tau N^v n_{t+1} - C c_{t+1})/(C - tau N^v/v)] + alpha (Y/K) beta E_t[y_{t+1} - k_{t+1}]; using alpha beta Y/K = 1 - beta(1-delta) this is (1/(C - tau N^v/v)) E_t[C(c_{t+1}-c_t) - tau N^v(n_{t+1}-n_t)] = (1 - beta(1-delta)) E_t[y_{t+1} - k_{t+1}]. (vi) TFP: z_{t+1} = psi z_t + epsilon_{t+1}.
7. STEP 7 - Map into Uhlig's notation. Canonical form: (1) 0 = A x_t + B x_{t-1} + C y_t + D z_t; (2) 0 = E_t[F x_{t+1} + G x_t + H x_{t-1} + J y_{t+1} + K y_t + L z_{t+1} + M z_t]; (3) z_{t+1} = N z_t + epsilon_{t+1}; (4) 0 = E_t[epsilon_{t+1}]. Here x_t = [k_{t+1}] (1x1 endogenous state), y_t = [c_t, y_t, n_t, i_t]' (4x1 controls), z_t = [z_t] (1x1 exogenous state). Rewrite the loglinear equations with everything on the right: 0 = (1-alpha)Y y_t - tau v N^v n_t; 0 = k_{t+1} - (1-delta)k_t - delta i_t; 0 = y_t - z_t - alpha k_t - (1-alpha) n_t; 0 = y_t - (C/Y) c_t - (I/Y) i_t; 0 = E_t[(tau N^v n_{t+1} - C c_{t+1})/(C - tau N^v/v)] + alpha beta (Y/K) E_t[y_{t+1} - k_{t+1}] - (tau N^v n_t - C c_t)/(C - tau N^v/v); z_{t+1} = psi z_t + epsilon_{t+1}.
8. STEP 8 - Contents of the matrices. A = [0; 1; 0; 0] (4x1). B = [0; -(1-delta); -alpha; 0] (4x1). C (4x4, columns ordered c_t, y_t, n_t, i_t) = row1 [0, (1-alpha)Y, -tau v N^v, 0]; row2 [0, 0, 0, -delta]; row3 [0, 1, -(1-alpha), 0]; row4 [-C/Y, 1, 0, -I/Y]. D = [0; 0; -1; 0] (4x1). F = [0] (no k_{t+2} in the Euler). G = [-alpha beta Y/K] = [beta(1-delta) - 1] = [-(1 - beta(1-delta))]. H = [0]. J (1x4, on E_t y_{t+1}) = [ -C/(C - tau N^v/v),  alpha beta Y/K,  tau N^v/(C - tau N^v/v),  0 ]. K (1x4, on y_t) = [ C/(C - tau N^v/v),  0,  -tau N^v/(C - tau N^v/v),  0 ]. L = [0]. M = [0]. N = [psi].
9. STEP 9 - Solve for P and Q. Guess x_t = P x_{t-1} + Q z_t and y_t = R x_{t-1} + S z_t. From (1), y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t). Substitute into (2) to get 0 = E_t[(F - JC^{-1}A) x_{t+1} + (G - JC^{-1}B - KC^{-1}A) x_t + (H - KC^{-1}B) x_{t-1} + (L - JC^{-1}D) z_{t+1} + (M - KC^{-1}D) z_t], i.e. define Ftilde = F - JC^{-1}A, Gtilde = G - JC^{-1}B - KC^{-1}A, Htilde = H - KC^{-1}B, Ltilde = L - JC^{-1}D, Mtilde = M - KC^{-1}D. Use E_t z_{t+1} = N z_t and E_t x_{t+1} = P x_t + Q N z_t, then x_t = P x_{t-1} + Q z_t, to obtain 0 = (Ftilde P^2 + Gtilde P + Htilde) x_{t-1} + (Ltilde N + Mtilde + Ftilde Q N + Ftilde P Q + Gtilde Q) z_t. Since this must hold for all (x_{t-1}, z_t), both coefficient blocks are zero: (a) 0 = Ftilde P^2 + Gtilde P + Htilde, (b) 0 = Ltilde N + Mtilde + Ftilde Q N + Ftilde P Q + Gtilde Q.
10. STEP 10 - Pick the stable root and get Q. Because P is a scalar here, P = (-Gtilde +/- sqrt(Gtilde^2 - 4 Ftilde Htilde))/(2 Ftilde). CHOOSE THE ROOT WITH P < 1 (in absolute value) to ensure stability (the other root gives an explosive capital path violating the transversality condition). Substituting P into (b) gives Q = -(Ltilde N + Mtilde)/(Ftilde N + Ftilde P + Gtilde).
11. STEP 11 - Recover R and S. Plug x_t = P x_{t-1} + Q z_t into y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t): y_t = -C^{-1}(A P + B) x_{t-1} - C^{-1}(A Q + D) z_t. Matching with y_t = R x_{t-1} + S z_t gives R = -C^{-1}(A P + B) (4x1) and S = -C^{-1}(A Q + D) (4x1).
12. STEP 12 - Calibration inside the Matlab program. Fix alpha, beta, delta, v, psi, sigma; compute Y/K = (1/beta - 1 + delta)/alpha, I/Y = delta alpha/(1/beta - 1 + delta), C/Y = 1 - I/Y; normalize/target N; get Y from the production function; then set tau = (1-alpha) Y / N^v (Q6.1 answer). Everything in A, B, C, D, F, G, H, J, K, L, M, N is then a function of the deep parameters and these steady-state objects.
13. STEP 13 - Matlab implementation. Start from exampl1modifv1.m (Uhlig toolkit, posted on Canvas). Load parameters -> compute steady state and tau -> build the twelve matrices -> either call Uhlig's solve.m/do_it.m or code the scalar quadratic explicitly -> obtain P, Q, R, S.
14. STEP 14 - IRF exercise (Q6.5). Shock: a single 1% innovation to z at date 0 (epsilon_0 = 0.01), as in Uhlig's programs, with no further shocks; z_t then decays as z_t = psi^t * 0.01. Horizon: simulate T = 150 periods. Initial condition: the economy sits at the steady state before the shock, so k_{-1} = 0. Iterate x_t = P x_{t-1} + Q z_t and y_t = R x_{t-1} + S z_t. PLOTTING CONVENTION: plot the vector y_t = (c, y, n, i) against time so that t = 0 is the impact period (the first response of the economy to the shock); INCLUDE t = -1 in the graph showing y = 0 (the pre-shock steady state); after the shock plot t = 1 up to t = 33. The plotting must be part of the same program that solves the model.
15. STEP 15 - Report by hand (Q6.6). Read off the first five values of log output: y_0 = S_y * 0.01 (impact), and for t = 1,...,4, y_t = R_y * P^{t-1} * Q * 0.01 * (accumulated) + S_y * psi^t * 0.01, i.e. iterate the law of motion by hand. THIS PART IS LEFT BLANK IN THE STUDENT'S COPY and remains an open to-do.

### Intuicion general

The whole project is a template for turning a fully non-linear stochastic model into a linear state-space object that Matlab can solve in closed form. The economics is standard RBC: a TFP shock raises the marginal product of both factors, so output, the wage and hours all rise; investment rises more than consumption because the household smooths consumption and capital is the only savings vehicle; capital accumulates slowly, so the propagation is governed by P (endogenous persistence) on top of psi (exogenous persistence). The GHH assumption is the important modeling twist: because utility depends on C - tau N^v/v, the wealth effect on labor supply is switched off and the intratemporal condition reduces to tau N_t^v = (1-alpha)Y_t, i.e. hours move mechanically with output, n_t = y_t / v. That makes hours much more volatile than under separable preferences and is the classic device for getting the RBC model to match the observed volatility of employment. Technically, the trick that makes everything tractable is writing factor payments as Y/N and Y/K: the Euler and labor conditions then contain only ratios, whose steady-state values are pinned down by beta, delta, alpha alone (alpha beta Y/K = 1 - beta(1-delta)), so the loglinear coefficients are simple functions of the deep parameters. The solution method is nothing more than 'guess a linear policy function, plug it in, and force each coefficient of x_{t-1} and z_t to vanish'; the only subtlety is the two-root quadratic in P, where the explosive root is discarded because it violates the transversality condition.

### Ejemplos y ejercicios

- Q6.5 IRF exercise: a 1% innovation to z at t = 0 (as in Uhlig's programs), simulated for T = 150 periods, with the vector y_t = (c, y, n, i) plotted against time; the graph must show t = -1 with y = 0 (pre-shock), t = 0 as the impact period, and then t = 1 through t = 33.
- Q6.6 asks to report by hand the first five values of output y_t after the shock (i.e. read off S_y * 1% at t = 0 and then y_t = R_y P^{t} k_0 + S_y psi^{t} z_0 for t = 1..4). This part is BLANK in the copy -- an outstanding item.
- The Matlab starting point is the file exampl1modifv1.m posted on Canvas (an Uhlig-toolkit example script).

### Anotaciones a mano (tuyas)

- p.1 (top margin, above the header): a handwritten note reading approximately 'Soy Ramirez va?' / 'Sy Ramirez va?' -- appears to be the grader or the student identifying authorship of the copy; partly illegible.
- p.1 (Lagrangian): the operator 'E_t sum_{j=0}^{infty}' is circled and 't = 0' is written underneath -- a note that the summation index should start at t = 0 (or that the expectation should be E_0 with the sum running from t = 0).
- p.1 (Lagrangian): all the '+j' time subscripts are struck through by hand (C_{t+j}, N_{t+j}, Z_{t+j}, K_{t+j}, K_{t+j+1}, lambda_{t+j}), i.e. the student rewrote the Lagrangian in plain t-notation.
- p.4 (right after the loglinearized Euler): the student wrote 'Checar (*)' ('check (*)') -- an explicit CHECK note pointing to the appended handwritten derivation on page 5, which is headed by the same asterisk symbol.
- p.4 (over the Euler equation of the loglinear system): a brace over 'alpha Y/K' with the annotation '1 - beta(1-delta)', i.e. the student replaced alpha beta Y/K by 1 - beta(1-delta) using the steady-state Euler equation.
- p.4 (bottom, handwritten rewriting of the Euler): '1/(C - tau N^v/v) E_t[C(c_{t+1}-c_t) + tau N^v(n_{t+1}-n_t)] = (1 - beta(1-delta)) E_t[y_{t+1} - k_{t+1}]'. NOTE A SIGN DISCREPANCY: on page 5 the same line is written with a MINUS, '... E_t[C(c_{t+1}-c_t) - tau N^v(n_{t+1}-n_t)] ...', which is the correct one given J and K; the page-4 '+' looks like a transcription slip.
- p.5 (full handwritten page, headed by the asterisk '(*)'): step-by-step verification of the loglinear Euler. Line 1: E_t[tau N^v n_{t+1} - C c_{t+1}] + alpha (Y/K)(C - tau N^v/v) beta E_t[y_{t+1}-k_{t+1}] - (tau N^v n_t - C c_t) = 0. Line 2: = 1/(C - tau N^v/v) E_t[tau N^v(n_{t+1}-n_t) - C(c_{t+1}-c_t)] + [alpha Y/K, underbraced 'en ss = 1/beta - (1-delta)'] beta E_t[y_{t+1}-k_{t+1}] = 0. Line 3: = 1/(C - tau N^v/v) E_t[tau N^v(n_{t+1}-n_t) - C(c_{t+1}-c_t)] + [beta(1/beta - (1-delta)), underbraced '(1 - beta(1-delta))'] E_t(y_{t+1}-k_{t+1}) = 0. Line 4 (final): 1/(C - tau N^v/v) E_t[C(c_{t+1}-c_t) - tau N^v(n_{t+1}-n_t)] = (1 - beta(1-delta)) E_t(y_{t+1}-k_{t+1}).
- p.6 (Q6.2): x_t highlighted in yellow, y_t = [c_t, y_t, n_t, i_t] highlighted in cyan, z_t left plain -- colour-coding the three Uhlig blocks.
- p.6 (Uhlig system, eqs. (1)-(4)): the same colour code is carried onto the general equations -- A x_t (yellow on x_t), B x_{t-1} (green), C y_t (cyan), D z_t (purple); in equation (2) the terms F x_{t+1}, L z_{t+1} and M z_t are struck through (because F = L = M = 0 here); K y_t is highlighted blue; in (3) the N is circled.
- p.6 (rewritten loglinear equations): the student circled/underlined each term and matched it by colour to the matrix entry it produces: (1-alpha)Y and -tau v N^v circled in cyan (row 1 of C); k_{t+1} highlighted yellow and -(1-delta)k_t, -delta i_t marked (row 2); -alpha k_t marked green (B); the Euler's numerator (tau N^v n_{t+1} - C c_{t+1}) and denominator (C - tau N^v/v) circled; psi z_t circled in (3).
- p.6 (matrix C): handwritten column headers 'C_t   y_t   n_t   i_t' placed above the four columns.
- p.6 (matrix A): the entry '1' highlighted yellow; matrix B: '-(1-delta)' and '-alpha' highlighted green; matrix D: '-1' highlighted purple; H = [0] highlighted green.
- p.6 (matrix G): under G = [-alpha beta Y/K] the student wrote, with two arrows, '(~ (1 - beta(1-delta)))' and then 'beta(1-delta) - 1', i.e. G = -(1 - beta(1-delta)) = beta(1-delta) - 1.
- p.7 (matrix J): handwritten column headers 'c_{t+1}  y_{t+1}  n_{t+1}  i_{t+1}' above J and 'c_t  y_t  n_t  i_t' above K; an arrow from J's second entry alpha beta Y/K with the note '(1 - beta(1-delta))'.
- p.7 (matrix K): the two non-zero entries C/(C - tau N^v/v) and -tau N^v/(C - tau N^v/v) highlighted blue.
- p.7: 'N = [psi]' circled.
- p.9 (Q6.6, 'Report by hand the first five values of output y_t in response to the shock'): LEFT COMPLETELY BLANK -- unanswered in this copy. Also note the printed typo 'the first give values' for 'the first five values'.
- Printed typos worth flagging: Q0 writes d/dN_t (N_t^v/v) = N_t^v (should be N_t^{v-1}); Q3 header writes 'the rations' for 'the ratios'; the loglinear feasibility is printed as 'y_t = + C/Y c_t + I/Y i_t'; Q6.3's title lists 'A,B,C,D,F,G,H,J,L,M,N' and omits K, although K is reported.

### Conexiones con otros temas

- This is the computational counterpart of the Topic 5 handwritten notes (Topic5Solving_by_hand.pdf): the notes solve the same kind of system by hand with scalar undetermined coefficients eta_kk, eta_kz, eta_lambda_k, eta_lambda_z, while the project does it in matrix form with P, Q, R, S. eta_kk is the hand-solved analogue of P.
- The steady-state block and the calibration logic (alpha from the capital share, beta from the real interest rate, delta from the depreciation rate, psi and sigma from the Solow residual, tau residually from the hours target) are the same as in the McGrattan (1994) / Kydland-Prescott calibration covered in Topic 1.
- GHH preferences here are the alternative to Hansen's (1985) indivisible labor for generating high hours volatility -- both are devices to raise the labor-supply elasticity of the RBC model.
- The Euler equation and the modified golden rule 1/beta = alpha Y/K + 1 - delta reappear in the midterm exam (Q1 and Q3) in their fiscal-distortion versions 1 = beta(1 - delta + f_k(1-tau_k)).
- For a thesis on labor demand elasticity: this model contains an explicit, parametric labor demand curve W_t = (1-alpha)Y_t/N_t whose elasticity is -1/alpha in partial equilibrium (K fixed); the project shows exactly how alpha, and only alpha, controls that curvature under Cobb-Douglas.

---

## Midterm Exam, Dynamic Macroeconomics II, Prof. Felipe Meza, ITAM, October 10, 2024 (100 points, 1:30 hours, multiple choice). Three questions: (1) Fiscal policies in a growth model with consumption and capital taxes (Ljungqvist & Sargent 2004, Exercise 11.2, 30 pts); (2) Permanent-income model with borrowing constraints and an MIT shock, V-shaped vs L-shaped recovery (30 pts); (3) Optimal (Ramsey) taxation via the Primal Approach, no-arbitrage, implementability condition and the Chamley-Judd zero-capital-tax result (Ljungqvist & Sargent 2004, Exercise 15.7, 40 pts). Includes the student's full handwritten worked solutions on the interleaved color sheets.

*Fuente: `Midterm_exam_Dynamic_Macro_II_oct2024_251013_052910.pdf`*

*Secciones: Cover: rules (100 points, 1:30 h, multiple choice, answer in pen, no electronic devices, no notes, no copying; calculations on color sheets which do not count for the grade) | Q1. Fiscal Policies (LS 11.2): A. utility, B. consumer's intertemporal budget constraint, C. government's intertemporal budget constraint, D. feasibility, E. technology, F. k_0 given, G. firm's problem | Q1.1 Steady state levels of capital, consumption and r_t/q_t with constant g, constant tau_k, tau_c = 0 (15 pts) | Q1.2 Unexpected reform: capital tax set to zero forever, financed by a constant consumption tax; comparative statics of the new steady state (15 pts) | Q2. Model with borrowing constraints and an MIT shock: A. utility, B. financial market with R beta = 1, C. sequential constraint, D. b_0 = 0, E. transversality condition | Q2.1 Consumption with a constant endowment and NO borrowing constraint (6 pts) | Q2.2 Consumption path in Case 1 'V-shaped recovery' (8 pts) | Q2.3 Consumption path in Case 2 'L-shaped recovery' (8 pts) | Q2.4 Identification: how an econometrician inside the model distinguishes shock persistence from consumption data (8 pts) | Q3. Optimal taxation (LS 15.7): A. utility over (c,l), B. time constraint, C. sequential budget constraint with labor and capital taxes and government debt, D. technology, E. feasibility, F. firm's problem, notation q_t = prod R_i^{-1} | Q3.1 No Arbitrage Condition (10 pts) | Q3.2 Implementability condition (10 pts) | Q3.3 Derivative of the Ramsey Lagrangian w.r.t. k_{t+1} using V_t of the Primal Approach (10 pts) | Q3.4 Equation giving the optimal value of the capital tax in steady state (10 pts)*

### Supuestos

> Q1: u strictly concave, strictly increasing, twice continuously differentiable; labor supply n_t inelastic and equal to 1; f homogeneous of degree 1 with strictly positive decreasing marginal returns; 0 < delta < 1; 0 < beta < 1; k_0 > 0 given; f(k_t,n_t) not given a specific functional form (the answers must be stated as one equation in one unknown).
>
> Q1.1: g_t = g > 0 constant; 1 > tau_kt = tau_k > 0 constant; tau_c = 0 for all t.
>
> Q1.2: initial capital = the steady state from 1.1; the policy change is COMPLETELY UNEXPECTED (an MIT shock); tau_k = 0 in all periods thereafter; the consumption tax is always constant and strictly between 0 and 1; g unchanged; the government must satisfy its present-value budget constraint.
>
> Q2: u strictly increasing, strictly concave, twice differentiable, with Inada condition lim_{c->0} u_c = +infinity; risk-free asset with constant gross return R > 1 and R beta = 1; endowment y_t >= 0 with finite present value; b_0 = 0; transversality lim_{T->infinity} R^{-T} b_{t+T} = 0; FOR 2.1-2.4 THERE IS NO BORROWING CONSTRAINT (the exam states this explicitly, so the household can freely borrow against future income).
>
> Q2 (MIT shock): the environment is deterministic; at t = 1 the income sequence changes unexpectedly; after that agents have perfect foresight.
>
> Q3: u(c_t,l_t) strictly concave, strictly increasing in consumption and leisure, twice continuously differentiable; 1 = l_t + n_t; f has constant returns to scale with decreasing and strictly positive marginal returns; b_0 = 0; q_0 = 1; a unique steady state exists; the initial capital tax tau_{a0} is taken as given (this is why the initial-capital term appears in the implementability condition).
>

### Conceptos clave

- **Arrow-Debreu / present-value budget constraint** - The consumer's lifetime constraint sum_t q_t[(1+tau_ct)c_t + k_{t+1} - (1-delta)k_t] <= sum_t [r_t k_t (1-tau_kt) + w_t n_t], where q_t is the intertemporal (date-0) price. Q1 is posed in this present-value form; Q3 is posed in sequential form with a bond b_{t+1}/R_t.
- **No-arbitrage condition for capital** - The requirement that holding capital one more period yields the same as the bond: in Q1's present-value language q_t = q_{t+1}(1-delta) + r_{t+1}(1-tau_k); in Q3's sequential language R_t = (1-tau_{a,t+1})(r_{t+1}+1-delta). Derived by collecting the terms in k_{t+1} in the budget constraint and setting the coefficient to zero (otherwise infinite arbitrage profits).
- **Capital tax wedge** - A tax tau_k on the return to capital drives a wedge in the Euler equation: 1 = beta(1-delta+f_k(1-tau_k)) rather than 1 = beta(1-delta+f_k). Because f is concave, a higher tau_k requires a HIGHER f_k, hence a LOWER steady-state capital stock.
- **Constant consumption tax is non-distortionary intertemporally** - In the Euler equation the consumption tax appears as the ratio (1+tau_ct)/(1+tau_{c,t+1}); if tau_c is constant over time the ratio is 1 and the tax does not distort the intertemporal margin (it acts like a lump-sum tax on the present value of consumption). This is the key to Q1.2.
- **MIT shock** - A completely unexpected, once-and-for-all change in the environment in an otherwise deterministic (perfect-foresight) model; agents did not assign any probability to it, but after it happens they have perfect foresight again. Named ironically in the literature; used here for the unanticipated income drop at t = 1 and for the unanticipated tax reform in Q1.2.
- **V-shaped vs L-shaped recovery** - V-shaped: income falls to y_l only at t = 1 and returns to y for t >= 2 (transitory shock). L-shaped: income stays at y_l forever from t = 1 on (permanent shock). The two differ only in the PERSISTENCE of the shock.
- **Permanent income hypothesis / consumption smoothing** - With beta R = 1 and no borrowing constraint, the Euler equation u'(c_t) = beta R u'(c_{t+1}) gives a flat consumption path c_t = c, and the level is the annuity value of lifetime resources: c/(1-beta) = sum beta^t y_t. Transitory shocks move consumption little (by the annuity factor (1-beta)); permanent shocks move it one-for-one.
- **Identification of shock persistence from consumption data** - Because the response of consumption to income scales with the persistence of the shock, observing a LARGE (i.e. lower) drop in consumption after the shock reveals a PERMANENT (L-shaped) income path, while a small drop reveals a transitory (V-shaped) one. This is the exam's Q2.4 and a textbook illustration of using theory to identify unobservables from observables.
- **Primal approach to Ramsey taxation** - Rather than choosing tax rates directly, the government chooses ALLOCATIONS subject to (i) feasibility and (ii) the implementability condition -- the single constraint that summarizes all the consumer's optimality conditions and budget constraint once prices and taxes have been substituted out. Taxes are then read off from the household's FOCs.
- **Implementability condition** - sum_t beta^t u_ct c_t = sum_t beta^t u_nt n_t + (1-tau_{a0})(r_0+1-delta) k_0 lambda, where lambda is the multiplier on the consumer's intertemporal budget constraint. Obtained by substituting the household FOCs beta^t u_ct = lambda q_t and beta^t u_nt = lambda q_t w_t (1-tau_nt) into the present-value budget constraint.
- **Pseudo-utility function V_t** - V_t = u(c_t, 1-n_t) + phi[u_ct c_t - u_nt n_t], where phi is the multiplier on the implementability condition; the Ramsey Lagrangian is J = sum beta^t {V_t + theta_t[f(k_t,n_t) - c_t - k_{t+1} + (1-delta)k_t - g_t]} - phi A, with A = (1-tau_{a0})(r_0+1-delta)k_0 lambda the initial-capital term.
- **Chamley-Judd zero capital taxation** - In steady state the Ramsey planner's FOC for k_{t+1} gives beta(f_k + 1 - delta) = 1, while the household's Euler with capital taxes gives 1 = beta(1-tau_a)(f_k+1-delta). The two are consistent only if tau_a = 0: the optimal long-run tax on capital income is zero.
- **Inelastic labor supply** - In Q1 labor supply n_t is fixed at 1, so there is no labor margin and the only distortions operate through consumption and capital; in Q3 labor is endogenous through u(c_t,l_t) with 1 = l_t + n_t, so a labor tax tau_nt distorts the intratemporal margin.

### Teoremas, lemas y proposiciones

> **Q1.1 -- Steady state with a constant capital tax and zero consumption tax (correct answer R1)**
>
> 1 = beta(1 - delta + f_k(1-tau_k)); f(k,1) = c + delta k + g; r/q = f_k. Three equations, one unknown each: the first gives k (since f_k is a decreasing function of k), the second gives c, the third gives r/q.
>
> *Supuestos requeridos:* g_t = g > 0 constant; 1 > tau_kt = tau_k > 0 constant; tau_c = 0 for all t; n_t = 1 inelastic; f homogeneous of degree 1 with strictly positive decreasing marginal returns; steady state: k_{t+1} = k_t = k so investment = delta k
>
> *Garantiza:* Student circled R1 and crossed out R2 and R4. R2 is wrong because it writes f_k - tau_k instead of f_k(1-tau_k); R3 is wrong because feasibility in steady state requires c + delta k + g, not c + (1-delta)k + g; R4 is wrong because the firm's FOC gives r/q = f_k gross of tax.

> **Q1.2 -- Replacing the capital tax with a constant consumption tax (correct answer R2)**
>
> Before the reform f_k = (1/beta - 1 + delta)/(1 - tau_k). After the reform (tau_k = 0, constant tau_c) the Euler ratio (1+tau_c)/(1+tau_c) = 1 so the consumption tax drops out and f_k = 1/beta - 1 + delta. Since 1/(1-tau_k) > 1, the required f_k FALLS; because f is concave (f_k decreasing in k), capital RISES. And since r/q = f_k, r/q FALLS.
>
> *Supuestos requeridos:* the reform is completely unexpected (MIT shock); initial capital equals the old steady state; government spending g unchanged; the new consumption tax is constant and strictly between 0 and 1; unique steady state
>
> *Garantiza:* Capital is bigger after the change and r/q is smaller after the change -> R2. (Student circled R2.) Economic content: a constant consumption tax is intertemporally non-distortionary, so eliminating the capital wedge raises the long-run capital stock and lowers the pre-tax return.

> **Q2.1 -- Permanent income with a constant endowment (correct answer R3)**
>
> With beta R = 1, no borrowing constraint, b_0 = 0 and y_t = y for all t, the Euler equation u'(c_t) = beta R u'(c_{t+1}) implies c_t = c constant, and the intertemporal budget constraint c/(1-beta) = y/(1-beta) gives c = y.
>
> *Supuestos requeridos:* u strictly increasing, strictly concave, twice differentiable, Inada lim_{c->0} u_c = +infinity; R beta = 1, R > 1; b_0 = 0; transversality lim_T R^{-T} b_{t+T} = 0; sum beta^t y_t < +infinity
>
> *Garantiza:* c = y (R3, circled). Autarky consumption; no borrowing or lending occurs.

> **Q2.2 -- V-shaped recovery (correct answer R3)**
>
> Income is y_1 = y_l at t = 1 and y_t = y for all t >= 2. Then c/(1-beta) = y_l + beta y + beta^2 y + ... = y_l + (beta/(1-beta)) y, so c = (1-beta) y_l + beta y, constant for all t >= 1.
>
> *Supuestos requeridos:* same as 2.1; the change is an unanticipated MIT shock realized at t = 1; 0 < y_l < y; b_1 = 0 (no assets carried in) -- the student flags that a non-zero b_1 would matter
>
> *Garantiza:* c = (1-beta) y_l + beta y (R3, circled). Only a fraction (1-beta) of the transitory income loss is absorbed by consumption -- the annuity value of the shock.

> **Q2.3 -- L-shaped recovery (correct answer R3)**
>
> If y_t = y_l for all t >= 1, then c/(1-beta) = y_l/(1-beta) and c = y_l for all t >= 1.
>
> *Supuestos requeridos:* same as 2.1-2.2; the drop is permanent
>
> *Garantiza:* c = y_l (R3, circled). A permanent shock is absorbed one-for-one by consumption.

> **Q2.4 -- Identifying persistence from consumption (correct answer R4)**
>
> Compare the two answers: c^{Case2} = y_l and c^{Case1} = (1-beta)y_l + beta y. Since y_l < y, we have y_l < (1-beta)y_l + beta y (equivalently beta y_l < beta y), so consumption is strictly LOWER in the L-shaped (permanent) case.
>
> *Supuestos requeridos:* the economist observes consumption but not the income sequence; she knows the model and the two candidate income paths; 0 < y_l < y
>
> *Garantiza:* If consumption is lower after the shock, income follows an L-shaped recovery -> R4 (circled). This is the exam's identification argument: consumption reveals the persistence of income shocks.

> **Q3.1 -- No Arbitrage Condition (correct answer R4)**
>
> R_t = (1 - tau_{a,t+1})(r_{t+1} + 1 - delta).
>
> *Supuestos requeridos:* consumer can hold both b_{t+1} (gross return R_t) and k_{t+1}; tau_at taxes capital earnings plus the asset value of capital net of depreciation; b_0 = 0
>
> *Garantiza:* R4 (circled). Derived from the FOCs for b_{t+1} and k_{t+1}: -lambda_t/R_t + lambda_{t+1} = 0 and -lambda_t + lambda_{t+1}(1-tau_{a,t+1})(r_{t+1}+1-delta) = 0. Both assets must offer the same after-tax return or the household's problem has no solution.

> **Q3.2 -- Implementability condition (correct answer R3)**
>
> sum_{t=0}^{infty} beta^t u_ct c_t = sum_{t=0}^{infty} beta^t u_nt n_t + (1 - tau_{a0})(r_0 + 1 - delta) k_0 lambda.
>
> *Supuestos requeridos:* household FOCs beta^t u_ct = lambda q_t and beta^t u_nt = lambda q_t w_t (1 - tau_nt); b_0 = 0; q_t = prod_{i=0}^{t-1} R_i^{-1}, q_0 = 1; the present-value budget constraint holds with equality
>
> *Garantiza:* R3 (circled). R1 omits lambda; R2 has a wrong sign/equals-zero form; R4 mistakenly multiplies the labor term by u_ct. The initial-capital term (1-tau_{a0})(r_0+1-delta)k_0 lambda is why the initial capital levy must be restricted (otherwise the planner would confiscate k_0 lump-sum).

> **Q3.3 -- Ramsey FOC with respect to k_{t+1} (correct answer R2)**
>
> beta^t theta_t(-) + beta^{t+1} theta_{t+1}(f_{k,t+1} + 1 - delta) = 0, i.e. -beta^t theta_t + beta^{t+1} theta_{t+1}(f_{k,t+1}+1-delta) = 0.
>
> *Supuestos requeridos:* V_t = u(c_t,1-n_t) + phi[u_ct c_t - u_nt n_t]; J = sum beta^t {V_t + theta_t[f(k_t,n_t) - c_t - k_{t+1} + (1-delta)k_t - g_t]} - phi A; theta_t is the multiplier on feasibility at t; capital appears only in the feasibility constraints of dates t and t+1
>
> *Garantiza:* R2 (circled). Since capital does not enter V_t (utility depends only on c and n), the Ramsey FOC in k reduces to the UNDISTORTED condition; in steady state theta_t = theta_{t+1}, so beta(f_k + 1 - delta) = 1, i.e. f_k + 1 - delta = 1/beta.

> **Q3.4 -- Optimal steady-state capital tax (answer R4; the Chamley-Judd result)**
>
> beta(f_k + 1 - delta) = beta(1 - tau_a)(f_k + 1 - delta). The left-hand side comes from the Ramsey FOC for k_{t+1} (which equals 1 in steady state) and the right-hand side from the household's Euler equation with capital taxation (which also equals 1 in steady state).
>
> *Supuestos requeridos:* a unique steady state exists; the firm's FOC gives r = f_k; the Ramsey allocation converges to a steady state with constant multipliers theta and phi
>
> *Garantiza:* The two are equal only if tau_a = 0: the optimal tax on capital income is ZERO in the long run (Chamley 1986, Judd 1985). The student's handwritten note on the last page reads: 'la unica manera en que son iguales es cuando tau_a = 0'. NOTE: unlike 3.1-3.3, no circle is visible on 3.4 in the scan; R4 is the option consistent with the student's own derivation.

### Formulas y resultados

| Resultado | Notacion | Significado | Cuando aplicar |
|---|---|---|---|
| Q1 utility | `\sum_{t=0}^{\infty}\beta^{t} u(c_t),\quad 0<\beta<1` | u strictly concave, strictly increasing, twice continuously differentiable; labor supply n_t inelastic and equal to 1. | Q1 throughout; there is no labor margin. |
| Q1 consumer's intertemporal budget constraint | `\sum_{t=0}^{\infty}\left\{q_t\left[(1+\tau_{ct})c_t + k_{t+1} - (1-\delta)k_t\right]\right\} \le \sum_{t=0}^{\infty}\left\{r_t k_t (1-\tau_{kt}) + w_t n_t\right\}` | tau_ct is a consumption tax, w_t the present-value real wage, r_t the present-value payment to capital, q_t the intertemporal price, tau_kt the tax on the return to capital ownership. | Q1.1 and Q1.2. |
| Q1 government's intertemporal budget constraint | `\sum_{t=0}^{\infty} q_t\left(\tau_{ct} c_t + \tau_{kt} r_t k_t\right) = \sum_{t=0}^{\infty} q_t g_t` | Present value of tax revenue equals present value of spending; no debt appears explicitly (Ricardian). | To argue that the reform in Q1.2 must raise the same present value of revenue. |
| Q1 feasibility | `f(k_t,n_t) = c_t + k_{t+1} - (1-\delta)k_t + g_t,\quad 0<\delta<1` | Output is consumed, invested, or spent by the government. | In steady state with n = 1: f(k,1) = c + delta k + g. |
| Q1 firm's problem | `\max \sum_{t=0}^{\infty}\left[q_t f(k_t,n_t) - r_t k_t - w_t n_t\right] \;\Rightarrow\; q_t f_k(k_t) = r_t \;\Rightarrow\; \frac{r_t}{q_t} = f_k` | Competitive firm equates the present-value marginal product to the present-value factor payment. | Gives the third answer in Q1.1: r/q = f_k. |
| Q1 consumer's FOC for c_t | `\beta^{t} u'(c_t) - \lambda q_t (1+\tau_{ct}) = 0 \;\Rightarrow\; q_t = \frac{\beta^{t}u'(c_t)}{\lambda(1+\tau_{ct})}` | Date-0 price is proportional to the tax-adjusted marginal utility. | Substitute into the no-arbitrage condition to get the Euler equation. |
| Q1 no-arbitrage (present-value form) | `q_t = q_{t+1}(1-\delta) + r_{t+1}(1-\tau_{k})` | Collecting terms in k_{t+1} in the budget constraint: k_{t+1}[q_{t+1}(1-delta) - q_t + r_{t+1}(1-tau_k)] = 0. | This is the student's blue annotation on page 2 and the first line of the last handwritten page. |
| Q1 Euler equation with taxes | `\frac{u'(c_t)}{\beta u'(c_{t+1})} = \left(f_k(1-\tau_{k,t+1}) + 1 - \delta\right)\left(\frac{1+\tau_{ct}}{1+\tau_{c,t+1}}\right)` | Both taxes appear: the capital tax multiplies the marginal product, and the consumption tax enters only as a GROWTH RATE (ratio), so a constant tau_c is intertemporally neutral. | Q1.1 and the comparative statics of Q1.2. |
| Q1.1 answer (R1) | `1 = \beta\left(1 - \delta + f_k(1-\tau_k)\right),\qquad f(k,1) = c + \delta k + g,\qquad \frac{r}{q} = f_k` | One equation in one unknown for each of k, c and r/q. | The circled answer. |
| Q1 steady-state marginal product of capital | `f_k = \frac{\frac{1}{\beta} - 1 + \delta}{1-\tau_k};\qquad \tau_k = 0 \Rightarrow f_k^{*} = \frac{1}{\beta} - 1 + \delta` | The capital tax raises the required pre-tax marginal product, hence lowers k. | Q1.2 comparative statics; the student drew the decreasing f_k(K) curve with dashed lines showing the two steady states. |
| Q2 sequential budget constraint | `c_t + R^{-1} b_{t+1} \le y_t + b_t,\quad y_t \ge 0\;\forall t,\quad \sum_{t=0}^{\infty}\beta^{t} y_t < +\infty,\quad b_0 = 0,\quad \lim_{T\to\infty} R^{-T} b_{t+T} = 0` | Risk-free asset b_{t+1} with constant gross return R > 1 and R beta = 1; endowment economy. | Q2.1-2.4. |
| Q2 FOCs | `c_t:\;\beta^{t}u'(c_t) = \lambda_t;\qquad b_{t+1}:\; -\frac{\lambda_t}{R} + \lambda_{t+1} = 0 \Rightarrow \frac{\lambda_t}{\lambda_{t+1}} = R` | Combining: u'(c_t) = beta R u'(c_{t+1}); with beta R = 1 this gives c_t = c constant. | Q2.1-2.3. |
| Q2 intertemporal budget constraint | `\sum_{t=0}^{\infty}\beta^{t} c_t = \sum_{t=0}^{\infty}\beta^{t} y_t \quad (\text{using } R^{-1} = \beta,\; b_0 = 0,\; \text{TVC})` | Present value of consumption equals present value of income. | Pin down the LEVEL of the flat consumption path. |
| Q2.1 answer (R3) | `\frac{c}{1-\beta} = \frac{y}{1-\beta} \;\Rightarrow\; c = y` | Constant endowment -> autarky. | Baseline before the MIT shock. |
| Q2.2 answer (R3), V-shaped recovery | `\frac{c}{1-\beta} = y_l + \beta y + \beta^{2} y + \cdots = y_l + \frac{\beta}{1-\beta} y \;\Rightarrow\; c = (1-\beta) y_l + \beta y` | Only (1-beta) of the transitory shortfall is absorbed by consumption; the rest is smoothed by borrowing. | Transitory shock. |
| Q2.3 answer (R3), L-shaped recovery | `\frac{c}{1-\beta} = \frac{y_l}{1-\beta} \;\Rightarrow\; c = y_l` | Permanent shock is absorbed one-for-one. | Permanent shock. |
| Q2.4 identification inequality | `c^{\text{L}} = y_l < (1-\beta) y_l + \beta y = c^{\text{V}} \iff \beta y_l < \beta y \iff y_l < y` | Consumption is strictly lower under the permanent (L-shaped) path. | To infer persistence from consumption data. |
| Q3 utility and time constraint | `\sum_{t=0}^{\infty}\beta^{t} u(c_t,l_t),\qquad 1 = l_t + n_t` | Endogenous labor: leisure l_t and labor n_t sum to the unit time endowment. | Q3 throughout. |
| Q3 sequential budget constraint | `c_t + k_{t+1} + \frac{b_{t+1}}{R_t} - b_t \le (1-\tau_{nt}) w_t n_t + (1-\tau_{at})(r_t + 1 - \delta) k_t,\quad b_0 = 0` | tau_nt is a labor income tax; tau_at taxes capital earnings PLUS the asset value of capital net of depreciation; b_{t+1} is government debt. | To derive the FOCs, the no-arbitrage condition and the implementability condition. |
| Q3 household FOCs | `c_t:\;\beta^{t}u_{ct} = \lambda_t;\quad n_t:\; -\beta^{t}u_{nt} + \lambda_t (1-\tau_{nt}) w_t = 0 \Rightarrow \frac{u_{nt}}{u_{ct}} = (1-\tau_{nt}) w_t;\quad b_{t+1}:\; -\frac{\lambda_t}{R_t} + \lambda_{t+1} = 0;\quad k_{t+1}:\; -\lambda_t + \lambda_{t+1}(1-\tau_{a,t+1})(r_{t+1}+1-\delta) = 0` | The n_t FOC is the LABOR WEDGE: the marginal rate of substitution between leisure and consumption equals the after-tax wage. | All of Q3. |
| Q3.1 No Arbitrage Condition (R4) | `R_t = (1-\tau_{a,t+1})(r_{t+1} + 1 - \delta)` | Bonds and capital must deliver the same after-tax return. | Q3.1; also used to write q_{t+1}/q_t = 1/R_t. |
| Q3 intertemporal price | `q_t = \prod_{i=0}^{t-1} R_i^{-1},\qquad q_0 = 1,\qquad \frac{q_{t+1}}{q_t} = \frac{1}{R_t}` | Date-0 price of a date-t good. | Converting the sequential constraints into a single present-value constraint. |
| Q3 present-value budget constraint | `\sum_{t=0}^{\infty} q_t c_t = \sum_{t=0}^{\infty} q_t w_t n_t (1-\tau_{nt}) + k_0 (1-\tau_{a0})(r_0 + 1 - \delta)` | Consolidated household constraint with b_0 = 0. | Substituting the FOCs into it produces the implementability condition. |
| Q3.2 Implementability condition (R3) | `\sum_{t=0}^{\infty}\beta^{t} u_{ct} c_t = \sum_{t=0}^{\infty}\beta^{t} u_{nt} n_t + (1-\tau_{a0})(r_0 + 1 - \delta) k_0 \lambda` | The single constraint that encodes household optimality plus budget balance in terms of allocations only. | Constraint of the Ramsey problem in the primal approach. |
| Q3 pseudo-utility and Ramsey Lagrangian | `V_t \equiv u(c_t, 1-n_t) + \phi\left[u_{ct} c_t - u_{nt} n_t\right];\qquad J = \sum_{t=0}^{\infty}\beta^{t}\left\{ V_t + \theta_t\left[f(k_t,n_t) - c_t - k_{t+1} + (1-\delta)k_t - g_t\right]\right\} - \phi A,\quad A \equiv (1-\tau_{a0})(r_0+1-\delta)k_0\lambda` | The Ramsey planner maximizes over allocations {c_t, n_t, k_{t+1}} with multiplier phi on implementability and theta_t on feasibility. | Q3.3-3.4. |
| Q3.3 Ramsey FOC for k_{t+1} (R2) | `-\beta^{t}\theta_t + \beta^{t+1}\theta_{t+1}\left(f_{k,t+1} + 1 - \delta\right) = 0` | Capital enters only through feasibility, so its Ramsey FOC is the undistorted intertemporal condition. | In steady state (theta constant) it collapses to f_k + 1 - delta = 1/beta. |
| Q3 household Euler with capital tax | `\frac{u_{ct}}{\beta u_{c,t+1}} = (1-\tau_{a,t+1})(r_{t+1} + 1 - \delta) \;\;\overset{\text{ss}}{\Longrightarrow}\;\; \frac{1}{\beta} = (1-\tau_a)(r + 1 - \delta)` | The private intertemporal condition, distorted by tau_a. | Compare with the Ramsey FOC to solve for the optimal tau_a. |
| Q3.4 optimal capital tax equation (R4) | `\beta(f_k + 1 - \delta) = \beta(1-\tau_a)(f_k + 1 - \delta) \;\Longrightarrow\; \tau_a = 0` | Chamley-Judd: zero capital income taxation in the long run (using r = f_k from the firm's FOC). | Final answer to Q3. |
| Q3 firm's FOCs (student's margin note) | `r_t = f_{k}(k_t,n_t) q_t,\qquad w_t = f_{n}(k_t,n_t) q_t` | Both factors are paid their marginal products; combined with the no-arbitrage condition this gives r = f_k in steady state. | To replace r by f_k in the final comparison. |

### [LABOR] Bloque laboral *(relevante para la tesis)*

Q1: labor is INELASTICALLY supplied at n_t = 1, so there is no labor-supply margin and the Frisch elasticity is exactly 0. Production is a generic f(k_t,n_t), homogeneous of degree 1, with strictly positive and decreasing marginal returns -- no functional form is imposed, so no specific labor-demand curvature parameter exists; labor demand is implicitly w_t = q_t f_n(k_t,n_t) from the firm's problem max sum [q_t f(k_t,n_t) - r_t k_t - w_t n_t], and with n fixed at 1 the wage simply clears at f_n(k,1). Q2: NO labor at all -- it is a pure endowment economy with exogenous y_t. Q3: labor is ENDOGENOUS. Utility u(c_t,l_t) with 1 = l_t + n_t, strictly concave and strictly increasing in both arguments, twice continuously differentiable; NO functional form is imposed, so the Frisch elasticity is not pinned down numerically -- it is whatever -u_l/(l u_ll) implies. The labor supply condition (labor wedge) is u_nt/u_ct = (1-tau_nt) w_t. Labor demand is w_t = f_n(k_t,n_t) from the firm's static problem max f(k_t,n_t) - r_t k_t - w_t n_t (the student wrote r_t = Pmg_{k_t} q_t and w_t = Pmg_{n_t} q_t in the margin). The curvature of labor demand is governed by the curvature of f in n, i.e. by f_nn < 0 and, given CRS, by the elasticity of substitution between k and n -- but since f is left generic no single parameter governs it. The tax tau_nt is the exogenous shifter of the labor-supply schedule, and this is exactly the structure an empirical design would exploit to identify the slope of labor demand.

### [POLICY] Instrumentos de politica

- tau_ct -- consumption tax (Q1): enters the consumer's intertemporal budget constraint multiplying c_t, as q_t(1+tau_ct)c_t, and enters the Euler equation only as the ratio (1+tau_ct)/(1+tau_{c,t+1}); a CONSTANT tau_c is therefore intertemporally non-distortionary. In Q1.1 tau_c = 0; in Q1.2 it becomes a constant in (0,1).
- tau_kt -- tax on the return to capital ownership (Q1): enters as r_t k_t (1-tau_kt) on the income side; in the Euler equation it appears as f_k(1-tau_k), raising the required pre-tax marginal product to (1/beta - 1 + delta)/(1-tau_k) and lowering steady-state capital. In Q1.1 constant with 1 > tau_k > 0; in Q1.2 set to zero forever.
- g_t -- government spending (Q1 and Q3): enters feasibility f(k_t,n_t) = c_t + k_{t+1} - (1-delta)k_t + g_t and the government's budget constraint sum q_t g_t. Constant at g > 0 in Q1 and unchanged by the reform in Q1.2.
- q_t -- intertemporal (date-0) price (Q1 and Q3): not an instrument but the price used to form present values; in Q3, q_t = prod_{i=0}^{t-1} R_i^{-1} with q_0 = 1.
- Government's intertemporal budget constraint (Q1): sum q_t(tau_ct c_t + tau_kt r_t k_t) = sum q_t g_t -- the constraint that ties the two tax instruments together in the reform of Q1.2.
- R (Q2) -- the constant gross risk-free rate on the asset b_{t+1}, with R beta = 1; not a policy instrument here but the market return governing the annuity factor.
- b_{t+1} (Q2) -- risk-free asset holdings; borrowing constraint b_{t+1} >= (bound) is announced in the title of Q2 but EXPLICITLY RULED OUT for parts 2.1-2.4 ('Assume that there is NO borrowing constraint').
- tau_nt -- labor income tax (Q3): enters the household's budget constraint as (1-tau_nt) w_t n_t and the intratemporal condition as u_nt/u_ct = (1-tau_nt)w_t. It is the distorting instrument that the Ramsey planner ends up relying on.
- tau_at -- tax on capital earnings plus the asset value of capital net of depreciation (Q3): enters as (1-tau_at)(r_t + 1 - delta)k_t; it appears in the no-arbitrage condition R_t = (1-tau_{a,t+1})(r_{t+1}+1-delta) and in the household Euler. Its optimal steady-state value is ZERO.
- tau_a0 -- the INITIAL-period capital tax (Q3): taken as given/restricted, and it survives in the implementability condition through the term (1-tau_a0)(r_0+1-delta)k_0 lambda. Without a restriction on it the Ramsey planner would confiscate the initial capital lump-sum.
- b_{t+1}/R_t -- government debt held by the household (Q3), with b_0 = 0; the vehicle that lets the government front-load or back-load revenue.

### [COMPUT] Metodo computacional

Pencil-and-paper (no computation): the exam explicitly forbids calculators, cellphones, tablets, laptops, class material and notes. The analytical chain in each question is: (i) write the Lagrangian of the household's problem with the appropriate (present-value or sequential) budget constraint; (ii) take FOCs with respect to c_t and the assets (k_{t+1}, b_{t+1}); (iii) combine them to obtain the no-arbitrage condition and the Euler equation; (iv) add the firm's FOCs (r/q = f_k, w/q = f_n) and feasibility; (v) impose the steady state to get one equation in one unknown; (vi) for the Ramsey problem, substitute the household FOCs into the present-value budget constraint to obtain the implementability condition, define the pseudo-utility V_t, form the Ramsey Lagrangian J with multipliers phi (implementability) and theta_t (feasibility), differentiate with respect to k_{t+1}, and compare the planner's condition with the household's Euler in steady state to solve for the optimal tax. Grading is multiple choice: the algebra must be done on the color sheets, which do not count.

### [RECETA] Solucion paso a paso

1. Q1 RECIPE (fiscal policies, present-value formulation). (1) Write the household Lagrangian with the Arrow-Debreu constraint sum q_t[(1+tau_ct)c_t + k_{t+1} - (1-delta)k_t] <= sum[r_t k_t(1-tau_kt) + w_t n_t]. (2) FOC c_t: beta^t u'(c_t) = lambda q_t(1+tau_ct). (3) Collect the coefficient of k_{t+1} in the constraint and set it to zero -> N.A.C.: q_t = q_{t+1}(1-delta) + r_{t+1}(1-tau_k). (4) Divide the c_t FOCs at t and t+1 and substitute the N.A.C. to obtain the Euler u'(c_t)/(beta u'(c_{t+1})) = (f_k(1-tau_k)+1-delta)((1+tau_ct)/(1+tau_{c,t+1})). (5) Firm FOC: r_t/q_t = f_k. (6) Impose the steady state (c_t = c, k_t = k, constant taxes): 1 = beta(1 - delta + f_k(1-tau_k)) gives k; feasibility f(k,1) = c + delta k + g gives c; r/q = f_k gives the return. -> Q1.1 answer R1. (7) For Q1.2, note (1+tau_c)/(1+tau_c) = 1 when tau_c is constant, so the reform removes only the capital wedge: f_k goes from (1/beta-1+delta)/(1-tau_k) down to 1/beta-1+delta; by concavity of f, k RISES and r/q = f_k FALLS. -> Q1.2 answer R2.
2. Q2 RECIPE (permanent income with an MIT shock). (1) Lagrangian with the sequential constraint c_t + b_{t+1}/R <= y_t + b_t. (2) FOCs: beta^t u'(c_t) = lambda_t and -lambda_t/R + lambda_{t+1} = 0, hence u'(c_t) = beta R u'(c_{t+1}); with beta R = 1, c_t = c for all t. (3) Iterate the sequential constraint forward, use b_0 = 0, R^{-1} = beta and the TVC lim R^{-T}b_{t+T} = 0 to get sum beta^t c_t = sum beta^t y_t. (4) Plug in each income path: constant y -> c = y; V-shaped (y_1 = y_l, y_t = y thereafter) -> c/(1-beta) = y_l + (beta/(1-beta))y -> c = (1-beta)y_l + beta y; L-shaped (y_t = y_l forever) -> c = y_l. (5) Compare the two: y_l < (1-beta)y_l + beta y iff y_l < y, so LOWER consumption reveals the PERMANENT (L-shaped) path. -> answers R3, R3, R3, R4.
3. Q3 RECIPE (Ramsey / primal approach). (1) Household Lagrangian with the sequential constraint c_t + k_{t+1} + b_{t+1}/R_t - b_t <= (1-tau_nt)w_t n_t + (1-tau_at)(r_t+1-delta)k_t. (2) FOCs: beta^t u_ct = lambda_t; u_nt/u_ct = (1-tau_nt)w_t; -lambda_t/R_t + lambda_{t+1} = 0; -lambda_t + lambda_{t+1}(1-tau_{a,t+1})(r_{t+1}+1-delta) = 0. (3) Equate the bond and capital returns -> N.A.C.: R_t = (1-tau_{a,t+1})(r_{t+1}+1-delta) [Q3.1, R4]. (4) Using q_t = prod R_i^{-1}, consolidate into sum q_t c_t = sum q_t w_t n_t(1-tau_nt) + k_0(1-tau_a0)(r_0+1-delta); substitute beta^t u_ct = lambda q_t and beta^t u_nt = lambda q_t w_t(1-tau_nt) -> IMPLEMENTABILITY: sum beta^t u_ct c_t = sum beta^t u_nt n_t + (1-tau_a0)(r_0+1-delta)k_0 lambda [Q3.2, R3]. (5) Define V_t = u(c_t,1-n_t) + phi[u_ct c_t - u_nt n_t] and J = sum beta^t{V_t + theta_t[f(k_t,n_t)-c_t-k_{t+1}+(1-delta)k_t-g_t]} - phi A. (6) Differentiate J w.r.t. k_{t+1}: -beta^t theta_t + beta^{t+1}theta_{t+1}(f_{k,t+1}+1-delta) = 0 [Q3.3, R2]; in steady state beta(f_k+1-delta) = 1. (7) Compare with the household's steady-state Euler 1 = beta(1-tau_a)(r+1-delta) and use r = f_k: beta(f_k+1-delta) = beta(1-tau_a)(f_k+1-delta) [Q3.4, R4], which holds only if tau_a = 0 -- the Chamley-Judd zero-capital-tax result.

### Intuicion general

The exam tests three of the course's central results, each stripped down to the algebra that identifies the answer. (1) Fiscal wedges: a capital income tax appears in the Euler equation as f_k(1-tau_k) and therefore drives a permanent wedge that lowers the long-run capital stock; a CONSTANT consumption tax appears only as the ratio (1+tau_c)/(1+tau_c') = 1 and therefore does not distort the intertemporal margin at all. Swapping the capital tax for a constant consumption tax is thus a move toward a less distortionary tax system: capital rises and the pre-tax return r/q = f_k falls. The picture the student drew -- a downward-sloping f_k(K) schedule with two horizontal lines -- IS the argument. (2) Permanent income and MIT shocks: with beta R = 1 and no borrowing constraint, consumption is flat and equals the annuity value of lifetime resources, so the response of consumption to an income shock is exactly the shock's persistence. This makes consumption an informative statistic about persistence -- the key identification lesson of Q2.4, and a direct macro analogue of using observed behavior to recover an unobserved structural object. (3) Ramsey taxation via the primal approach: because capital does not enter the pseudo-utility function V_t (utility depends only on c and n), the planner's FOC for k_{t+1} is undistorted, beta(f_k+1-delta) = 1; but the household's Euler under a capital tax reads 1 = beta(1-tau_a)(f_k+1-delta). Consistency forces tau_a = 0 -- Chamley-Judd. The deeper reason is that a permanent capital tax compounds into an exponentially growing distortion of the relative price of future consumption, so it is optimal to raise revenue from labor (and from the initial, sunk capital stock) instead.

### Ejemplos y ejercicios

- Q1.2 is a concrete tax-reform experiment: eliminate the capital income tax, replace it with a constant consumption tax, keep g fixed, and trace the new steady state.
- Q2 Case 1 'V-shaped recovery' (income falls only at t = 1) versus Case 2 'L-shaped recovery' (income stays low forever) is a stylized COVID-19-style recession experiment used to teach the difference between transitory and permanent shocks.
- Q2.4 places an econometrician INSIDE the model who observes only consumption -- an explicit identification exercise.
- Q3 is Ljungqvist & Sargent (2004) Exercise 15.7, the canonical Chamley-Judd zero-capital-tax problem.

### Anotaciones a mano (tuyas)

- GENERAL: the exam PDF interleaves the printed pages with the student's handwritten color-sheet work: printed p.2 is followed by a full handwritten solution to Q1; printed p.4 by a handwritten solution to Q2; printed p.7 by a handwritten solution to Q3; and a final grid-paper page with a two-column, cleaner rewrite of Q1 (left) and Q3 (right).
- Printed p.2 (top right margin, blue): 'q_t - q_{t+1}(1-delta) = r_{t+1}(1-tau_k)' -- the no-arbitrage / user-cost condition, written next to the consumer's intertemporal budget constraint.
- Printed p.3 (Q1.1): R1 CIRCLED (the correct answer). R2 and R4 are struck through. Above R1 the student wrote in blue 'k_{t+1} = I_t + (1-delta)k_t' -- reminding that in steady state investment equals delta k, which is what discriminates R1 from R3.
- Printed p.3 (Q1.2): R2 CIRCLED and underlined (capital bigger, r/q smaller after the change).
- Handwritten sheet after p.2 (Q1 solution): max sum beta^t u(c_t) s.a. sum q_t[(1+tau_ct)c_t + k_{t+1} + (1-delta)k_t] <= sum [r_t k_t(1-tau_kt) + w_t n_t]; Lagrangian; c_t FOC: beta^t u'(c_t) - lambda q_t(1+tau_ct) = 0; k_{t+1} FOC: lambda r_{t+1}(1-tau_{k,t+1}) - lambda q_t + lambda q_{t+1}(1-delta) = 0; the two combined into u'(c_t)/(beta u'(c_{t+1})) = (q_t/q_{t+1})((1+tau_ct)/(1+tau_{c,t+1})) and then = (Pmg_k(1-tau_{k,t+1}) + 1 - delta)((1+tau_ct)/(1+tau_{c,t+1})); firm: max sum q_t f(k_t,n_t) - r_t k_t - w_t n_t, k_t FOC: q_t f'(k_t) - r_t = 0 => r_t/q_t = Pmg_k; 'en ss' r/q = Pmg_k; 'f(k,1) = c - delta k + g' [SIC -- should be c + delta k + g; apparent slip]; then (r_{t+1}/q_{t+1})(1-tau_{k,t+1}) - q_t/q_{t+1} + (1-delta) = 0; Pmg_k(1-tau_{k,t+1}) + 1 - delta = q_t/q_{t+1}; 1/beta = Pmg_k(1-tau_k) + 1 - delta; => Pmg_k = (1/beta - 1 + delta)/(1-tau_k); 'si tau_k = 0 => Pmg_k* = 1/beta - 1 + delta'. Accompanied by a HAND-DRAWN GRAPH of a downward-sloping Pmg_k schedule against K with two dashed horizontal levels and an arrow pointing right -- the visual proof that lowering the required Pmg_k raises K.
- Printed p.4 (Q2, right margin, blue): 'beta^t u'(c_t) = lambda_t'; 'b_{t+1}: lambda_{t+1} = lambda_t R^{-1}'; 'u'(c_t) = R beta u'(c_{t+1}) => c_t = c_{t+1}'; 'c_t + R^{-1}b_{t+1} <= y_t + b_t'; 'R^{-1}c_{t+1} + R^{-2}b_{t+2} <= R^{-1}y_{t+1} + R^{-1}b_{t+1}'; 'sum R^{-t}c_t <= sum R^{-t}y_t => c sum R^{-t} <= y sum R^{-t}'; 'beta = R^{-1} => c ...' (iterating the sequential constraint forward into the present-value constraint).
- Handwritten sheet after p.4 (Q2 solution): max sum beta^t u(c_t) s.a. c_t + b_{t+1}/R <= y_t + b_t for all t; Lagrangian; c_t: beta^t u'(c_t) = lambda_t => u'(c_t)/(beta u'(c_{t+1})) = R, 'si beta R = 1 ent. c_t = c for all t'; b_{t+1}: -lambda_t/R + lambda_{t+1} = 0 => lambda_t/lambda_{t+1} = R; 'RPI' (restriccion presupuestal intertemporal): sum beta^t c_t = sum beta^t y_t; 'si y_t = y for all t': c/(1-beta) = y/(1-beta) => c = y; 'si y_1 = y_l, y_t = y for all t > 1': c/(1-beta) = y_l + beta y + beta^2 y + ... = y_l + beta y[1 + beta + beta^2 + ...] = y_l + (beta/(1-beta))y, so c = (1-beta)y_l + beta y; 'si y_t = y_l for all t': c = y_l.
- Printed p.5 (Q2.1): R3 (c = y) CIRCLED.
- Printed p.5 (Q2.2): R3 (c = (1-beta)y_l + beta y) CIRCLED. In the margin: 'c (1/(1-beta)) <= y_l + sum_{t=1}^{infty} y beta^{t-1} + b_1' with '+ b_1' HIGHLIGHTED IN YELLOW and an arrow with the note (partly illegible) 'esto importa[ria] ... aqui lo habiamos tirado ... si b_1 o b_0 =/= 0' -- i.e. a CHECK note that the answer relies on zero initial assets and would change if b_1 or b_0 were non-zero. Below: 'c = ((R-1)/R)y_l + y beta' and 'c = (1-beta)y_l + beta y'.
- Printed p.5 (Q2.3): R3 (c = y_l) CIRCLED. In the margin: 'c(beta/(beta-1)) <= ...' then 'Nota: c_2 < c_1 => y_l < (1-beta)y_l + beta y => beta y_l < beta y => y_l < y (check mark)' -- the verification that consumption is lower in the L-shaped case, which is the argument for 2.4.
- Printed p.6 (Q2.4): R4 CIRCLED ('If consumption is lower after the shock, income follows an L-shaped recovery').
- Printed p.7 (Q3.F, firm's problem, right margin): 'r_t = Pmg_{k_t} q_t' and 'w_t = Pmg_{n_t} q_t'.
- Handwritten sheet after p.7 (Q3 solution): max sum beta^t u(c_t,l_t) s.a. c_t + k_{t+1} + b_{t+1}/R - b_t <= (1-tau_nt)w_t n_t + (1-tau_at)(r_t+1-delta)k_t, with l_t = (1-n_t) noted above; Lagrangian; c_t: beta^t u_ct = lambda_t => u_ct/(beta u_{c,t+1}) = R; n_t: -beta^t u_nt + lambda_t(1-tau_nt)w_t = 0 => u_nt/u_ct = (1-tau_nt)w_t; b_{t+1}: -lambda_t/R + lambda_{t+1} = 0; k_{t+1}: -lambda_t + lambda_{t+1}(1-tau_{a,t+1})(r_{t+1}+1-delta) = 0 => R = (1-tau_{a,t+1})(r_{t+1}+1-delta); 'RPI': sum q_t c_t = sum (1-tau_nt)w_t n_t + (1-tau_a0)(r_0+1-delta)k_0; 'CPO ...' substituting the FOCs: sum (beta^t u_ct/lambda) c_t = sum (beta^t u_nt/lambda) n_t + A, hence sum beta^t u_ct c_t = sum beta^t u_nt n_t + lambda A; V_t = u(c_t,1-n_t) + phi[u_ct c_t - u_nt n_t]; J = sum beta^t {V_t + theta_t[f(k_t,n_t) - c_t - k_{t+1} + (1-delta)k_t - g_t]} - phi A; k_{t+1}: beta^{t+1}theta_{t+1}(f_{k,t+1}+1-delta) - beta^t theta_t = 0, 'en ss' f_k + 1 - delta = 1/beta; Euler: u_ct/(beta u_{c,t+1}) = (1-tau_{a,t+1})(r_{t+1}+1-delta), 'ss' 1/beta = (1-tau_a)(r+1-delta); final line: (f_k + 1 - delta) = (1-tau_a)(r + 1 - delta) with 'f_k' written above 'r'.
- Printed p.8 (Q3.1): R4 CIRCLED. (Q3.2): R3 CIRCLED. (Q3.3): R2 CIRCLED. (Q3.4): NO circle visible in the scan -- but the student's own derivation on the last page implies R4.
- FINAL PAGE (grid paper, two columns separated by a red vertical line; the printed statement of 1.1 is pasted at the top left). LEFT COLUMN (Q1, cleaner rewrite): PV(c) <= PV(w n) + sum q_t((1-delta)k_t - k_{t+1}) + sum r_t k_t(1-tau_k); collecting k_{t+1}: q_{t+1}(1-delta)k_{t+1} - q_t k_{t+1} + r_{t+1}k_{t+1}(1-tau_k) = k_{t+1}[q_{t+1}(1-delta) - q_t + r_{t+1}(1-tau_k)]; '=> N.A.C.: q_t = q_{t+1}(1-delta) + r_{t+1}(1-tau_k)'; L = sum beta^t u(c_t) + lambda(VP(after tax income) - VP(gross I) - sum q_t c_t(1+tau_c)); 'k_t:' (left blank); 'c_t: beta^t u'(c_t) = lambda q_t(1+tau_c) => q_t = beta^t u'(c_t)/(lambda(1+tau_c))'; '=> Euler: beta^t u'(t)/(lambda(1+tau_ct)) = [beta^{t+1}u'(t+1)/(lambda(1+tau_{c,t+1}))](1-delta) + r_{t+1}(1-tau_k)'; 'firm: max sum pi_t; r_t = q_t f_k(t) = y_t'; '=> ss: u'(t)/(lambda(1+tau_c)) = [beta u'(t+1)/(lambda(1+tau_{c,t+1}))](1-delta) + [beta u'(t+1)/(lambda(1+tau_{c,t+1}))] f_k(t)(1-tau_k)'; 'u'(t)/(1+tau_c) = [beta u'(t+1)/(1+tau_c)][(1-delta) + f_k(t)(1-tau_k)]'; '=> 1 = beta(1 - delta + f_k(1-tau_k))'; 'f(k,1) = c + delta k + g'; '(r/q) = f_k' CIRCLED. RIGHT COLUMN (Q3, cleaner rewrite): 'N.A.C.: (1-tau_{a,t+1})(r_{t+1}+1-delta)/R_t = 1 for all t'; 'R.P.I.: sum q_t(.) = sum q_t w_t n_t(1-tau_nt) + k_0(1-tau_a0)(r_0+1-delta)'; 'L = sum_{t=0}^{infty} beta^t u(t) + lambda(VPI - VPC)'; 'c_t: beta^t u_c(t) = lambda q_t'; 'n_t: beta^t u_n(t) = lambda q_t w_t(1-tau_nt)'; 'Sustituyendo las C.P.O.'s en RPI => sum (beta^t u_c(t)/lambda)c_t = sum (beta^t u_n(t)/lambda)n_t + k_0(1-tau_a0)(r_0+1-delta)' with the arrow label 'IC'; 'Sea A = (1-tau_a0)(r_0+1-delta) lambda k_0'; 'sum beta^t u_c(t)c_t = sum beta^t u_n(t)n_t + A'; 'Sea V_t = u(c_t,1-n_t) + phi[u_c(t)c_t - u_n(t)n_t] - phi A'; 'J = sum beta^t {V_t + theta_t[f(n_t,n_t) - c_t - k_{t+1} + (1-delta)k_t - g_t]}'; 'k_{t+1}: -beta^t theta_t + beta^{t+1}theta_{t+1}(f_k(t+1)+1-delta) = 0'; 'Notando que q_{t+1}/q_t = 1/R_t'; 'Euler: beta^t u_ct = beta^{t+1}u_{c,t+1} q_t/q_{t+1}; u_ct = beta u_{c,t+1}R_t = beta u_{c,t+1}(1-tau_{a,t+1})(r_{t+1}+1-delta)'; 'En ss => Euler: 1 = beta(1-tau_a)(r+1-delta)'; '=> [de] k_{t+1}: 1 = beta(f_k + (1-delta)) -> f_k = r'; '.'. la unica manera en que son iguales es cuando tau_a = 0' -- the Chamley-Judd conclusion, written out in Spanish.
- Language note: the student's work mixes Spanish and English -- 'Pmg_k' = producto marginal del capital (marginal product of capital), 'RPI' = restriccion presupuestal intertemporal (intertemporal budget constraint), 'CPO' = condicion de primer orden (first order condition), 'en ss' = en estado estacionario (in steady state), 'IC' = implementability condition, 'VPI/VPC' = valor presente del ingreso / del consumo.

### Conexiones con otros temas

- The steady-state Euler 1 = beta(1 - delta + f_k(1-tau_k)) is the taxed version of the project's 1/beta = alpha Y/K + (1-delta) (set tau_k = 0 and f_k = alpha Y/K).
- Q1's fiscal wedges are the same distortions McGrattan (1994) introduces as stochastic fiscal shocks in the RBC model of Topic 1; there they generate business-cycle dynamics, here they shift the steady state.
- Q2 is the permanent income / natural-debt-limit / transversality material of Topic 2 (NotesDynMacroIITopic2.1.pdf) applied to an MIT shock; the absence of a binding borrowing constraint is what makes the annuity formula exact.
- The MIT-shock device in Q1.2 and Q2 is the deterministic counterpart of the stochastic TFP innovation whose IRF the computing project asks for; both compute the transition after an unanticipated one-time change.
- For a thesis on labor demand elasticity: Q3's labor wedge u_nt/u_ct = (1-tau_nt) w_t is exactly the object an empirical labor-supply/demand study tries to decompose; the exam's structure (a tax that shifts the after-tax wage while the marginal product schedule w_t = f_n(k_t,n_t) stays put) is precisely a labor-DEMAND-curve-tracing experiment, since a labor tax shifts supply and traces out demand. Conversely, Q1's inelastic labor supply (n = 1) is the limiting case in which the wage is entirely demand-determined.

---
