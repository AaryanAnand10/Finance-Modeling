# Finance-Modeling


# 🎯 Quant Finance: What Each Model/Formula Predicts

A complete **"Formula → Purpose"** reference guide:

---

## 📈 1. STOCK PRICE PREDICTION & SIMULATION

| Method / Formula | Predicts / Used For |
|---|---|
| **Geometric Brownian Motion (GBM)** $$dS_t = \mu S_t dt + \sigma S_t dW_t$$ | Future **stock price paths** (simulation) |
| **ARIMA / GARCH** | **Time-series forecasting** of prices & volatility |
| **Fama-French 3/5 Factor Model** $$R_i = R_f + \beta_1(MKT) + \beta_2(SMB) + \beta_3(HML)...$$ | **Stock returns** based on size, value, profitability factors |
| **CAPM** $$E(R_i) = R_f + \beta(E(R_m) - R_f)$$ | **Expected return** of a stock vs market |
| **Kalman Filter** | **Real-time price estimation**, filtering noise from signals |

---

## 🧾 2. OPTIONS & DERIVATIVES PRICING

| Method / Formula | Predicts / Used For |
|---|---|
| **Black-Scholes Formula** $$C = S_0 N(d_1) - Ke^{-rT}N(d_2)$$ | **Price of European call/put options** |
| **Black-Scholes PDE** $$\frac{\partial V}{\partial t} + \frac{1}{2}\sigma^2 S^2 \frac{\partial^2 V}{\partial S^2} + rS\frac{\partial V}{\partial S} - rV = 0$$ | **Price of ANY derivative** under BS assumptions |
| **Binomial Tree (CRR)** $$C = e^{-rT}[pC_u + (1-p)C_d]$$ | **American & European option prices** step-by-step |
| **Monte Carlo Simulation** $$\hat{V} = e^{-rT} \frac{1}{N}\sum_{i=1}^{N} \text{Payoff}_i$$ | **Exotic/complex option prices** via simulation |
| **Heston Model** $$dv_t = \kappa(\theta - v_t)dt + \xi\sqrt{v_t}dW_t^v$$ | Options prices when **volatility is itself random** |
| **Merton Jump-Diffusion** $$dS = \mu S dt + \sigma S dW_t + S dJ_t$$ | Options prices with **sudden price jumps** (crashes) |
| **Finite Difference Method (FDM)** | Numerically solves PDE to price **American options** |

---

## 📉 3. VOLATILITY PREDICTION

| Method / Formula | Predicts / Used For |
|---|---|
| **GARCH(1,1)** $$\sigma_t^2 = \omega + \alpha \epsilon_{t-1}^2 + \beta \sigma_{t-1}^2$$ | **Future volatility** of asset returns |
| **Implied Volatility (from BS)** $$C_{market} = BS(S, K, r, T, \sigma_{imp})$$ | **Market's expectation** of future volatility |
| **VIX Model** | **Market fear / 30-day expected volatility** of S&P 500 |
| **EWMA (RiskMetrics)** $$\sigma_t^2 = \lambda \sigma_{t-1}^2 + (1-\lambda)r_{t-1}^2$$ | **Short-term volatility** with more weight on recent data |
| **Heston Model** | **Stochastic volatility** — volatility surface modeling |
| **Volatility Smile/Skew** | Shows how **implied vol varies** across strike prices |

---

## 💰 4. INTEREST RATE PREDICTION

| Method / Formula | Predicts / Used For |
|---|---|
| **Vasicek Model** $$dr_t = \kappa(\theta - r_t)dt + \sigma dW_t$$ | **Short-term interest rate** evolution (can go negative) |
| **CIR Model** $$dr_t = \kappa(\theta - r_t)dt + \sigma\sqrt{r_t}dW_t$$ | **Short-term rate** (stays positive always) |
| **Hull-White Model** $$dr_t = [\theta(t) - \alpha r_t]dt + \sigma dW_t$$ | **Yield curve fitting** & interest rate derivatives |
| **HJM Framework** $$df(t,T) = \alpha(t,T)dt + \sigma(t,T)dW_t$$ | **Entire forward rate curve** evolution |
| **Nelson-Siegel Model** | **Yield curve shape** (level, slope, curvature) |
| **LIBOR Market Model (LMM)** | Pricing **caps, floors, swaptions** |

---

## ⚠️ 5. RISK MEASUREMENT & MANAGEMENT

