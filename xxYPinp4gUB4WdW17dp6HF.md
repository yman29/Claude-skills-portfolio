

Statistics for Quants
From Data to Decisions, Not p-Values
Amit Kumar Jha, Quant Analyst at UBS
## December 26, 2025
## Contents
Module 1: Probability vs Statistics (The Hidden Confusion)5
Module 2: Data Is Not IID (And Never Was)8
Module 3: Estimation Error Is the Dominant Risk12
Module 4: Regression Is a Model, Not a Fact14
## Module 5: Time Series: Memory, Not Just Noise17
Module 6: Volatility Is Not a Parameter21
## Module 7: Correlation Is Conditional, Not Structural23
Module 8: Hypothesis Testing Is Mostly Useless (If Misused)26
Module 9: Forecasting vs Risk Estimation29
Module 10: Bayesian Thinking for Quants (Without Religion)34
Module 11: Model Risk as a Statistical Object36
Module 12: Backtesting Is a Statistical Minefield40
Module 13: From Statistics to PnL Attribution42
Module 14: Interview Toolkit (Stats Edition)45
## Statistical Debugging Protocol: When Models Break48
Mental Models: Think Like a Bayesian Statistician49
## Appendix: Statistics Formula Sheet52
Final Interview Checklist—Statistics52
## 1© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

How to Use This Notes (Very Important)
## Purpose
These notes are not about estimation. They are about inference under uncertainty.
## Module Overview
What this notes is NOT:
-  Not ML engineering
-  Not academic hypothesis testing
-  Not cookbook regressions
What it IS:
-  Statistics as a decision-making system under model risk
-  Econometrics as controlled lies with error bars
## Desk Takeaway:
“The market didn’t break your model—your inference was weak.”
Crisis Playbook - The 3 Ds (Stats Edition)
When models break, follow the 3 Ds:
-  De-risk: Cut position size by 50% immediately
-  De-leverage: Reduce factor exposure to 1/3 of normal limits
-  Defend: Hold 2-3× normal reserves, assume correlations → 1
## Interview Gold:
"In crisis, I don’t trust calibrated parameters—I trust shrinkage and reserves.  If my model says ρ = 0.3, I
stress at 0.9. The cost of being wrong is losing my job."
## Red Flag:
Never say:  "My statistical model handles all market conditions." (Shows you’ve never lived through a
crisis)
## 2© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

MethodCore AssumptionState Variables   DependenceTail
## Handling
Estimation  ApplicationsFailure ModeDesk Usage
OLS LinearLinear, IID errorsCoefficients βStaticIgnoredLeast
squares
Factor attribution   Autocorr,
heterosked
## Basic
analysis
OLS Log-Log  Log-log linear,
constant elast.
Elasticities βStaticIgnoredLeast
squares
## Multiplicative
relations
Non-linearityEcon
modeling
OLS Log-Lin   Log-lin,
semi-elasticity
## Semi-elasticities
β
StaticIgnoredLeast
squares
Growth ratesHeteroskedasticityGrowth
models
OLS Lin-Log   Lin-log,
diminishing returns
Coefficients βStaticIgnoredLeast
squares
## Diminishing
effects
## Misspecification   Utility
functions
ARStationary lag
structure
AR coeffs φLinear
memory
IgnoredMLE/Yule-
## Walker
## Short-term
forecasting
## Non-stationarity  Signal
modeling
MAInvertible, finite
memory
MA coeffs θLinear
memory
IgnoredMLE/OLS   Forecasting,
smoothing
## Parameter
redundancy
## Noise
filtering
ARMAStationary AR+MA   φ, θLinear
memory
IgnoredMLEStationary seriesNon-stationarity  Legacy
systems
ARIMAIntegrated ARMA,
d diffs
φ, θ, dLinear
memory
IgnoredMLE/Box-
## Jenkins
## Non-stationary
series
## Over-
differencing
## Macro
forecasting
ARFIMALong memory,
fractional d
φ, θ, d
## (fractional)
## Hyperbolic
decay
IgnoredMLE/WhittleLong-memory
series
## Spurious
detection
Interest rates
GARCHConditional
variance
σ
## 2
t
Vol clustering   GaussianQuasi-
## MLE
VaR, vol
forecasting
Crisis lagRisk mgmt
GJR-GARCH   Asymmetric vol
## (leverage)
σ
## 2
t
, leverage
term
## Asymmetric
clustering
GaussianQuasi-
## MLE
Equity vol skewSlow asymmetry  Equity risk
EGARCHLog vol,
exponential
log σ
## 2
t
Vol clustering   GaussianMLENo positivity
constraint
Log transform
issues
## Vol
forecasting
GARCH-MVol-in-mean effectσ
## 2
t
in mean eq.Risk-return
tradeoff
GaussianMLERisk premium
modeling
## Spurious
significance
Asset pricing
IGARCHUnit root in
variance
σ
## 2
t
(persist=1)Infinite
memory
GaussianMLERiskMetrics styleNon-stationaryShort-term
risk
VARMulti-variate linear   Vector of coeffs
## A
## Cross-variate
lags
IgnoredOLS/MLE   Multi-asset
forecasting
## Dimension
explosion
## Macro
models
BayesianPrior beliefPosterior
distribution
## Sequential
update
Via priorMCMC/ConjugateParameter
uncertainty
Prior misspecHigh-dim
EVTTail exponent ξThreshold
exceedances
## Asymptotic
independence
## Explicit
modeling
MLE/PWM Stress testing tails   Threshold
choice
Crisis models
CopulasMarginal +
dependence
## Copula
parameters
## Flexible
dependence
Via copula   MLE/IFM   Non-Gaussian
dependence
Model selection    Portfolio risk
Factor/PCALatent factorsFactor loadings   Factor
structure
IgnoredEigen
decompo-
sition
## Dimension
reduction
Factor instability  Risk decomp
## Non-
parametric
## Minimal
assumptions
## Empirical
distribution
Data-drivenKernel
smoothing
Kernel/SplinesFlexible fittingCurse of dimEcon
estimation
## Table 1: Statistics Methods Landscape: Problem → Risk → Method Mapping
LevelProblem ClassMethod ChoiceWhy Upgrade?Data Requirement
1Simple  correlation,   linear  rela-
tionship
OLSFast, interpretableT> 100
2Autocorrelation in residualsARMA/GARCHMemory in varianceT> 500
3Multi-collinearity,   high  dimen-
sion
Ridge/LASSOShrinkage, stabilityT> 10p
4Parameter uncertainty, prior infoBayesianIncorporate   priors,    sequential
update
## Any T
5Long memory seriesARFIMAFractional integrationT> 1000
6Non-linear dependence, tail riskCopulas, EVTTail dependence, asymmetryT> 1000
7Regimeswitches,structural
breaks
Markov-switchingTime-varying parametersT> 1000
8Model   risk,    ensemble   uncer-
tainty
Ensemble methodsRobust,  uncertainty  quantifica-
tion
Multiple models
Table 2: Statistical Complexity Ladder - When to Upgrade Your Method
## 3© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

MetricOLSARIMAGARCHBayesianARFIMA
In-Sample R
## 2
## 0.150.18N/A0.200.22
Out-of-Sample R
## 2
## 0.020.04N/A0.120.08
StabilityHighMediumHighHighMedium
InterpretabilityHighMediumMediumMediumMedium
Fit SpeedFastMediumMediumSlowMedium
Forecast SpeedFastFastFastMediumFast
Primary FailureAssumption violationsNon-stationaritySlow adaptationPrior misspecificationSpurious   long   mem-
ory
Table 3: Method Performance Comparison (1Y FX Return Prediction)
Data TypeExamplesTypical FeaturesDependencePrimary MethodRed Flag
IID Cross-SectionMonthlyreturns,
survey data
Independent,  stable
moments
NoneOLS, t-testsAssuming    IID    for
time series
Time Series (Stationary)Interestrate
changes, spreads
## Autocorrelation,
constant vol
Linear AR/GARCHARMA, GARCHIgnoring unit root
Time Series (Non-Stationary)Equity prices, macro
aggregates
## Trends,stochastic
drift
Persistent shocksCointegration,dif-
ferencing
Spurious regression
High-Dimensional1000+ stock returns,
text data
p>T,multi-
collinearity
Factor structureRidge,PCA,
## Bayesian
Raw   OLS   without
shrinkage
Tail-HeavyEM   FX,   crypto   re-
turns
## Skewness>|1|,
kurtosis > 5
Extreme eventsEVT, t-distributionAssuming    normal-
ity
Regime-SwitchingCrisis  periods,  pol-
icy changes
Parameters    change
suddenly
Markov switchingMS-GARCH, DCCStatic parameters
Long MemoryInterestrates,
volatility
Slow hyperbolic de-
cay
## Fractionalintegra-
tion
## ARFIMA,FI-
## GARCH
Using   short   mem-
ory models
## Table 4: Data Regime Recognition & Statistical Method Selection Guide
Crisis TypeWhat BreaksStatistical AdjustmentReserve MultiplierExample
Correlation BreakdownStatic correlation matrixUseDCCorregime-
switching ρ
2-3×COVID March 2020
Volatility ExplosionGARCH    persistence    too
low
Increase ω by 50%, fix α +
β = 0.99
1.5×Volmageddon 2018
Parameter InstabilityCalibrated θ driftsShorten    estimation    win-
dow to 60 days
1.2×Brexit 2016
Tail EventGaussian assumptionSwitchtot-distribution
(ν = 5) or EVT
## 2×SNB 2015
Structural BreakModel specificationReset model, use robust SE,
increase lambda
1.5×Fed policy shift 2022
Sample Size CollapseHigh-dim with small TEmergency shrinkage λ =
## 0.5
3×New asset class launch
Long Memory BreakdownShort memory modelsSwitch   to   ARFIMA   with
d = 0.45
1.5×Rate regime shift
Regime Shift (Unknown)All assumptionsSwitchtonon-
parametric/buckets
5×Unknown unknowns
## Table 5: Crisis Mode Adjustments - When Normal Statistics Break
## 4© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Statistical Tradeoff Matrix: There Is No Free Lunch
## The Fundamental Tradeoffs
ChoiceGainCostBreak-Even
More parameters↑ Fit↑ Variancep<
## √
## T
Longer history↓ SE↑ Regime mixingT< 2× HL
regime
Higher frequency↑ Samples↑ NoiseSignal-to-noise > 2
More factors↑ R²↑ CollinearityVIF < 5
## Shrinkage↓ Variance↑ Biasλ
## ∗
= arg min MSE
Robustness↓ Outlier impact↓ EfficiencyFat tails?
Non-parametric↓ Misspec↑ VarianceT> 10× bandwidth
## −1
Bayesian prior↓ Variance↑ SubjectivityPrior well-calibrated?
Ensemble↓ Model risk↑ ComplexityModels uncorrelated
The Bias-Variance Tradeoff (The Only Equation That Matters)
## E[(
## ˆ
θ− θ)
## 2
## ] =   Bias
## 2
## (
## ˆ
θ)
## |
## {z}
Simplicity cost
+Var(
## ˆ
θ)
## |{z}
Complexity cost
## Visual Memory Aid:
## Model Complexity
## Error
## Total Error
## Bias²
## Variance
## Sweet Spot
Interview: "I choose complexity just left of the minimum—better to underfit than overfit in finance."
Module 1: Probability vs Statistics (The Hidden Confusion)
## Module Overview
What this module is about: This module clarifies the fundamental confusion between probability (math) and
statistics (inference) that causes 90% of quantitative mistakes.
Why this matters: Most quants confuse random variables, realized data, and future uncertainty—leading to
models that fit history but fail live.
What confusion this clears:
-  Why calibration̸= truth
-  Why backtests lie
-  Sampling error vs structural error
After this module, you should be able to answer: “Why does a perfect backtest still lose money?”
## 5© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 1.1 Probability = Model→ Data, Statistics = Data→ Model
## Core Formula
p(x|θ)
## |
## {z}
## Probability
vsp(θ|x)
## |{z}
## Statistics
Probability: Given a model, what data should I expect? (Forward) Statistics: Given data, what model is plausi-
ble? (Inverse)
"The Inverse Problem Is Ill-Posed"
Memory: Many models fit the same data.
Interview: “I don’t trust calibrated parameters—I trust out-of-sample predictive checks.”
## MODEL
p(x|  )
## DATA
x
## 1
, x
## 2
## , . . .
## PROBABILITY
## Model  Data
## DATA
x
## 1
, x
## 2
## , . . .
## INFERENCE
p(  |x)
## UNCERTAINTY
## STATISTICS
## Data  Model
Probability vs Statistics: Forward vs Inverse Problems
Figure 1: Probability vs Statistics: Forward vs Inverse Problems
## 1.2 Why Calibration̸= Truth
Three models fit EUR/USD smile equally well:
-  SABR: ρ =−0.2, ν = 0.5
-  Heston: κ = 2, ξ = 0.8
-  Local Vol: σ(K, T) surface
Problem: They give wildly different hedge ratios for barriers.
## 6© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Calibration Risk
"Same fit, different dynamics"
"Residual PnL is the only truth-teller"
"Interview: ’I don’t trust calibration—I trust hedging error.’"
## 1.3 Quick Interview Cheat Sheet — Module 1
## Module 1: Inference Over Estimation
Core Concept: Statistics is about decision-making under uncertainty, not finding “true” parameters.
## Interview Triggers:
-  "Backtest looks great but loses live?" → "Overfitting to noise"
-  "Which model is true?" → "All are wrong, some are useful"
-  "Parameter confidence interval?" → "Better: hedge error distribution"
## Desk Wisdom:
-  Models don’t break—your inference does
-  Stability > Accuracy (for hedging)
Common Trap: "Don’t say ’the model is correctly specified.’" (It’s never true)
Memory Aid: "Probability = math, Statistics = opinion with error bars."
Interviewer Is Testing: Can you separate model risk from market risk?
The 3-Second Answer (Module 1)
Question: "Why did my perfectly calibrated model fail in production?"
Your opening line:
"You solved the inverse problem but not the prediction problem. Calibration fits history—it doesn’t guarantee
the model structure captures future dynamics. The market didn’t change; your inference was overconfident."
Why this wins:
-  Shows you understand the fundamental epistemic problem
-  Distinguishes calibration from predictive validity
-  Avoids blaming the market (shows maturity)
Follow-up ready:
-  "How to fix?" → Walk-forward validation, parameter regularization
-  "How detect?" → Residual PnL > 5%
-  "Best practice?" → Ensemble models, hold model reserves
Red flag to avoid:
Never say: "The market was wrong" (shows you don’t understand your job)
The Calibration Triangle (Memory Device):
Good FitGood Prediction
## Good Hedge
## ?
## ?
## ?
## 7© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

