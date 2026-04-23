# Capital Asset Pricing Model (CAPM) – Multi-Asset & Portfolio Analysis

## 📌 Overview

This project implements the Capital Asset Pricing Model (CAPM) to estimate the relationship between systematic risk (beta) and expected return.

The model is extended to:

- Multiple assets
- A dynamically constructed portfolio
- Beta estimation using both covariance and regression

## 🧠 Key Concepts

### 1. Log Returns

Monthly log returns are computed as:

$$ r_t = \ln\left(\frac{P_t}{P_{t-1}}\right) $$

### 2. CAPM Equation

The expected return of an asset (or portfolio):

$$ E[R_i] = R_f + \beta_i (E[R_m] - R_f) $$

Where:

- $R_f$: Risk-free rate
- $R_m$: Market return
- $\beta$: Sensitivity to market movements

### 3. Beta (Systematic Risk)

Beta is calculated using covariance:

$$ \beta_i = \frac{\text{Cov}(R_i, R_m)}{\text{Var}(R_m)} $$

### 4. Linear Regression Model

$$ R_i = \alpha + \beta R_m + \epsilon $$

Where:

- $\alpha$: abnormal return
- $\beta$: market sensitivity

### 5. Portfolio Return

$$ R_p = \sum w_i R_i $$

### 6. Portfolio Beta

$$ \beta_p = \sum w_i \beta_i $$

## ⚙️ Methodology

1. Collect historical price data using `yfinance`
2. Resample daily prices into monthly data
3. Compute log returns
4. Estimate beta using:
   - Covariance method
   - Linear regression
5. Construct a random portfolio (Dirichlet weights)
6. Compute:
   - Portfolio beta
   - Expected return using CAPM
7. Visualize the market vs portfolio relationship

## 📈 Assets Used

- Apple Inc.
- Tesla Inc.
- Walmart Inc.
- Market Proxy: SPDR S&P 500 ETF Trust

## 📊 Results

### Portfolio Beta

- Covariance Method: **1.2637**
- Regression Method: **1.2637**

> 👉 Consistency between methods validates the implementation.

### Expected Return (CAPM)

- Risk-Free Rate: **1%**
- Market Return: **15.73%**
- Portfolio Expected Return: **19.62%**

### Alpha (Excess Return)

$$ \alpha = 0.0122 $$

> 👉 Indicates positive abnormal performance relative to CAPM.

## 📉 Visualization

The regression plot shows:

- Scatter of market vs portfolio returns
- CAPM regression line

> 👉 The slope represents beta, and the intercept represents alpha.

## 🔍 Key Insights

- **Tesla Inc.** exhibits high beta → highly sensitive to market movements
- **Walmart Inc.** shows low beta → defensive asset
- Portfolio beta (~1.26) indicates above-market risk exposure
- Positive alpha suggests potential outperformance vs CAPM prediction

---

## Data Source

Data was obtained using the `yfinance` library from Yahoo Finance.

This project is for **educational purposes only** and does not constitute financial advice.