| Method / Formula | Predicts / Used For |
|---|---|
| **Value at Risk (VaR)** $$VaR_\alpha = \mu - z_\alpha \cdot \sigma$$ | **Maximum expected loss** at a confidence level (e.g., 95%) |
| **Expected Shortfall (CVaR)** $$ES_\alpha = E[L \mid L > VaR_\alpha]$$ | **Average loss beyond VaR** (tail risk) |
| **Beta (β)** $$\beta = \frac{Cov(R_i, R_m)}{Var(R_m)}$$ | **Systematic risk** of an asset vs the market |
| **Greeks (Delta, Gamma, Vega...)** $$\Delta = \frac{\partial V}{\partial S}, \quad \Gamma = \frac{\partial^2 V}{\partial S^2}$$ | **Sensitivity of option price** to various factors |
| **Stress Testing / Scenario Analysis** | Portfolio loss under **extreme market conditions** |
| **Copula Models (Gaussian, Clayton)** $$C(u,v) = \Phi_\rho(\Phi^{-1}(u), \Phi^{-1}(v))$$ | **Joint default probability** / tail dependency (CDOs) |

---

## 🗂️ 6. PORTFOLIO OPTIMIZATION

| Method / Formula | Predicts / Used For |
|---|---|
| **Markowitz Mean-Variance** $$\min \mathbf{w}^T \Sigma \mathbf{w} \quad \text{s.t.} \quad \mathbf{w}^T\mu = \mu_p$$ | **Optimal portfolio weights** for given risk/return |
| **Sharpe Ratio** $$SR = \frac{E(R_p) - R_f}{\sigma_p}$$ | **Risk-adjusted return** of a portfolio |
| **Black-Litterman Model** | Portfolio weights combining **market equilibrium + investor views** |
| **PCA (Principal Component Analysis)** | **Key risk drivers** in a portfolio / yield curve |
| **Risk Parity** | Allocate so each asset contributes **equal risk** |
| **Kelly Criterion** $$f^* = \frac{bp - q}{b}$$ | **Optimal bet/position size** to maximize long-run growth |

---

## 🤖 7. ALGORITHMIC TRADING & ML MODELS

| Method / Formula | Predicts / Used For |
|---|---|
| **Linear Regression / Ridge / Lasso** | **Price/return forecasting** from features |
| **LSTM Neural Networks** | **Sequential price prediction** using deep learning |
| **Reinforcement Learning (RL)** | **Optimal trading strategy** (buy/sell/hold decisions) |
| **Random Forest / XGBoost** | **Classification of market direction** (up/down) |
| **Pairs Trading (Cointegration)** $$\text{Spread} = P_A - \gamma P_B$$ | **Mean-reverting spread** between two correlated assets |
| **Kalman Filter** | **Dynamic hedge ratio** estimation in stat-arb |
| **Sentiment Analysis (NLP)** | Predict price moves from **news/social media** |

---

## 🔢 8. CREDIT RISK MODELS

| Method / Formula | Predicts / Used For |
|---|---|
| **Merton Structural Model** $$V_E = V_A N(d_1) - De^{-rT}N(d_2)$$ | **Probability of default** (firm value vs debt) |
| **Altman Z-Score** $$Z = 1.2X_1 + 1.4X_2 + 3.3X_3 + 0.6X_4 + X_5$$ | **Bankruptcy prediction** using financial ratios |
| **CDS Pricing Model** | **Credit Default Swap** fair premium / default probability |
| **Hazard Rate Model** $$\lambda(t) = \lim_{\Delta t \to 0}\frac{P(t < T \leq t+\Delta t \mid T > t)}{\Delta t}$$ | **Instantaneous default probability** over time |
| **Gaussian Copula (Li Model)** | **Correlated defaults** in CDO tranches |

---

## 🗺️ QUICK SUMMARY MAP

```
WHAT YOU WANT TO PREDICT         →    USE THIS MODEL
─────────────────────────────────────────────────────
Future Stock Price               →    GBM, ARIMA, LSTM
Option Price                     →    Black-Scholes, Binomial, Monte Carlo
Volatility                       →    GARCH, Heston, EWMA
Interest Rates                   →    Vasicek, CIR, Hull-White
Portfolio Risk                   →    VaR, CVaR, Markowitz
Optimal Weights                  →    Mean-Variance, Black-Litterman
Probability of Default           →    Merton, Altman Z-Score, Hazard Rate
Trading Signals                  →    ML Models, Pairs Trading, RL
Tail/Systemic Risk               →    Copula, Stress Testing, ES
```

---