All three are independent. Backtest shows Fit, not Hedge quality.
## Inference Quality Checklist (30-second):
## Score =
σ
## OOS
σ
## IS
## |{z}
## < 1.5?
## ×
Residual PnL
Total PnL
## |
## {z}
## < 5%?
## × N
params
## /
## √
## T
## |
## {z}
## < 1?
If Score > 2 → Inference is weak
Module 2: Data Is Not IID (And Never Was)
## Module Overview
What this module is about:  This module explains why the IID (Independent and Identically Distributed)
assumption—foundation of 95% of statistics textbooks—fails in markets and leads to catastrophic risk under-
estimation.
Why this matters: If you assume IID when data is dependent, your Sharpe ratios are lies, your VaR is wrong,
and your hedges fail.
What confusion this clears:
-  Why CLT misleads in finance
-  Why volatility clusters
-  Why tail events arrive in bursts
After this module, you should be able to answer: “Why does historical volatility underestimate future risk?”
2.1 The IID Fiction vs Market Reality
AssumptionAcademic StatsMarket Reality
IndependentNo memoryVol clustering: high vol→ more high vol
IdenticalSame distributionRegime shifts: crisis vs calm distributions differ
StationaryParameters fixedDrift/vol evolve: r
d
− r
f
, ρ change
NormalCLT appliesFat tails: jumps, kurtosis > 3
Table 6: IID assumption failure in financial data
## Core Formula
## IID: X
t
## ⊥⊥ X
t−1
## ,  E[X
t
] = μ,  Var(X
t
) = σ
## 2
## Core Formula
Reality: σ
## 2
t
= ω + αX
## 2
t−1
+ βσ
## 2
t−1
## (GARCH)
The "PTSD Market" Mnemonic:
P = Persistence (vol clustering)
T = Thick tails (kurtosis > 3)
S = Serial correlation (memory)
## D = Drift (non-stationarity)
Interview line: "Markets have PTSD, not amnesia."
## 8© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 050100150200250
## 0.02
## 0.01
## 0.00
## 0.01
## 0.02
## 0.03
## 0.04
## Returns
Constant volatility
No memory
Nice theory
IID Assumption
(Independent, Identical)
## 050100150200250
## 1.5
## 1.0
## 0.5
## 0.0
## 0.5
## 1.0
## 1.5
## 2.0
## Returns
Vol clusters
Fat tails
Regime shifts
## Market Reality
(Clustering, Regimes)
Why IID Assumption Destroys Risk Models
Figure 2: Why IID Assumption Destroys Risk Models
2.2 Why Volatility Clusters (And Your VaR Lies)
GARCH(1,1) intuition: - Yesterday’s vol feeds today’s vol - Shocks persist with half-life≈ ln(0.5)/ ln(α + β)
Consequence: - 1-day VaR scales as
## √
T only under IID - Real scaling: VaR
## T
≈ σ
t
## √
T· (1 + clustering adjustment)
## Clustering Risk
"VaR assumes amnesia—markets have memory"
"10-day VaR is 2x 1-day under IID, but 3-4x under GARCH"
"Interview: ’I scale VaR by GARCH term structure, not square root.’"
## 9© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 2.3 Quick Interview Cheat Sheet — Module 2
Module 2: Memory Kills IID
Core Concept: Financial data has serial dependence—volatility clusters, regimes persist.
Must-Know:
-  Vol clustering → σ
t
depends on σ
t−1
-  Sharpe ratio overstated by
p
1 + 2ρ where ρ = autocorrelation
-  CLT fails for tails (stable distributions)
## Interview Triggers:
-  "Why historical vol too low?" → "Sampled during calm regime"
-  "Why Sharpe 2.0 but drawdown 30%?" → "Return serial correlation"
-  "How to test IID?" → "Ljung-Box on squared returns"
## Desk Wisdom:
-  Use GARCH-scaled VaR, not
## √
## T
-  Check autocorrelation at lag 1, 5, 21 days
Common Trap: "Don’t say ’assume returns are IID’ in an interview." (Shows you’re dangerous)
Memory Aid: "IID = amnesia. Markets = PTSD."
Interviewer Is Testing: Do you know why bootstrap fails on time series?
## Autocorrelation Detection
## Quick Test:
## Q = T(T + 2)
h
## ∑
k=1
ρ
## 2
k
T− k
∼ χ
## 2
## (h)
On returns: Tests memory in mean (usually low)
On squared returns: Tests memory in variance (always high)
Interview line:
"Ljung-Box on squared returns rejects IID at 99.9%—that’s why we use GARCH."
The 3-Second Answer (Module 2)
Question: "My 10-day VaR is
## √
10× 1-day VaR. What’s wrong?"
Your opening line:
"Square root scaling assumes IID. Markets have volatility clustering—high vol periods persist.  The correct
scaling factor is closer to (
## √
10 + GARCH persistence) typically 3-4x, not 3.16x. Your VaR is underestimating
tail risk by 20-30%."
Why this wins:
-  Immediately identifies the flawed assumption
-  Quantifies the impact (20-30% underestimate)
-  References GARCH (shows technical depth)
Follow-up ready:
-  "How to fix?" → Use GARCH forecast for σ
t+T
-  "Alternative?" → Filtered historical simulation
-  "Regulatory?" → Basel allows
## √
T but it’s wrong
Red flag to avoid:
Never say: "Square root rule is fine" (shows you don’t understand tail risk)
VaR Scaling Reality Check:
VaR
## T-day
= VaR
## 1-day
## ×
## √
## T×
## 
## 1 +
α + β
## 2
## 
## |{z}
GARCH adjustment
## 10© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Example:  α + β = 0.96⇒ 10-day VaR =
## √
## 10× 1.48 = 4.68×  (not 3.16× )
Connecting the Dots: How Concepts Chain Together
## The Statistical Causality Chain
Data NOT IID
Use GARCH
for volatility
Scale VaR
by GARCH term
Test for
VaR breaches
Kill model if
10+ breaches
## Module 2
## Module 6
## Module 9
## Module 13
## Chain Reaction Examples
Chain 1: From Estimation to Reserves
High N/T
## Mod 3
## −−−→ Unstable
## ˆ
ρ
## Mod 7
−−−→ Regime risk
## Mod 11
−−−−→ Hold 20% reserve
Chain 2: From Testing to Trading
Test 100 factors
## Mod 8
−−−→ 5 false positives
## Mod 12
−−−−→ Walk-forward fails
## Mod 13
−−−−→ Don’t trade
Chain 3: From Calibration to Hedging
## Calibrate Heston
## Mod 1
## −−−→
## ˆ
ρ =−0.2± 0.1
## Mod 11
−−−−→ Vega hedge error
## Mod 13
−−−−→ Residual PnL 5%
The "If-Then" Cascade (Decision Tree)
IF (Data NOT IID)
THEN (Check autocorrelation)
## IF (ACF(²) > 0.2)
THEN (Use GARCH)
## IF ( +  > 0.98)
THEN (Persistence too high)
IF (Crisis mode)
THEN (Manual override:  × 1.5)
Memory: Statistics is a decision tree, not a formula sheet.
## 11© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Module 3: Estimation Error Is the Dominant Risk
## Module Overview
What this module is about: Parameter uncertainty dominates market uncertainty in modern trading.  A 1%
error in ρ can cause more PnL swing than a 1% spot move.
Why this matters:  Quants obsess over model sophistication but ignore that their parameters are estimated
with massive error—especially in high dimensions.
What confusion this clears:
-  Why calibrated parameters drift daily
-  Why shrinkage (James-Stein) beats MLE
-  Why dimensionality is your enemy
After this module, you should be able to answer:  “Why does correlation matrix estimation blow up with
100 assets?”
3.1 Parameter Risk vs Market Risk
Total variance decomposition:
## Core Formula
## Var(
## ˆ
θ)
## |{z}
## Parameter Risk
+ Var(X|θ)
## |{z}
## Market Risk
For correlation: - Var(
## ˆ
ρ)≈
## (1−ρ
## 2
## )
## 2
## T−1
- To get SE(
## ˆ
ρ)< 0.05: need T> 400 days
"You Need 2 Years of Data for 1 Good Correlation"
Memory: With 50 assets, need 50× 49/2 = 1225 correlations.
Reality: You have 252 days → 0.2 observations per parameter.
3.2 Shrinkage: The James-Stein Miracle
Problem: MLE for mean
## ˆ
μ =
## ̄
X has high variance when N is large.
Solution: Shrink toward common mean
## Core Formula
## ˆ
μ
## JS
## =
## ̄
## X +
## 
## 1−
## N− 2
## ∑
## X
## 2
i
## 
## (X−
## ̄
## X)
Why it works: Bias-variance tradeoff. In high dimensions, variance dominates MSE.
## Shrinkage Insight
"Always shrink high-dimensional estimates"
"Ledoit-Wolf for covariance, Bayesian for everything"
"Interview: ’Raw correlation matrix is noise—shrinkage is signal.’"
## 12© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 3.3 Quick Interview Cheat Sheet — Module 3
## Module 3: Parameter Risk > Market Risk
Core Concept: Your parameter estimates are more uncertain than the market itself.
Must-Know:
## •  SE(
## ˆ
ρ) =
## 1−ρ
## 2
## √
## T
-  Need T> N for covariance matrix invertibility
-  Ledoit-Wolf shrinkage constant: λ
## ∗
## =
π−c
π
where π = noise, c = signal
## Interview Triggers:
-  "Why correlation unstable?" → "Dimensionality: 1225 params, 252 days"
-  "How to stabilize?" → "Shrink to constant correlation or factor structure"
-  "When does MLE fail?" → "N/T> 0.1 (always in finance)"
## Desk Wisdom:
-  Never use raw sample covariance
-  Shrinkage beats MLE in finite samples
Common Trap: "Don’t say ’MLE is optimal’—that’s only asymptotically." (Markets don’t wait for∞)
Memory Aid: "Data matrix must be fat (T ≫ N) or world blows up."
Interviewer Is Testing: Can you compute effective sample size per parameter?
## Sample Size Doom Table
AssetsParametersMin Days Needed
## 1055550
## 50122512,250
## 100495049,500
## 500125,2501.25M
Reality: You have 252 days.
Conclusion: Dimensionality must be crushed.
The 3-Second Answer (Module 3)
Question: "Your 50-asset correlation matrix has eigenvalues from -0.2 to 5.0. Problem?"
Your opening line:
"Negative eigenvalues mean the matrix isn’t PSD—you have spurious correlations from overfitting. The small-
est eigenvalue is -0.2→ your covariance matrix is generating imaginary variances. Fix: Ledoit-Wolf shrinkage
toward diagonal or constant correlation."
Why this wins:
-  Immediately diagnoses the core problem (non-PSD)
-  Quantifies impact (imaginary variances)
-  Gives concrete solution (shrinkage)
Follow-up ready:
-  "How much shrinkage?" → Cross-validation or LW formula
-  "Alternative?" → Factor models (PCA), Graphical Lasso
-  "Impact on PnL?" → Hedge ratios become nonsensical
Red flag to avoid:
Never say: "Just use the sample matrix" (shows you want to blow up the desk)
## The Dimensionality Doom Formula:
## SE(
## ˆ
ρ) =
1− ρ
## 2
## √
## T− 3
## 13© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Quick Table for ρ = 0.5:
Days (T)
## SE(
## ˆ
ρ)95% CI Width
## 600.11± 0.22
## 2520.05± 0.10
## 10000.03± 0.06
Memory:  Need 250+ days for correlation±10% accu-
racy
Ledoit-Wolf Shrinkage (One-Liner):
λ
## ∗
## =
## ∑
i̸=j
## Var(
## ˆ
σ
ij
## )
## ∑
i̸=j
## (
## ˆ
σ
ij
## −
## ̄
σ)
## 2
Rule of thumb:  λ≈
## N
## T
when N ≪ T
Module 4: Regression Is a Model, Not a Fact
## Module Overview
What this module is about:  Regression is the most abused tool in quant finance.  Quants run it on every-
thing—factors, spreads, PnL—without checking if assumptions hold.
Why this matters: Faulty regression assumptions produce spurious "alpha" that evaporates when traded. All
static hedges derived from regression fail when correlations break.
What confusion this clears:
-  Why OLS fails with autocorrelated errors
-  Why endogeneity destroys causality
## •  Why R
## 2
is a dangerous drug
After this module, you should be able to answer:  “Why does my factor model’s beta change sign out-of-
sample?”
4.1 OLS Assumptions: Which Fail in Markets?
The OLS Checklist:
- E[ε] = 0 (true if drift adjusted)
-  Var(ε) = σ
## 2
(FALSE: heteroskedastic)
-  ε
t
## ⊥ X
t
(FALSE: endogeneity)
-  ε
t
⊥ ε
t−1
(FALSE: autocorrelation)
-  rank(X) = p (FALSE: multicollinearity)
## Core Formula
## ˆ
β
## OLS
## = (X
## ′
## X)
## −1
## X
## ′
y
When assumptions fail:  - Autocorr:  SE(
## ˆ
β) is wrong → false significance - Heterosked:
## ˆ
β is still consistent but
inefficient - Endogeneity:
## ˆ
β is biased and inconsistent → garbage
## 4.2 Endogeneity: The Causality Killer
## Definition: X
t
correlated with ε
t
(omitted variable bias)
FX Example:  - Regress EUR/USD returns on rate differential - Omitted:  ECB policy stance → rates and spot -
## Result:
## ˆ
β is biased upward
Test: Durbin-Wu-Hausman test for endogeneity
## 14© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 020406080100
## 2
## 1
## 0
## 1
## 2
## Residuals
## Good Residuals: No Pattern
## 020406080100
## 1.5
## 1.0
## 0.5
## 0.0
## 0.5
## 1.0
## 1.5
## Residuals
## Autocorrelated: Model Misspecified
## 020406080100
## Index
## 4
## 2
## 0
## 2
## 4
## Residuals
## Heteroskedastic: Vol Not Constant
## 21012
Theoretical quantiles
## 2
## 1
## 0
## 1
## 2
## Ordered Values
Q-Q Plot: Gaussian?
Figure 3: Regression Residual Patterns: Good vs Problems
## 15© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Endogeneity Risk
"Regression explains history, not causality"
"Instrumental variables or GTFO"
"Interview: ’Is rate differential exogenous? No—policy drives both rates and spot.’"
## 4.3 R
## 2
Is a Dangerous Drug
## Problem: R
## 2
always increases with more regressors
## Adjusted R
## 2
## :
## Core Formula
## ̄
## R
## 2
## = 1−
## (1− R
## 2
## )(n− 1)
n− p− 1
## Better: Out-of-sample R
## 2
## OOS
## = 1−
## ∑
## (y−
## ˆ
y
## OOS
## )
## 2
## ∑
## (y−
## ̄
y)
## 2
Reality check: Most factor models have R
## 2
## OOS
## < 0.1
## 4.4 Quick Interview Cheat Sheet — Module 4
## Module 4: Regression = Assumption Bomb
Core Concept: OLS assumes things markets violate daily.
Must-Know:
-  Autocorrelation → Use Newey-West HAC standard errors
-  Heteroskedasticity → Use White robust SE
-  Endogeneity → Use IV, 2SLS, or give up
## •  R
## 2
> 0.9 in-sample → R
## 2
## OOS
## < 0.1 (overfit)
## Interview Triggers:
-  "Why beta unstable?" → "Regime change, omitted variables"
-  "Why t-stats high but PnL low?" → "Autocorrelation inflates significance"
-  "How to test model?" → "Out-of-sample only, no peeking"
## Desk Wisdom:
-  Never trust regression without residual diagnostics
-  Plot ε
t
vs ε
t−1
—if you see pattern, OLS is dead
Common Trap: "Don’t say ’the factor is significant at 5%.’" (Significant̸= tradable)
Memory Aid: "Regression = pattern-matching, not causality."
Interviewer Is Testing: Can you smell spurious correlation?
## Residual Diagnostics Checklist
Plot these before trusting
## ˆ
β:
-  ε
t
vs time (trend?)
-  ε
## 2
t
vs time (heteroskedastic?)
-  ε
t
vs ε
t−1
## (autocorrelation?)
-  ε
t
vs X
t
## (endogeneity?)
If any show pattern→ OLS is invalid.
## 16© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

