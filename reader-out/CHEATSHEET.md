# Cheatsheet - Dynamic Macroeconomics II (Meza, ITAM)

## Mapa del curso

| Archivo | Modelo | Instrumentos de politica | Metodo de solucion |
|---|---|---|---|
| `Macro_Din_II_Topics1.1and1.2.pdf` | Topic 1: Models of Real Business Cycles (1.1 Stylized Facts & HP Filter; 1. | tau_{k_t}, tau_{n_t}, g_t, T_t, Calibrated long, No monetary policy in | Hodrick-Prescott (HP) filter for detrending (lambda=1600 quarterly, lambda=100 annual). Calibra |
| `Macro_Din_II_Topic2.1Basic.pdf` | Fiscal Policy / Ricardian Equivalence -- Basic Model (pure endowment econom | - | Purely analytical: (i) the 'solving forward' iterative substitution technique to derive the Nat |
| `NotesDynMacroIITopic2.1.pdf` | Handwritten companion notes to Topic 2.1 Basic Model: step-by-step derivati | - | 'Solving forward' (iterative substitution) technique, worked out step by step by hand; Lagrangi |
| `Macro_Din_II_Topic2.1Government.pdf` | Fiscal Policy / Ricardian Equivalence -- Model with Government (formal stat | g_t, tau_t, B_t, R, No distortionary taxes, subsidies, or monetary ins | Purely analytical/proof-based: 'solving forward' and 'solving backward' algebraic substitution  |
| `NotesMacroDynIITopic2.1Gov.pdf` | Handwritten companion notes to Topic 2.1 Government: full worked derivation | tau_t, tau, y | 'Solving backward' (iterative backward substitution of the sequential budget constraint from a  |
| `Macro_Din_II_Topic2.2FirstPartFINALVERSI` | Fiscal Policies in the Growth Model — First Part: non-stochastic one-sector | g_t, tau_ct, tau_kt, tau_nt, tau_ht, tau_it | None implemented yet; this file sets up the theoretical equilibrium system (feasibility, NAC, c |
| `Macro_Din_II_Topic2.2SecondPart.pdf` | Fiscal Policies in the Growth Model — Second Part: steady state of the capi | g_t, tau_it, tau_kt, tau_ct, Note | Shooting algorithm (discrete-time nonlinear difference-equation solver): (1) compute steady sta |
| `Macro_Din_II_Topic2.2ThirdPartFINALVERSI` | Fiscal Policies in the Growth Model — Third Part: which taxes are distortin | g_t, tau_ct, tau_kt, tau_nt, tau_ht, tau_it | Two model 'experiments' once solved on the computer: (1) impulse-response -- perturb one exogen |
| `NotesDynMacroIITopic2.2.pdf` | Handwritten notes, Continuous-Time (Ramsey) Model, Part 1: constructing the | - | Phase-diagram / graphical shooting-method reasoning (no numbers, no code): identify the c-dot=0 |
| `NotesDynMacroIITopic2.2secondpart.pdf` | Handwritten notes, Continuous-Time (Ramsey) Model, Part 2: the saddle path/ | - | Purely graphical/phase-diagram reasoning (no numerical algorithm executed here), but it supplie |
| `Macro_Din_II_Topic2.3FirstPartFINALVERSI` | Optimal Fiscal Policy with Commitment — First Part: the Ramsey Problem, Cha | tau_kt, tau_nt, g_t, b_t / b_{t+1}, tau_k0, S_it / S_t | None — purely analytical derivation via Lagrangian methods and steady-state characterization; n |
| `Macro_Din_II_Topic2.3SecondPartFINALVERS` | Optimal Fiscal Policy with Commitment — Second Part: the primal approach to | tau_kt, tau_nt, b_t, g_t, Phi, p_zt = F_zt | None — purely analytical Lagrangian/primal-approach derivation of steady-state results; no nume |
| `Macro_Din_II_Agosto_2018Topic3.1FirstPar` | A Monetary Model — First Part: money demand via a shopping-time transaction | tau_t, B_t (or b_t), M_t, g_t, Seigniorage f(R_m)(1, Consolidated gove | Graphical/geometric solution method explicitly invoked ('let's solve the equilibrium using a gr |
| `NotesDynMacroIITopic3.1.pdf` | Handwritten student lecture notes, Topic 3.1 (October 2020): the seigniorag | tau, tau_0, B, B_0, B', M_0, R_m, g, Seigniorage f(R_m)(1 | Purely graphical/diagrammatic solution method — hand-drawn Laffer curves and their intersection |
| `Macro_Din_II_Agosto_2018Topic3.1SecondPa` | Monetary economics — shopping-time money-in-the-utility model (Topic 3.1 Se | tau_t, g, g_t, B, R_t, R_m, R_{mt}, M_t, M_0, M_0' | Primarily analytical/graphical: long-run and short-run graph analysis of the shopping-time mode |
| `Macro_Din_II_Agosto_2018Topic4.2CORREGID` | Exogenous growth in the (deterministic) neoclassical growth model with dist | tau_t^c, tau_t^x, tau_t^k, tau_t^l, tr_t, G_t | The lecture itself IS a computational-method prerequisite: 'detrending' — transforming trending |
| `Macro_Din_II_Agosto_2019Topic5FirstPart(` | Computational/solution methods for DSGE models — log-linearization (first-o | - | Log-linearization by hand: (1) substitute X_t=X-bar*e^{x_t} into every equation of the nonlinea |
| `Macro_Din_II_Agosto_2019Topic5SecondPart` | Uhlig's Method of Undetermined Coefficients for solving linear (log-lineari | - | Uhlig's Method of Undetermined Coefficients, done fully by hand for the example: (1) write the  |
| `Macro_Din_II_Agosto_2019Topic5ThirdPart.` | Computational implementation — using Harald Uhlig's Matlab toolkit (Undeter | - | Harald Uhlig's Matlab toolkit for solving linear rational-expectations models via the Method of |
| `Topic5Solving_by_hand.pdf` | Topic 5 (handwritten lecture notes, Prof. Felipe Meza): 'Solving the model  | - | Method of undetermined coefficients, done by hand: (1) start from the reduced loglinear pair (9 |
| `Proyecto.pdf` | Computing Program (Proyecto Computacional), Dynamic Macroeconomics II, ITAM | - | (1) Write the planner's Lagrangian with GHH utility and the resource constraint. (2) Take FOCs  |
| `Midterm_exam_Dynamic_Macro_II_oct2024_25` | Midterm Exam, Dynamic Macroeconomics II, Prof. Felipe Meza, ITAM, October 1 | tau_ct, tau_kt, g_t, q_t, Government's intertemporal budget constraint | Pencil-and-paper (no computation): the exam explicitly forbids calculators, cellphones, tablets |

## Supuestos clave por tema

**Topic 1: Models of Real Business Cycles (1.1 Stylized Facts & HP Filter; 1.2 Standard RBC **

- 0<beta<1, 0<delta<1 (McGrattan standard model)
- gamma>0, 0<theta<1 (functional form parameters)
- -1<rho_lambda<1 (TFP shock persistence)
- Competitive economy: agents take prices and initial capital k_0 as given
- Household does all investment, so the firm's problem is static
- Calibration principle: never calibrate a parameter to reproduce exactly the fact the model aims to explain (else no explanatory power)
- Hansen (1985): consumers work a fixed N hours or 0 (discrete/indivisible choice); non-convex choice set convexified via lotteries
- McGrattan fiscal extension: balanced government budget every period (no public debt in this version); taxes/spending follow a VAR known by consumers (no informational asymmetry)
- 1<lambda<R type growth conditions do not appear here (that's Topic 2.1); relevant instead: TFP grows geometrically lambda_t=lambda_0(1+g)^t, incompatible with plain stationary AR(1) unless detrended

**Fiscal Policy / Ricardian Equivalence -- Basic Model (pure endowment economy, no governmen**

- beta in (0,1)
- u(.) strictly increasing, strictly concave, twice differentiable
- Inada condition: lim_{c->0} u'(c) = +infinity
- No uncertainty in the economy
- Single risk-free asset with fixed gross return R>1
- {y_t} non-stochastic, y_t>=0, with sum beta^t y_t < infinity
- b_0 given exogenously
- R*beta=1 (key simplifying assumption throughout)
- Either b_{t+1}>=0 (no borrowing) OR the Natural Debt Limit b_{t+1}>=b-tilde_{t+1} is imposed (two alternative, not simultaneous, restrictions)
- No default risk

**Handwritten companion notes to Topic 2.1 Basic Model: step-by-step derivation of the Natur**

- R*beta=1 assumed when simplifying the Euler equation
- c_t=0 assumed (for all t) specifically to derive the tightest Natural Debt Limit bound -- not assumed to be optimal, just the worst-case repayment scenario
- Transversality Condition lim_{T->infinity} R^{-T} b_{t+T}=0 assumed (boxed in red) to close the forward-substitution derivation

**Fiscal Policy / Ricardian Equivalence -- Model with Government (formal statement and proof**

- Government purchases g_t do not enter the household's utility and are not productive (not public investment)
- Taxes tau_t are lump-sum (not distortionary) -- essential for Ricardian equivalence
- Sign convention: B_t>0 denotes public debt (opposite convention from the household's b_t)
- Equilibrium requires (1) household optimization given taxes and (2) government budget balance every period, given (b_0,B_0)
- Natural Debt Limit imposed on the household (carried from the Basic model)
- Alternative tax sequence {tau-bar_t} must have identical present value to {tau_t} for Ricardian equivalence to hold
- No uncertainty, no default risk (carried over from the Basic model)

**Handwritten companion notes to Topic 2.1 Government: full worked derivation of Step 4 in t**

- b_0 is identical and exogenous across the original and the adjusted asset sequences (carried from Step 3 of the printed proof)
- The original {tau_t} and the alternative {tau-bar_t} have equal present value (the defining hypothesis of the Ricardian Proposition)

**Fiscal Policies in the Growth Model — First Part: non-stochastic one-sector growth model w**

- Model is non-stochastic (perfect foresight).
- Taxes are distorting: tau_c (consumption), tau_k (capital earnings), tau_n (labor earnings), tau_h (lump-sum), and a subsidy tau_i on investment, all exogenous sequences.
- Government spending {g_t} is exogenous.
- U(c,1-n) is strictly increasing in both arguments, twice continuously differentiable, and strictly concave.
- F(k,n) is homogeneous of degree one with positive and decreasing marginal products of capital and labor.
- Initial government assets are zero when constructing the government's intertemporal budget constraint.
- All trades take place at t=0 (equivalent to sequential trading; Arrow-Debreu under uncertainty).
- Free entry among firms (zero-profit condition).
- Households can short-sell capital (borrow it), invoked in deriving the NAC.
- In the particular case: labor supply is exogenous/inelastic, n_t=1 for all t.

**Fiscal Policies in the Growth Model — Second Part: steady state of the capital difference **

- lim_{t->infinity} z_t = z-bar (exogenous fiscal variables converge to constants).
- Shooting requires S>T, where T is the period after which exogenous variables are constant.
- Model has a single endogenous state variable (capital), needed for Shooting to be tractable.
- Continuous-time block: inelastic labor supply n=1; f(k)=k^alpha; CRRA utility with curvature sigma; discount rate rho.
- Model exhibits saddle-point stability.

**Fiscal Policies in the Growth Model — Third Part: which taxes are distorting versus non-di**

- Labor supply is inelastic in the 'effects of taxes' analysis (baseline case).
- No government (g_t=0, no taxes) when introducing endogenous labor supply, 'for simplicity.'
- Utility separable log-log in consumption and leisure with weight psi on leisure.
- Cobb-Douglas production k^alpha n^{1-alpha}.

**Handwritten notes, Continuous-Time (Ramsey) Model, Part 1: constructing the phase diagram **

- Continuous-time primitives as in the companion slides: production f(k), inelastic labor supply, discount rate rho, depreciation delta, CRRA curvature sigma.
- f'(k) is strictly decreasing (diminishing marginal returns to capital), used to sign the dynamics in each region.

**Handwritten notes, Continuous-Time (Ramsey) Model, Part 2: the saddle path/stable arm, off**

- f'(k) is strictly decreasing (diminishing marginal returns to capital).
- rho>0 (positive discounting / impatience).
- Off-path behavior is ruled out by two separate optimality conditions: the Euler equation rules out consumption 'jumps'; the Transversality Condition rules out perpetual over-accumulation.

**Optimal Fiscal Policy with Commitment — First Part: the Ramsey Problem, Chamley's (dual) a**

- 0 < beta < 1 (household discount factor)
- u strictly increasing in c_t and 1-n_t, twice continuously differentiable, strictly concave
- F(k_t,n_t) homogeneous of degree one, positive and diminishing marginal returns in both inputs
- No uncertainty
- Government commits to future tax rates and will not deviate from the announced plan
- Government can issue public debt b_t (positive or negative)
- tau_k0 restricted to be a small number (essentially zero) so that taxing only the initial, inelastically-supplied capital stock is not a trivial solution to the Ramsey Problem
- Lump-sum taxes are ruled out (otherwise the Ramsey Problem is trivial: set all distortionary taxes to zero)
- Government expenditures g_t constant after some period T; Ramsey Problem's solution converges to a steady state (used for the tau_k=0 derivation)
- Judd's extension: all N agents share the SAME discount factor beta (critical — result fails if beta_i != beta_j)
- Judd's extension: government budget balanced in the baseline (stated as inessential — result is the same if relaxed)
- Two-class case: alpha_1 > alpha_2 = 0 (planner cares only about workers), workers do not save, capitalists do not work

**Optimal Fiscal Policy with Commitment — Second Part: the primal approach to the Ramsey Pro**

- Same underlying economy as in Chamley's (First Part) setup; government can issue debt
- Lump-sum taxes ruled out (recap from First Part) — otherwise the Ramsey Problem is trivially solved by setting all distortionary taxes to zero
- Correia (1996): production F(k_t,n_t,z_t) has constant returns to scale with strictly positive, decreasing marginal returns
- Correia (1996): z_t is inelastically supplied, z_t = Z (fixed) for all t
- Correia (1996): factor z priced competitively, p_zt = F_zt (profit maximization)
- Ramsey Problem's solution assumed to converge to a steady state (both in the baseline primal model and in the Correia extension)
- tau_k0 fixed/given as in the First Part

**A Monetary Model — First Part: money demand via a shopping-time transaction technology, th**

- Endowment economy with no uncertainty
- Representative household has one unit of time, split between leisure and shopping: 1 = l_t + s_t
- Single good, divided between private consumption {c_t} and government purchases {g_t}
- u_c, u_l > 0; u_cc, u_ll < 0; u_cl >= 0
- H >= 0, H_c, H_cc >= 0, H_{m/p} <= 0, H_{m/p,m/p} >= 0, H_{c,m/p} <= 0
- b_{t+1} can be positive or negative (government bonds); tau_t is a lump-sum tax; y > 0 constant endowment
- m_{t+1} >= 0 (nonnegativity of nominal money holdings), given initial stocks m_0, b_0
- No-arbitrage requires i_t >= 0, i.e., R_t >= R_mt
- M_0 = m_0, {g_t, tau_t} exogenous
- Government budget constraint follows from consolidating the fiscal and monetary branches, per Sargent and Wallace (1981)
- Assumed fiscal deficit in the long run: g - tau + B(R-1)/R > 0
- tau_0 != tau and B_0 != B allowed at t=0 (short run can differ from the t>=1 stationary values)

**Handwritten student lecture notes, Topic 3.1 (October 2020): the seigniorage Laffer curve,**

- Government budget for t>=1 assumed to represent a deficit: g-\tau+B(R-1)/R>0 (boxed/labeled assumption in the notes)
- f'(R_m) >= 0 (seigniorage/money-demand function increasing in R_m) taken into account when drawing the t=0 diagram
- Example assumes -(g+B_0-\tau_0)+B/R>0, otherwise M_0/p_0 could be negative, contradicting the assumed M_0>0, p_0>=0
- There may exist an R_m such that f(R_m)=0 'as in the example in the book' (referenced but not derived here)
- At R_m=1, seigniorage=0; for R_m>1, seigniorage<0
- To implement the Friedman rule, need g-\tau+B(R-1)/R<0, i.e., a sufficiently large fiscal surplus
- An 'extra assumption' on H is needed to generate the kinked/satiated shape shown on the last page (H flat beyond psi(c))

**Monetary economics — shopping-time money-in-the-utility model (Topic 3.1 Second Part: mone**

- B>0 (real value of public debt must equal PV of net-of-interest government surplus)
- Extra assumption: for all c there exists m_{t+1}/p_t=\psi(c) such that H_{\widehat m_{t+1}}=0 for m_{t+1}/p_t \ge \psi(c) (existence of a satiation point)
- \nu \ge 0 (degree of homogeneity of shopping technology H)
- u_c,u_l>0;\ u_{cc},u_{ll}<0;\ u_{cl}\ge 0 (utility curvature/cross-partial used in the Friedman-rule proof)
- b_0=m_0=0 (initial conditions for the Ramsey plan)
- Transversality conditions: \lim_{T\to\infty} q_T \frac{b_{T+1}}{R_t}=0 and \lim_{T\to\infty} q_T \widehat m_{T+1}=0

**Exogenous growth in the (deterministic) neoclassical growth model with distortionary taxes**

- Total Factor Productivity and/or population grow at exogenous rates (some variables display growth so a steady state in levels does not exist)
- F is homogeneous of degree 1 (constant returns to scale in K and effective labor ZL)
- Utility multiplicatively separable, U(c,1-l)=c^{1-sigma}v(l)/(1-sigma) (KPR-type, balanced-growth consistent)
- beta-tilde=beta(1+g_n)(1+g_z)^{1-sigma}<1 required for convergence of detrended intertemporal utility
- G_t (government spending) is exogenous
- c_t,x_t>=0

**Computational/solution methods for DSGE models — log-linearization (first-order Taylor app**

- Uncertainty about future exogenous productivity (stochastic TFP)
- Log utility in consumption, linear (indivisible-labor) disutility of labor: log(C_t)-AN_t
- Cobb-Douglas production with capital share rho
- Linearization performed around the deterministic steady state
- Uhlig's timing convention: at time t, capital K_{t-1} is given and K_t is chosen (different from the more common convention of K_t given, K_{t+1} chosen — explicitly flagged: 'keep difference in mind')

**Uhlig's Method of Undetermined Coefficients for solving linear (log-linearized) rational-e**

- Same underlying RBC model assumptions as Topic 5 First Part (log utility, linear/indivisible labor disutility, Cobb-Douglas production, AR(1) TFP)
- Guessed functional form: policy functions are linear in the (single) state variables k_{t-1} and z_t
- Both matched equations must hold for ALL values of k_{t-1} and z_t simultaneously, so all coefficients multiplying them must independently equal zero (identification argument underlying Undetermined Coefficients)

**Topic 5 (handwritten lecture notes, Prof. Felipe Meza): 'Solving the model by hand' -- the**

- The full non-linear model has ALREADY been loglinearized and algebraically reduced to the two equations (9) and (10) in (k_t, lambda_t, z_t) -- the notes explicitly say 'assume by now you have done algebra to get equation (9) and (10) in the Presentation, p.12'.
- The equilibrium is a linear (first-order) function of the minimal state (k_{t-1}, z_t) -- i.e. a linear rational-expectations solution exists and is unique after imposing stability.
- z_t follows an AR(1): z_{t+1} = psi z_t + epsilon_{t+1} with E_t epsilon_{t+1} = 0.
- alpha_2 =/= 0 and alpha_5 =/= 0 (needed to divide).
- The two equations must hold for ANY possible value of (k_{t-1}, z_t), which is what licenses coefficient matching.
- Exactly one root of the quadratic satisfies |eta_kk| < 1 (saddle-path stability).

**Computing Program (Proyecto Computacional), Dynamic Macroeconomics II, ITAM (solution by C**

- Representative agent, closed economy, no government, no taxes and no distortions: the planner's allocation equals the competitive equilibrium.
- Period utility is GHH: ln(C_t - tau N_t^v / v). Consumption enters logarithmically inside the composite, and there is no wealth effect on labor supply.
- v > 1, so the disutility of labor is strictly convex (increasing marginal disutility of hours).
- tau > 0 is a preference weight on the disutility of work (NOT a tax).
- Technology is Cobb-Douglas with constant returns to scale, Y_t = Z_t K_t^alpha N_t^{1-alpha}, 0 < alpha < 1.
- Capital depreciates at a constant rate 0 < delta < 1 and takes one period to build (K_{t+1} chosen at t).
- Discount factor 0 < beta < 1, constant.
- TFP is an AR(1) in logs with persistence 0 < psi < 1 and iid innovations with mean 0 and variance sigma^2 (distribution D unspecified beyond its first two moments -- certainty equivalence of the loglinear solution means only sigma matters).
- The economy is close enough to the non-stochastic steady state that a first-order (log)linear approximation is accurate; e^x approx 1 + x.
- The matrix C is invertible (there are exactly as many equations in the deterministic block as control variables).
- Only one root of the quadratic in P satisfies |P| < 1 (saddle-path stability / Blanchard-Kahn holds).

**Midterm Exam, Dynamic Macroeconomics II, Prof. Felipe Meza, ITAM, October 10, 2024 (100 po**

- Q1: u strictly concave, strictly increasing, twice continuously differentiable; labor supply n_t inelastic and equal to 1; f homogeneous of degree 1 with strictly positive decreasing marginal returns; 0 < delta < 1; 0 < beta < 1; k_0 > 0 given; f(k_t,n_t) not given a specific functional form (the answers must be stated as one equation in one unknown).
- Q1.1: g_t = g > 0 constant; 1 > tau_kt = tau_k > 0 constant; tau_c = 0 for all t.
- Q1.2: initial capital = the steady state from 1.1; the policy change is COMPLETELY UNEXPECTED (an MIT shock); tau_k = 0 in all periods thereafter; the consumption tax is always constant and strictly between 0 and 1; g unchanged; the government must satisfy its present-value budget constraint.
- Q2: u strictly increasing, strictly concave, twice differentiable, with Inada condition lim_{c->0} u_c = +infinity; risk-free asset with constant gross return R > 1 and R beta = 1; endowment y_t >= 0 with finite present value; b_0 = 0; transversality lim_{T->infinity} R^{-T} b_{t+T} = 0; FOR 2.1-2.4 THERE IS NO BORROWING CONSTRAINT (the exam states this explicitly, so the household can freely borrow against future income).
- Q2 (MIT shock): the environment is deterministic; at t = 1 the income sequence changes unexpectedly; after that agents have perfect foresight.
- Q3: u(c_t,l_t) strictly concave, strictly increasing in consumption and leisure, twice continuously differentiable; 1 = l_t + n_t; f has constant returns to scale with decreasing and strictly positive marginal returns; b_0 = 0; q_0 = 1; a unique steady state exists; the initial capital tax tau_{a0} is taken as given (this is why the initial-capital term appears in the implementability condition).

## Teoremas esenciales

| Teorema | Supuestos requeridos | Resultado |
|---|---|---|
| **RBC model shortfall (Kydland & Prescott 1982) and its resolution** | Cobb-Douglas technology k^theta n^(1-theta); divisible labor with log-separable utility ln(c)+gamma ln(l); TFP follows AR(1); competitive equilibrium, representative agent | Motivates two documented extensions: Hansen (1985) indivisible labor (lotteries -> linear-in-leisure utility, amplifies hours volatility) and McGrattan (1994) fiscal shocks (distortionary taxes lower the model-implied ho |
| **Perfect consumption smoothing result** | strictly concave, strictly increasing, twice differentiable u(.); Inada condition; R*beta=1; no uncertainty; borrowing constraint (whichever form) never binds | Whether or not the constraint binds depends entirely on the shape/timing of the income path {y_t}, as illustrated by Examples 1-3 (unconstrained, constrained only at t=0, and always constrained, respectively). |
| **Natural Debt Limit derivation (worked algebra)** | Transversality Condition holds; c_t=0 is feasible (Inada-type condition rules out negative consumption, not that zero itself is optimal) | Even with consumption driven to the lowest feasible level, the consumer cannot repay more than b-tilde_t; this is the loosest possible (Natural) debt limit. |
| **Ricardian Proposition** | Natural Debt Limit imposed on the household; same government expenditure path {g_t}; alternative tax sequence has identical present value to the original; no uncertainty, no default risk, single bond  | Proved in 5 steps: (1) household's optimal consumption is unchanged because it depends on taxes only through their present value (via the solved-forward budget constraint for b_0); (2)-(3) the adjusted borrowing sequence |
| **Step 4 of the Ricardian Proposition proof (Transversality transfer)** | b_0 is identical and exogenous in both the original and the adjusted asset sequences; original {tau_t} and alternative {tau-bar_t} have equal present value; the original sequence {b_{t+1}} already sat | Closes the equivalence argument on the household side: the adjusted debt sequence is a valid equilibrium object (satisfies both the Natural Debt Limit, shown in Step 3, and now the Transversality Condition), so consumpti |
| **Euler's theorem on homogeneous functions of degree one (applied to the firm's problem)** | F is homogeneous of degree one; F has positive and decreasing marginal products of capital and labor | The firm's discounted profit sum sum_t [q_t F(k_t,n_t) - r_t k_t - w_t n_t] can be rewritten as sum_t [(q_t F_kt - r_t) k_t - (q_t F_lt - w_t) n_t]; with free entry, zero profit requires each bracket to vanish termwise,  |
| **k_GR > k_ss** | f'(k) strictly decreasing; rho>0 | k_GR > k_ss; illustrated by a declining f'(k) curve mapping delta+rho to k_ss and delta to k_GR, with k_ss to the left of k_GR. |
| **The economy does not reach k_GR** | rho>0 | Equilibrium capital converges to k_ss < k_GR, not to the Golden Rule level. |
| **Chamley–Judd zero capital tax (steady state, representative agent)** | Neoclassical growth model with F(k,n) homogeneous of degree 1, positive and diminishing marginal returns; No uncertainty, government commits to tax plan; Lump-sum taxes ruled out (tau_k0 restricted to | tilde r = r (after-tax rental rate equals before-tax rental rate) ⇒ tau_k = 0; result is robust to eliminating government debt (b_{t+1}=b_t=0). |
| **Judd (1985) extension with heterogeneous agents** | N agents i=1,...,N with distinct utilities u_i(c_it,1-n_it); All agents share the SAME discount factor beta; Lump-sum transfers S_it >= 0 allowed, government budget balanced (result unchanged if relax | r = tilde r (tau_k=0) again in steady state; result breaks down if discount factors differ across agents (beta_i != beta_j), because the steady-state Euler equation used in the proof would then hold for only one agent. |
| **Two-class special case (workers vs. capitalists)** | alpha_1 > alpha_2 = 0; Same beta for both classes | tau_k = 0 even though the planner is maximizing only the utility of the non-capital-owning class. |
| **Primal-approach confirmation of tau_k=0** | Same underlying neoclassical growth economy as Chamley's setup (govt can issue debt); Steady state exists | tau_k = 0, confirming the Chamley/Judd result via an alternative (primal) method. |
| **Correia (1996): steady-state capital tax under incomplete taxation** | F(k,n,z) constant returns to scale, strictly positive and decreasing marginal returns; z_t = Z fixed (inelastically supplied); Factor z priced competitively at p_zt = F_zt; Steady state exists | tau_k is generally nonzero; its sign is determined entirely by the sign of F_zk (since Z>0, u_c>0, Phi>0, theta>0, F_k>0). tau_k = 0 only when F_zk = 0. For Cobb-Douglas technology, F_zk > 0, so tau_k > 0. |
| **No-arbitrage / Fisher-equation derivation** | m_{t+1} >= 0 (nonnegativity of nominal balances) | The gross real return on bonds must be at least as large as the gross real return on money; otherwise households could achieve unbounded consumption via unbounded nominal money holdings. |
| **Stationary real interest rate** | Stationary equilibrium (constant inflation, constant c, constant s) | R = 1/beta; consumption is pinned down directly by c = y - g since y,g are exogenous in the endowment economy. |
| **Long-run equilibrium determination (Laffer curve equation)** | Stationary equilibrium for t>=1; f'(R_m) >= 0 (money demand increasing in R_m); Assumed deficit: g - tau + B(R-1)/R > 0 | Because the seigniorage function is hump-shaped (Laffer curve), the equation generically has two solutions for R_m; the model/slide states 'we will work with the classic one' without further specifying selection criteria |
| **Short-run price level determination** | M_0 = m_0 given; {g_t,tau_t} exogenous | p_0 is pinned down residually after R_m is found; the equilibrium is solved in two stages: long run first (find R_m), then short run (find p_0). |
| **Two-root selection heuristic (student's own informal argument)** | Deficit line lies below the peak of the Laffer curve (two intersections exist) | Equilibrium selection convention: pick the higher-R_m (lower-inflation) intersection as the relevant steady state. |
| **Friedman rule implementation condition** | 1/beta > 1 lies beyond the peak of the seigniorage Laffer curve, on its downward-sloping segment where seigniorage revenue is negative | The intersection of the deficit line with the Laffer curve at R_m=1/beta requires the deficit line itself to lie below zero, i.e. a primary-plus-interest surplus, not a deficit. |
| **Ramsey-optimality of Friedman's rule in the shopping-time model with homogeneous transaction technology** | nu >= 0 (degree of homogeneity of H); u_c, u_l > 0; u_cc, u_ll < 0; u_cl >= 0 (curvature/cross-partial assumption used in the proof); existence, for every c, of a finite satiation point psi(c) | Proved by exhaustive cases on nu: nu>1 forces multipliers phi and theta_t to be zero or of opposite sign, but phi>0 and theta_t>0 by insatiability — contradiction unless H_m-hat=0; nu=1 forces theta_t=0, contradicting th |
| **Well-posedness of the detrended household problem** | multiplicatively separable utility of KPR type, c^{1-sigma}v(l)/(1-sigma); beta(1+g_n)(1+g_z)^{1-sigma}<1 | Guarantees the household's detrended optimization problem is well posed, i.e. the model can be solved as a stationary dynamic program/Euler-equation system after removing trend. |
| **Reciprocal-roots / saddle-path uniqueness result for eta_KK** | log-linearized Hansen/Uhlig RBC system; guessed linear policy-function form for k_t and lambda_t | At most one root is stable (modulus <1); this stable root is the economically relevant/selected solution, ensuring a unique bounded (non-explosive) policy function for capital — a characteristic feature of the neoclassic |
| **Quadratic characterization of the capital autoregressive coefficient** | alpha_2 =/= 0 and alpha_5 =/= 0; the two loglinear equations (9) and (10) hold for every possible value of (k_{t-1}, z_t); z_t follows z_{t+1} = psi z_t + epsilon_{t+1} with E_t epsilon_{t+1} = 0 | eta_kk is a root of a scalar quadratic; take the root with \|eta_kk\| < 1 and recover eta_lambda_k = -alpha_1/alpha_2 + eta_kk/alpha_2. This is the by-hand version of Uhlig's Ftilde P^2 + Gtilde P + Htilde = 0 with the P |
| **Convexity criterion for the labor-disutility exponent** | N_t > 0; tau > 0 | v > 1 is exactly what makes the disutility of work convex (increasing marginal disutility), which is required for an interior, well-behaved labor choice. Note the document's typo: it prints d/dN (N^v/v) = N_t^v when it s |
| **Uhlig's undetermined-coefficient characterization of P and Q** | C is square and invertible (here 4x4, one equation of the deterministic block per control variable); the expectational block has as many equations as endogenous states (here 1); z_t is AR(1) with matr | Since P is a scalar here, P = (-Gtilde +/- sqrt(Gtilde^2 - 4 Ftilde Htilde)) / (2 Ftilde); choose the root with P < 1 for stability. Then Q solves the second (linear) equation, and R = -C^{-1}(A P + B), S = -C^{-1}(A Q + |
| **Steady-state modified golden rule with depreciation** | Cobb-Douglas technology; constant discount factor beta; no taxes, no growth | Pins down the steady-state capital-output ratio from beta, delta, alpha alone; the identity alpha beta Y/K = 1 - beta(1-delta) is precisely the simplification the student writes over the loglinear Euler equation and over |
| **Q1.1 -- Steady state with a constant capital tax and zero consumption tax (correct answer R1)** | g_t = g > 0 constant; 1 > tau_kt = tau_k > 0 constant; tau_c = 0 for all t; n_t = 1 inelastic; f homogeneous of degree 1 with strictly positive decreasing marginal returns; steady state: k_{t+1} = k_t | Student circled R1 and crossed out R2 and R4. R2 is wrong because it writes f_k - tau_k instead of f_k(1-tau_k); R3 is wrong because feasibility in steady state requires c + delta k + g, not c + (1-delta)k + g; R4 is wro |
| **Q1.2 -- Replacing the capital tax with a constant consumption tax (correct answer R2)** | the reform is completely unexpected (MIT shock); initial capital equals the old steady state; government spending g unchanged; the new consumption tax is constant and strictly between 0 and 1; unique  | Capital is bigger after the change and r/q is smaller after the change -> R2. (Student circled R2.) Economic content: a constant consumption tax is intertemporally non-distortionary, so eliminating the capital wedge rais |
| **Q2.1 -- Permanent income with a constant endowment (correct answer R3)** | u strictly increasing, strictly concave, twice differentiable, Inada lim_{c->0} u_c = +infinity; R beta = 1, R > 1; b_0 = 0; transversality lim_T R^{-T} b_{t+T} = 0; sum beta^t y_t < +infinity | c = y (R3, circled). Autarky consumption; no borrowing or lending occurs. |
| **Q2.2 -- V-shaped recovery (correct answer R3)** | same as 2.1; the change is an unanticipated MIT shock realized at t = 1; 0 < y_l < y; b_1 = 0 (no assets carried in) -- the student flags that a non-zero b_1 would matter | c = (1-beta) y_l + beta y (R3, circled). Only a fraction (1-beta) of the transitory income loss is absorbed by consumption -- the annuity value of the shock. |
| **Q2.3 -- L-shaped recovery (correct answer R3)** | same as 2.1-2.2; the drop is permanent | c = y_l (R3, circled). A permanent shock is absorbed one-for-one by consumption. |
| **Q2.4 -- Identifying persistence from consumption (correct answer R4)** | the economist observes consumption but not the income sequence; she knows the model and the two candidate income paths; 0 < y_l < y | If consumption is lower after the shock, income follows an L-shaped recovery -> R4 (circled). This is the exam's identification argument: consumption reveals the persistence of income shocks. |
| **Q3.1 -- No Arbitrage Condition (correct answer R4)** | consumer can hold both b_{t+1} (gross return R_t) and k_{t+1}; tau_at taxes capital earnings plus the asset value of capital net of depreciation; b_0 = 0 | R4 (circled). Derived from the FOCs for b_{t+1} and k_{t+1}: -lambda_t/R_t + lambda_{t+1} = 0 and -lambda_t + lambda_{t+1}(1-tau_{a,t+1})(r_{t+1}+1-delta) = 0. Both assets must offer the same after-tax return or the hous |
| **Q3.2 -- Implementability condition (correct answer R3)** | household FOCs beta^t u_ct = lambda q_t and beta^t u_nt = lambda q_t w_t (1 - tau_nt); b_0 = 0; q_t = prod_{i=0}^{t-1} R_i^{-1}, q_0 = 1; the present-value budget constraint holds with equality | R3 (circled). R1 omits lambda; R2 has a wrong sign/equals-zero form; R4 mistakenly multiplies the labor term by u_ct. The initial-capital term (1-tau_{a0})(r_0+1-delta)k_0 lambda is why the initial capital levy must be r |
| **Q3.3 -- Ramsey FOC with respect to k_{t+1} (correct answer R2)** | V_t = u(c_t,1-n_t) + phi[u_ct c_t - u_nt n_t]; J = sum beta^t {V_t + theta_t[f(k_t,n_t) - c_t - k_{t+1} + (1-delta)k_t - g_t]} - phi A; theta_t is the multiplier on feasibility at t; capital appears o | R2 (circled). Since capital does not enter V_t (utility depends only on c and n), the Ramsey FOC in k reduces to the UNDISTORTED condition; in steady state theta_t = theta_{t+1}, so beta(f_k + 1 - delta) = 1, i.e. f_k +  |
| **Q3.4 -- Optimal steady-state capital tax (answer R4; the Chamley-Judd result)** | a unique steady state exists; the firm's FOC gives r = f_k; the Ramsey allocation converges to a steady state with constant multipliers theta and phi | The two are equal only if tau_a = 0: the optimal tax on capital income is ZERO in the long run (Chamley 1986, Judd 1985). The student's handwritten note on the last page reads: 'la unica manera en que son iguales es cuan |

## Formulas esenciales por tema

### Topic 1: Models of Real Business Cycles (1.1 Stylized Facts & HP Filter; 1.2 Standard RBC 

- **Trend-cycle decomposition**: `Y_t = Y_t^c + Y_t^g` - Output equals cyclical plus trend component
- **HP filter minimization problem**: `\min_{\{Y_t^g\}} \sum_{t=1}^{T}(Y_t-Y_t^g)^2 + \lambda\sum_{t=1}^{T-1}\big[(Y_{t+1}^g-Y_t^g)-(Y_t^g-Y_{t-1}^g)\big]^2` - First term penalizes deviation of the trend from the data (fit), second term penalizes changes in the trend's growth rate (smoothness/curvature)
- **Log growth-rate approximation**: `\log(Y_t/Y_t^g) = \log(Y_t)-\log(Y_t^g) \approx \log(Y_t^c)` - Working in logs, the log difference between actual and trend approximates the percentage cyclical deviation
- **Household objective (McGrattan 1994 standard model)**: `\max\ E_0\sum_{t=0}^{\infty}\beta^t\big[u(c_t,\ell_t)\mid x_0\big]` - Consumer maximizes expected discounted utility from consumption and leisure
- **Budget constraint (1)**: `c_t+i_t \le r_tk_t+w_tn_t` - Consumption plus investment cannot exceed capital and labor income
- **Law of motion of capital (2)**: `i_t = k_{t+1}-(1-\delta)k_t` - Investment equals net change in capital plus depreciation; net investment k_{t+1}-k_t differs from gross investment k_{t+1}-k_t+\delta k_t
- **Time constraint (3)**: `1 = \ell_t+n_t` - Total time endowment normalized to 1 splits between leisure and labor
- **Firm problem and output (4)**: `\max\ y_t-w_tn_t-r_tk_t\ \ \text{s.t.}\ \ y_t=\lambda_tf(k_t,n_t)` - Representative competitive firm maximizes static profit given TFP lambda_t
- **Factor pricing (marginal products)**: `w_t=\lambda_tf_{n_t}=MP_{n_t}, \quad r_t=\lambda_tf_{k_t}=MP_{k_t}` - Competitive wages/rental rates equal marginal products
- **Feasibility**: `c_t+i_t = y_t` - Aggregate resource constraint in the baseline model (no government)
- **TFP AR(1) process**: `\lambda_{t+1} = (1-\rho_\lambda)\bar\lambda+\rho_\lambda\lambda_t+\varepsilon_{t+1}, \quad \varepsilon\sim(0,\sigma_\varepsilon^2)` - TFP follows a first-order autoregressive process with persistence rho_lambda in (-1,1)
- **Functional forms**: `u(c_t,\ell_t)=\ln(c_t)+\gamma\ln(\ell_t), \qquad f(k_t,n_t)=k_t^{\theta}n_t^{1-\theta}` - Log-separable utility and Cobb-Douglas production, \gamma>0,\ 0<\theta<1
- **Measured TFP**: `\lambda_t = \dfrac{y_t}{k_t^{\theta}n_t^{1-\theta}}` - Solow-residual style computation of TFP from data given theta
- **TFP detrending regression (McGrattan)**: `\ln TFP_t = \beta_0+\beta_1 t; \qquad \ln\lambda_t^{consistent} = \ln TFP_t-\beta_1 t` - Because TFP grows geometrically (\lambda_t=\lambda_0(1+g)^t, so \ln TFP_t\approx \ln\lambda_0+gt), incompatible with stationary AR(1); regress log TFP on a linear trend and remove 
- **Beta calibration via steady-state Euler equation**: `\beta=\dfrac{1}{1+r}` - Discount factor pinned down by the real interest rate
- **Delta calibration regression**: `i_t-(k_{t+1}-k_t) = \delta k_t` - Regression linking investment and capital change to depreciation
- **Theta calibration via steady-state Euler equation**: `1=\beta\Big[\theta\dfrac{y}{k}+(1-\delta)\Big]` - Steady-state condition linking capital share theta to the K/Y ratio
- **Gamma calibration via consumption-leisure condition**: `\dfrac{\gamma c}{1-n} = (1-\theta)\dfrac{y}{n}` - Steady-state MRS between consumption and leisure equals the after-tax wage/marginal product of labor
- **Hansen (1985) linear-in-leisure utility**: `u(c_t,\ell_t) = \ln(c_t)+\gamma_2\ell_t` - Result of convexifying the discrete work/no-work choice via lotteries
- **McGrattan (1994) utility with government spending**: `u(c_t+\pi g_t,\ell_t), \quad \pi\ge 0` - Government expenditure enters utility as an imperfect substitute for private consumption, weight pi
- **Balanced-budget transfer rule**: `g_t+T_t = \tau_{k_t}(r_t-\delta)k_t+\tau_{n_t}w_tn_t` - Endogenous lump-sum transfers T_t close the government budget every period given exogenous g_t and tax rates
- **Consumer budget constraint with taxes**: `c_t+i_t \le (1-\tau_{n_t})w_tn_t+r_tk_t-\tau_{k_t}(r_t-\delta)k_t+T_t` - Distortionary labor and net-capital-income taxation plus lump-sum transfer
- **Exogenous shock VAR**: `v_{t+1} = (I-\rho_v)\bar v+\rho_v v_t+\varepsilon_{t+1}, \quad \varepsilon\sim(0,\Sigma), \quad v_t=(\lambda_t,g_t,\tau_{k_t},\tau_{n_t})` - Vector generalization of the AR(1); rho_v is diagonal with entries rho_lambda, rho_g, rho_n, rho_k
- **New feasibility with government**: `c_t+i_t+g_t = y_t` - Resource constraint including government purchases
- **Static labor supply**: `\max\ u=\ln(c)+b\ln(1-n)\ \ \text{s.t.}\ \ c\le wn \ \Rightarrow\ n=\dfrac{1}{1+b}` - In a static economy labor supply depends only on preference parameter b, not on the wage
- **Two-period labor supply FOC**: `\dfrac{1-n_1}{1-n_2} = \dfrac{1}{\beta(1+r)}\dfrac{w_2}{w_1}` - Relative labor supply across two periods depends on relative wages and the interest rate (intertemporal substitution in labor supply)
- **Two-period labor supply FOC with taxes**: `\dfrac{1-n_1}{1-n_2} = \dfrac{1}{\beta(1+r)}\dfrac{w_2}{w_1}\dfrac{1-\tau_2}{1-\tau_1}` - Labor income tax wedge modifies the intertemporal labor-supply condition; equal tax rates across periods leave the condition unchanged (last term vanishes)

### Fiscal Policy / Ricardian Equivalence -- Basic Model (pure endowment economy, no governmen

- **Household objective**: `\sum_{t=0}^{\infty}\beta^t u(c_t)` - Discounted lifetime utility from consumption only (no leisure/labor)
- **Sequential budget constraint (1)**: `c_t+\dfrac{b_{t+1}}{R} \le y_t+b_t` - Consumption plus new bond purchases cannot exceed endowment plus maturing bond value
- **Finite PV endowment condition**: `\sum_{t=0}^{\infty}\beta^t y_t < \infty` - Technical condition ensuring the household's problem is well defined
- **No-borrowing restriction**: `c_t \le y_t+b_t-\tfrac{1}{R}b_{t+1}, \quad b_{t+1}\ge 0` - Households can lend but never borrow
- **Natural Debt Limit derivation**: `\tilde b_t = -\sum_{j=0}^{\infty}R^{-j}y_{t+j} = -PV(y)` - Obtained by setting c_t=0 for all t and solving forward; the alternative constraint is b_{t+1}\ge \tilde b_{t+1}<0
- **Transversality Condition**: `\lim_{T\to\infty} R^{-T}b_{t+T}=0` - Assumed limiting condition needed to close the forward-substitution derivation
- **Lagrangian of consumer's problem (no borrowing)**: `\mathcal{L}=\sum_{t=0}^{\infty}\Big[\beta^t u(c_t)+\lambda_t\big(y_t+b_t-c_t-\tfrac{b_{t+1}}{R}\big)+\mu_t b_{t+1}\Big]` - lambda_t is the multiplier on the budget constraint (always strictly positive), mu_t on b_{t+1}\ge0 (Kuhn-Tucker)
- **Modified Euler equation**: `u'(c_t) = \beta R\, u'(c_{t+1}) + \dfrac{R\mu_t}{\beta^t}` - Standard Euler equation augmented by the shadow value of the binding borrowing constraint
- **Example 1: present value of alternating endowment**: `PV(y)=\sum_{t=0}^{\infty}\beta^t y_t = \sum_{t=0}^{\infty}\beta^{2t}(y_h+\beta y_\ell) = \dfrac{y_h+\beta y_\ell}{1-\beta^2}` - Splitting the alternating sequence into 2-period blocks and summing a geometric series in beta^2
- **Example 1: constant consumption level**: `\dfrac{\bar c}{1-\beta} = \dfrac{y_h+\beta y_\ell}{1-\beta^2} \ \Rightarrow\ \bar c=\dfrac{y_h+\beta y_\ell}{1+\beta}` - Equating PV(c) to PV(y) under perfect smoothing, c_t=cbar for all t
- **Example 1: optimal bond-holding sequence (2)**: `b_{t+1}=\begin{cases}\dfrac{y_h-y_\ell}{1+\beta} & t=0,2,4,\dots\\[4pt] 0 & t=1,3,5,\dots\end{cases}` - Consumer saves in high-income periods, decumulates in low-income periods, never binds the constraint
- **Multiplier recovery**: `\mu_t=\beta^tR^{-1}u'(c_t)-\beta^{t+1}u'(c_{t+1})` - Backing out the Lagrange multiplier from the optimal consumption sequence via the Euler equation
- **Example 3 growth condition**: `1<\lambda<R, \quad \lambda\beta<1` - Endowment grows geometrically, y_t=\lambda^t, growth rate below R ensures PV(y) converges, but \lambda\beta<1 keeps the household wanting to bring income forward

### Handwritten companion notes to Topic 2.1 Basic Model: step-by-step derivation of the Natur

- **Sequential budget constraint (starting point)**: `c_t+\dfrac{b_{t+1}}{R}=y_t+b_t` - Base equation to be iterated forward
- **First forward-substitution step**: `b_t=c_t-y_t+\dfrac{c_{t+1}}{R}+\dfrac{b_{t+2}}{R^2}-\dfrac{y_{t+1}}{R}` - Result of substituting the period t+1 constraint into the period t constraint once
- **General forward solution (after invoking TC)**: `b_t=\sum_{j=0}^{\infty}R^{-j}(c_{t+j}-y_{t+j})` - Closed-form present-value expression for b_t once the boxed Transversality term vanishes
- **Natural Debt Limit**: `\tilde b_t=-\sum_{j=0}^{\infty}R^{-j}y_{t+j}` - Obtained by setting c_t=0 for all t in the general forward solution
- **Lagrangian**: `\mathcal L=\sum_{t=0}^{\infty}\Big(\beta^t u(c_t)+\lambda_t(y_t+b_t-c_t-\tfrac{b_{t+1}}{R})+\mu_t b_{t+1}\Big)` - Constrained optimization setup for the household's problem under the no-borrowing restriction
- **FOC w.r.t. c_t**: `\beta^t u'(c_t)-\lambda_t=0` - Marginal utility of consumption equals the shadow price of resources
- **FOC w.r.t. b_{t+1}**: `-\dfrac{\lambda_t}{R}+\lambda_{t+1}+\mu_t=0` - Marginal cost of saving equals its discounted marginal benefit plus the shadow value of relaxing the borrowing constraint
- **Euler equation (with multiplier)**: `u'(c_t)=\beta R\,u'(c_{t+1})+\dfrac{\mu_t R}{\beta^t}` - Combining the two FOCs; reduces to the standard Euler equation under R\beta=1 when \mu_t=0: u'(c_t)=u'(c_{t+1})+\dfrac{\mu_t R}{\beta^t}
- **Example 1: PV(y) via even/odd split**: `PV(y)=y_h+\beta y_\ell+\beta^2 y_h+\dots=(y_h+\beta y_\ell)(1+\beta^2+\beta^4+\dots)=\dfrac{y_h+\beta y_\ell}{1-\beta^2}` - Sum-\beta^2 Sum = 1 telescoping trick applied to Sum=1+\beta^2+\beta^4+\dots
- **Bond sequence recursion (Example 1)**: `c_0+\dfrac{b_1}{R}=y_0+b_0; \quad \bar c+\dfrac{b_1}{R}=y_h+0 \Rightarrow b_1=R(y_h-\bar c); \quad c_1+\dfrac{b_2}{R}=y_1+b_1 \Rightarrow \bar c+\dfrac{b_2}{R}=y_\ell+b_1` - Period-by-period recursive construction of the optimal bond-holding sequence once cbar is known

### Fiscal Policy / Ricardian Equivalence -- Model with Government (formal statement and proof

- **Government sequential budget constraint**: `B_t+g_t = \tau_t+\dfrac{B_{t+1}}{R}` - Government debt plus spending financed by current taxes and new borrowing
- **Government intertemporal budget constraint**: `B_t=\sum_{j=0}^{\infty}R^{-j}(\tau_{t+j}-g_{t+j})` - Obtained by solving forward and imposing the Transversality Condition \lim_{T\to\infty}R^{-T}B_{t+T}=0
- **Consumer's modified sequential budget constraint**: `c_t+\dfrac{b_{t+1}}{R}\le y_t+b_t-\tau_t` - Household resource constraint net of lump-sum taxes
- **Consumer's intertemporal constraint (solve forward)**: `b_t=\sum_{j=0}^{\infty}R^{-j}(c_{t+j}+\tau_{t+j}-y_{t+j})` - Present-value form of the household budget constraint including taxes
- **New Natural Debt Limit (disposable income)**: `\tilde b_t=-\sum_{j=0}^{\infty}R^{-j}(y_{t+j}-\tau_{t+j})` - Household can never borrow more than the present value of its disposable (after-tax) income
- **Equal-present-value tax condition**: `\sum_{t=0}^{\infty}R^{-t}\tau_t=\sum_{t=0}^{\infty}R^{-t}\bar\tau_t` - Definition of a Ricardian-equivalent alternative tax sequence
- **Adjusted debt sequences**: `\bar b_t=\sum_{j=0}^{\infty}R^{-j}(c_{t+j}+\bar\tau_{t+j}-y_{t+j}), \qquad \bar B_t=\sum_{j=0}^{\infty}R^{-j}(\bar\tau_{t+j}-g_{t+j})` - New equilibrium bond/debt levels implied by keeping the same {c_t},{g_t} but using the alternative tax sequence
- **Step 1: solve forward for b_0**: `b_0=\sum_{t=0}^{\infty}R^{-t}(c_t-y_t)+\sum_{t=0}^{\infty}R^{-t}\tau_t` - Shows the optimal consumption plan depends on the tax sequence only through its present value
- **Step 3: NDL check**: `\bar b_t=\sum_{j=0}^{\infty}R^{-j}(c_{t+j}+\bar\tau_{t+j}-y_{t+j}) \ge \tilde b_t=-\sum_{j=0}^{\infty}R^{-j}(y_{t+j}-\bar\tau_{t+j})` - Holds automatically because the consumption stream {c_t} is non-negative
- **Step 4: solve backward for b-bar_k**: `\bar b_k=\sum_{j=1}^{k}R^{j}\big[y_{k-j}-\bar\tau_{k-j}-c_{k-j}\big]+R^{k}b_0` - Backward substitution (from period k down to 0) of the sequential budget constraint
- **Step 4: difference equation**: `b_k-\bar b_k=\sum_{j=1}^{k}R^{j}\big[\bar\tau_{k-j}-\tau_{k-j}\big]` - Difference between original and adjusted debt at k depends only on discounted tax differences
- **Step 4: rescaled difference**: `R^{1-k}(b_k-\bar b_k)=R\sum_{t=0}^{k-1}R^{-t}\big[\bar\tau_t-\tau_t\big]` - As k\to\infty, since \{b_{t+1}\} satisfies the Transversality Condition and the tax sequences have equal present value, \{\bar b_{t+1}\} must too
- **Step 5: government budget solved forward at t=0**: `B_0=\sum_{t=0}^{\infty}R^{-t}\tau_t-\sum_{t=0}^{\infty}R^{-t}g_t` - Government's initial debt depends on taxes and spending only through present values

### Handwritten companion notes to Topic 2.1 Government: full worked derivation of Step 4 in t

- **Disposable income definition**: `\hat y_t = y_t-\tau_t` - Endowment net of the original lump-sum tax
- **Backward recursion base step**: `c_{k-1}+\dfrac{b_k}{R}=\hat y_{k-1}+\bar b_{k-1} \ \Rightarrow\ b_k=R(\hat y_{k-1}-c_{k-1}+\bar b_{k-1})` - Isolating b_k from the constraint at period k-1
- **Iterated backward solution**: `b_k=\sum_{j=1}^{k}R^{j}(\hat y_{k-j}-c_{k-j})+R^{k}b_0=\sum_{j=1}^{k}R^{j}(y_{k-j}-\tau_{k-j}-c_{k-j})+R^{k}b_0` - Closed-form expression for b_k (or b-bar_k under the alternative tax plan) purely in terms of b_0 and the history of disposable income minus consumption
- **Difference of debt sequences**: `b_k-\bar b_k=\sum_{j=1}^{k}R^{j}(\bar\tau_{k-j}-\tau_{k-j})` - Because b_0 and {c_t} are identical across the two plans, the entire difference collapses to discounted tax differences
- **Rescaled difference**: `R^{1-k}(b_k-\bar b_k)=R\sum_{t=0}^{k-1}R^{-t}(\bar\tau_t-\tau_t)` - Re-indexing and rescaling the previous formula into a form directly comparable to the Transversality Condition's R^{-T}b_{t+T} object

### Fiscal Policies in the Growth Model — First Part: non-stochastic one-sector growth model w

- **Utility function**: `\sum_{t=0}^{\infty}\beta^t U(c_t,1-n_t),\quad 0<\beta<1` - Lifetime utility over consumption and leisure; U strictly increasing in both arguments, twice continuously differentiable, strictly concave.
- **Production function**: `y_t = F(k_t,n_t)` - Homogeneous of degree one, positive and decreasing marginal products of capital and labor.
- **Law of motion for capital**: `k_{t+1} = (1-\delta)k_t + x_t` - Capital accumulates from gross investment x_t net of depreciation delta.
- **Feasibility condition**: `y_t = c_t + x_t + g_t` - Output splits between private consumption, investment, and government purchases.
- **Government's intertemporal budget constraint**: `\sum_{t=0}^{\infty} q_t g_t \le \sum_{t=0}^{\infty}\{\tau_{ct}q_tc_t - \tau_{it}q_t[k_{t+1}-(1-\delta)k_t] + r_t\tau_{kt}k_t + w_t\tau_{nt}n_t + q_t\tau_{ht}\}` - Present value of government purchases cannot exceed present value of net tax/subsidy revenue.
- **Consumer's intertemporal budget constraint**: `\sum_{t=0}^{\infty}\{q_t(1+\tau_{ct})c_t + (1-\tau_{it})q_t[k_{t+1}-(1-\delta)k_t]\} \le \sum_{t=0}^{\infty}\{r_t(1-\tau_{kt})k_t + w_t(1-\tau_{nt})n_t - q_t\tau_{ht}\}` - Present value of after-tax consumption plus after-subsidy net investment cannot exceed present value of after-tax factor income minus lump-sum taxes.
- **Firm's problem**: `\max_{\{k_t,n_t\}_{t=0}^{\infty}} \sum_{t=0}^{\infty}[q_tF(k_t,n_t) - r_tk_t - w_tn_t]` - Firm chooses capital and labor sequences to maximize present-value profit given the price system.
- **Household FOCs**: `\beta^t U_{1t} = \mu q_t(1+\tau_{ct}), \qquad \beta^t U_{2t} = \mu w_t(1-\tau_{nt})` - Marginal utility of consumption (leisure) equated to multiplier mu times the after-tax price of consumption (after-tax wage).
- **Zero profit conditions**: `r_t = q_tF_{kt}, \qquad w_t = q_tF_{nt}` - With free entry and constant-returns technology, factor prices equal the value of marginal products.
- **No Arbitrage Condition (NAC)**: `r_t(1-\tau_{kt}) + (1-\tau_{it})q_t(1-\delta) - q_{t-1}(1-\tau_{it-1}) = 0,\quad t\ge1` - Equates the after-tax return from holding capital one period to its after-tax purchase price the previous period; prevents arbitrage.
- **Transversality Condition**: `\lim_{T\to\infty}(1-\tau_{iT})q_Tk_{T+1} = 0` - Present value of the terminal capital stock (net of investment subsidy) must vanish asymptotically.
- **User Cost of Capital (UCC)**: `r_{t+1} = \left(\frac{1}{1-\tau_{k,t+1}}\right)\left[q_t(1-\tau_{it}) - q_{t+1}(1-\tau_{i,t+1}) + \delta q_{t+1}(1-\tau_{i,t+1})\right]` - One-period-forward rewriting of the NAC giving the cost of owning (not selling) one unit of capital for one more period, as a function of taxes/subsidy, depreciation, and prices.
- **Particular case: exogenous labor (n=1)**: `U(c,1-n)=u(c),\; n=1;\quad f(k)=F(k,1);\quad F_k=f'(k),\; F_n=f(k)-f'(k)k;\quad f(k_t)=c_t+g_t+k_{t+1}-(1-\delta)k_t` - Simplification with inelastic labor supply reduces the model to a single control (consumption/capital) using intensive-form production.
- **Second-order nonlinear difference equation for capital**: `u'(c_t) = \beta u'(c_{t+1})\frac{1+\tau_{ct}}{1+\tau_{ct+1}}\left[\frac{1-\tau_{k,t+1}}{1-\tau_{it}}f'(k_{t+1}) + \frac{1-\tau_{i,t+1}}{1-\tau_{it}}(1-\delta)\right]` - Euler equation with prices substituted out (using q_t = beta^t u'(c_t) / [mu(1+tau_ct)]) and consumption replaced via feasibility, yielding a second-order difference equation purel

### Fiscal Policies in the Growth Model — Second Part: steady state of the capital difference 

- **Exogenous state vector**: `z_t = [g_t\ \tau_{it}\ \tau_{kt}\ \tau_{ct}]'` - Collects the exogenous fiscal variables relevant to the capital difference equation under inelastic labor supply (tau_n and tau_h drop out).
- **Difference equation / steady state**: `H(k_t,k_{t+1},k_{t+2},z_t,z_{t+1})=0,\quad \lim_{t\to\infty}z_t=\bar z,\quad H(\bar k,\bar k,\bar k;\bar z,\bar z)=0` - General second-order difference equation for capital and its steady state given convergent exogenous variables.
- **Steady-state Euler condition**: `1=\beta\left[\frac{1-\tau_k}{1-\tau_i}f'(\bar k)+(1-\delta)\right]` - Steady-state version of the Euler equation from Part 1: after-tax marginal product of capital net of depreciation equals the inverse discount factor.
- **Closed-form steady-state capital (Cobb-Douglas)**: `\bar k = \left(\frac{1-\tau_k}{1-\tau_i}\cdot\frac{\alpha A}{\frac{1}{\beta}-1+\delta}\right)^{\frac{1}{1-\alpha}}\quad \text{if } f(k)=Ak^\alpha` - Explicit solution for steady-state capital under Cobb-Douglas technology.
- **Shooting: period-0 feasibility step**: `f(k_0)=c_0+g_0+k_1-(1-\delta)k_0` - Given k_0 and a guess c_0, solve for k_1.
- **Shooting: Euler forward step**: `u'(c_0)=\beta u'(c_1)\frac{1+\tau_{c0}}{1+\tau_{c1}}\left[\frac{1-\tau_{k1}}{1-\tau_{i1}}f'(k_1)+\frac{1-\tau_{i1}}{1-\tau_{i0}}(1-\delta)\right]` - Solve for c_1 given k_1 and the tax sequence.
- **Bisection bounds on c_0**: `c^{\ell}=0,\qquad c^{h}=f(k_0)+(1-\delta)k_0\ (\text{equivalent to }k_1=0);\qquad c_0=\tfrac12(c^{\ell}+c^{h})` - Low bound is zero consumption; high bound consumes everything (drives k_1 to zero). New guess is the midpoint, with the relevant bound updated depending on whether k_S over- or und
- **Rest of the equilibrium allocation**: `c_t=f(k_t)+(1-\delta)k_t-k_{t+1}-g_t,\quad q_t=\frac{\beta^tu'(c_t)}{1+\tau_{ct}},\quad r_t=q_tf'(k_t),\quad w_t=q_t(f(k_t)-k_tf'(k_t))` - Once the capital path is known, consumption, prices, and factor payments follow algebraically (q_t normalized by setting q_0=1, since it carries the intertemporal budget-constraint
- **Gross real after-tax interest rate**: `u'(c_t)=\beta u'(c_{t+1})R_{t+1},\qquad R_{t+1}=\frac{1+\tau_{ct}}{1+\tau_{ct+1}}\left[\frac{1-\tau_{it+1}}{1-\tau_{it}}(1-\delta)+\frac{1-\tau_{kt+1}}{1-\tau_{it}}f'(k_{t+1})\right]` - Defines the after-tax gross real return R_{t+1} implicit in the Euler equation.
- **CRRA utility and IES**: `u(c_t)=\frac{c_t^{1-\sigma}-1}{1-\sigma},\ \sigma>0,\sigma\ne1;\qquad \ln\left(\frac{c_{t+1}}{c_t}\right)=\frac1\sigma\ln\beta+\frac1\sigma\ln R_{t+1}` - With CRRA utility the Euler equation implies log consumption growth is linear in the log gross real rate with slope 1/sigma; that slope is, by definition, the intertemporal elastic
- **Continuous-time utility and feasibility**: `\int_0^{\infty}\frac{c^{1-\sigma}-1}{1-\sigma}e^{-\rho t}dt;\qquad \dot k=\frac{\partial k}{\partial t};\qquad y=c+\dot k+\delta k;\qquad f(k)=k^\alpha,\ n=1` - Continuous-time analog of the model: CRRA flow utility discounted at rate rho, capital accumulation as a time derivative, feasibility, and Cobb-Douglas-in-k production with inelast
- **Continuous-time Euler equation**: `\frac{\dot c}{c}=\frac1\sigma(f_k-\delta-\rho)` - Consumption growth rate equals (1/sigma) times the gap between the net-of-depreciation marginal product of capital and the discount rate.

### Fiscal Policies in the Growth Model — Third Part: which taxes are distorting versus non-di

- **Equilibrium system (baseline, inelastic labor)**: `c_t = f(k_t) + (1-\delta)k_t - k_{t+1} - g_t;\quad q_t=\frac{\beta^tu'(c_t)}{1+\tau_{ct}};\quad r_t=q_tf'(k_t);\quad w_t=q_t(f(k_t)-k_tf'(k_t));\quad u'(c_t)=\beta u'(c_{t+1})R_{t+1};\quad R_{t+1}=\frac{1+\tau_{ct}}{1+\tau_{ct+1}}\left[\frac{1-\tau_{it+1}}{1-\tau_{it}}(1-\delta)+\frac{1-\tau_{kt+1}}{1-\tau_{it}}f'(k_{t+1})\right]` - Reprints, in one block, the full pricing/allocation system from Parts 1-2, used to read off which taxes appear where.
- **Utility with leisure (endogenous labor case)**: `u(c_t,1-n_t) = \ln(c_t) + \psi\ln(1-n_t)` - Additively separable log utility in consumption and leisure with leisure weight psi.
- **Feasibility (no government)**: `c_t + k_{t+1} - (1-\delta)k_t = y_t` - Resource constraint with government purchases set to zero for simplicity.
- **Cobb-Douglas production**: `y_t = f(k_t,n_t) = k_t^{\alpha} n_t^{1-\alpha}` - Two-factor constant-returns technology with capital share alpha.
- **Euler equation with endogenous labor**: `\frac{c_{t+1}}{c_t} = \beta[\alpha k_{t+1}^{\alpha-1}n_{t+1}^{1-\alpha} + 1 - \delta]` - Intertemporal consumption-savings condition, now with labor n_{t+1} entering the marginal product of capital.
- **Consumption-leisure equation**: `\frac{\psi c_t}{1-n_t} = (1-\alpha)k_t^{\alpha} n_t^{-\alpha}` - Static intratemporal condition: MRS between leisure and consumption equals the marginal product of labor (real wage, since q_0 is normalized).

### Handwritten notes, Continuous-Time (Ramsey) Model, Part 1: constructing the phase diagram 

- **Continuous-time Euler equation**: `\frac{\dot c}{c} = \frac{1}{\sigma}(f'(k)-\delta-\rho)` - Growth rate of consumption as a function of the gap between the net marginal product of capital and the discount rate, scaled by 1/sigma.
- **c-dot=0 locus**: `f'(k)=\delta+\rho` - Equation depending only on k; its solution is the steady-state capital k_ss, shown as a vertical line in the (k,c) plane.
- **Continuous-time feasibility**: `\dot k = f(k) - c - \delta k` - Capital accumulation net of consumption and depreciation.
- **k-dot=0 locus**: `c = f(k) - \delta k` - Hump-shaped curve: rises while extra output from more capital exceeds extra depreciation, eventually falls once depreciation dominates diminishing returns.
- **Sign of dynamics off the loci**: `k>k_{ss} \Rightarrow f'(k)<\delta+\rho \Rightarrow \dot c<0;\qquad k<k_{ss} \Rightarrow \dot c>0;\qquad \text{fixed } k,\ \text{higher } c \Rightarrow \dot k<0;\ \text{lower } c \Rightarrow \dot k>0` - Direction of movement in each region, derived from diminishing marginal returns (f' decreasing) and from the feasibility identity.

### Handwritten notes, Continuous-Time (Ramsey) Model, Part 2: the saddle path/stable arm, off

- **k-dot=0 locus boundary behavior**: `k=0 \Rightarrow c=0\ (\text{from feasibility with } \dot k=0);\quad \text{for sufficiently high } k,\ \delta k \text{ dominates the marginal increase in } f(k)` - The k-dot=0 locus passes through the origin and eventually turns down and returns toward the k-axis at high capital levels.
- **Golden Rule problem**: `k_{GR} = \arg\max_{k}\{c = f(k) - \delta k\},\qquad \text{F.O.C. } f'(k)=\delta` - Capital level maximizing steady-state consumption, ignoring impatience.
- **Modified Golden Rule (actual steady state)**: `k_{ss}:\ f'(k)=\delta+\rho` - Capital level actually reached in equilibrium, accounting for the discount rate rho.

### Optimal Fiscal Policy with Commitment — First Part: the Ramsey Problem, Chamley's (dual) a

- **Household lifetime utility**: `\sum_{t=0}^{\infty}\beta^t u(c_t,1-n_t),\ 0<\beta<1` - Utility over consumption and leisure (1-n_t); u strictly increasing, twice continuously differentiable, strictly concave.
- **Euler's theorem decomposition**: `F(k_t,n_t)=F_k(t)k_t+F_n(t)n_t` - Since F is homogeneous of degree one (CRS), output exactly exhausts factor payments at marginal products.
- **Capital accumulation**: `k_{t+1}=(1-\delta)k_t+x_t` - Law of motion for capital given gross investment x_t and depreciation delta.
- **Feasibility**: `y_t=c_t+x_t+g_t` - Output splits into consumption, investment and government purchases.
- **Government sequential budget constraint**: `g_t=\tau_{kt}r_tk_t+\tau_{nt}w_tn_t+\frac{b_{t+1}}{R_t}-b_t` - Government purchases financed by capital tax revenue, labor tax revenue, and net bond issuance.
- **Household sequential budget constraint**: `c_t+k_{t+1}-(1-\delta)k_t+\frac{b_{t+1}}{R_t}-b_t=(1-\tau_{nt})w_tn_t+(1-\tau_{kt})r_tk_t` - Consumption plus net capital accumulation plus net bond purchases equals after-tax labor and capital income.
- **Household FOCs**: `c_t:\ u_c(t)=\lambda_t;\quad n_t:\ u_l(t)=\lambda_t(1-\tau_{nt})w_t;\quad k_{t+1}:\ \lambda_t=\beta\lambda_{t+1}[(1-\tau_{k,t+1})r_{t+1}+1-\delta];\quad b_{t+1}:\ \lambda_t\frac{1}{R_t}=\beta\lambda_{t+1}` - Standard consumer optimality conditions with Lagrange multiplier beta^t lambda_t.
- **Euler equation**: `u_{ct}=\beta u_{ct+1}[(1-\tau_{k,t+1})r_{t+1}+(1-\delta)]` - Intertemporal consumption smoothing given after-tax return on capital.
- **Consumption-leisure (labor supply) condition**: `u_{lt}=u_{ct}(1-\tau_{nt})w_t` - Marginal rate of substitution between leisure and consumption equals the after-tax wage.
- **No-arbitrage condition**: `R_t=(1-\tau_{kt})r_{t+1}+(1-\delta)` - Bonds and capital must offer the same after-tax return in equilibrium (note: slide 7 writes tau_kt while the FOC on the previous slide uses tau_{k,t+1} — a possible notational inco
- **Present-value household budget constraint**: `\sum_{t=0}^{\infty}\left(\prod_{i=0}^{t-1}R_i^{-1}\right)c_t=\sum_{t=0}^{\infty}\left(\prod_{i=0}^{t-1}R_i^{-1}\right)(1-\tau_{nt})w_tn_t+[(1-\tau_{k0})r_0+1-\delta]k_0+b_0` - Intertemporal budget after eliminating capital/bond terms via NAC, obtained by iterating and consolidating consecutive period budget constraints.
- **Transversality conditions**: `\lim_{T\to\infty}\left(\prod_{i=0}^{T-1}R_i^{-1}\right)k_{T+1}=0;\qquad \lim_{T\to\infty}\left(\prod_{i=0}^{T-1}R_i^{-1}\right)\frac{b_{T+1}}{R_T}=0` - Rules out Ponzi schemes / ensures the consolidated present-value budget constraint is valid.
- **Firm's problem**: `\Pi_t=F(k_t,n_t)-r_tk_t-w_tn_t;\quad F_k(t)=r_t,\ F_n(t)=w_t;\quad \Pi=0` - Competitive firms take prices as given; profits are zero in equilibrium by CRS.
- **Chamley's after-tax prices**: `\tilde r_t=(1-\tau_{kt})r_t;\qquad \bar w_t=(1-\tau_{nt})w_t` - Redefine the problem in terms of net-of-tax prices that the government effectively 'chooses'.
- **Government revenue as residual**: `\tau_{kt}r_tk_t+\tau_{nt}w_tn_t=F(k_t,n_t)-\tilde r_tk_t-\bar w_tn_t` - Tax revenue equals output minus what households actually receive net of taxes.
- **Ramsey Lagrangian (representative agent)**: `\mathcal{L}=\sum_{t=0}^{\infty}\beta^t\{U(c_t,1-n_t)+\psi_t[F(k_t,n_t)-\tilde r_tk_t-\bar w_tn_t+\tfrac{b_{t+1}}{R_t}-b_t-g_t]+\theta_t[F(k_t,n_t)-c_t-k_{t+1}+(1-\delta)k_t-g_t]+\mu_{1t}[u_l(t)-u_c(t)\bar w_t]+\mu_{2t}[u_c(t)-\beta u_c(t+1)(\tilde r_{t+1}+1-\delta)]\}` - Government maximizes utility subject to its own budget constraint (psi_t), feasibility (theta_t), and household optimality conditions (mu_1t, mu_2t) with R_t=\tilde r_{t+1}+1-\delt
- **FOC w.r.t. capital**: `\theta_t=\beta\{\psi_{t+1}[F_{k,t+1}-\tilde r_{t+1}]+\theta_{t+1}[F_{k,t+1}+1-\delta]\}` - theta_t and psi_t are positive multipliers: marginal value of an extra unit of production and of an extra unit of government revenue, respectively.
- **Steady-state capital-tax result**: `\theta=\beta\{\psi[r-\bar r]+\theta[r+1-\delta]\};\quad 1=\beta(\bar r+1-\delta);\quad (\theta+\psi)(r-\bar r)=0\ \Rightarrow\ \bar r=r\ \Rightarrow\ \tau_k=0` - Combining the steady-state FOC for capital with the consumer's steady-state Euler equation forces the after-tax and before-tax rental rates to coincide.
- **Household budget with net taxes (Judd, agent i)**: `c_{it}+k_{it+1}-(1-\delta)k_{it}=\bar w_tn_{it}+\tilde r_tk_{it}+S_{it}` - Each agent i faces the same prices/taxes but receives individual lump-sum transfer S_it.
- **Social welfare function**: `\sum_{i=1}^{N}\alpha_iu_i(c_{it},1-n_{it}),\quad \alpha_i\ge0,\ \sum_{i=1}^N\alpha_i=1` - Ramsey planner's objective is a weighted average of individual utilities.
- **Aggregate notation**: `x_t\equiv\sum_{i=1}^Nx_{it},\ x=c,n,k,S` - Shorthand for economy-wide aggregates.
- **N-agent Ramsey Lagrangian**: `\mathcal{L}=\sum_{t=0}^{\infty}\beta^t\Big\{\sum_{i=1}^N\alpha_iu_i(c_{it},1-n_{it})+\psi_t[F(k_t,n_t)-\tilde r_tk_t-\bar w_tn_t-g_t-S_t]+\theta_t[F(k_t,n_t)-c_t-k_{t+1}+(1-\delta)k_t-g_t]+\sum_i\mu_{i1t}[u_{ilt}-u_{ict}\bar w_t]+\sum_i\mu_{i2t}[u_{ict}-\beta u_{ict+1}(\tilde r_{t+1}+1-\delta)]+\sum_i\varepsilon_{it}[\bar w_tn_{it}+\tilde r_tk_{it}+S_{it}-c_{it}-k_{it+1}+(1-\delta)k_{it}]\Big\}` - Adds individual budget constraints (multipliers epsilon_it) because, unlike the representative-agent case, aggregate feasibility + government budget do not imply each individual bu
- **N-agent FOC w.r.t. k_{i,t+1}**: `\theta_t+\varepsilon_{it}=\beta\{\psi_{t+1}[F_{k,t+1}-\tilde r_{t+1}]+\theta_{t+1}[F_{k,t+1}+1-\delta]+\varepsilon_{i,t+1}(\tilde r_{t+1}+1-\delta)\}` - Same structure as the one-agent FOC, plus terms from each individual's budget constraint.

### Optimal Fiscal Policy with Commitment — Second Part: the primal approach to the Ramsey Pro

- **Consolidated intertemporal budget (illustrative, before iterating)**: `c_t+\frac{c_{t+1}}{R_t}+\frac{k_{t+2}}{R_t}+\frac{b_{t+2}}{R_tR_{t+1}}=b_t+\ldots` - Two consecutive sequential budget constraints combined, eliminating debt one period at a time.
- **Transversality conditions**: `\lim_{T\to\infty}\left(\prod_{i=0}^{T-1}R_i^{-1}\right)k_{T+1}=0;\qquad \lim_{T\to\infty}\left(\prod_{i=0}^{T-1}R_i^{-1}\right)\frac{b_{T+1}}{R_T}=0` - Standard no-Ponzi / optimality conditions ensuring the consolidated constraint is valid as T -> infinity.
- **Household present-value budget constraint (Arrow-Debreu form)**: `\sum_{t=0}^{\infty}q_tc_t=\sum_{t=0}^{\infty}q_t(1-\tau_{nt})w_tn_t+[(1-\tau_{k0})r_0+1-\delta]k_0+b_0,\qquad q_t=\prod_{i=0}^{t-1}R_i^{-1},\ q_0=1` - The household's entire lifetime budget expressed with Arrow-Debreu prices q_t, having imposed the No-Arbitrage Condition to eliminate k_{t+1} terms.
- **Step 1: household FOCs (present-value form)**: `\beta^tu_{ct}=\lambda q_t;\quad \beta^tu_{lt}=\lambda q_t(1-\tau_{nt})w_t\ \Rightarrow\ q_t=\beta^t\frac{u_{ct}}{u_{c0}};\quad (1-\tau_{nt})w_t=\frac{u_{lt}}{u_{ct}}` - Household FOCs w.r.t. c_t, n_t for the present-value problem with multiplier lambda; evaluated at t=0 with q_0=1 gives lambda=u_c0.
- **No-arbitrage in intertemporal prices**: `\frac{q_t}{q_{t+1}}=(1-\tau_{k,t+1})r_{t+1}+1-\delta` - Rewritten version of the original NAC R_t=(1-tau_kt+1)r_t+1+1-delta using Arrow-Debreu prices.
- **Firm FOCs**: `F_{kt}=r_t;\quad F_{nt}=w_t` - Competitive factor pricing.
- **Step 2: substituted intertemporal budget constraint**: `\sum_{t=0}^{\infty}\beta^t\frac{u_{ct}}{u_{c0}}c_t=\sum_{t=0}^{\infty}\beta^t\frac{u_{ct}}{u_{c0}}\frac{u_{lt}}{u_{ct}}n_t+\{[(1-\tau_{k0})F_{k0}+1-\delta]k_0+b_0\}=0` - Budget constraint with all prices/taxes replaced by allocation-based expressions.
- **Definition of A**: `A\equiv u_{c0}\{[(1-\tau_{k0})F_{k0}+1-\delta]k_0+b_0\}` - Collects all initial-condition terms (k_0, b_0, tau_k0) into a single constant.
- **Implementability Condition (IC)**: `\sum_{t=0}^{\infty}\beta^t(u_{ct}c_t-u_{lt}n_t)-A=0` - The single constraint (obtained by multiplying the Step-2 budget by u_c0) that the primal-approach Ramsey Problem must respect in place of individually tracking prices and taxes.
- **V(c,n,Phi) and Ramsey Lagrangian**: `V(c_t,n_t,\Phi)\equiv u(c_t,1-n_t)+\Phi(u_c(t)c_t-u_l(t)n_t);\qquad \mathcal{J}=\sum_{t=0}^{\infty}\beta^t\{V(c_t,n_t,\Phi)+\theta_t[F(k_t,n_t)-c_t-k_{t+1}+(1-\delta)k_t-g_t]\}-\Phi A` - Reformulates the primal Ramsey Problem: maximize J over {c_t,n_t,k_{t+1}} and Phi, given k_0, b_0, tau_k0.
- **First-order conditions of J**: `c_t:\ V_{ct}=\theta_t;\quad n_t:\ V_{nt}=-\theta_tF_{nt};\quad k_{t+1}:\ \theta_t=\beta\theta_{t+1}[F_{k,t+1}+1-\delta];\quad c_0:\ V_{c0}=\theta_0+\Phi A_c;\quad n_0:\ V_{n0}=-\theta_0F_{n0}+\Phi A_n` - System of FOCs (six equations) determining {c_0,n_0,{c_t,n_t,k_t}_{t=1}^{\infty},\Phi}. Capital FOC can be rewritten as V_{ct}=\beta V_{c,t+1}[F_{k,t+1}+1-\delta].
- **Step 4: steady-state tau_k derivation**: `1=\beta[F_k+(1-\delta)]\ \text{(FOC)};\qquad \frac{q_t}{q_{t+1}}=(1-\tau_{k,t+1})F_{k,t+1}+1-\delta\ \text{(NAC, steady state:}\ 1/\beta=(1-\tau_k)F_k+1-\delta)\ \Rightarrow\ \tau_k=0` - Comparing the steady-state capital FOC with the steady-state NAC pins down tau_k=0, matching Chamley's dual-approach result.
- **Correia (1996): Implementability Condition with extra factor**: `\sum_{t=0}^{\infty}\beta^t\{u_{ct}c_t-u_{lt}n_t-u_{ct}F_{zt}Z\}-A=0` - IC augmented with the revenue stream from the untaxed factor Z, sum_t q_t p_zt Z, converted to allocation terms via u_ct F_zt Z.
- **V(c,n,k,Phi) with untaxed factor**: `V(c_t,n_t,k_t,\Phi)=u(c_t,1-n_t)+\Phi(u_{ct}c_t-u_{lt}n_t-u_{ct}F_{zt}Z)` - Now depends explicitly on k_t (through F_zt=F_z(k_t,n_t,Z)), unlike the baseline V(c,n,Phi).
- **Lagrangian and capital FOC (Correia extension)**: `\mathcal{J}=\sum_{t=0}^{\infty}\beta^t\{V(c_t,n_t,k_t,\phi)+\theta_t[F(k_t,n_t)-c_t-k_{t+1}+(1-\delta)k_t-g_t]\}-\phi A;\qquad \theta_t=\beta V_{k,t+1}+\beta\theta_{t+1}[F_{k,t+1}+1-\delta]` - Because V now depends on k_t, an extra term V_{k,t+1} appears in the FOC for k_{t+1} relative to the baseline model.
- **Steady-state derivation of tau_k under incomplete taxation**: `\theta=\beta V_k+\beta\theta[F_k+(1-\delta)]\ \Rightarrow\ 1=\beta[F_k+(1-\delta)]+\frac{\beta}{\theta}V_k;\qquad \text{NAC steady state: } 1=\beta[(1-\tau_k)F_k+(1-\delta)];\qquad \Rightarrow\ \frac{\beta}{\theta}V_k=-\beta\tau_kF_k\ \Rightarrow\ \tau_k=-\frac{V_k}{\theta F_k}` - Combines the steady-state FOC and NAC to isolate tau_k as a function of V_k.
- **V_k and final tau_k formula**: `\frac{\partial V}{\partial k_t}=-\Phi u_{ct}F_{zkt}Z\quad\Rightarrow\quad \tau_k=\frac{\Phi u_cF_{zk}Z}{\theta F_k}` - The steady-state optimal capital tax under incomplete taxation, expressed in terms of the cross-partial F_zk, the untaxed factor endowment Z, and the multipliers Phi and theta.

### A Monetary Model — First Part: money demand via a shopping-time transaction technology, th

- **Household utility**: `\sum_{t=0}^{\infty}\beta^tu(c_t,l_t),\ 0<\beta<1,\quad u_c,u_l>0,\ u_{cc},u_{ll}<0,\ u_{cl}\ge0` - Lifetime utility over consumption and leisure in the endowment economy.
- **Time constraint**: `1=l_t+s_t` - One unit of time split between leisure and shopping time.
- **Shopping-time technology (example)**: `s_t=H\left(c_t,\frac{m_{t+1}}{p_t}\right);\qquad H=\frac{c_t}{m_{t+1}/p_t}\cdot\varepsilon,\ \varepsilon>0` - General transaction technology and a specific parametric example.
- **Household sequential budget constraint**: `c_t+\frac{b_{t+1}}{R_t}+\frac{m_{t+1}}{p_t}=y-\tau_t+b_t+\frac{m_t}{p_t}` - Consumption plus bond purchases plus new money holdings equals endowment net of lump-sum tax plus existing bond and money holdings.
- **No-arbitrage condition (bonds vs money)**: `1-\frac{p_t}{p_{t+1}}\cdot\frac{1}{R_t}\ge0` - Required for a bounded consumption set; if violated, households could achieve unbounded consumption by holding unbounded nominal balances.
- **Real return on money and Fisher equation**: `R_{mt}\equiv\frac{p_t}{p_{t+1}};\qquad 1+i_t\equiv\frac{R_t}{R_{mt}};\qquad 1-\frac{p_t}{p_{t+1}R_t}=1-\frac{R_{mt}}{R_t}=1-\frac{1}{1+i_t}=\frac{i_t}{1+i_t}\ge0` - Decomposes the nominal rate into real and inflation components; equivalent no-arbitrage condition requires i_t>=0.
- **Household Lagrangian**: `L=\sum_{t=0}^{\infty}\beta^t\Big\{u(c_t,l_t)+\lambda_t\Big(y-\tau_t+b_t+\frac{m_t}{p_t}-c_t-\frac{b_{t+1}}{R_t}-\frac{m_{t+1}}{p_t}\Big)+\mu_t\Big(1-l_t-H\big(c_t,\tfrac{m_{t+1}}{p_t}\big)\Big)\Big\}` - Household maximizes utility subject to budget constraint and the time/shopping constraint.
- **FOCs (1)-(4)**: `c_t:\ u_{ct}-\lambda_t-\mu_tH_{ct}=0\ (1);\quad l_t:\ u_{lt}-\mu_t=0\ (2);\quad b_{t+1}:\ -\lambda_t\tfrac{1}{R_t}+\beta\lambda_{t+1}=0\ (3);\quad m_{t+1}:\ -\lambda_t\tfrac{1}{p_t}-\mu_tH_{m/pt}\tfrac{1}{p_t}+\beta\lambda_{t+1}\tfrac{1}{p_{t+1}}=0\ (4)` - Interior-solution first-order conditions.
- **Shadow price of wealth**: `\lambda_t=u_{ct}-u_{lt}H_{ct}\ (5)` - Marginal utility of consumption net of the marginal disutility of the extra shopping time that consumption requires.
- **Real interest rate**: `R_t=\frac{1}{\beta}\frac{\lambda_t}{\lambda_{t+1}}=\frac{1}{\beta}\frac{u_{ct}-u_{lt}H_{ct}}{u_{ct+1}-u_{lt+1}H_{ct+1}}\ (6)` - Depends on the discount factor and shopping-adjusted marginal utilities.
- **Cost-of-holding-money condition**: `\frac{R_t-R_{mt}}{R_t}\lambda_t=-\mu_tH_{m/p}(t)\ (7);\qquad \left(1-\frac{R_{mt}}{R_t}\right)\left[\frac{u_{ct}}{u_{lt}}-H_c(t)\right]+H_{m/pt}=0\ (8)` - The opportunity cost of holding money (R_t-R_mt) equals the marginal benefit of real balances in reducing shopping time.
- **Implicit money demand function**: `\frac{m_{t+1}}{p_t}=F(c_t,R_{mt}/R_t)\ (9)` - Real balances demanded increase in both consumption and R_mt/R_t (via the Implicit Function Theorem); since R_mt/R_t=1/(1+i_t), real balances fall with the nominal interest rate.
- **Government sequential budget constraint**: `g_t=\tau_t+\frac{B_{t+1}}{R_t}-B_t+\frac{M_{t+1}-M_t}{p_t}` - Consolidated fiscal (tau_t,B_t) and monetary (M_t) branches financing government purchases; B_0, M_0>0 given, {g_t,\tau_t} exogenous.
- **Stationary-equilibrium relations**: `p_t/p_{t+1}=R_m,\ \forall t;\quad R_t=R=1/\beta;\quad c_t=c=y-g;\quad m_{t+1}/p_t=F(c,R_m/R)\equiv f(R_m),\ f'(R_m)\ge0` - Definition and implications of a stationary equilibrium.
- **Long-run government budget (Laffer-curve equation)**: `g-\tau+\frac{B(R-1)}{R}=f(R_m)(1-R_m),\quad \forall t\ge1` - The gross-of-interest deficit g-\tau+B(R-1)/R must equal seigniorage revenue f(R_m)(1-R_m); g-\tau is the primary deficit, f(R_m)(1-R_m) is a concave ('Laffer') function of R_m.
- **Short-run government budget (initial price level)**: `\frac{M_0}{p_0}=f(R_m)-(g+B_0-\tau_0)+\frac{B}{R}` - Given R_m from the long run and M_0 exogenous, this pins down p_0.
- **Example functional forms**: `u(c_t,l_t)=\frac{c_t^{1-\delta}}{1-\delta}+\frac{l_t^{1-\alpha}}{1-\alpha};\qquad H(c_t,m_{t+1}/p_t)=\frac{c_t}{1+m_{t+1}/p_t}` - CRRA-type utility over consumption and leisure and a specific shopping-time function used for the graphical worked example.

### Handwritten student lecture notes, Topic 3.1 (October 2020): the seigniorage Laffer curve,

- **Long-run government budget identity**: `g-\tau+\frac{B(R-1)}{R}=f(R_m)(1-R_m)` - Same long-run equation as in the slide deck (File 3), re-derived graphically here; region '>0' above the horizontal axis corresponds to a deficit (assumption), '<0' below correspon
- **Short-run (t=0) government budget**: `\frac{M_0}{p_0}=f(R_m)-(g+B_0-\tau_0)+\frac{B}{R}` - Upward-sloping in R_m (given f'(R_m)>=0); example assumes -(g+B_0-\tau_0)+B/R>0 so that M_0/p_0>0 is guaranteed (consistent with M_0>0, p_0>=0).
- **Quantity-theory proportionality**: `\Delta M_0 \Rightarrow \text{same } \%\Delta \text{ in } p_0` - A given percentage change in the initial money stock produces an equal percentage change in the initial price level, holding R_m fixed (R_m determined independently in the long-run
- **Friedman-rule implementation condition**: `R_m=\frac{1}{\beta};\qquad \text{need } g-\tau+\frac{B(R-1)}{R}<0` - To hit the Friedman-optimal R_m=1/beta on the seigniorage Laffer curve (where seigniorage is negative, i.e., beyond the curve's zero-crossing at R_m=1), the government budget line 
- **Inflation rate in terms of R_m**: `R_m=\frac{p_t}{p_{t+1}};\qquad \text{inflation rate}=\frac{1}{R_m}-1` - Relates the model's real-return-on-money object R_m to the conventional inflation rate.

### Monetary economics — shopping-time money-in-the-utility model (Topic 3.1 Second Part: mone

- **Quantitative theory of money**: `P_t = \frac{v_t M_t}{Y_t}` - price level as a function of velocity, money supply and real expenditure
- **Fiscal prerequisites of zero inflation (govt. budget constraint, t>=1)**: `g - \tau + \frac{B(R-1)}{R} = f(R_m)(1-R_m)` - government budget constraint relating primary deficit, real debt service, and seigniorage revenue f(R_m)(1-R_m)
- **Present-value debt condition for pi=0**: `B = \frac{R}{R-1}(\tau-g) = \sum_{t=0}^{\infty} R^{-t}(\tau-g)` - real government debt equals present value of primary surpluses when R_m=1
- **Money's rate of return vs nominal rate**: `\frac{R_m}{R} = \frac{1}{1+i}` - relation linking the real return on money R_m, the real interest rate R and the nominal interest rate i
- **Fisher equation and Friedman rule**: `1+i=(1+r)(1+\pi) \;\Longrightarrow\; \pi=-r \text{ when } i=0` - under the Friedman rule (i=0), the optimal inflation rate equals minus the real interest rate (deflation)
- **Friedman-rule value of R_m**: `R_m=\frac{1}{\beta} > 1` - the gross return on money that implements the Friedman rule
- **Government surplus condition to attain any R_m in (1,1/beta)**: `g-\tau+\frac{B(R-1)}{R} < 0` - a sufficiently large gross-of-interest fiscal surplus is required (low spending, low debt, high taxes)
- **Shopping technology homogeneity**: `s_t=H(c_t,\widehat m_{t+1})=c_t^{\nu} H\!\left(1,\frac{\widehat m_{t+1}}{c_t}\right) \ \forall c_t>0` - shopping time as a homogeneous-of-degree-nu function of consumption and real balances
- **Euler's theorem applied to H**: `\nu H(c,\widehat m) = H_c c + H_{\widehat m}\widehat m` - decomposition of H implied by its homogeneity degree
- **Household sequential budget constraint**: `c_t+\frac{b_{t+1}}{R_t}+\frac{m_{t+1}}{p_t}=(1-\tau_t)(1-l_t-s_t)+b_t+\frac{m_t}{p_t}` - period budget constraint with real wage normalized to 1 and labor tax tau_t
- **Household present-value budget constraint (eq. 1)**: `\sum_{t=0}^{\infty} q_t\left(c_t+\frac{i_t}{1+i_t}\widehat m_{t+1}\right)=\sum_{t=0}^{\infty} q_t(1-\tau_t)(1-l_t-s_t)+b_0+\widehat m_0` - lifetime budget constraint after substituting s_t=H(c_t,\widehat m_{t+1})
- **FOCs of household problem (2)-(4)**: `(2)\ \beta^t u_{c_t}-\lambda q_t[(1-\tau_t)H_{c_t}+1]=0;\quad (3)\ \beta^t u_{l_t}-\lambda q_t(1-\tau_t)=0;\quad (4)\ -\lambda q_t\left[(1-\tau_t)H_{\widehat m_{t+1}}+\frac{i_t}{1+i_t}\right]=0` - first-order conditions with respect to c_t, l_t, m-hat_{t+1}
- **Consumption-leisure equation**: `\frac{u_{l_t}}{1-\tau_t}=u_{c_t}-u_{l_t}H_{c_t}` - intratemporal optimality condition combining (2) and (3)
- **Implementability Condition**: `\sum_{t=0}^{\infty}\beta^t\Big[(u_{c_t}-u_{l_t}H_{c_t})c_t-u_{l_t}H_{\widehat m_{t+1}}\widehat m_{t+1}-u_{l_t}\big(1-l_t-H(c_t,\widehat m_{t+1})\big)\Big]=0` - single intertemporal constraint summarizing all household optimality + budget conditions, price/tax-free
- **Ramsey problem**: `\max \sum_{t=0}^{\infty}\beta^t u(c_t,l_t) \text{ s.t. Implementability Condition (mult. }\phi\text{) and } 1-l_t-H(c_t,\widehat m_{t+1})=c_t+g_t \text{ (mult. }\theta_t\text{)}` - planner's problem choosing allocations to maximize utility subject to implementability and feasibility
- **Feasibility / technology**: `y_t=c_t+g_t,\qquad y_t=n_t` - output equals consumption plus government spending; output equals labor input (linear technology, no capital)
- **Time constraint**: `1=l_t+s_t+n_t` - time is allocated between leisure, shopping time and labor

### Exogenous growth in the (deterministic) neoclassical growth model with distortionary taxes

- **Population and technology growth**: `N_t=N_0(1+g_n)^t,\ N_0=1; \qquad Y_t=F(K_t,Z_tL_t),\ Z_t=(1+g_z)^t` - exogenous population growth rate g_n and labor-augmenting technology growth rate g_z
- **Per-capita and detrended variable definitions**: `v_t=\frac{V_t}{N_t}; \qquad \widehat v_t=\frac{V_t}{N_t(1+g_z)^t}` - per-capita variable v_t and detrended variable v-hat_t for any aggregate V_t
- **Household problem (levels)**: `\max_{\{c_t,x_t,l_t\}} \sum_{t=0}^{\infty}\beta^t[U(c_t,1-l_t)]N_t \ \text{s.t.}\ (1+\tau_t^c)c_t+(1+\tau_t^x)x_t=(1-\tau_t^k)r_tk_t+(1-\tau_t^l)w_tl_t+\tau_t^k\delta k_t+tr_t,\quad N_{t+1}k_{t+1}=[(1-\delta)k_t+x_t]N_t,\quad c_t,x_t\ge0` - household maximizes discounted utility over consumption, investment and leisure subject to a budget constraint with consumption/investment/capital/labor taxes and transfers, and pe
- **Capital accumulation rewritten**: `K_{t+1}=(1-\delta)K_t+X_t \;\Longrightarrow\; (1+g_n)k_{t+1}=(1-\delta)k_t+x_t` - aggregate capital law of motion converted to per-capita form using N_{t+1}/N_t=1+g_n
- **Firm's problem**: `\max_{K_t,L_t} F(K_t,Z_tL_t)-w_tL_t-r_tK_t` - representative firm chooses capital and labor to maximize profit given effective-labor-augmenting technology
- **Government budget constraint**: `G_t+N_ttr_t=\tau_t^k(r_t-\delta)N_tk_t+\tau_t^lw_tl_tN_t+\tau_t^cN_tc_t+\tau_t^xN_tx_t` - government spending plus transfers financed by capital, labor, consumption and investment tax revenue (G_t exogenous)
- **Feasibility conditions**: `N_t(c_t+x_t)+G_t=F(K_t,Z_tL_t); \qquad N_tk_t=K_t; \qquad N_tl_t=L_t` - aggregate resource constraint and market-clearing for capital and labor
- **Utility functional form (KPR-type)**: `U(c_t,1-l_t)=\frac{c_t^{1-\sigma}}{1-\sigma}\cdot v(l_t)` - multiplicatively separable utility, consumption CRRA times a decreasing function v of labor
- **Detrended intertemporal utility**: `c_t=(1+g_z)^t\widehat c_t \;\Rightarrow\; \sum_{t=0}^{\infty}\big(\beta(1+g_n)(1+g_z)^{1-\sigma}\big)^t \frac{\widehat c_t^{1-\sigma}}{1-\sigma}v(l_t)` - lifetime utility rewritten in terms of the stationary variable c-hat_t and a modified discount factor
- **Modified discount factor**: `\widetilde\beta=\beta(1+g_n)(1+g_z)^{1-\sigma}, \quad \text{need } \widetilde\beta<1` - combines time discounting with population/technology growth
- **Detrended household budget constraint**: `(1+\tau_t^c)\widehat c_t+(1+\tau_t^x)\widehat x_t=(1-\tau_t^k)r_t\widehat k_t+(1-\tau_t^l)\widehat w_tl_t+\tau_t^k\delta\widehat k_t+\widehat{tr}_t` - budget constraint with all quantity variables replaced by their detrended counterparts
- **Detrended capital accumulation**: `(1+g_z)(1+g_n)\widehat k_{t+1}=(1-\delta)\widehat k_t+\widehat x_t` - law of motion for detrended capital
- **Intensive-form production function**: `F\!\left(\frac{K_t}{N_tZ_t},\frac{Z_tL_t}{N_tZ_t}\right)=\frac{F(K_t,Z_tL_t)}{N_tZ_t}\equiv f(\widehat k_t,l_t)` - production function per unit of effective labor, using homogeneity of degree 1 of F
- **Detrended feasibility**: `\widehat y_t=\widehat c_t+\widehat x_t+\widehat g_t` - detrended resource constraint (with g_t growing at rate g_z in the long run so g-hat_t is stationary)
- **Lagrangian (household)**: `\mathcal L=\sum_{t=0}^{\infty}\Big\{\widetilde\beta^t U(\widehat c_t,1-l_t)+\lambda_t[(1-\tau_t^k)r_t\widehat k_t+(1-\tau_t^l)\widehat w_tl_t+\tau_t^k\delta\widehat k_t+\widehat{tr}_t-(1+\tau_t^c)\widehat c_t-(1+\tau_t^x)\widehat x_t]+\mu_t[(1-\delta)\widehat k_t+\widehat x_t-(1+g_z)(1+g_n)\widehat k_{t+1}]\Big\}` - Lagrangian for the detrended household optimization problem
- **Consumption-leisure condition**: `\frac{U_2(\widehat c_t,1-l_t)}{U_1(\widehat c_t,1-l_t)}=\frac{1-\tau_t^l}{1+\tau_t^c}\widehat w_t` - static intratemporal labor-supply/leisure condition, wedge driven by labor and consumption taxes
- **Detrended Euler equation**: `\frac{1+\tau_t^x}{1+\tau_t^c}U_1(\widehat c_t,1-l_t)=\widehat\beta\Big\{\frac{U_1(\widehat c_{t+1},1-l_{t+1})}{1+\tau_{t+1}^c}\big[(1-\tau_{t+1}^k)r_{t+1}+\delta\tau_{t+1}^k+(1-\delta)(1+\tau_{t+1}^x)\big]\Big\}, \quad \widehat\beta=\frac{\widetilde\beta}{(1+g_z)(1+g_n)}=\beta(1+g_z)^{-\sigma}` - intertemporal optimality condition in detrended variables, with an extra step relative to the standard Euler equation because of investment taxes
- **Firm FOCs (detrended)**: `r_t=f_1(\widehat k_t,l_t); \qquad \widehat w_t=f_2(\widehat k_t,l_t)` - factor prices equal marginal products of the intensive-form production function

### Computational/solution methods for DSGE models — log-linearization (first-order Taylor app

- **Categorization of solution methods**: `Table: {Deterministic-Linear: Blanchard-Kahn, Uhlig's Undetermined Coefficients, Uribe & Schmitt-Grohe; Stochastic-Linear: same as Deterministic-Linear; Deterministic-Nonlinear: system-of-equations solver, Shooting, Dynamic Programming; Stochastic-Nonlinear: Dynamic Programming (slow), McGrattan's Weighted Residuals}` - classification of solution methods by model class (linear/nonlinear, deterministic/stochastic)
- **Household problem**: `\max E_0\sum_{t=0}^{\infty}\beta^t[\log(C_t)-AN_t]` - expected discounted utility, log consumption minus linear disutility of labor (indivisible labor)
- **Feasibility / budget constraint**: `C_t+K_t=Y_t+(1-\delta)K_{t-1}` - resource constraint of the closed-economy RBC model
- **Production function**: `Y_t=Z_tK_{t-1}^{\rho}N_t^{1-\rho}` - Cobb-Douglas production with capital share rho
- **TFP process**: `\log(Z_t)=(1-\psi)\log(\bar Z)+\psi\log(Z_{t-1})+\varepsilon_t,\ \varepsilon\sim(0,\sigma_\varepsilon^2)` - AR(1) process in logs for total factor productivity
- **System of equations**: `\frac{1}{C_t}=\Lambda_t;\quad A=\Lambda_t(1-\rho)\frac{Y_t}{N_t};\quad R_t=\rho\frac{Y_t}{K_{t-1}}+(1-\delta);\quad Y_t=Z_tK_{t-1}^{\rho}N_t^{1-\rho};\quad C_t+K_t=Y_t+(1-\delta)K_{t-1};\quad \Lambda_t=\beta E_t[\Lambda_{t+1}R_{t+1}];\quad \log(Z_t)=(1-\psi)\log(\bar Z)+\psi\log(Z_{t-1})+\varepsilon_t` - complete nonlinear equilibrium system (7 equations) prior to log-linearization
- **Log-deviation definition**: `x_t\equiv\log(X_t)-\log(\bar X), \qquad X_t=\bar X e^{x_t}` - log-deviation of a variable from its steady-state value
- **First-order Taylor approximation**: `f(x)\approx f(x_0)+f'(x_0)(x-x_0)` - generic linearization formula, applied around steady state x_0
- **Steady-state simplifications**: `1=\beta\bar R; \qquad \bar R=\rho\frac{\bar Y}{\bar K}+(1-\delta)` - steady-state relations used to simplify log-linearized coefficients
- **Log-linearized FOC for consumption/multiplier**: `c_t=-\lambda_t` - from 0=1/C_t-\Lambda_t linearized
- **Log-linearized labor condition**: `n_t=\lambda_t+y_t` - from A=\Lambda_t(1-\rho)Y_t/N_t linearized
- **Log-linearized capital-return definition**: `\bar R r_t=\rho\frac{\bar Y}{\bar K}(y_t-k_{t-1})` - linearized rental-rate definition
- **Log-linearized production function**: `y_t=z_t+\rho k_{t-1}+(1-\rho)n_t` - linearized Cobb-Douglas production function
- **Log-linearized feasibility**: `y_t=\frac{\bar C}{\bar Y}c_t+\frac{\bar K}{\bar Y}\big(k_t-(1-\delta)k_{t-1}\big)` - linearized resource constraint
- **Log-linearized Euler equation**: `\lambda_t=E_t(\lambda_{t+1}+r_{t+1})` - linearized intertemporal optimality condition
- **AR(1) TFP (kept in levels)**: `z_t=\psi z_{t-1}+\varepsilon_t` - the technology process is already log-linear, no Taylor expansion needed

### Uhlig's Method of Undetermined Coefficients for solving linear (log-linearized) rational-e

- **General Uhlig system — static block**: `0=Ax_t+Bx_{t-1}+Cy_t+Dz_t` - equations not involving expectations
- **General Uhlig system — dynamic/expectational block**: `0=E_t\big[Fx_{t+1}+Gx_t+Hx_{t-1}+Jy_{t+1}+Ky_t+Lz_{t+1}+Mz_t\big]` - equations involving conditional expectations of future variables
- **Exogenous process**: `z_{t+1}=Nz_t+\varepsilon_{t+1}, \qquad 0=E_t[\varepsilon_{t+1}]` - law of motion of exogenous state(s)
- **Policy functions (general)**: `x_t=Px_{t-1}+Qz_t; \qquad y_t=Rx_{t-1}+Sz_t` - endogenous state and other endogenous variables as linear functions of lagged states and current shocks
- **Reduced two-variable relation (eq. 8)**: `y_t=\frac{1}{\rho}z_t+k_{t-1}+\frac{1-\rho}{\rho}\lambda_t` - output expressed in terms of state k_{t-1}, shock z_t, and multiplier lambda_t (after eliminating n_t via the labor condition)
- **Coefficients alpha_1..alpha_6**: `\alpha_1=\frac{\bar Y}{\bar K}+(1-\delta);\ \alpha_2=\frac{\bar C}{\bar K}+\frac{1-\rho}{\rho}\frac{\bar Y}{\bar K};\ \alpha_3=\frac{\bar Y}{\rho\bar K};\ \alpha_4=0;\ \alpha_5=1+(1-\rho)\frac{\bar Y}{\bar R\bar K};\ \alpha_6=\frac{\bar Y}{\bar R\bar K}` - steady-state ratios combined into shorthand coefficients for the reduced system
- **Reduced feasibility equation (eq. 9)**: `0=-k_t+\alpha_1k_{t-1}+\alpha_2\lambda_t+\alpha_3z_t` - capital law of motion in terms of lagged capital, multiplier and shock
- **Reduced Euler equation (eq. 10)**: `0=E_t\big[-\lambda_t+\alpha_4k_t+\alpha_5\lambda_{t+1}+\alpha_6z_{t+1}\big]` - Euler equation in terms of the multiplier and shock only (alpha_4=0 in this example)
- **Guessed linear policy functions**: `k_t=\eta_{KK}k_{t-1}+\eta_{Kz}z_t; \qquad \lambda_t=\eta_{\lambda K}k_{t-1}+\eta_{\lambda z}z_t` - conjectured form of the solution, linear in the state variables
- **Coefficient-matching equations on k_{t-1}**: `0=-\eta_{KK}+\alpha_1+\alpha_2\eta_{\lambda K}; \qquad 0=-\eta_{\lambda K}+\alpha_4\eta_{KK}+\alpha_5\eta_{\lambda K}\eta_{KK}` - conditions obtained because eqs. (9)-(10) must hold for all k_{t-1}
- **Quadratic equation for eta_KK**: `0=\eta_{KK}^2-\left(\alpha_1-\frac{\alpha_2}{\alpha_5}\alpha_4+\frac{1}{\alpha_5}\right)\eta_{KK}+\frac{\alpha_1}{\alpha_5}` - characteristic equation whose roots are the candidate values of eta_KK
- **Closed-form solution for eta_KK**: `\eta_{KK}=\frac12\left[\left(\alpha_1-\frac{\alpha_2}{\alpha_5}\alpha_4+\frac1{\alpha_5}\right)\pm\sqrt{\left(\alpha_1-\frac{\alpha_2}{\alpha_5}\alpha_4+\frac1{\alpha_5}\right)^2-4\frac{\alpha_1}{\alpha_5}}\right]` - quadratic formula applied to the characteristic equation
- **z_t-coefficient equations**: `0=-\eta_{Kz}+\alpha_2\eta_{\lambda z}+\alpha_3; \qquad 0=-\eta_{\lambda z}+\alpha_4\eta_{Kz}+\alpha_5\eta_{\lambda K}\eta_{Kz}+(\alpha_5\eta_{\lambda z}+\alpha_6)\psi` - conditions obtained because eqs. (9)-(10) must hold for all z_t
- **Closed-form solutions for eta_lambdaz, eta_Kz**: `\eta_{\lambda z}=\frac{\alpha_4\alpha_3+\alpha_5\eta_{\lambda K}\alpha_3+\alpha_6\psi}{1-\alpha_4\alpha_2-\alpha_5\eta_{\lambda K}\alpha_2-\alpha_5\psi}; \qquad \eta_{Kz}=\alpha_2\eta_{\lambda z}+\alpha_3` - completes the policy function coefficients on the exogenous shock

### Topic 5 (handwritten lecture notes, Prof. Felipe Meza): 'Solving the model by hand' -- the

- **Equation (9) (Presentation p.12)**: `0 = -k_t + \alpha_1 k_{t-1} + \alpha_2 \lambda_t + \alpha_3 z_t` - The deterministic (intratemporal + resource) block reduced to one equation relating capital today, capital yesterday, the multiplier and TFP.
- **Equation (10) (Presentation p.12)**: `0 = E_t\left[-\lambda_t + \alpha_4 k_t + \alpha_5 \lambda_{t+1} + \alpha_6 z_{t+1}\right]` - The expectational (Euler) block.
- **Conjectured policy function for capital (a)**: `k_t = \eta_{kk} k_{t-1} + \eta_{kz} z_t` - Capital is a linear function of the two states.
- **Conjectured policy function for the multiplier (b)**: `\lambda_t = \eta_{\lambda k} k_{t-1} + \eta_{\lambda z} z_t` - The costate/multiplier is a linear function of the same two states.
- **Equation (9) after substitution and factoring**: `0 = \left(-\eta_{kk} + \alpha_1 + \alpha_2 \eta_{\lambda k}\right) k_{t-1} + \left(-\eta_{kz} + \alpha_2 \eta_{\lambda z} + \alpha_3\right) z_t` - Both bracketed coefficients must be zero.
- **Equation (10) after substitution and factoring**: `0 = k_{t-1}\left(-\eta_{\lambda k} + \alpha_4 \eta_{kk} + \alpha_5 \eta_{\lambda k}\eta_{kk}\right) + z_t\left(-\eta_{\lambda z} + \alpha_4 \eta_{kz} + \alpha_5 \eta_{\lambda z}\psi + \alpha_6 \psi + \alpha_5 \eta_{\lambda k}\eta_{kz}\right)` - Same logic; note the product terms alpha_5 eta_lambda_k eta_kk and alpha_5 eta_lambda_k eta_kz arising from substituting k_t inside lambda_{t+1}.
- **Expectation of the AR(1)**: `E_t\left(\psi z_t + \varepsilon_{t+1}\right) = \psi z_t` - Removes z_{t+1} and epsilon_{t+1} from the expectational equation.
- **Restriction on k_{t-1} from (9)**: `-\eta_{kk} + \alpha_1 + \alpha_2 \eta_{\lambda k} = 0 \;\Longrightarrow\; \eta_{\lambda k} = -\frac{\alpha_1}{\alpha_2} + \frac{\eta_{kk}}{\alpha_2}` - Expresses the multiplier's loading on capital in terms of eta_kk.
- **Restriction on k_{t-1} from (10)**: `-\eta_{\lambda k} + \alpha_4 \eta_{kk} + \alpha_5 \eta_{\lambda k}\eta_{kk} = 0` - The second equation in the two unknowns (eta_kk, eta_lambda_k).
- **Intermediate substitution**: `+\frac{\alpha_1}{\alpha_2} - \frac{\eta_{kk}}{\alpha_2} + \alpha_4\eta_{kk} - \alpha_5\frac{\alpha_1}{\alpha_2}\eta_{kk} + \alpha_5\frac{\eta_{kk}}{\alpha_2}\eta_{kk} = 0` - After plugging eta_lambda_k out; then multiply every term by alpha_2/alpha_5.
- **After multiplying by alpha_2/alpha_5**: `\frac{\alpha_1}{\alpha_5} - \eta_{kk}\frac{1}{\alpha_5} + \eta_{kk}\alpha_4\frac{\alpha_2}{\alpha_5} - \alpha_1 \eta_{kk} + \eta_{kk}^{2} = 0` - Same equation normalized so that the coefficient on eta_kk^2 is 1.
- **THE QUADRATIC IN eta_kk (boxed in the notes)**: `0 = \eta_{kk}^{2} - \eta_{kk}\left(\alpha_1 - \frac{\alpha_2}{\alpha_5}\alpha_4 + \frac{1}{\alpha_5}\right) + \frac{\alpha_1}{\alpha_5}` - The central result of the note: a monic scalar quadratic whose roots are the candidate autoregressive coefficients of capital.
- **Recovering eta_lambda_k**: `\eta_{\lambda k} = -\frac{\alpha_1}{\alpha_2} + \frac{\eta_{kk}}{\alpha_2}` - Once the stable eta_kk is chosen, eta_lambda_k follows directly.
- **Restriction on z_t from (9)**: `-\eta_{kz} + \alpha_2 \eta_{\lambda z} + \alpha_3 = 0` - First of the two linear equations in the z-loadings.
- **Restriction on z_t from (10)**: `-\eta_{\lambda z} + \alpha_4 \eta_{kz} + \alpha_5 \eta_{\lambda k}\eta_{kz} + \left(\alpha_5 \eta_{\lambda z} + \alpha_6\right)\psi = 0` - Second linear equation; eta_lambda_k is already known so the only unknowns are eta_kz and eta_lambda_z.

### Computing Program (Proyecto Computacional), Dynamic Macroeconomics II, ITAM (solution by C

- **Planner's Lagrangian**: `\mathcal{L} = E_t \sum_{j=0}^{\infty} \beta^{j}\left\{ \ln\!\left(C_{t+j} - \tau \frac{N_{t+j}^{v}}{v}\right) + \lambda_{t+j}\left[ Z_{t+j}K_{t+j}^{\alpha}N_{t+j}^{1-\alpha} + K_{t+j}(1-\delta) - C_{t+j} - K_{t+j+1} \right]\right\}` - Planner maximizes expected discounted GHH utility subject to the period resource constraint; lambda_{t+j} is the multiplier on feasibility.
- **FOC for consumption**: `\frac{1}{C_t - \tau \frac{N_t^{v}}{v}} = \lambda_t` - Marginal utility of the GHH composite equals the shadow value of resources.
- **FOC for labor**: `\frac{\tau N_t^{v-1}}{C_t - \tau \frac{N_t^{v}}{v}} = \lambda_t (1-\alpha) Z_t \left(\frac{K_t}{N_t}\right)^{\alpha}` - Marginal disutility of an extra hour (in utils) equals the marginal product of labor times the shadow value of resources.
- **FOC for capital (Euler in multiplier form)**: `E_t\left[\beta \lambda_{t+1}\left( \alpha Z_{t+1}\left(\frac{N_{t+1}}{K_{t+1}}\right)^{1-\alpha} + (1-\delta)\right) - \lambda_t\right] = 0` - Intertemporal optimality: giving up one unit of consumption today buys the gross return on capital tomorrow.
- **FOC for the multiplier (feasibility)**: `Z_t K_t^{\alpha} N_t^{1-\alpha} + K_t(1-\delta) - C_t - K_{t+1} = 0` - Resource constraint holds with equality.
- **Wage (marginal product of labor)**: `W_t = (1-\alpha) Z_t \left(\frac{K_t}{N_t}\right)^{\alpha} = (1-\alpha)\frac{Y_t}{N_t}` - Competitive real wage = labor share times average product of labor.
- **Gross return to capital**: `R_{t+1} = \alpha Z_t \left(\frac{N_t}{K_t}\right)^{1-\alpha} + (1-\delta) = \alpha \frac{Y_t}{K_t} + (1-\delta)` - Rental rate plus undepreciated capital.
- **Ratio of multipliers**: `\frac{\lambda_{t+1}}{\lambda_t} = \frac{C_t - \tau \frac{N_t^{v}}{v}}{C_{t+1} - \tau \frac{N_{t+1}^{v}}{v}}` - Stochastic discount factor written in terms of the GHH composite.
- **Leisure-consumption (intratemporal) equation**: `\tau N_t^{v} = (1-\alpha) Y_t` - Labor supply = labor demand. Obtained by multiplying tau N^{v-1} = W_t by N_t and using W_t N_t = (1-alpha)Y_t. Note that C_t has dropped out: GHH kills the wealth effect.
- **Capital accumulation**: `I_t = K_{t+1} - (1-\delta)K_t` - Law of motion of capital.
- **Technology**: `Y_t = Z_t K_t^{\alpha} N_t^{1-\alpha}` - Cobb-Douglas production with capital share alpha and TFP Z_t.
- **Feasibility**: `Y_t = C_t + I_t` - Closed economy, no government: output is consumed or invested.
- **Euler equation**: `\frac{1}{C_t - \tau \frac{N_t^{v}}{v}} = \beta E_t\left[\frac{1}{C_{t+1} - \tau \frac{N_{t+1}^{v}}{v}}\left(\alpha \frac{Y_{t+1}}{K_{t+1}} + (1-\delta)\right)\right]` - Intertemporal condition in terms of the GHH composite and the ratio Y/K.
- **TFP process**: `\ln Z_t = (1-\psi)\ln \overline{Z} + \psi \ln Z_{t-1} + \epsilon_t,\quad \epsilon_t \overset{iid}{\sim} D(0,\sigma^2)` - AR(1) in logs for total factor productivity with persistence psi and long-run mean Zbar.
- **Steady state system**: `\tau N^{v} = (1-\alpha) Y;\quad I = \delta K;\quad Y = Z K^{\alpha} N^{1-\alpha};\quad Y = C + I;\quad \frac{1}{\beta} = \alpha\frac{Y}{K} + (1-\delta)` - Five equations for the five steady-state unknowns (given parameters and a normalization).
- **Steady-state capital-output ratio**: `\frac{Y}{K} = \frac{\frac{1}{\beta} - 1 + \delta}{\alpha}\quad\Longleftrightarrow\quad \alpha\beta\frac{Y}{K} = 1 - \beta(1-\delta)` - Implied by the steady-state Euler equation.
- **Steady-state great ratios**: `\frac{I}{Y} = \delta\frac{K}{Y} = \frac{\delta\alpha}{\frac{1}{\beta}-1+\delta},\qquad \frac{C}{Y} = 1 - \frac{I}{Y}` - Investment and consumption shares of output at the steady state.
- **Loglinear leisure-consumption**: `(1-\alpha) Y\, y_t = \tau v N^{v} n_t \quad\text{(from } 0 = (1-\alpha)Y e^{y_t} - \tau (N e^{n_t})^{v})` - Percent change in output must equal v times the percent change in hours scaled by the steady-state weights; using tau N^v = (1-alpha)Y this is simply y_t = v n_t.
- **Loglinear capital accumulation**: `0 = K e^{k_{t+1}} - (1-\delta) K e^{k_t} - I e^{i_t} \;\Rightarrow\; 0 \approx K k_{t+1} - (1-\delta)K k_t - \delta K i_t \;\Rightarrow\; k_{t+1} = (1-\delta)k_t + \delta i_t` - Log-deviation law of motion; note I = delta K was used to cancel levels.
- **Loglinear technology**: `0 = Y e^{y_t} - Z e^{z_t}(K e^{k_t})^{\alpha}(N e^{n_t})^{1-\alpha} \;\Rightarrow\; y_t = z_t + \alpha k_t + (1-\alpha) n_t` - Exact in logs for Cobb-Douglas (the approximation is not even needed).
- **Loglinear feasibility**: `0 = Y e^{y_t} - C e^{c_t} - I e^{i_t} \;\Rightarrow\; y_t = \frac{C}{Y}c_t + \frac{I}{Y}i_t` - Output deviation is the share-weighted average of consumption and investment deviations.
- **Loglinear Euler (project's printed version)**: `\frac{\tau N^{v} n_t - C c_t}{C - \tau\frac{N^{v}}{v}} = E_t\left[\frac{\tau N^{v} n_{t+1} - C c_{t+1}}{C - \tau\frac{N^{v}}{v}}\right] + \alpha\frac{Y}{K}\beta E_t\left[y_{t+1} - k_{t+1}\right]` - Loglinearized intertemporal condition. Intermediate step: 0 approx E_t[tau N^v n_{t+1} - C c_{t+1}] + alpha (Y/K)(C - tau N^v/v) beta E_t[y_{t+1}-k_{t+1}] - (tau N^v n_t - C c_t).
- **Loglinear Euler (student's simplified version, page 5 '(*)')**: `\frac{1}{C - \tau\frac{N^{v}}{v}}\, E_t\!\left[C(c_{t+1}-c_t) - \tau N^{v}(n_{t+1}-n_t)\right] = \left(1 - \beta(1-\delta)\right) E_t\!\left[y_{t+1} - k_{t+1}\right]` - Same equation after using the steady-state relation alpha Y/K = 1/beta - (1-delta), so that beta alpha Y/K = 1 - beta(1-delta). This is the cleanest form to program.
- **Loglinear TFP**: `z_{t+1} = \psi z_t + \epsilon_{t+1}` - AR(1) in log-deviations, so N (Uhlig) = psi.
- **Uhlig's system**: `0 = A x_t + B x_{t-1} + C y_t + D z_t;\;\; 0 = E_t[F x_{t+1} + G x_t + H x_{t-1} + J y_{t+1} + K y_t + L z_{t+1} + M z_t];\;\; z_{t+1} = N z_t + \varepsilon_{t+1};\;\; 0 = E_t[\varepsilon_{t+1}]` - General canonical form of a loglinearized DSGE model.
- **Uhlig vectors in this model**: `x_t = [k_{t+1}]_{1\times 1},\quad y_t = [c_t,\, y_t,\, n_t,\, i_t]_{4\times 1},\quad z_t = [z_t]_{1\times 1}` - One endogenous state (next-period capital), four controls/jumps, one exogenous state.
- **Matrix A**: `A = \begin{bmatrix}0\\1\\0\\0\end{bmatrix}` - Coefficient on x_t = k_{t+1}; only the capital-accumulation row involves k_{t+1}.
- **Matrix B**: `B = \begin{bmatrix}0\\-(1-\delta)\\-\alpha\\0\end{bmatrix}` - Coefficient on x_{t-1} = k_t: -(1-delta) in the accumulation equation and -alpha in the production function.
- **Matrix C**: `C = \begin{bmatrix} 0 & (1-\alpha)Y & -\tau v N^{v} & 0\\ 0 & 0 & 0 & -\delta\\ 0 & 1 & -(1-\alpha) & 0\\ -\frac{C}{Y} & 1 & 0 & -\frac{I}{Y}\end{bmatrix}` - Coefficients on the controls, columns ordered (c_t, y_t, n_t, i_t) -- the student annotated these column labels by hand.
- **Matrix D**: `D = \begin{bmatrix}0\\0\\-1\\0\end{bmatrix}` - z_t only enters the production function, with coefficient -1 as written (0 = y_t - z_t - alpha k_t - (1-alpha)n_t).
- **Matrices F, G, H**: `F = [0],\qquad G = \left[-\alpha\beta\frac{Y}{K}\right] = [\beta(1-\delta)-1] = [-(1-\beta(1-\delta))],\qquad H = [0]` - The expectational equation has no k_{t+2} and no k_t (in Uhlig indexing, no x_{t+1} and no x_{t-1}); it only contains k_{t+1} = x_t with coefficient -alpha beta Y/K.
- **Matrix J**: `J = \left[\; \frac{-C}{C-\tau\frac{N^{v}}{v}} \quad \alpha\beta\frac{Y}{K} \quad \frac{\tau N^{v}}{C-\tau\frac{N^{v}}{v}} \quad 0 \;\right]` - Coefficients on E_t y_{t+1} = (c_{t+1}, y_{t+1}, n_{t+1}, i_{t+1}). Note alpha beta Y/K = 1 - beta(1-delta).
- **Matrix K**: `K = \left[\; \frac{C}{C-\tau\frac{N^{v}}{v}} \quad 0 \quad \frac{-\tau N^{v}}{C-\tau\frac{N^{v}}{v}} \quad 0 \;\right]` - Coefficients on the date-t controls in the Euler equation; exactly minus the c and n entries of J (no y_t, no i_t).
- **Matrices L, M, N**: `L = [0],\qquad M = [0],\qquad N = [\psi]` - z does not appear directly in the Euler equation (it enters only through y and k); N is the AR(1) persistence.
- **Tilde matrices (elimination of y_t)**: `\tilde F = F - JC^{-1}A;\;\; \tilde G = G - JC^{-1}B - KC^{-1}A;\;\; \tilde H = H - KC^{-1}B;\;\; \tilde L = L - JC^{-1}D;\;\; \tilde M = M - KC^{-1}D` - What is left of the expectational equation once controls are substituted out with y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t).
- **Quadratic for P**: `0 = \tilde F P^{2} + \tilde G P + \tilde H \;\Longrightarrow\; P = \frac{-\tilde G \pm \sqrt{\tilde G^{2} - 4\tilde F\tilde H}}{2\tilde F}` - P is a scalar here, so the standard quadratic formula applies.
- **Linear equation for Q**: `0 = \tilde L N + \tilde M + \tilde F Q N + \tilde F P Q + \tilde G Q \;\Longrightarrow\; Q = \frac{-(\tilde L N + \tilde M)}{\tilde F N + \tilde F P + \tilde G}` - Once P is known, Q follows from the z_t coefficient block.
- **Solution matrices R and S**: `R = -C^{-1}(A P + B),\qquad S = -C^{-1}(A Q + D)` - Obtained by plugging x_t = P x_{t-1} + Q z_t into y_t = -C^{-1}(A x_t + B x_{t-1} + D z_t) and matching coefficients with y_t = R x_{t-1} + S z_t.
- **Recursive law of motion (solution)**: `x_t = P x_{t-1} + Q z_t,\qquad y_t = R x_{t-1} + S z_t` - The policy functions of the loglinearized economy.
- **Calibration of tau**: `\tau = (1-\alpha)\frac{Y}{N^{v}}` - Solve the steady-state leisure-consumption condition tau N^v = (1-alpha)Y for tau, given a target for steady-state hours N (typically a normalization such as N = 1 or N = 1/3) and 

### Midterm Exam, Dynamic Macroeconomics II, Prof. Felipe Meza, ITAM, October 10, 2024 (100 po

- **Q1 utility**: `\sum_{t=0}^{\infty}\beta^{t} u(c_t),\quad 0<\beta<1` - u strictly concave, strictly increasing, twice continuously differentiable; labor supply n_t inelastic and equal to 1.
- **Q1 consumer's intertemporal budget constraint**: `\sum_{t=0}^{\infty}\left\{q_t\left[(1+\tau_{ct})c_t + k_{t+1} - (1-\delta)k_t\right]\right\} \le \sum_{t=0}^{\infty}\left\{r_t k_t (1-\tau_{kt}) + w_t n_t\right\}` - tau_ct is a consumption tax, w_t the present-value real wage, r_t the present-value payment to capital, q_t the intertemporal price, tau_kt the tax on the return to capital ownersh
- **Q1 government's intertemporal budget constraint**: `\sum_{t=0}^{\infty} q_t\left(\tau_{ct} c_t + \tau_{kt} r_t k_t\right) = \sum_{t=0}^{\infty} q_t g_t` - Present value of tax revenue equals present value of spending; no debt appears explicitly (Ricardian).
- **Q1 feasibility**: `f(k_t,n_t) = c_t + k_{t+1} - (1-\delta)k_t + g_t,\quad 0<\delta<1` - Output is consumed, invested, or spent by the government.
- **Q1 firm's problem**: `\max \sum_{t=0}^{\infty}\left[q_t f(k_t,n_t) - r_t k_t - w_t n_t\right] \;\Rightarrow\; q_t f_k(k_t) = r_t \;\Rightarrow\; \frac{r_t}{q_t} = f_k` - Competitive firm equates the present-value marginal product to the present-value factor payment.
- **Q1 consumer's FOC for c_t**: `\beta^{t} u'(c_t) - \lambda q_t (1+\tau_{ct}) = 0 \;\Rightarrow\; q_t = \frac{\beta^{t}u'(c_t)}{\lambda(1+\tau_{ct})}` - Date-0 price is proportional to the tax-adjusted marginal utility.
- **Q1 no-arbitrage (present-value form)**: `q_t = q_{t+1}(1-\delta) + r_{t+1}(1-\tau_{k})` - Collecting terms in k_{t+1} in the budget constraint: k_{t+1}[q_{t+1}(1-delta) - q_t + r_{t+1}(1-tau_k)] = 0.
- **Q1 Euler equation with taxes**: `\frac{u'(c_t)}{\beta u'(c_{t+1})} = \left(f_k(1-\tau_{k,t+1}) + 1 - \delta\right)\left(\frac{1+\tau_{ct}}{1+\tau_{c,t+1}}\right)` - Both taxes appear: the capital tax multiplies the marginal product, and the consumption tax enters only as a GROWTH RATE (ratio), so a constant tau_c is intertemporally neutral.
- **Q1.1 answer (R1)**: `1 = \beta\left(1 - \delta + f_k(1-\tau_k)\right),\qquad f(k,1) = c + \delta k + g,\qquad \frac{r}{q} = f_k` - One equation in one unknown for each of k, c and r/q.
- **Q1 steady-state marginal product of capital**: `f_k = \frac{\frac{1}{\beta} - 1 + \delta}{1-\tau_k};\qquad \tau_k = 0 \Rightarrow f_k^{*} = \frac{1}{\beta} - 1 + \delta` - The capital tax raises the required pre-tax marginal product, hence lowers k.
- **Q2 sequential budget constraint**: `c_t + R^{-1} b_{t+1} \le y_t + b_t,\quad y_t \ge 0\;\forall t,\quad \sum_{t=0}^{\infty}\beta^{t} y_t < +\infty,\quad b_0 = 0,\quad \lim_{T\to\infty} R^{-T} b_{t+T} = 0` - Risk-free asset b_{t+1} with constant gross return R > 1 and R beta = 1; endowment economy.
- **Q2 FOCs**: `c_t:\;\beta^{t}u'(c_t) = \lambda_t;\qquad b_{t+1}:\; -\frac{\lambda_t}{R} + \lambda_{t+1} = 0 \Rightarrow \frac{\lambda_t}{\lambda_{t+1}} = R` - Combining: u'(c_t) = beta R u'(c_{t+1}); with beta R = 1 this gives c_t = c constant.
- **Q2 intertemporal budget constraint**: `\sum_{t=0}^{\infty}\beta^{t} c_t = \sum_{t=0}^{\infty}\beta^{t} y_t \quad (\text{using } R^{-1} = \beta,\; b_0 = 0,\; \text{TVC})` - Present value of consumption equals present value of income.
- **Q2.1 answer (R3)**: `\frac{c}{1-\beta} = \frac{y}{1-\beta} \;\Rightarrow\; c = y` - Constant endowment -> autarky.
- **Q2.2 answer (R3), V-shaped recovery**: `\frac{c}{1-\beta} = y_l + \beta y + \beta^{2} y + \cdots = y_l + \frac{\beta}{1-\beta} y \;\Rightarrow\; c = (1-\beta) y_l + \beta y` - Only (1-beta) of the transitory shortfall is absorbed by consumption; the rest is smoothed by borrowing.
- **Q2.3 answer (R3), L-shaped recovery**: `\frac{c}{1-\beta} = \frac{y_l}{1-\beta} \;\Rightarrow\; c = y_l` - Permanent shock is absorbed one-for-one.
- **Q2.4 identification inequality**: `c^{\text{L}} = y_l < (1-\beta) y_l + \beta y = c^{\text{V}} \iff \beta y_l < \beta y \iff y_l < y` - Consumption is strictly lower under the permanent (L-shaped) path.
- **Q3 utility and time constraint**: `\sum_{t=0}^{\infty}\beta^{t} u(c_t,l_t),\qquad 1 = l_t + n_t` - Endogenous labor: leisure l_t and labor n_t sum to the unit time endowment.
- **Q3 sequential budget constraint**: `c_t + k_{t+1} + \frac{b_{t+1}}{R_t} - b_t \le (1-\tau_{nt}) w_t n_t + (1-\tau_{at})(r_t + 1 - \delta) k_t,\quad b_0 = 0` - tau_nt is a labor income tax; tau_at taxes capital earnings PLUS the asset value of capital net of depreciation; b_{t+1} is government debt.
- **Q3 household FOCs**: `c_t:\;\beta^{t}u_{ct} = \lambda_t;\quad n_t:\; -\beta^{t}u_{nt} + \lambda_t (1-\tau_{nt}) w_t = 0 \Rightarrow \frac{u_{nt}}{u_{ct}} = (1-\tau_{nt}) w_t;\quad b_{t+1}:\; -\frac{\lambda_t}{R_t} + \lambda_{t+1} = 0;\quad k_{t+1}:\; -\lambda_t + \lambda_{t+1}(1-\tau_{a,t+1})(r_{t+1}+1-\delta) = 0` - The n_t FOC is the LABOR WEDGE: the marginal rate of substitution between leisure and consumption equals the after-tax wage.
- **Q3.1 No Arbitrage Condition (R4)**: `R_t = (1-\tau_{a,t+1})(r_{t+1} + 1 - \delta)` - Bonds and capital must deliver the same after-tax return.
- **Q3 intertemporal price**: `q_t = \prod_{i=0}^{t-1} R_i^{-1},\qquad q_0 = 1,\qquad \frac{q_{t+1}}{q_t} = \frac{1}{R_t}` - Date-0 price of a date-t good.
- **Q3 present-value budget constraint**: `\sum_{t=0}^{\infty} q_t c_t = \sum_{t=0}^{\infty} q_t w_t n_t (1-\tau_{nt}) + k_0 (1-\tau_{a0})(r_0 + 1 - \delta)` - Consolidated household constraint with b_0 = 0.
- **Q3.2 Implementability condition (R3)**: `\sum_{t=0}^{\infty}\beta^{t} u_{ct} c_t = \sum_{t=0}^{\infty}\beta^{t} u_{nt} n_t + (1-\tau_{a0})(r_0 + 1 - \delta) k_0 \lambda` - The single constraint that encodes household optimality plus budget balance in terms of allocations only.
- **Q3 pseudo-utility and Ramsey Lagrangian**: `V_t \equiv u(c_t, 1-n_t) + \phi\left[u_{ct} c_t - u_{nt} n_t\right];\qquad J = \sum_{t=0}^{\infty}\beta^{t}\left\{ V_t + \theta_t\left[f(k_t,n_t) - c_t - k_{t+1} + (1-\delta)k_t - g_t\right]\right\} - \phi A,\quad A \equiv (1-\tau_{a0})(r_0+1-\delta)k_0\lambda` - The Ramsey planner maximizes over allocations {c_t, n_t, k_{t+1}} with multiplier phi on implementability and theta_t on feasibility.
- **Q3.3 Ramsey FOC for k_{t+1} (R2)**: `-\beta^{t}\theta_t + \beta^{t+1}\theta_{t+1}\left(f_{k,t+1} + 1 - \delta\right) = 0` - Capital enters only through feasibility, so its Ramsey FOC is the undistorted intertemporal condition.
- **Q3 household Euler with capital tax**: `\frac{u_{ct}}{\beta u_{c,t+1}} = (1-\tau_{a,t+1})(r_{t+1} + 1 - \delta) \;\;\overset{\text{ss}}{\Longrightarrow}\;\; \frac{1}{\beta} = (1-\tau_a)(r + 1 - \delta)` - The private intertemporal condition, distorted by tau_a.
- **Q3.4 optimal capital tax equation (R4)**: `\beta(f_k + 1 - \delta) = \beta(1-\tau_a)(f_k + 1 - \delta) \;\Longrightarrow\; \tau_a = 0` - Chamley-Judd: zero capital income taxation in the long run (using r = f_k from the firm's FOC).
- **Q3 firm's FOCs (student's margin note)**: `r_t = f_{k}(k_t,n_t) q_t,\qquad w_t = f_{n}(k_t,n_t) q_t` - Both factors are paid their marginal products; combined with the no-arbitrage condition this gives r = f_k in steady state.

## Bloque laboral por modelo - donde vive epsilon_D

**`Macro_Din_II_Topics1.1and1.2.pdf`**

Production is Cobb-Douglas: f(k_t,n_t)=k_t^theta n_t^(1-theta), 0<theta<1 (theta = capital's share; the CURVATURE parameter governing diminishing marginal product of labor and the elasticity of substitution between capital and labor, which is unity under Cobb-Douglas). The labor demand condition is competitive marginal-product pricing: w_t = lambda_t f_{n_t} = MP_{n_t} = lambda_t(1-theta)k_t^theta n_t^{-theta} (equivalently w_t=(1-theta) y_t/n_t in the government-extended model's steady-state calibration equation). Baseline utility/labor-supply specification is separable and NOT GHH: u(c_t,l_t) = ln(c_t) + gamma ln(l_t) [with l_t=1-n_t], gamma>0 governing the strength of the income effect on labor supply and calibrated (gamma approx 2, or 2.33 with government) to match average hours n approx 0.27; this generates a finite, model-implied Frisch elasticity (no closed-form Frisch elasticity is stated in the slides). Hansen (1985) modifies this to LINEAR-in-leisure utility u(c_t,l_t)=ln(c_t)+gamma_2 l_t via lotteries over an indivisible (work N hours or 0) individual choice -- this is the mechanism that makes AGGREGATE labor supply behave as if the (aggregate) Frisch elasticity were effectively very high/infinite along the extensive margin, amplifying hours volatility. The two-period/intertemporal labor supply FOCs, (1-n1)/(1-n2)=[1/(beta(1+r))](w2/w1) and its tax-augmented version with the wedge (1-tau2)/(1-tau1), show labor supply's curvature also depends on relative (present vs. future) after-tax wages -- i.e., intertemporal substitution in labor supply, directly relevant to how labor demand/supply elasticities are identified.

**`Macro_Din_II_Topic2.2FirstPartFINALVERSION.pdf`**

Part 1 keeps the production function fully general: F(k,n), homogeneous of degree one with positive and decreasing marginal products (no explicit Cobb-Douglas or CES form given). Labor demand emerges from the firm's zero-profit condition via Euler's theorem: w_t = q_t F_nt (wage equals price times marginal product of labor); since F is only assumed homogeneous of degree 1 here, the curvature of labor demand is whatever curvature F_nn has -- it is not pinned down numerically in this file. Utility is general U(c_t,1-n_t) (strictly increasing, strictly concave, twice differentiable) -- not GHH, not explicitly separable/CES in leisure; no Frisch elasticity is derived. The household's labor-supply FOC is beta^t U_2t = mu w_t (1-tau_nt), so combined with the consumption FOC, labor supply satisfies U_2t/U_1t = w_t(1-tau_nt) / [q_t(1+tau_ct)], i.e. MRS(leisure,consumption) equals the after-tax wage relative to the after-tax consumption price. However, the 'particular case' used to derive the tractable second-order difference equation SHUTS DOWN the labor margin entirely: U(c,1-n)=u(c) with n=1 fixed, i.e. inelastic labor supply, Frisch elasticity = 0 by construction. No curvature parameter (alpha, elasticity of substitution) for capital-labor substitution is specified in Part 1; F is left generic.

**`Macro_Din_II_Topic2.2SecondPart.pdf`**

The discrete-time part of this file keeps labor supply exogenous/suppressed (inherited from Part 1's 'particular case'); production is written in intensive form f(k) with no separate n. The 'Continuous-time dynamics' section explicitly assumes inelastic labor supply (n=1) with production f(k)=k^alpha -- i.e. labor is fixed and absorbed into the function; no separate labor demand condition or wage equation is derived. No utility-of-leisure term and no Frisch elasticity appear anywhere in this file. The curvature/substitution parameter that IS pinned down is sigma, the CRRA coefficient governing intertemporal (not labor) substitution: IES=1/sigma, entering directly in the continuous-time Euler equation c-dot/c=(1/sigma)(f'(k)-delta-rho).

**`Macro_Din_II_Topic2.2ThirdPartFINALVERSIONfixlastslide.pdf`**

This file is the one place in the chunk where both sides of the labor block are made fully explicit. (1) In the baseline 'Effects of taxes' system, labor supply is still inelastic (restated explicitly on page 4); under that assumption tau_n literally disappears from the system of equations, and a constant tau_c is also non-distorting -- only tau_i and tau_k always distort. A handwritten annotation on page 4 derives what the marginal condition WOULD be if labor entered: 'Umgc/Umgh = w(1-tau_n)' (marginal utility of consumption over marginal utility of leisure equals the after-tax wage), with the note 'No hay en el modelo' (not present in the model) because n is fixed. (2) The final two slides DO switch on endogenous labor supply, using additively separable log utility u(c,1-n)=ln(c)+psi*ln(1-n) -- NOT GHH (GHH would remove the wealth effect on labor supply; here it is fully separable, so a wealth effect on labor supply IS present). Production is Cobb-Douglas y=k^alpha n^{1-alpha}, so alpha (equivalently 1-alpha, labor's share) is the curvature parameter governing the marginal product of labor: F_n=(1-alpha)k^alpha n^{-alpha}, F_nn=-alpha(1-alpha)k^alpha n^{-alpha-1}<0. The implicit labor demand condition (from the same zero-profit/Euler's-theorem logic as Part 1, specialized to Cobb-Douglas) is w_t=q_t(1-alpha)k_t^alpha n_t^{-alpha}; combined with the household's static FOC this yields the printed consumption-leisure equation psi*c_t/(1-n_t) = (1-alpha)k_t^alpha n_t^{-alpha}, i.e. MRS(leisure,c)=wage. The implied Frisch elasticity under log-log separable utility is finite (not infinite as under GHH with linear disutility of labor) and depends on the steady-state labor share n-bar, though it is not computed explicitly in the slides.

**`NotesDynMacroIITopic2.2.pdf`**

Same continuous-time set-up as SecondPart.pdf page 12: inelastic labor supply (n=1, not modeled as a choice); Cobb-Douglas-in-capital-only intensive production f(k)=k^alpha is implicit (inherited from the companion slide, not re-derived here). No separate labor demand or labor supply equation appears; labor is entirely absent from the phase-diagram derivation, consistent with the 'particular case' simplification carried over from the discrete-time slides. No Frisch elasticity, no CES/GHH specification, no wage equation.

**`NotesDynMacroIITopic2.2secondpart.pdf`**

Same as NotesDynMacroIITopic2.2.pdf -- continuous-time Ramsey model with inelastic labor supply; no labor margin appears anywhere in this file. Not applicable.

**`Macro_Din_II_Topic2.3FirstPartFINALVERSIONfixes2.pdf`**

Production is a generic CRS function F(k_t,n_t) (not specified as Cobb-Douglas or CES in this file) with Euler's theorem F(k,n)=F_k k+F_n n. Labor demand comes from the firm's static profit-maximization FOC F_n(t)=w_t (competitive wage = marginal product of labor). Labor supply/consumption-leisure margin: u_l(t)=u_c(t)(1-\tau_{nt})w_t, derived from a generic period utility u(c_t,1-n_t) (twice differentiable, strictly concave) — no GHH form and no explicit Frisch elasticity is assumed or computed; the curvature of labor demand is left implicit in F_n and its cross-partial F_{nk} rather than pinned to a specific parameter such as a capital share alpha. The labor tax tau_nt enters as a simple multiplicative wedge on the wage in the consumption-leisure condition. Judd's heterogeneous-agent case adds a second labor-supply margin per agent type i, u_ilt/u_ict=(1-tau_nt)w_t, still with generic utility.

**`Macro_Din_II_Topic2.3SecondPartFINALVERSION.pdf`**

Production remains a generic function F(k_t,n_t) in the baseline primal model (no Cobb-Douglas/CES specified), extended to F(k_t,n_t,z_t) with constant returns to scale in the Correia extension (Cobb-Douglas invoked only at the very end, as an example, to sign F_zk). Labor demand: firm FOC F_nt=w_t (unchanged from First Part). The labor-supply/consumption-leisure margin is embedded inside the Implementability Condition and the V(c,n,Phi) function: V = u(c,1-n) + Phi(u_c c - u_l n) — the multiplier Phi re-weights marginal utilities of consumption and labor in the planner's effective objective, which is the primal-approach mechanism for encoding the labor-tax distortion, but no specific functional form (GHH, separable CRRA, etc.) or Frisch elasticity value is assumed; u(c,1-n) stays fully generic. The parameter that explicitly governs a factor-substitution/curvature margin in this file is F_zk (the cross-partial between the untaxed factor Z and capital) — analogous in role to a labor-demand curvature parameter but for the Z-k margin rather than the k-n margin; it is what determines whether the derived tau_k is positive, negative, or zero.

**`Macro_Din_II_Agosto_2018Topic3.1SecondPartand3.2.pdf`**

Labor enters only through a linear technology y_t=n_t (output equals labor input directly; no capital, no Cobb-Douglas/CES production function in this model). There is no separate 'labor demand' condition of the W=(1-alpha)Y/N type because the real wage is normalized to 1 and there is no diminishing marginal product of labor here. The household allocates time 1=l_t+s_t+n_t among leisure l_t, shopping time s_t=H(c_t,m-hat_{t+1}), and labor n_t; income is (1-tau_t)(1-l_t-s_t) at wage 1, net of labor tax tau_t. Utility u(c_t,l_t) is left in general (not necessarily separable) form with only sign/curvature assumptions (u_c,u_l>0; u_cc,u_ll<0; u_cl>=0) — not GHH, no explicit Frisch elasticity computed. The one parameter that governs curvature/substitution in this model is nu, the degree of homogeneity of the shopping-time technology H(c,m-hat) in consumption and real balances; it determines how shopping time and money demand respond to consumption, and it is exactly the parameter for which the Friedman-rule optimality proof is shown to hold for any nu>=0.

**`Macro_Din_II_Agosto_2018Topic4.2CORREGIDO.pdf`**

Production is a generic constant-returns function F(K_t,Z_tL_t) (homogeneous of degree 1 in K and effective labor ZL — not restricted to Cobb-Douglas in this deck), transformed into intensive form f(k-hat_t,l_t)=F(K_t,Z_tL_t)/(N_tZ_t). The firm's detrended FOCs give the labor-demand and capital-rent conditions: r_t=f_1(k-hat_t,l_t) and w-hat_t=f_2(k-hat_t,l_t) — factor prices equal marginal products of the intensive-form production function (the familiar Cobb-Douglas special case W=(1-alpha)Y/N would follow only if F were specialized, which is not done here). On the household side, utility is U(c_t,1-l_t)=c_t^{1-sigma}v(l_t)/(1-sigma) — a multiplicatively separable, KPR-type (balanced-growth-consistent) specification with v(.) left generic, so no explicit Frisch elasticity is pinned down; the curvature in consumption is governed by sigma, and the curvature/substitutability of labor supply is governed by the (unspecified) shape of v(l). The labor-leisure optimality condition is U_2(c-hat_t,1-l_t)/U_1(c-hat_t,1-l_t) = [(1-tau_t^l)/(1+tau_t^c)]*w-hat_t, so the labor tax tau^l and the consumption tax tau^c jointly wedge the labor-supply margin, and the after-tax detrended wage w-hat_t is exactly the firm's f_2(k-hat,l) — the closest analogue here to a 'labor demand = labor supply' condition. No explicit CES/elasticity-of-substitution parameter between K and L appears since F is left generic (homogeneous of degree 1).

**`Macro_Din_II_Agosto_2019Topic5FirstPart(1).pdf`**

Utility is log(C_t)-AN_t: additively separable and LINEAR in hours N_t (Hansen 1985 indivisible-labor specification), which implies via the standard lottery/indivisible-labor argument an effectively infinite Frisch elasticity of aggregate labor supply — a deliberate modeling choice to generate large employment volatility. Production is Cobb-Douglas, Y_t=Z_tK_{t-1}^rho*N_t^{1-rho}: the curvature/substitution parameter is rho (capital's share), which pins the elasticity of substitution between capital and labor at 1 (Cobb-Douglas) and governs the diminishing-marginal-product curvature of the (implicit) labor demand relation. There is no separate 'labor demand=(1-alpha)Y/N' equation written explicitly (no posted wage in this closed RBC model), but it is implicit: combining the static FOCs A=Lambda_t(1-rho)Y_t/N_t and 1/C_t=Lambda_t gives A*C_t=(1-rho)Y_t/N_t, i.e. the marginal rate of substitution between consumption and leisure equals the marginal product of labor (1-rho)Y_t/N_t. In log-linearized form this collapses to n_t=lambda_t+y_t.

**`Macro_Din_II_Agosto_2019Topic5SecondPart(1).pdf`**

Same model as Part 1: n_t is among the 'other endogenous variables' y_t=[c_t,y_t,n_t,lambda_t,r_t] (note: this y_t is Uhlig's generic vector notation, distinct from output y_t — a labeling collision the slides do not resolve explicitly). The consumption-leisure/labor equation 0=-n_t+y_t+lambda_t (a row of matrix C) is one of the 'static' equations used to eliminate n_t, c_t, r_t and reduce the system to the two dynamic variables k_t and lambda_t (eq. 8: y_t=(1/rho)z_t+k_{t-1}+((1-rho)/rho)lambda_t). The curvature parameter rho (Cobb-Douglas capital share) reappears throughout the alpha_1..alpha_6 coefficients that determine the policy function — in particular alpha_3=Y-bar/(rho*K-bar) and the (1-rho)/rho term multiplying lambda_t in eq. (8) — so rho continues to govern how strongly labor/output respond to the multiplier (shadow value of wealth) and to capital.

**`Topic5Solving_by_hand.pdf`**

Labor does not appear explicitly in these notes: the system has already been reduced to two equations in capital k_t and the multiplier lambda_t, with hours substituted out. Implicitly, hours n_t (and consumption, output, investment) are recovered afterwards from the static equations as linear functions of (k_{t-1}, z_t), exactly as y_t = R x_{t-1} + S z_t does in the project. Hence any labor-demand curvature parameter (alpha in Cobb-Douglas) and labor-supply curvature parameter (v) are buried inside the reduced-form coefficients alpha_1,...,alpha_6.

**`Proyecto.pdf`**

PRODUCTION: Cobb-Douglas Y_t = Z_t K_t^alpha N_t^{1-alpha}, constant returns to scale, labor share (1-alpha). LABOR DEMAND: the marginal product condition W_t = (1-alpha) Z_t (K_t/N_t)^alpha = (1-alpha) Y_t/N_t. Inverting, ln N_t = (1/alpha)[ln(1-alpha) + ln Z_t + alpha ln K_t - ln W_t], so with capital predetermined the (short-run, partial-equilibrium) labor demand elasticity is d ln N_t / d ln W_t = -1/alpha. THE CURVATURE OF LABOR DEMAND IS GOVERNED SOLELY BY alpha (the capital share); under Cobb-Douglas the elasticity of substitution between K and N is 1, so -1/alpha is exactly the conditional labor demand elasticity holding K fixed, and it becomes perfectly elastic (horizontal) once K adjusts fully in the long run. In loglinear form labor demand is w_t = y_t - n_t = z_t + alpha k_t - alpha n_t. UTILITY / LABOR SUPPLY: GHH period utility ln(C_t - tau N_t^v / v). The intratemporal FOC is tau N_t^{v-1} / (C_t - tau N_t^v/v) = lambda_t W_t, and with 1/(C_t - tau N_t^v/v) = lambda_t it collapses to tau N_t^{v-1} = W_t, hence ln N_t = (1/(v-1))(ln W_t - ln tau). FRISCH ELASTICITY OF LABOR SUPPLY = 1/(v-1). Because preferences are GHH there is NO wealth effect: the Frisch, Marshallian and Hicksian labor-supply elasticities all coincide at 1/(v-1). The parameter v > 1 governs the curvature (convexity) of labor supply; v -> 1 gives infinitely elastic labor supply, v -> infinity gives inelastic labor supply. EQUILIBRIUM: multiplying by N_t gives tau N_t^v = W_t N_t = (1-alpha)Y_t, so in loglinear form (1-alpha)Y y_t = tau v N^v n_t, i.e. n_t = y_t / v: hours are output divided by v. Combining supply (n_t = (1/(v-1))w_t) with demand (w_t = z_t + alpha k_t - alpha n_t) gives the equilibrium hours response n_t = z_t/(v-1+alpha) + alpha k_t/(v-1+alpha) -- the standard identification problem: only the intersection is observed, so alpha (demand curvature) and v (supply curvature) cannot be separated from the equilibrium (w, n) pair alone; one needs a shifter of supply (or of demand) to trace out the other curve. The relevant natural experiment in this model is the TFP shock z_t, which is a pure LABOR DEMAND shifter and therefore traces out the labor SUPPLY curve, not the demand curve.

**`Midterm_exam_Dynamic_Macro_II_oct2024_251013_052910.pdf`**

Q1: labor is INELASTICALLY supplied at n_t = 1, so there is no labor-supply margin and the Frisch elasticity is exactly 0. Production is a generic f(k_t,n_t), homogeneous of degree 1, with strictly positive and decreasing marginal returns -- no functional form is imposed, so no specific labor-demand curvature parameter exists; labor demand is implicitly w_t = q_t f_n(k_t,n_t) from the firm's problem max sum [q_t f(k_t,n_t) - r_t k_t - w_t n_t], and with n fixed at 1 the wage simply clears at f_n(k,1). Q2: NO labor at all -- it is a pure endowment economy with exogenous y_t. Q3: labor is ENDOGENOUS. Utility u(c_t,l_t) with 1 = l_t + n_t, strictly concave and strictly increasing in both arguments, twice continuously differentiable; NO functional form is imposed, so the Frisch elasticity is not pinned down numerically -- it is whatever -u_l/(l u_ll) implies. The labor supply condition (labor wedge) is u_nt/u_ct = (1-tau_nt) w_t. Labor demand is w_t = f_n(k_t,n_t) from the firm's static problem max f(k_t,n_t) - r_t k_t - w_t n_t (the student wrote r_t = Pmg_{k_t} q_t and w_t = Pmg_{n_t} q_t in the margin). The curvature of labor demand is governed by the curvature of f in n, i.e. by f_nn < 0 and, given CRS, by the elasticity of substitution between k and n -- but since f is left generic no single parameter governs it. The tax tau_nt is the exogenous shifter of the labor-supply schedule, and this is exactly the structure an empirical design would exploit to identify the slope of labor demand.
