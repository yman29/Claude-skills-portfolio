# Quant Reference Library — Index
*14 books compressed from ~11MB to ~120KB. Add new files here.*

---

## How to use
When answering a quant question, load the 1-2 most relevant files from this index.
Multiple topics = load multiple files.

---

## File Index

| File | Topics |
|------|--------|
| `ml-for-quants-notes.md` | ML algorithms (all), bias-variance, feature engineering, walk-forward, leakage, backtesting checklist, crisis mode (ML), 10 commandments, interview phrases, daily health check |
| `stats-for-quants-notes.md` | Regression diagnostics (VIF, Breusch-Pagan, DW, RESET, AD), GARCH variants, Bayesian, hypothesis testing, multiple testing, crisis mode (stats), 3Ds, interview phrases |
| `advances-in-financial-ml.md` | Dollar/volume/tick bars, CUSUM filter, triple-barrier labeling, meta-labeling, sample weights, fractional differentiation, purged K-fold CV, MDI/MDA/SFI feature importance |
| `portfolio-optimization.md` | MVO formulations, Black-Litterman, Ledoit-Wolf shrinkage, factor models, transaction cost constraints, CVaR, robust optimization, risk budgeting, Python code |
| `machine-trading-chan.md` | Kelly formula, Sharpe vs Calmar, efficient frontier, factor models (time-series vs cross-sectional), AR/ARIMA/VAR, Kalman filter, mean reversion (half-life, OU), cointegration pairs trading, vol targeting, regime detection |
| `advanced-portfolio-management.md` | Factor vs idio returns, IR definition, proportional sizing rule, risk decomposition (%idio var), tactical factor management, performance attribution, stop-loss, leverage rules |
| `quant-equity-portfolio.md` | Fundamental Law (IR=IC×√BR), IC/IR/breadth, Z-score alpha model, composite signals, factor groupings, MVO constraints, tracking error minimization, backtesting protocol, data mining prevention |
| `statistically-sound-ml.md` | Walk-forward vs CV, overlap problem, MCPT (Monte Carlo permutation test), selection bias, multiple testing, Cramer's V for indicator screening, IS/OOS gap, signal boosting/meta-labeling |
| `learn-algo-trading.md` | Technical indicators (SMA/EMA/RSI/MACD/Bollinger/APO/momentum) with Python, mean reversion strategy, trend-following, StatArb, max drawdown code, Sharpe/Sortino code, risk checks, order types, backtester architecture |
| `advanced-algo-trading.md` | Bayesian statistics (MCMC/PyMC3), stochastic vol model, ARIMA fitting, GARCH(1,1), ARIMA+GARCH strategy, cointegration (CADF/Johansen), pairs trading code, HMM regime detection, ensemble ML (RF/AdaBoost), NLP/SVM |
| `ml-for-algo-trading.md` | ML workflow, alpha factor engineering, Alphalens (IC/quantile returns/turnover), LightGBM/XGBoost, SHAP values, LSTM, alternative data, NLP/sentiment signals, pyfolio, long-short portfolio construction |
| `science-algo-trading-kissell.md` | Market impact models (Almgren-Chriss, square-root law), VWAP/TWAP/IS/POV algorithms, pre-trade analysis, post-trade TCA, implementation shortfall attribution, optimal execution, alpha decay, urgency |
| `python-for-finance.md` | Monte Carlo option pricing, Black-Scholes analytics, Greeks (delta/gamma/vega/theta), implied vol, VaR/CVaR code, efficient frontier, CAPM regression, GBM/Heston/OU simulation, Nelson-Siegel yield curve, duration |
| `quant-finance-python.md` | Black-Scholes (with dividends/FX), Bachelier model, smile-adjusted Greeks, delta hedging P&L, VaR/CVaR methods comparison, mean-CVaR optimization, bond pricing/duration, risk contributions/parity, CAPM/Fama-French code |

---

## Quick topic routing

| Question about... | Load these files |
|-------------------|-----------------|
| Walk-forward leakage | `ml-for-quants-notes` + `statistically-sound-ml` |
| GARCH / volatility modeling | `stats-for-quants-notes` + `advanced-algo-trading` |
| Portfolio optimization / MVO | `portfolio-optimization` + `quant-finance-python` |
| Factor models / alpha research | `quant-equity-portfolio` + `ml-for-algo-trading` |
| Mean reversion / pairs trading | `machine-trading-chan` + `advanced-algo-trading` |
| Execution / market impact | `science-algo-trading-kissell` |
| Options / derivatives | `python-for-finance` + `quant-finance-python` |
| ML model selection | `ml-for-quants-notes` + `ml-for-algo-trading` |
| Backtesting methodology | `advances-in-financial-ml` + `statistically-sound-ml` |
| Performance attribution | `advanced-portfolio-management` + `quant-equity-portfolio` |
| Interview prep | `ml-for-quants-notes` + `stats-for-quants-notes` |
| Crisis protocols | `ml-for-quants-notes` + `stats-for-quants-notes` |
| Risk management | `advanced-portfolio-management` + `portfolio-optimization` |

---

## Adding new references
Drop `.md` file into this directory and add a row to the table above.