The 3-Second Answer (Module 4)
Question: "You regress EUR/USD returns on 10 factors. All t-stats > 3. Sharpe 2.0 in backtest. Live PnL is -5%.
## Why?"
Your opening line:
"You  overfitted  to  noise.With  10  factors  and  252  days,  you  have  24  degrees  of  freedom  per  parame-
ter—guaranteed false discovery. The t-stats are inflated by autocorrelation and heteroskedasticity. Live PnL is
the only real test."
Why this wins:
-  Immediately identifies overfitting (degrees of freedom argument)
-  Cites specific violations (autocorr, heterosked)
-  Dismisses in-sample stats (shows pragmatism)
Follow-up ready:
-  "How many factors?" →
## √
T rule: max
## √
252≈ 16 for 252 days
-  "Fix?" → Rid regression, LASSO, out-of-sample validation
-  "Better model?" → Fewer factors, more economic intuition
Red flag to avoid:
Never say: "Add more factors to improve fit" (shows you want to overfit)
## Regression Red Flag Decision Tree:
## Run Regression
## Residuals
white noise?
## Heterosked?
(Plot ε
## 2
t
## )
## Endogeneity?
(Corr(X, ε))
## Use
Robust SE
Use IV
or Kill
## No
## No
R² Penalty (Information Criterion):
AIC = 2p− 2 ln(
## ˆ
L)BIC = ln(T)· p− 2 ln(
## ˆ
## L)
Rule: If adding variable increases AIC, you’re overfitting
## Module 5: Time Series: Memory, Not Just Noise
## Module Overview
What this module is about:  Cross-sectional stats assume independence;  time series stats explicitly model
memory. Using the wrong toolkit destroys your analysis.
Why this matters:  Mean reversion tests, stationarity assumptions, and cointegration are the bedrock of stat
arb—99% of quants misuse them.
What confusion this clears:
-  Difference between stationary and non-stationary processes
-  Why unit root tests have low power
-  When "mean reversion" is spurious
After this module, you should be able to answer: “Why did my mean-reverting spread stop reverting?”
## 17© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

5.1 Stationarity vs Non-Stationarity
Stationary: Mean, variance constant over time
## Core Formula
## X
t
= μ + ε
t
## ,ε
t
∼ WN(0, σ
## 2
## )
Non-stationary (Unit Root):
## Core Formula
## X
t
## = X
t−1
+ ε
t
(Random Walk)
Near-unit root:
## Core Formula
## X
t
= φX
t−1
+ ε
t
## ,φ = 0.99
Problem: Near-unit root looks mean-reverting in-sample but trends out-of-sample.
## 5.2 Mean Reversion Tests
Augmented Dickey-Fuller (ADF):
## Core Formula
## ∆X
t
= α + γX
t−1
## +
p
## ∑
i=1
δ
i
## ∆X
t−i
+ ε
t
Null hypothesis: γ = 0 (unit root)
Alternative: γ< 0 (mean reversion)
Power problem: ADF has 20% power for φ = 0.95 with T = 252.
"Mean Reversion Tests Are Weak"
"Memory: ADF fails when you need it most—near unit root."
## 5.3 Cointegration: The Only Real Mean Reversion
Definition: Two series X
t
## , Y
t
are I(1) (unit root), but linear combination Z
t
## = X
t
− βY
t
is I(0) (stationary).
Stat arb: Trade Z
t
when it deviates from equilibrium.
Test: Engle-Granger two-step: 1. Regress X
t
= α + βY
t
+ ε
t
- Test ε
t
for stationarity (ADF)
## Cointegration Risk
"’Mean reversion’ without cointegration is noise"
"Half-life > 30 days = untradable"
"Interview: ’My spread’s half-life doubled—regime shift broke cointegration.’"
## 18© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 0255075100125150175200
## Time
## 0.06
## 0.04
## 0.02
## 0.00
## 0.02
## 0.04
## 0.06
## Value
## Mean Reverting
## Constant Var
## STATIONARY (AR(0.7))
ADF: Reject Null
## 0255075100125150175200
## Time
## 0.00
## 0.05
## 0.10
## 0.15
## 0.20
## 0.25
## 0.30
## 0.35
## Value
## No Mean Reversion
## Exploding Var
UNIT ROOT (Random Walk)
ADF: Fail to Reject
Stationarity vs Unit Root: ADF Test
Figure 4: Stationarity vs Unit Root: ADF Test Visualization
## 5.4 Quick Interview Cheat Sheet — Module 5
## Module 5: Memory Economics
Core Concept: Time series have persistence—model it or die.
Must-Know:
-  ADF null = unit root (fail to reject = non-stationary)
-  Half-life =− ln(2)/ ln(φ)
-  Cointegration requires ε
t
stationary
## Interview Triggers:
-  "Spread stopped reverting?" → "Cointegration broke, regime shift"
-  "How to trade mean reversion?" → "Only if cointegrated AND half-life < 20 days"
-  "ADF p-value = 0.06?" → "Not mean-reverting at 5%—don’t trade it"
## Desk Wisdom:
-  90% of "mean-reverting" spreads are spurious
-  Test on rolling window—if β changes, it’s noise
Common Trap: "Don’t trade a spread because ’it looks mean-reverting’." (Need statistical proof)
Memory Aid: "Stationary = returns to mean. Cointegrated = returns to relationship."
Interviewer Is Testing: Can you distinguish spurious regression from cointegration?
## 19© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Half-Life Rule of Thumb
## Half-life =
− ln(2)
ln|φ|
## Tradability:
•< 10 days: Excellent
-  10-20 days: Good
-  20-30 days: Marginal
•> 30 days: Untradable (sharpe too low)
## Interview:
"My spread’s half-life is 15 days → expected return per trade = 1%, Sharpe  1.5"
The 3-Second Answer (Module 5)
Question: "You find a spread with ADF p-value = 0.03 (stationary). Live trading loses money. Why?"
Your opening line:
"ADF tests in-sample stationarity.  Live data is out-of-sample.  The spread likely has a near-unit root (φ =
0.97) that looked mean-reverting in backtest but trends live. Check half-life and rolling ADF—if φ varies over
time, the relationship is unstable."
Why this wins:
-  Distinguishes in-sample from out-of-sample (key insight)
-  Identifies near-unit root trap (common failure mode)
-  Gives diagnostic (half-life, rolling test)
Follow-up ready:
-  "How to fix?" → Only trade if half-life < 20 days on rolling window
-  "Better test?" → KPSS (stationarity as null) or variance ratio
-  "Alternative?" → Use cointegration on multiple series (Johansen)
Red flag to avoid:
Never say: "ADF p-value < 0.05 means it’s tradable" (shows you don’t understand power)
Half-Life Visual Guide:
## Days
## Deviation
ε
## 0
ε
## 0
## /2
ε
## 0
## /4
## HL
## 10d20d
## HL =
− ln(2)
ln|φ|
Engle-Granger 2-Step Mnemonic: "RATE"
## 1.  Regress: Y
t
= α + βX
t
+ ε
t
-  ADF test on residuals ε
t
-  Test:  p< 0.05? (cointegrated)
-  Estimate half-life: HL =− ln(2)/ ln|φ|
## 20© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Module 6: Volatility Is Not a Parameter
## Module Overview
What this module is about:  Volatility is treated as a number to estimate.  It is a stochastic process that must
be forecasted. Using realized vol as a parameter is like driving using your rearview mirror.
Why this matters:  GARCH models fit beautifully but forecast poorly.   Understanding why separates risk
managers from traders.
What confusion this clears:
-  Realized vs implied vs conditional volatility
-  Why GARCH works in-sample and fails out-of-sample
-  How to trade vol of vol
After this module,  you should be able to answer:  “Why does my GARCH(1,1) forecast underperform a
naive moving average?”
6.1 Three Types of Volatility
TypeDefinitionUse CaseProblem
## Realized
q
## 1
## T
## ∑
r
## 2
t
BacktestingLooks backward
## Impliedσ
## BS
from optionsPricingRisk premium embedded
## Conditionalσ
t|t−1
from modelForecastingModel risk
Table 7: Volatility taxonomy: each answers a different question
## Core Formula
σ
## 2
realized,T
## =
## 1
## T
## T
## ∑
t=1
r
## 2
t
(Backward-looking)
## Core Formula
σ
## 2
t+1|t
= ω + αr
## 2
t
+ βσ
## 2
t
(Forward-looking)
6.2 GARCH: The Volatility Workhorse
## GARCH(1,1) SDE:
## Core Formula
σ
## 2
t
= ω + αε
## 2
t−1
+ βσ
## 2
t−1
Persistence: α + β (typically 0.95-0.99) Half-life: − ln(0.5)/ ln(α + β)
Why GARCH fails out-of-sample: 1. Parameters drift (regime changes) 2. Gaussian assumption underestimates
tails 3. Mean reversion too slow in crisis
GARCH Risk
"GARCH is slow to react to shocks"
"After a jump, takes days to mean-revert"
## 21© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

"Interview: ’I use GARCH for baseline, overlay jump filter for tails.’"
## 0.04
## 0.02
## 0.00
## 0.02
## 0.04
## Returns
Returns with Volatility Clustering
## High Vol Regimes
## 0100200300400500
## Days
## 0.008
## 0.010
## 0.012
## 0.014
## 0.016
## 0.018
## Volatility
## Volatility Clustering: High Vol  More High Vol
## Realized Vol (20d)
## True Vol
Figure 5: GARCH Volatility Clustering: Market Reality
## 6.3 Quick Interview Cheat Sheet — Module 6
## Module 6: Vol = Stochastic Process
Core Concept: Volatility is not a parameter—it’s a conditional forecast.
Must-Know:
-  Realized vol is backward, conditional is forward
-  GARCH persistence α + β≈ 0.97
-  Vol of vol ξ drives option smile convexity
## Interview Triggers:
-  "GARCH vs realized?" → "GARCH smooths, realized jumps"
-  "Why GARCH fails?" → "Parameters not robust, slow crisis response"
-  "How to trade vol?" → "Sell realized, buy conditional (var swap)"
## Desk Wisdom:
-  Use GARCH for term structure, not tails
-  Overlay jump-diffusion for policy events
Common Trap: "Don’t use GARCH σ
t
as if it’s observed." (It’s model output)
Memory Aid: "Realized = rearview, conditional = GPS, implied = market’s GPS."
Interviewer Is Testing: Can you forecast distribution not just point estimate?
## 22© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Vol Forecast Scorecard
Rank models by out-of-sample log-likelihood:
GARCH : baseline
GJR-GARCH : +0.05 (asymmetric)
EGARCH : +0.03 (log vol)
Realized GARCH : +0.10 (uses intraday)
## Machine Learning : +0.02 (overfits)
## Interview:
"More complexity adds 0.02 log-lik but 0.10 parameter risk."
The 3-Second Answer (Module 6)
Question:  "Forecast vol for next week:  1-week realized = 15%, GARCH = 12%, ATM vol = 18%.  Which do you
use?"
Your opening line:
"I use GARCH (12%) as baseline, scale by ATM/implied (18%) as risk premium multiplier. Realized (15%) is
backward-looking. The trade: if GARCH « ATM, vol is rich→ sell options. If GARCH » ATM, vol is cheap→
buy."
Why this wins:
-  Distinguishes backward/forward/market-implied
-  Gives trading rule (vol rich/cheap)
-  References risk premium (sophisticated)
Follow-up ready:
-  "How to blend?" → σ
blend
= wσ
## GARCH
+ (1− w)σ
## ATM
-  "What weight?" → w≈ 0.7 based on out-of-sample MSE
-  "Edge?" → Buy when σ
## GARCH
> σ
## ATM
+ 2 vol pts
Red flag to avoid:
Never say: "I use realized vol for forecast" (shows you don’t understand prediction)
GARCH(1,1) Parameter Health Check:
σ
## 2
t
=   ω
## |{z}
## ≥0
+   α
## |{z}
## ∈[0,1]
ε
## 2
t−1
+   β
## |{z}
## ∈[0,1]
σ
## 2
t−1
## Check
ConditionRed Flag
## Non-negativityω> 0ω< 0
Stationarityα + β< 1α + β≥ 1
Mean reversion
α + β< 0.99α + β> 0.99
Reaction speedα> 0.05α< 0.02
## Module 7: Correlation Is Conditional, Not Structural
## Module Overview
What this module is about: Static correlation matrices are the most dangerous object on a trading floor. They
assume relationships are permanent—they’re not.  Correlation is a regime-dependent, time-varying, crisis-
exploding parameter.
Why this matters:  Every multi-asset portfolio, FX triangle, and quanto model assumes correlation stability.
When it breaks, diversification vanishes and you have 10x leverage on a single bet.
## 23© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

What confusion this clears:
-  Why correlation → 1 in crisis
-  Why rolling windows are too slow
-  How to model correlation as stochastic
After this module, you should be able to answer:  “Why does my 50-asset portfolio VaR spike 5x during
stress?”
## 7.1 Correlation Regimes
RegimeTypical ρDriverExample
Normal0.2-0.4EconomicsEquity-factor corr
Risk-on0.5-0.7Beta exposureEM FX correlation
Crisis0.9-1.0Flight to qualityCOVID March 2020
Policy-0.5 to +0.5Central bankSNB 2015 EUR/CHF
Table 8: Correlation regimes: static matrix assumes only row 1
## Core Formula
ρ
ij,t
= ρ
normal
ij
## · 1
calm
+ ρ
crisis
ij
## · 1
stress
Switching: Markov chain with low persistence → correlation jumps
## EUR/USDGBP/USDJPY/USD
## EUR/USD
## GBP/USD
## JPY/USD
## 10.2-0.1
## 0.210.3
## -0.10.31
## Normal Regime
## 0.2-0.3
## EUR/USDGBP/USDJPY/USD
## EUR/USD
## GBP/USD
## JPY/USD
## 10.85-0.8
## 0.851-0.75
## -0.8-0.751
## Crisis Regime
1.0 (Diversification Death)
## 0.0
## 0.2
## 0.4
## 0.6
## 0.8
## 1.0
## 0.8
## 0.6
## 0.4
## 0.2
## 0.0
## 0.2
## 0.4
## 0.6
## 0.8
## 1.0
Correlation Matrix: Normal vs Crisis
Figure 6: Correlation Matrix: Normal vs Crisis Regime
Correlation Regime Detection (Real-Time):
## Regime
t
## =
## 
## 
## 
## 
## 
## Crisisif
## ̄
ρ
## 5d
## >
## ̄
ρ
## 60d
## + 0.3
## Calmif
## ̄
ρ
## 5d
## <
## ̄
ρ
## 60d
## − 0.1
Normal    otherwise
Interview: "I monitor 5d vs 60d correlation spread daily"
## 24© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

7.2 Dynamic Conditional Correlation (DCC)
DCC-GARCH: Model correlation as GARCH process
## Core Formula
## Q
t
= (1− a− b)
## ̄
Q + aε
t−1
ε
## ′
t−1
+ bQ
t−1
## Core Formula
## R
t
## =
## ̃
## Q
## −1
t
## Q
t
## ̃
## Q
## −1
t
Pros: Captures correlation clustering
Cons: Slow to react, still Gaussian
## Correlation Risk
"Correlation is a random variable, not a parameter"
"Hold 20% reserve for ρ instability"
"Interview: ’I model ρ
t
as DCC, stress ρ→ 0.9 for reserves.’"
## 7.3 Quick Interview Cheat Sheet — Module 7
## Module 7: Correlation = Regime Variable
Core Concept: ρ is conditional on volatility regime.
Must-Know:
-  Correlation  1 in crisis (flight to quality)
-  DCC captures clustering but lags
-  Tail correlation̸= linear correlation
## Interview Triggers:
-  "Why diversification fail?" → "ρ → 1, you’re leveraged 5x"
-  "How to model ρ?" → "DCC, regime-switching, copulas"
-  "Correlation hedge?" → "Basket options, not static matrix"
## Desk Wisdom:
-  Stress test ρ at 0.9 for all pairs
-  Use 1-month rolling, not 1-year (slow)
Common Trap: "Don’t use historical ρ from calm period for stress." (It’s useless)
Memory Aid: "Correlation = fear gauge. High vol = high ρ."
Interviewer Is Testing: Do you know when correlation breaks?
Tail Correlation vs Linear Correlation
Linear: ρ =
Cov(X,Y)
σ
## X
σ
## Y
Tail: λ
q
= Pr(Y< F
## −1
## Y
(q)|X< F
## −1
## X
## (q))
For q = 0.05:
-  Linear ρ = 0.3 → Tail λ = 0.15 (asymptotic independence)
-  Linear ρ = 0.8 → Tail λ = 0.60 (asymptotic dependence)
## Interview:
"For risk management, tail correlation matters—not linear ρ."
## 25© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

The 3-Second Answer (Module 7)
Question: "Your 10-asset portfolio has average ρ = 0.3. Stress test shows VaR 5x higher. Why?"
Your opening line:
"Average ρ hides regime risk.  In stress, ρ→ 0.9 for 8 out of 10 assets.  Your portfolio becomes 90% correlated
→ effective diversification drops from 10 to 1.5 assets. VaR scales by
p
## N
effective
, so 5x spike."
Why this wins:
-  Translates correlation change to diversification collapse
-  Quantifies effective assets (1.5 vs 10)
-  Gives VaR scaling (shows risk system intuition)
Follow-up ready:
-  "How to hedge?" → Buy correlation swaps or basket vol
-  "How to model?" → Regime-switching correlation matrix
-  "Reserve?" → Hold 20% of notional for correlation blow-up
Red flag to avoid:
Never say: "Correlation is stable in crisis" (shows you’ve never lived through one)
Effective Number of Assets (Diversification):
## N
eff
## =
## N
## 1 + (N− 1)
## ̄
ρ
## Quick Reference:
## N
## ̄
ρN
eff
## Diversification
100.15.3Good
## 10
0.52.0Weak
500.33.4Poor
500.81.2Dead
Module 8: Hypothesis Testing Is Mostly Useless (If Misused)
## Module Overview
What this module is about:  Finance misuses p-values more than any other field.  Hypothesis testing was
designed for controlled experiments, not non-stationary market data.
Why this matters:  A "significant" factor with p < 0.01 typically has zero out-of-sample Sharpe.  Statistical
significance̸= economic significance.
What confusion this clears:
-  p-value fallacy
-  Multiple testing bias
-  Why "reject null" is meaningless in finance
After this module, you should be able to answer: “Why are 99% of published factors false positives?”
8.1 p-Value Fallacy
Definition: Pr(data|null) not Pr(null|data)
Finance error:  - Run 1000 cross-sectional regressions - Find 50 with p < 0.05 - Claim "5% significant" (WRONG:
you ran 1000 tests)
Truth: Expected false discoveries = m· α where m = tests
## 8.2 Multiple Testing: The Factor Zoo
Problem: 400+ factors published, most are noise.
## 26© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 0.00.20.40.60.81.0
p-values
## 0
## 5
## 10
## 15
## 20
## 25
Number of Tests
## False Positives: 52
## True Positives: 27
## False Discovery Rate: 65.8%
## Multiple Testing: 1000 Factor Tests, 50 Real Signals
True Nulls (Noise)
## True Signals
## = 0.05 Threshold
## Figure 7: Multiple Testing Problem: 1000 Factor Tests, 50 Real Signals
## 27© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Bonferroni correction:
## Core Formula
α
adj
## =
α
m
For m = 400: - α = 0.05 → α
adj
= 0.000125 - Need t-stat > 3.5, not 1.96
False Discovery Rate (FDR):
## Core Formula
## FDR = E
## 
## False Positives
## Total Rejections
## 
Rule: FDR > 0.3 → junk science
## Multiple Testing Risk
"5% significance with 100 tests = 5 false positives"
"Hold-out validation is the only cure"
"Interview: ’I use Benjamini-Hochberg FDR control, not raw p-values.’"
## 8.3 Quick Interview Cheat Sheet — Module 8
Module 8: p-Values Are Not Answers
Core Concept: Statistical significance is irrelevant—economic significance (Sharpe) matters.
Must-Know:
-  p < 0.05 with 100 tests → 5 false positives expected
-  Bonferroni: α
adj
= α/m
-  FDR control > raw p-values
## Interview Triggers:
-  "Factor significant at 1%?" → "How many factors tested?"
-  "Why factors fail live?" → "Multiple testing, p-hacking"
-  "How to validate?" → "Hold-out + out-of-sample Sharpe"
## Desk Wisdom:
-  Never trade a factor with t-stat < 3.5 if screened from many
-  Out-of-sample Sharpe > 0.5 matters more than p < 0.01
Common Trap:  "Don’t say ’statistically significant’ without saying ’economically significant’." (They’re
different)
Memory Aid: "p-value = probability of fooling yourself."
Interviewer Is Testing: Can you smell p-hacking?
## 28© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Multiple Testing Doom Table
Tests (m)Raw αBonferroni α
adj
## 10.050.050
## 100.050.005
## 1000.050.0005
## 10000.050.00005
Reality: Asset management tests 1000s of signals.
Conclusion: Need t-stat > 4 to be believable.
The 3-Second Answer (Module 8)
Question: "A paper finds a factor with t-stat = 3.0 (p < 0.003). Is it tradable?"
Your opening line:
"Only if it’s one of a few hypotheses tested. If they screened 100 factors, the Bonferroni-adjusted t-stat threshold
is 3.8. A t-stat of 3.0 is expected noise. I need to see out-of-sample Sharpe > 0.5, not in-sample t-stat."
Why this wins:
-  Immediately applies multiple testing correction
-  Gives adjusted threshold (3.8)
-  Shifts to economic metric (Sharpe)
Follow-up ready:
-  "How many tests?" → Ask directly
-  "Hold-out test?" → Need 20% of sample untouched
-  "Robust?" → Test on international data, different periods
Red flag to avoid:
Never say: "p < 0.05 means it’s real" (shows you don’t understand false discovery)
## Multiple Testing Formula Card:
Expected False Positives = m× α
## FDR =
## False Positives
## Total Rejections
## =
m
## 0
· α
## R
## Bonferroni Quick Table:
Tests (m)Required pRequired t-stat
## 10.0501.96
## 10
## 0.0052.81
## 1000.00053.48
## 10000.000054.06
Module 9: Forecasting vs Risk Estimation
## Module Overview
What this module is about: Forecasting aims to be right (minimize MSE). Risk estimation aims to be conser-
vative (cover tails). Using a forecasting model for risk is like using a scooter for a tank.
Why this matters: VaR models use volatility forecasts, but volatility is optimized for accuracy—not for cap-
turing tail events. This creates systematic VaR breaches.
What confusion this clears:
-  Why GARCH VaR fails in crisis
-  How to forecast densities, not just vol
-  Why risk models must be biased (conservative)
## 29© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

After this module, you should be able to answer: “Why does my VaR model breach 10 days in a row during
stress?”
9.1 Forecasting Accuracy vs Risk Coverage
Forecasting loss: L = (y
t+1
## −
## ˆ
y
t+1
## )
## 2
## (symmetric)
Risk estimation loss: L =
## (
## (y
t+1
## −
## ˆ
q
α
## )
## 2
if y
t+1
## <
## ˆ
q
α
## 0otherwise
## (asymmetric)
Implication: Risk models must be biased high to avoid breaches.
## 9.2 Density Forecasting: The Real Goal
Point forecast:
## ˆ
y
t+1
Density forecast:  p(y
t+1
## |F
t
## )
## Evaluation: Log-likelihood
## Core Formula
logL =
## T
## ∑
t=1
log p(y
t
## |F
t−1
## )
Better: CRPS (Continuous Ranked Probability Score) evaluates full density.
9.3 Conditional VaR (CoVaR) and Expected Shortfall
VaR: q
α
## = F
## −1
## (α)
## Expected Shortfall:
## Core Formula
## ES
α
= E[Y|Y< q
α
## ] =
## 1
α
## Z
q
α
## −∞
y f (y)dy
Advantage: ES is coherent (subadditive), VaR is not.
VaR Failure
"VaR ignores tail shape"
"ES captures severity of breaches"
"Interview: ’I report ES, not VaR—regulatory minimum.’"
## 30© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 9.4 Quick Interview Cheat Sheet — Module 9
## Module 9: Risk̸= Forecast
Core Concept: Risk models must be conservative, not accurate.
Must-Know:
-  VaR breaches should be < 1% (250 days → 2-3 breaches)
-  ES is subadditive; VaR is not
-  Density forecast > point forecast
## Interview Triggers:
-  "VaR breached 5 days?" → "Model not conservative enough"
-  "How to improve?" → "Increase vol forecast by 20% buffer"
-  "ES vs VaR?" → "ES is coherent, captures tail shape"
## Desk Wisdom:
-  Add 20% reserve to volatility forecast
-  Stress vol-of-vol ξ 2x normal
Common Trap: "Don’t minimize MSE for risk models." (Minimize breaches, not accuracy)
Memory Aid: "Forecast = hit bullseye. Risk = don’t miss board."
Interviewer Is Testing: Do you understand loss function asymmetry?
## Risk Model Calibration
Backtesting VaR:
-  Kupiec test: LR =−2 ln
## 
(1− p)
## T−N
p
## N
## (1−N/T)
## T−N
## (N/T)
## N
## 
∼ χ
## 2
## (1)
-  Accept if breaches N ∈ [ pT− 1.96
p
p(1− p)T, pT + 1.96
p
p(1− p)T]
## Interview:
"VaR 99% breached 8 times in 250 days → 3.2% breach rate → p-value < 0.01 → model rejected"
The 3-Second Answer (Module 9)
Question: "Your GARCH VaR at 99% is breached 10 days in a row during crisis. Model broken?"
Your opening line:
"Yes.  VaR assumes conditional coverage—breaches should be independent.  10 in a row shows clustering of
exceedances (Christoffersen test).  The model’s volatility forecast is too low and too slow.  I need to increase
conditional vol by 30% and add a jump component."
Why this wins:
-  Cites specific test (Christoffersen)
-  Identifies two failures: level and speed
-  Gives fix (increase vol + add jumps)
Follow-up ready:
-  "How to adjust?" → σ
adj
= σ
## GARCH
× (1 + stress buffer)
-  "What buffer?" → 20-30% based on historical breach clustering
-  "Alternative?" → Use filtered historical simulation (non-parametric)
Red flag to avoid:
Never say: "VaR breaches are expected in crisis" (shows you don’t understand conditional coverage)
## Loss Function Asymmetry:
## L
forecast
## = (y−
## ˆ
y)
## 2
vsL
risk
## =
## (
(y− q
α
## )
## 2
if y< q
α
## 0otherwise
## 31© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Crisis Playbook: The 3 Ds (Statistics Edition)
## DE-RISK
Cut position size
by 50% immediately
## DE-LEVERAGE
Reduce exposure
to 1/3 normal limits
## DEFEND
Hold 2-3× reserves
## Assume      1
TRIGGER CONDITIONS (Any 2 = Activate 3Ds)
## Correlation  50%
## Volatility  2×
Param drift > 20%
3 consecutive VaR breaches
Liquidity dries up
Policy uncertainty
Residual PnL > 5% for 3 days
Model assumptions violated
No clear hedge
Figure 8: Crisis Playbook: The 3 Ds (Statistics Edition)
VaR Backtesting (Kupiec Test):
LR =−2 ln
## 
(1− p)
## T−N
p
## N
## (1− N/T)
## T−N
## (N/T)
## N
## 
∼ χ
## 2
## (1)
Reject if LR > 3.84  at 5% level
## 32© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

One-Pager Cheat Sheets (Print and Laminate)
## Card 1: Crisis Mode Activation
## CRISIS MODE - ACTIVATE IMMEDIATELY
Triggers (Any 2 = Crisis):
□  VaR breach 3 consecutive days
□  Correlation ↑ 50% in 5 days
□  Volatility > 2× trailing 60d avg
□  Liquidity (bid-ask) > 3× normal
□  Residual PnL > 5% for 2 days
## □  News: "unprecedented", "crisis", "contagion"
Actions (Execute within 1 hour):
-  Cut positions by 50%
-  De-leverage: 1/3 normal limits
-  Increase reserves: 3× cash buffer
-  Assume  = 0.9 for all pairs
-  Notify CRO and risk committee
-  Switch to manual risk approval
Do NOT:
-  Trust your models (they’re calibrated to calm markets)
-  Add positions ("doubling down")
-  Assume "mean reversion" (crisis can last months)
## Card 2: Daily Model Health Check (5 Minutes)
## DAILY HEALTH CHECK
## Morning Checklist:
-  Parameter drift: ∥
## ˆ
θ
t
## −
## ˆ
θ
t−1
## ∥< 0.05?□
-  Residual PnL:|ε
t
## |< 3%?□
-  VaR breach: None in last 5 days?□
-  Correlation: max
ij
## |
## ˆ
ρ
ij
## |< 0.75?□
-  Vol spike: σ
t
## /σ
t−60
## < 1.5?□
-  Liquidity: Bid-ask < 2× normal?□
If any box unchecked:
-  1 fail → Investigate (30 min deep dive)
-  2 fails → Reduce size by 30%
-  3+ fails → Crisis mode (see Card 1)
## 33© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Card 3: Interview Emergency Phrases
## INTERVIEW PHRASES
When stuck, use these:
-  "That’s a great question. Let me think about the economic intuition first..."
-  "I’d want to check parameter stability before trusting that result."
-  "The residual PnL would tell us if this model is actually working."
-  "In-sample that looks good, but I care about walk-forward performance."
-  "I don’t recall the exact formula, but I can derive it from [X]."
-  "Let me work through a simple example to build intuition."
-  "That assumes [X]—if violated, we’d need [Y] instead."
-  "I’d validate that with a bootstrap before making a trading decision."
Never say:
-  "I don’t know" (say "Let me think through it")
-  "The market is wrong" (you’re wrong)
-  "This always works" (nothing always works)
-  "Trust the model" (trust the residuals)
Module 10: Bayesian Thinking for Quants (Without Religion)
## Module Overview
What this module is about: Bayesian thinking is a mental model, not just MCMC. It’s about updating beliefs
with data, not about priors vs frequentism wars.
Why this matters: Markets update continuously. Your prior is yesterday’s posterior. Frequentist p-values are
irrelevant—what matters is predictive distribution.
What confusion this clears:
-  Prior as regularization, not belief
-  Why shrinkage is Bayesian
-  How to think in posteriors
After this module, you should be able to answer: “Why is ridge regression Bayesian?”
## 10.1 Prior = Regularization
Bayesian update:
## Core Formula
p(θ|y)
## |{z}
## Posterior
∝   p(y|θ)
## |
## {z}
## Likelihood
· p(θ)
## |
## {z}
## Prior
Ridge regression:
## Core Formula
## ˆ
β
ridge
= arg min∥y− Xβ∥
## 2
+ λ∥β∥
## 2
Equivalence: Ridge = Gaussian prior β∼N (0, τ
## 2
I) with λ = σ
## 2
## /τ
## 2
## .
## 34© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

"Prior = Shrinkage = Bias-Variance Tradeoff"
"Memory: Bayesian is just a disciplined way to regularize."
## 10.2 Conjugate Priors: Analytical Updates
Beta-Bernoulli: - Prior: θ ∼ Beta(α, β) - Likelihood: y∼ Bernoulli(θ) - Posterior: θ|y∼ Beta(α +
## ∑
y, β + n−
## ∑
y)
Application:  Estimate probability of VaR breach - Prior:  θ ∼  Beta(2, 98) (2% breach rate) - Data:  5 breaches in
250 days - Posterior: θ|y∼ Beta(7, 343) → mean = 2.0%
## Bayesian Update
"Prior + Likelihood = Posterior"
"Yesterday’s posterior is today’s prior"
"Interview: ’I update correlation priors daily with new data.’"
## 10.3 Quick Interview Cheat Sheet — Module 10
## Module 10: Bayesian = Updating Machine
Core Concept: Bayesian thinking is about sequential updating, not philosophical wars.
Must-Know:
## •  Prior× Likelihood = Posterior
-  Ridge = Gaussian prior
-  Beta prior for probabilities, Dirichlet for weights
## Interview Triggers:
-  "Why Bayesian?" → "Natural for sequential data, regularizes"
-  "Prior choice?" → "Use prior as shrinkage target"
-  "Frequentist vs Bayesian?" → "Both are tools; Bayesian updates better"
## Desk Wisdom:
-  Use empirical Bayes: estimate prior from data
-  Conjugate priors for speed
Common Trap: "Don’t get into philosophy debates." (Use what works)
Memory Aid: "Bayes = learning. Prior = old knowledge."
Interviewer Is Testing: Can you update beliefs with data?
## Empirical Bayes Shortcut
Problem: Need prior but don’t want to choose.
Solution: Estimate prior hyperparameters from data.
## Example:
-  Data: N correlation estimates
## ˆ
ρ
i
-  Prior: ρ
i
∼N (μ, σ
## 2
## )
## •  Estimate:
## ˆ
μ =
## 1
## N
## ∑
## ˆ
ρ
i
## ,
## ˆ
σ
## 2
## = Var(
## ˆ
ρ
i
## )− SE
## 2
## Interview:
"Empirical Bayes lets data tell you how much to shrink."
## 35© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

The 3-Second Answer (Module 10)
Question: "Why is ridge regression Bayesian?"
Your opening line:
"Ridge penalty λ∥β∥
## 2
equals Gaussian prior  β ∼ N (0, τ
## 2
I).   The posterior mode is ridge solution:
## ˆ
β =
## (X
## ′
X + λ I)
## −1
## X
## ′
y.  Bayesian gives probability distribution; ridge gives point estimate—but same regulariza-
tion."
Why this wins:
-  Shows mathematical equivalence (deep)
-  Connects penalty to prior (intuition)
-  Distinguishes posterior mode from full posterior
Follow-up ready:
-  "What prior for LASSO?" → Laplace (double exponential)
-  "Advantage of full Bayes?" → Posterior predictive intervals
-  "When not Bayesian?" → When prior is wrong and data is thin
Red flag to avoid:
Never say: "Bayesian is subjective" (shows you don’t understand priors as regularization)
## Conjugate Prior Quick Reference:
LikelihoodPriorPosterior
Bernoulli( p)Beta(α, β)Beta(α +
## ∑
y, β + n−
## ∑
y)
Normal(μ, σ
## 2
## )
## Normal(μ
## 0
, τ
## 2
)Normal(μ
## 1
, τ
## 2
## 1
## )
μ unknownμ
## 1
## =
τ
## −2
μ
## 0
## +nσ
## −2
## ̄
x
τ
## −2
## +nσ
## −2
Memory: Prior precision + Data precision = Posterior precision
Module 11: Model Risk as a Statistical Object
## Module Overview
What this module is about: Model risk is usually hand-waved.  It can be quantified: parameter uncertainty,
specification error, and instability.
Why this matters: Regulators require model risk capital (FRTB). If you can’t quantify it, you can’t manage it.
What confusion this clears:
-  How to propagate parameter uncertainty to PnL
-  Why ensemble models beat single models
-  How to compute model reserves
After this module, you should be able to answer: “How much capital should I hold for model risk?”
## 11.1 Parameter Uncertainty Propagation
## Problem:
## ˆ
θ has varianceΣ
## ˆ
θ
. This creates PnL variance.
Solution: Delta method
## Core Formula
Var(V(
## ˆ
θ))≈∇
θ
## V(θ)
## ′
## Σ
## ˆ
θ
## ∇
θ
## V(θ)
Example: Heston price V(ρ, ξ) - Var(
## ˆ
ρ) = 0.01, Var(
## ˆ
ξ) = 0.04, Cov = 0.02 - ∂V/∂ρ = 5, ∂V/∂ξ = 2 - Var(V) =
## 5
## 2
## · 0.01 + 2
## 2
## · 0.04 + 2· 5· 2· 0.02 = 0.25 + 0.16 + 0.40 = 0.81
## 36© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Parameter Uncertainty
"Calibrated θ is random"
"Delta method → PnL variance"
"Interview: ’I hold 2% reserve for parameter uncertainty.’"
## 11.2 Model Instability Metrics
Parameter drift:
## Core Formula
## Drift
t
## =∥
## ˆ
θ
t
## −
## ˆ
θ
t−1
## ∥
Ensemble dispersion:
## Core Formula
σ
## 2
model
## =
## 1
## K
## K
## ∑
k=1
## (V
k
## −
## ̄
## V)
## 2
Rule: If σ
model
> 0.05· V, hold 10% reserve.
11.3 Ensemble Modeling: The Wisdom of Crowds
Idea: Average K models to reduce variance
## Core Formula
## ̄
## V =
## 1
## K
## K
## ∑
k=1
## V(
## ˆ
θ
k
## )
Why it works: - Bias: Bias(
## ̄
## V) =
## 1
## K
## ∑
Bias(V
k
## ) - Variance: Var(
## ̄
## V) =
σ
## 2
## K
(if independent)
"Ensemble = Bagging for Models"
"Memory: If models are diverse, ensemble beats any single."
## 37© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Parameter Uncertainty
## 35%
Spec. Error (Misspec)
## 30%
## Estimation Error
## 20%
## Implementation Error
## 10%
## Data Quality
## 5%
## Total Reserve Required:
$12M (12% of notional)
## Breakdown:
Param Risk: $4.2M
Spec Risk: $3.6M
Est Risk: $2.4M
Impl Risk: $1.2M
Data Risk: $0.6M
## Model Risk Decomposition
$100M Exotic Book
## Figure 9: Model Risk Decomposition: Capital Requirements
## 38© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 11.4 Quick Interview Cheat Sheet — Module 11
## Module 11: Model Risk = Measurable
Core Concept: Model risk is parameter uncertainty + specification error.
Must-Know:
-  Delta method for parameter risk
-  Ensemble dispersion for model risk
-  Reserve = 5-20% of notional
## Interview Triggers:
-  "Model risk capital?" → "Delta method on parameters"
-  "Stability metric?" → "Parameter drift, ensemble spread"
-  "How to reduce?" → "Ensemble, regularization"
## Desk Wisdom:
-  Model risk reserve = largest residual PnL in last year
-  Document model limitations (regulator requirement)
Common Trap: "Don’t ignore model risk." (It’s 30-50% of total risk in exotic books)
Memory Aid: "Model risk = what you don’t know you don’t know."
Interviewer Is Testing: Can you quantify model risk?
## Model Risk Reserve Formula
Parameter risk:
## Reserve
param
= z
## 0.99
## ·
q
## ∇V
## ′
## Σ
## ˆ
θ
## ∇V
Specification risk:
## Reserve
spec
## =max
t∈last year
|Residual
t
## |
## Total:
## Reserve
total
## = Reserve
param
## + Reserve
spec
## Interview:
"I hold 5% for param risk + 10% for spec risk = 15% total."
The 3-Second Answer (Module 11)
Question: "How much capital for model risk on a 100Mexoticbook?”
Your opening line:
"Three components:  1) Parameter uncertainty:  Reserve =  2· SE(
## ˆ
θ)·∇
θ
V ≈  $3M.  2) Specification error:
max residual PnL last year = $5M. 3) Ensemble dispersion:  10% of value.  Total reserve = $10M (10% of
notional)."
Why this wins:
-  Decomposes into three measurable components
-  Quantifies each (shows you know formulas)
-  Gives total (operational answer)
Follow-up ready:
-  "How to reduce?"→ Shrink parameters, ensemble models
-  "Regulatory?"→ FRTB requires model risk add-on
-  "Approval?"→ Model risk committee reviews quarterly
Red flag to avoid:
Never say: "Model risk is not quantifiable" (shows you can’t manage it)
## 39© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Module 12: Backtesting Is a Statistical Minefield
## Module Overview
What this module is about: Backtests look great because they’re designed to.  Lookahead bias, survivorship
bias, and overfitting make 99% of backtests worthless.
Why this matters: Every failed quant strategy looked amazing in backtest. Learning to spot bias is survival.
What confusion this clears:
-  Seven types of backtest bias
-  Why walk-forward is minimum requirement
-  When to kill a model
After this module, you should be able to answer: “Why do 90% of quant strategies fail out-of-sample?”
## 12.1 Seven Deadly Biases
BiasHow It Inflates SharpeFix
LookaheadUse future data (e.g., earnings)Lag signals by 1 day
SurvivorshipOnly winners in universeUse point-in-time universe
OverfittingToo many parameters
## √
T rule for params
Transaction costIgnore slippageModel 5-10 bps per trade
RegimeFit to one regimeWalk-forward test
ShortingAssume easy borrowAdd 50 bps borrow cost
P-hackingTest many, pick bestBonferroni correction
Table 9: Backtest biases and their fixes
"If It Looks Too Good, It’s Biased"
Memory: Sharpe > 2.0 in backtest = there’s a catch (overfitting, lookahead bias, or hidden costs).
## 02004006008001000
Time (Days)
## 0.1
## 0.0
## 0.1
## 0.2
## Cumulative Returns
Train 1Test 1Train 2Test 2
Walk-Forward Testing: Rolling Window Validation
## Train 1
## Test 1
## Train 2
## Test 2
## Train 3
## Test 3
Figure 10: Walk-Forward Testing: Rolling Window Validation
## 40© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

12.2 Walk-Forward Testing: The Only Valid Method
Step 1:  Train on [1, t], test on [t + 1, t + h] Step 2:  Move forward h days, repeat Step 3:  Average performance
across windows
Why it works: Simulates live trading—no lookahead.
## Core Formula
OOS Sharpe =
μ
## WF
σ
## WF
12.3 When to Kill a Model
Kill criteria: - OOS Sharpe < 0.5 - Max drawdown > 3x backtest - 3 consecutive months of negative PnL - Param-
eter drift > 20%
## Model Death
"3 strikes and you’re out"
"Kill faster than you think"
"Interview: ’I kill models after 2 months unexplained loss.’"
## 12.4 Quick Interview Cheat Sheet — Module 12
## Module 12: Backtest = Marketing
Core Concept: All backtests are suspicious until proven clean.
Must-Know:
-  Lookahead bias is most common (lag everything)
-  Walk-forward is minimum requirement
## •  Sharpe
## OOS
## < 0.5× Sharpe
## IS
= overfit
## Interview Triggers:
-  "Sharpe 3.0?" → "Show me walk-forward"
-  "How many parameters?" → "p<
## √
## T"
-  "Transaction costs?" → "5-10 bps per trade"
## Desk Wisdom:
-  Assume 50% of backtest alpha is illusion
-  Kill model if OOS Sharpe < 0.5
Common Trap: "Don’t trust any backtest you didn’t cheat yourself." (Assume bias)
Memory Aid: "Backtest is what you want to believe. Walk-forward is truth."
Interviewer Is Testing: Can you design an unbiased test?
## 41© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Walk-Forward Template
## Setup:
-  Initial train: 500 days
-  Test window: 50 days
-  Step size: 50 days
-  Total periods: 10
## Metric:
OOS Sharpe =
## √
## 10·
mean(r
## WF,1
, . . . , r
## WF,10
## )
sd(r
## WF,1
, . . . , r
## WF,10
## )
## Interview:
"Walk-forward is the computational version of live trading."
The 3-Second Answer (Module 12)
Question: "A PM shows you a backtest with Sharpe 2.5, return 20%, drawdown 5%. What’s your first question?"
Your opening line:
"Show me the walk-forward Sharpe. And tell me: 1) How many parameters? 2) Transaction cost assumption?
3) Is universe point-in-time? My guess: walk-forward Sharpe < 0.8, parameters > 20, costs ignored."
Why this wins:
-  Immediately asks for walk-forward (unbiased)
-  Lists three key bias checks (shows experience)
-  Gives prediction (shows confidence)
Follow-up ready:
-  "If walk-forward Sharpe = 0.6?" → Still tradable with size limits
-  "If parameters >
## √
T?" → Overfit, reject
-  "If no costs?" → Add 5 bps, see if Sharpe > 1.0
Red flag to avoid:
Never say: "That looks great, let’s trade it" (shows you trust backtests)
Walk-Forward Sharpe Ratio:
## Sharpe
## WF
## =
## √
K· mean(r
## 1
, . . . , r
## K
## )
sd(r
## 1
, . . . , r
## K
## )
where  K = number of OOS windows
## Overfitting Detector:
## Overfit Score = 1−
## Sharpe
## OOS
## Sharpe
## IS
## •< 0.3: Acceptable
-  0.3-0.6: Moderate overfit
•> 0.6: Severe overfit (don’t trade)
Module 13: From Statistics to PnL Attribution
## Module Overview
What this module is about: Statistics must explain PnL. If it can’t, it’s useless.  Residual PnL is the only test
of a model’s validity.
Why this matters: Quants build beautiful models that can’t explain why they lost money. If you can’t attribute
PnL, you can’t manage risk.
What confusion this clears:
## 42© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

-  How to link statistical drivers to PnL
-  Why residual PnL is model failure signal
-  When to kill a model (statistical criteria)
After this module, you should be able to answer: “Why did my factor model lose 5% last month?”
13.1 PnL Attribution Framework
Total PnL:
## Core Formula
PnL =
## K
## ∑
k=1
β
k
## ·∆F
k
## |
## {z}
Factor PnL
## +α
## |{z}
## True Alpha
## +ε
## |{z}
Residual/Model Error
Interpretation: - Factor PnL: explained by model - α: skill (should be small) - ε: model failure (should be zero)
"If Residual PnL Is Non-Zero, Model Is Wrong"
"Memory: Residual > 3% of total PnL = investigate."
13.2 Statistical Tests for Model Failure
- Residual autocorrelation:
## Core Formula
## Q = T(T + 2)
h
## ∑
k=1
ρ
k
## (ε)
## 2
T− k
∼ χ
## 2
## (h)
Reject if: Q> χ
## 2
## 0.95
(h) → model missing dynamics
- Residual heteroskedasticity:
## Core Formula
## ARCH LM = T· R
## 2
ε
## 2
∼ χ
## 2
( p)
Reject if: ARCH LM> χ
## 2
## 0.95
( p) → vol model broken
- α persistence:
## Core Formula
α
t
= φα
t−1
+ u
t
Test: If φ significant → factor missing
13.3 When to Kill a Model (Statistical Criteria)
Kill if:  1. |ε
t
|>  5%·|PnL| for 3 days 2.   ACF(ε)
## 1
>  0.3 (serial correlation) 3.   ARCH LM>  10 (vol model
misspecified) 4. α significantly negative for 1 month
## 43© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Model Death
"3 strikes on residuals = kill"
"Better no model than wrong model"
"Interview: ’I killed a factor model after 1 month negative alpha.’"
## 13.4 Quick Interview Cheat Sheet — Module 13
## Module 13: Residual = Truth
Core Concept: Residual PnL is the only honest model diagnostic.
Must-Know:
-  Residual autocorr → missing dynamics
-  ARCH LM → vol model broken
-  Negative α → factor decay
## Interview Triggers:
-  "PnL unexplained?" → "Residual autocorrelation test"
-  "Model broken?" → "Residual > 5% total PnL"
-  "Factor decay?" → "Rolling β and α"
## Desk Wisdom:
-  Plot ε
t
daily—if trending, model dead
-  Kill faster than you think (2 weeks max)
Common Trap: "Don’t ignore residual because model is ’theoretically sound’." (Theory  reality)
Memory Aid: "Residual PnL = model error = career risk."
Interviewer Is Testing: Can you diagnose model failure from PnL?
## Kill Decision Tree
Is residual PnL:
•> 5% for 3 days? → Kill
•> 3% for 1 week? → Reduce size 50%
•> 1% for 2 weeks? → Investigate
## •< 1%? → Keep
## Interview:
"I automate kill after 3 days > 5% residual."
## 44© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

The 3-Second Answer (Module 13)
Question: "Your factor model PnL = -$2M. Factor PnL = -$1M, alpha = -$0.5M, residual = -$0.5M. What broke?"
Your opening line:
"The residual is $0.5M (25% of loss)—model failure. The alpha is -$0.5M (factor decay/mis-specification). The
factor exposure contributed -$1M (market move).  I need to:  1) Investigate residual (serial correlation?), 2)
Re-estimate factor loadings, 3) Check if factor is still viable."
Why this wins:
-  Decomposes PnL into three drivers
-  Flags residual as model failure
-  Gives action plan (shows you manage risk)
Follow-up ready:
-  "How investigate residual?" → ACF, ARCH LM tests
-  "Factor decay?" → Rolling β stability
-  "Kill threshold?" → 2 weeks negative residual
Red flag to avoid:
Never say: "Market moved against us" (ignores model failure)
Module 14: Interview Toolkit (Stats Edition)
## 14.1 Top 15 Statistics Interview Questions
- "You have 252 days, 50 assets. Can you estimate a full covariance matrix?"
Question:  Dimensionality problem.
Answer:  "No. Covariance matrix has 1225 parameters → need T> p for invertibility. Even with T = 252,
estimates are noisy. Use Ledoit-Wolf shrinkage or factor model to reduce dimensionality to < 50 params."
- "Your regression R
## 2
= 0.6 in-sample, 0.1 out-of-sample. What happened?"
## Question:  Overfitting.
Answer:   "You overfit to noise. Ratio OOS/IS < 0.2 suggests too many parameters relative to sample size.
Check p/T ratio—if > 0.1, guaranteed overfit. Fix: ridge regression, fewer factors, cross-validation."
- "GARCH(1,1) parameters: α + β = 0.98. Half-life?"
Question:  GARCH persistence.
Answer:  "Half-life =− ln(0.5)/ ln(0.98)≈ 34 days. High persistence means shocks take 34 days to halve.
If α + β> 0.99, half-life > 69 days—too slow to react to crisis."
- "ADF test p-value = 0.06. Is spread mean-reverting?"
Question:  Unit root test interpretation.
Answer:   "No. Fail to reject null of unit root at 5% level. For trading, need p < 0.05 (preferably < 0.01). At
p=0.06, probability of spurious mean reversion is high. Don’t trade it."
- "You test 100 signals, 5 have p < 0.05. How many are real?"
Question:  Multiple testing.
Answer:   "Expected false positives = 100× 0.05 = 5. So likely 0 are real. Use Bonferroni: need p < 0.0005
(t-stat > 3.5) to claim significance. Or use FDR control."
## 45© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

- "Correlation matrix has negative eigenvalue -0.1. Problem?"
Question:  Positive definiteness.
Answer:   "Matrix not PSD → generates imaginary variances. Fix: Ledoit-Wolf shrinkage toward diagonal
or constant correlation. Shrinkage intensity λ =
π−c
π
where π is noise, c is signal."
- "Bayesian prior θ ∼ N(0, 1), likelihood
## ˆ
θ = 0.5± 0.2. Posterior?"
Question:  Bayesian update.
Answer:   "Posterior mean = precision-weighted: (
## 1
## 1
## · 0 +
## 1
## 0.04
## · 0.5)/(
## 1
## 1
## +
## 1
## 0.04
) = 0.48. Posterior variance =
1/(1 + 25) = 0.038. Result: θ|y∼ N(0.48, 0.195)."
- "Residuals show autocorrelation at lag 1 = 0.3. Model broken?"
Question:  Residual diagnostics.
Answer:   "Yes.  White noise should have AC    0.  AC=0.3 suggests missing AR structure.  Run Ljung-Box
test: Q = T(T + 2)ρ
## 2
/(T− 1)∼ χ
## 2
(1). If Q> 3.84, reject null → model misspecified."
- "Walk-forward Sharpe = 0.4, backtest Sharpe = 2.0. Trade it?"
Question:  Walk-forward evaluation.
Answer:  "No. Ratio 0.2 < 0.5 indicates severe overfit. Live Sharpe likely < 0.4 after costs. Minimum viable
OOS Sharpe = 0.5 for single strat, 0.3 for diversified book. This model is untradable."
- "ES 97.5% vs VaR 99%—which to report?"
Question:  Risk measure choice.
Answer:   "ES. It’s coherent (subadditive) and captures tail shape.  VaR only gives threshold, not severity.
Under FRTB, ES is regulatory standard. VaR is useful for limit setting but insufficient for capital."
- "You have 10 factors but only 200 days. How to regress?"
Question:  High dimensionality.
Answer:"Can’t use OLS—overfit guaranteed.   Use ridge (L2) or LASSO (L1) with λ chosen by cross-
validation. Or PCA to 3 factors. Rule:  p<
## √
T ≈ 14 for 200 days."
- "GARCH volatility forecast = 12%, ATM vol = 18%. Trade?"
Question:  Volatility arbitrage.
Answer:    "ATM vol is 6 vol points rich vs GARCH. Sell options (sell vol).  But check:  GARCH may be
underestimating tail risk. Add 30% stress buffer to GARCH: 12%× 1.3 = 15.6% still < 18% → sell."
- "Correlation jumps from 0.3 to 0.8. Diversification lost?"
Question:  Correlation breakdown.
Answer:   "Yes.  Effective assets N
eff
=  N· (1 + (N− 1)ρ)/N.  For ρ =  0.3, N
eff
## =  10· 3.7/10 =  3.7.  For
ρ = 0.8, N
eff
= 8.2. You’re 2x more concentrated."
## 46© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

- "Factor returns have skew = -1.0, kurtosis = 5.0. Gaussian?"
Question:  Non-Gaussian features.
Answer:   "No.  Gaussian has skew=0, kurtosis=3.  Skew=-1 suggests left tail, kurtosis=5 suggests fat tails.
Use robust regression or t-distribution errors.  Check Jarque-Bera:  J B =  T(skew
## 2
## /6 + (kurt− 3)
## 2
## /24) ∼
χ
## 2
(2). Reject Gaussian if J B> 5.99."
- "How to detect overfitting without out-of-sample data?"
Question:  Overfitting detection.
Answer:    "Use information criteria:  AIC = 2p− 2 ln(
## ˆ
L), BIC = ln(T) p− 2 ln(
## ˆ
L).  If adding a parameter
reduces log-likelihood by < 1, it’s overfit. Or cross-validation: split data 10-fold, average performance."
## 14.2 Pressure Questions
- "Your factor model has 50 factors. t-stats all > 2.0. Sharpe 2.5. Problem?"
Question:  Dimensionality trap.
Answer:   "You have p = 50, T = 252 → p/T = 0.2 → guaranteed overfit. t-stats are inflated because you
tested many factors. Expected false positives = 50× 0.05 = 2.5 at α = 0.05. Real Sharpe likely < 0.5. Only
solution: cut to top 5 factors by economic intuition."
- "You find cointegrated spread. Half-life = 40 days. Trade it?"
Question:  Tradability assessment.
Answer:    "No.  Half-life > 30 days is untradable—sharpe too low.  Mean reversion too slow to capture
before costs erode profit. Need half-life < 20 days for Sharpe > 1.0. Also check: does cointegration hold on
rolling 1-year windows?"
- "Your GARCH(1,1) has α + β = 0.995. Problem?"
Question:  GARCH persistence danger.
Answer:    "Half-life = − ln(0.5)/ ln(0.995) ≈  138 days.  Too persistent—shocks take 6 months to decay.
Model will be slow to adapt to new regime.  Reduce persistence by using component GARCH or EWMA
with λ = 0.94."
- "Backtest shows 0.1 Sharpe, walk-forward shows -0.2. How?"
Question:  Negative OOS Sharpe.
Answer:"Transaction  costs  not  included  in  backtest.   Slippage,  market  impact,  fees  turn  small  edge
negative.  Or factor decay: in-sample period had regime favorable to factor.  Or overfit: parameters tuned
to noise. Live trading will lose money—don’t deploy."
- "You have 1000 signals. Want to test without overfitting. How?"
Question:  Large-scale testing.
Answer:  "Use FDR control (Benjamini-Hochberg) at 10% rate. Or split data: 50% training, 30% validation,
20% final test. Only validate top 20 signals from training. Or use bootstrap: sample with replacement 500
times, test signal stability."
## 47© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## 14.3 Mini Exercises
## Exercise Format
For each scenario: (1) Identify statistical problem, (2) Propose solution, (3) State trade-off.
Exercise 1: Auto-correlated errors in regression
-  Problem: OLS SEs wrong → false significance
-  Solution: Newey-West HAC standard errors
-  Trade-off: Less efficient if errors not autocorrelated
Exercise 2: 100 factors, 200 days
-  Problem: Overfit, p/T = 0.5 » 0.1 threshold
-  Solution: Ridge regression or PCA to reduce dimension
-  Trade-off: Bias-variance tradeoff, less interpretability
Exercise 3: Correlation matrix not PSD
-  Problem: Negative eigenvalues → imaginary variances
-  Solution: Ledoit-Wolf shrinkage toward constant correlation
-  Trade-off: Introduces bias but ensures invertibility
Exercise 4: GARCH volatility clusters
-  Problem: Vol persistence violates IID
-  Solution: Use GARCH forecast for VaR scaling
-  Trade-off: Model risk if GARCH parameters unstable
Exercise 5: p-value = 0.01 after 200 tests
-  Problem: Multiple testing, expected false positives = 10
-  Solution: Bonferroni: require p < 0.00025
-  Trade-off: Higher type II error (miss true factors)
## Statistical Debugging Protocol: When Models Break
The 5-Level Diagnostic
-  Level 1: Data Quality (5 min)
- Missing values? → Impute or drop
- Outliers (> 5)? → Winsorize at 99th percentile
- Duplicates? → Dedup by timestamp
- Time zones aligned? → Convert to UTC
- Corporate actions adjusted? → Check split/dividend data
-  Level 2: Distributional Checks (10 min)
- QQ plot → Fat tails? Use t-dist
- Skewness > |1|? → Log transform
- Kurtosis > 5? → Robust estimation
- Jarque-Bera reject? → Non-parametric methods
## 48© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

- Histogram multimodal? → Mixture model
-  Level 3: Dependence Structure (15 min)
- ACF(returns) → Mean reversion?
- ACF(returns²) → Vol clustering?
- PACF → AR order?
- Ljung-Box → Serial correlation?
- ADF → Unit root?
-  Level 4: Model Diagnostics (20 min)
- Residual plot → Pattern? (Misspecification)
- Residual ACF → Autocorr? (Add AR/MA)
- Residual² ARCH-LM → Vol clustering? (Use GARCH)
- QQ plot (residuals) → Non-normal? (Robust SE)
- Rolling  → Stable? (Parameter constancy)
-  Level 5: Out-of-Sample Validation (30 min)
- Walk-forward backtest → Sharpe OOS vs IS
- Parameter stability → _t vs _{t-60}
- Residual PnL → || < 5%?
- VaR backtesting → Kupiec + Christoffersen
- Stress testing → Max drawdown < 3× expected?
## The Decision Tree
Model fails
Data issue?
Fix data
Next level
## Distributional?
TransformRobust method
## Dependence?
Add dynamics
## GARCH
## Misspecification?
## Respecify
Kill model
Mental Models: Think Like a Bayesian Statistician
Mental Model 1: "Everything Is a Distribution"
DON’T think:
## ˆ
β = 0.5
DO think:
## ˆ
β∼N (0.5, 0.1
## 2
## )
## •  Parameter → Distribution
-  Forecast → Predictive distribution
-  Risk → Tail of distribution
Mental Model 2: "Uncertainty Compounds"
## Total Uncertainty
## 2
## = Parameter
## 2
## |
## {z}
## Estimation
## +  Model
## 2
## |
## {z}
## Specification
## + Market
## 2
## |
## {z}
## Volatility
## 49© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Interview insight: "Most quants only model market risk. I add 20% for parameter + model risk."
Mental Model 3: "The Map Is Not the Territory"
"All models are wrong, but some are useful." — George Box
## Translation:
## •  Model  Reality
## •  Calibration  Truth
## •  In-sample  Out-of-sample
## •  Significance  Importance
Mental Model 4: "Asymmetric Loss Functions"
L(model fails)≫ L(model conservative)
Implication: Better to overestimate risk than underestimate
## Scenario
CostAction
VaR too low (breach)Lose jobAdd 30% buffer
VaR too high (conservative)
Lower SharpeAcceptable
Overfit (Sharpe 3→0)Lose capitalKill fast
Underfit (Sharpe 0.5→0.8)
Miss opportunityAcceptable
Rule: When in doubt, be conservative.
Mental Model 5: "Bayesian Updating in Real Life"
Prior: "This factor should work" (weak belief)
Data: OOS Sharpe = -0.2 for 3 months
Posterior: "This factor doesn’t work" (strong belief)
P(factor works|data)
## |{z}
## Posterior
## =
## Low
z}|{
P(data|factor works)·
## Prior
z}|{
P(factor works)
## P(data)
## |{z}
## Evidence
## ≈ 0.05
Action: Kill the factor (posterior < 0.1)
Speed Math for Interviews: Estimate Without Calculator
## Quick Approximations (±10% Accuracy)
- Standard Error of Correlation
## SE(
## ˆ
ρ)≈
## 1
## √
## T
(when ρ≈ 0)
Example: 250 days → SE≈ 1/
## √
## 250≈ 1/16≈ 0.06
- GARCH Half-Life
## HL≈
## 0.7
1− (α + β)
## 50© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Example: α + β = 0.95 → HL≈ 0.7/0.05 = 14 days
- VaR Scaling (Approximate)
VaR
## 10d
≈ 3.5× VaR
## 1d
(not 3.16 with GARCH)
## 4. Bonferroni Cutoff
t
critical
## ≈ 2 +
ln(m)
## 2
Example: 100 tests → t≈ 2 + 2.3 = 4.3 (exact: 3.88)
- Sample Size for Correlation
## T
needed
## ≈
## 400
(1− ρ
## 2
## )
## 2
for SE< 0.1
Example: ρ = 0.5 → T ≈ 400/0.56≈ 700 days
- Effective Number of Assets
## N
e f f
## ≈
## N
## 1 + N·
## ̄
ρ
(for small
## ̄
ρ)
Example: 50 assets,
## ̄
ρ = 0.3 → N
e f f
## ≈ 50/16≈ 3
- Sharpe from Win Rate
Sharpe≈ 2× ( p
win
## − 0.5)×
## √
Trades/Year
Example: 55% win rate, 100 trades/yr → Sharpe≈ 2× 0.05× 10 = 1.0
## Mental Multiplication Tricks
Square roots (interview favorites):
## √
## 2≈ 1.4
## √
## 3≈ 1.7
## √
## 5≈ 2.2
## √
## 10≈ 3.2
## √
## 250≈ 16
Natural logs:
ln(2)≈ 0.7
ln(10)≈ 2.3
ln(100)≈ 4.6
Quick t-stats to p-values:
t-stat
p-value (two-tailed)Significance
## 1.960.055%
## 2.58
## 0.011%
## 3.29
## 0.0010.1%
## 51© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

## Interview Speed Drills
Drill 1: 250 days, 50 assets, correlation matrix. How many parameters?
## Answer:  50× 49/2 = 1225
Obs per param:  250/1225≈ 0.2 → Disaster!
Drill 2: GARCH with α = 0.08, β = 0.90. Half-life?
Answer:  0.7/(1− 0.98) = 0.7/0.02 = 35 days
Drill 3: Test 200 factors at 5%. How many false positives?
Answer:  200× 0.05 = 10 expected false positives
Drill 4: Sharpe 2.0 in-sample, 0.6 out-of-sample. Overfit ratio?
Answer:  1− 0.6/2.0 = 0.7 = 70% overfit → Don’t trade!
## Appendix: Statistics Formula Sheet
Top 10 Formulas to Memorize:
## 1.  OLS:
## ˆ
β = (X
## ′
## X)
## −1
## X
## ′
y
-  SE of
## ˆ
ρ: SE(
## ˆ
ρ) =
## 1−ρ
## 2
## √
## T−3
-  GARCH: σ
## 2
t
= ω + αε
## 2
t−1
+ βσ
## 2
t−1
-  Half-life: HL =− ln(2)/ ln|φ|
-  VaR Scaling: VaR
## T
= VaR
## 1
## ×
## √
## T× (1 +
α+β
## 2
## )
-  Ledoit-Wolf: λ
## ∗
## =
## N
## T
## (approx)
-  Bonferroni: α
adj
= α/m
-  Expected Shortfall: ES
α
## =
## 1
α
## R
q
α
## −∞
y f (y)dy
-  Ljung-Box: Q = T(T + 2)
## ∑
h
k=1
ρ
## 2
k
## T−k
∼ χ
## 2
## (h)
## 10.  N
eff
## : N
eff
## =
## N
## 1+(N−1)
## ̄
ρ
Final Interview Checklist—Statistics
60-Second Self-Test
□  Can derive OLS and know when it fails
□  Can test for stationarity (ADF) and interpret
□  Can compute GARCH persistence and half-life
□  Can detect autocorrelation (Ljung-Box)
□  Can compute Bonferroni/FDR corrections
□  Can explain why R
## 2
is dangerous
□  Can propagate parameter uncertainty (delta method)
□  Can design walk-forward test
□  Can distinguish VaR from ES
□  Can quantify model risk
If you can’t answer any of these in 60 seconds, reread that module.
## 52© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

Avoid SayingSay Instead
“Assume returns are IID”“Model   conditional   dependence   via
## GARCH”
“p < 0.05 means factor works”“NeedFDRcorrectionandOOS
## Sharpe”
## “R
## 2
= 0.8 good fit”“OOS R
## 2
matters, not in-sample”
“Model is correctly specified”“All models are wrong, some useful”
“Correlation matrix is fine”“Check PSD, shrink if needed”
If–Then Statistical Decision Logic
-  If p/T> 0.1 → Shrink or reduce dimension
-  If ADF p > 0.05 → Not mean-reverting
-  If α + β> 0.99 → GARCH too persistent
-  If residual AC > 0.2 → Model misspecified
-  If p-value < 0.05 after m tests → Require p< α/m
-  If OOS Sharpe < 0.5 → Do not trade
-  If residual PnL > 5% → Investigate model
Interview line: "I use statistical tests as diagnostic tools, not decision rules."
## Regression Diagnostics Deep Dive
## Multicollinearity Detection
Variance Inflation Factor (VIF):
## VIF
j
## =
## 1
## 1− R
## 2
j
## (1)
where R
## 2
j
is from regressing X
j
on all other regressors.
## Decision Rule:
-  VIF< 5: Acceptable
-  VIF∈ [5, 10]: Moderate collinearity
-  VIF> 10: Severe multicollinearity→ Remove variable or use ridge
## Interview:
"VIF = 15 for a factor means 93% of its variance is explained by other factors—it’s redundant.  Either drop it or
use PCA."
## Heteroskedasticity Tests
Breusch-Pagan Test:
-  Run OLS: y = Xβ + ε
## 2.  Regress
## ˆ
ε
## 2
on X:
## ˆ
ε
## 2
= Xγ + u
-  Test statistic: LM = n· R
## 2
ε
## 2
∼ χ
## 2
( p)
## White Test:
## Include X, X
## 2
, and cross-products X
i
## X
j
in step 2.
## Decision:
-  If p< 0.05: Reject homoskedasticity
## 53© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

-  Fix: Use White robust standard errors or WLS
## Interview:
"Breusch-Pagan tests if variance depends on X. White tests all possible forms. If rejected, OLS
## ˆ
β is still consistent
but SEs are wrong."
## Autocorrelation Tests
Durbin-Watson Statistic:
## DW =
## ∑
## T
t=2
## (
## ˆ
ε
t
## −
## ˆ
ε
t−1
## )
## 2
## ∑
## T
t=1
## ˆ
ε
## 2
t
## (2)
## Interpretation:
-  DW ≈ 2: No autocorrelation
-  DW< 1.5: Positive autocorrelation
-  DW> 2.5: Negative autocorrelation
Ljung-Box Test (more powerful):
## Q = T(T + 2)
h
## ∑
k=1
## ˆ
ρ
## 2
k
T− k
∼ χ
## 2
## (h)(3)
Fix: Add AR/MA terms or use Newey-West HAC standard errors.
## Functional Form Misspecification
Ramsey RESET Test:
-  Run OLS: y = Xβ + ε
## 2.  Compute
## ˆ
y
## 2
## ,
## ˆ
y
## 3
## ,
## ˆ
y
## 4
-  Regress: y = Xβ + γ
## 2
## ˆ
y
## 2
+ γ
## 3
## ˆ
y
## 3
+ γ
## 4
## ˆ
y
## 4
+ u
## 4.  Test: H
## 0
: γ
## 2
= γ
## 3
= γ
## 4
= 0 using F-test
## Decision:
-  If p< 0.05: Model misspecified (non-linear relationship)
-  Fix: Add polynomials, logs, or interaction terms
Distribution Testing for Model Validation
## Normality Tests
- Jarque-Bera Test:
## J B =
## T
## 6
## 
## S
## 2
## +
## (K− 3)
## 2
## 4
## 
∼ χ
## 2
## (2)(4)
where S = skewness, K = kurtosis.
Decision: Reject normality if J B> 5.99 (at 5%).
- Kolmogorov-Smirnov Test:
D = sup
x
## |F
n
## (x)− F
## 0
## (x)|(5)
where F
n
= empirical CDF, F
## 0
= hypothesized CDF.
Critical value: D
crit
## =
## 1.36
## √
n
at 5%.
## 54© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

- Anderson-Darling Test:
## A
## 2
## =−n−
## 1
n
n
## ∑
i=1
## (2i− 1)[ln F
## 0
## (X
i
) + ln(1− F
## 0
## (X
n+1−i
## ))](6)
Advantage: More sensitive to tails than KS test.
## 4. Cramér-von Mises Test:
## W
## 2
## =
n
## ∑
i=1
## 
## F
## 0
## (X
i
## )−
## 2i− 1
## 2n
## 
## 2
## +
## 1
## 12n
## (7)
## Interview Comparison:
TestTail SensitivityPowerUse Case
Jarque-BeraLowMediumQuick check
KSLowLowGeneral purpose
Anderson-DarlingHighHighRisk models
Cramér-von MisesMediumHighBalanced
## Desk Wisdom:
"For VaR models, use Anderson-Darling—it catches fat tails that KS misses. JB is fast but crude."
Chi-Square Goodness-of-Fit
## Test Statistic:
χ
## 2
## =
k
## ∑
i=1
## (O
i
## − E
i
## )
## 2
## E
i
∼ χ
## 2
(k− p− 1)(8)
where O
i
= observed frequency, E
i
= expected frequency, p = estimated parameters.
Application: Test if returns follow a specific distribution (normal, t, etc.).
## Requirement: E
i
≥ 5 for each bin (merge bins if needed).
## Parameter Stability Tests
CUSUM Test:
## W
t
## =
t
## ∑
s=k+1
## ˆ
ε
s
## ˆ
σ
## (9)
## Decision: If W
t
exceeds bounds±a
## √
T− k (typically a = 0.948 for 5%), parameter instability detected.
Chow Test for Structural Break:
## F =
## (RSS
c
## − RSS
## 1
## − RSS
## 2
## )/k
## (RSS
## 1
## + RSS
## 2
## )/(n
## 1
+ n
## 2
## − 2k)
∼ F(k, n
## 1
+ n
## 2
## − 2k)(10)
## Interview:
"Chow test splits sample at known break point (e.g., COVID). CUSUM detects unknown breaks."
## Residual Diagnostics Checklist (30-second)
## 1.  Plot
## ˆ
ε
t
vs time: Trend? → Missing variable
## 2.  Plot
## ˆ
ε
t
vs
## ˆ
y
t
: Fan shape? → Heteroskedasticity
## 3.  ACF(
## ˆ
ε
t
## ): Spikes? → Autocorrelation
## 55© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.

-  QQ plot: Deviates from line? → Non-normality
-  VIF:> 10? → Multicollinearity
## Kill Criteria:
-  DW< 1.2 or> 2.8
-  Breusch-Pagan p< 0.05
-  VIF> 15 for any variable
-  RESET p< 0.05
-  Anderson-Darling p< 0.01 (tails don’t match)
## Quick Interview Cheat Sheet — Module 4.5
## Module 4.5: Diagnostic Tests
Core Concept: Every model has testable assumptions—violate them and your inference is garbage.
Must-Know:
-  VIF> 10→ drop variable
-  Breusch-Pagan→ robust SEs
-  DW̸= 2→ Newey-West
-  Anderson-Darling→ best for tails
## Interview Triggers:
-  "How detect multicollinearity?"→ "VIF or condition number"
-  "Residuals look weird?"→ "Plot all 4 diagnostics"
-  "Which normality test?"→ "AD for tails, JB for speed"
## Desk Wisdom:
-  Run diagnostics before trusting any regression
-  AD test beats KS for fat tails
## Common Trap:
"Don’t ignore diagnostic p-values< 0.05—they’re telling you the model is broken."
## Memory Aid:
"VHAT: VIF, Heteroskedasticity, Autocorrelation, Tails."
Interviewer Is Testing: Can you diagnose model failures systematically?
Table 10: Diagnostic Test Quick Reference for Model Validation
ProblemTestH
## 0
Fix if Rejected
MulticollinearityVIFVIF< 5Drop variable / Ridge
HeteroskedasticityBreusch-PaganConstant varianceRobust SE / WLS
AutocorrelationDurbin-Watsonρ = 0Newey-West / Add AR
Non-normalityAnderson-DarlingNormal distRobust methods
MisspecificationRESETLinear formAdd polynomials
Parameter driftCUSUMStable paramsRegime switching
## 56© 2025 Amit Kumar Jha. All Rights Reserved. Redistribution Prohibited.