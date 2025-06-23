# Portfolio-design

This project implements a multi-strategy **portfolio construction framework** that combines traditional **mean-variance optimization (MVO)** techniques with **machine learning-based return forecasting**. Strategies are evaluated on performance metrics such as return, volatility, and Sharpe ratio.

---

##  Objective

Design a portfolio using historical returns from a basket of U.S. stocks, applying both traditional optimization (with constraints) and machine learning models to generate robust, out-of-sample allocation strategies.

---

## Data Overview

- **Assets**: 10 large-cap stocks (e.g., AAPL, MSFT, AMZN, NVDA, GOOGL, etc.)
- **Source**: Yahoo Finance via the `yfinance` library
- **Frequency**: Monthly resampled adjusted close prices (2015–2025)

---

## Strategies Implemented

### 1. **Classic Mean-Variance Optimization (MVO)**
- Uses the past 12 months of returns to estimate expected return and covariance.
- Allocates based on inverse-covariance weighting.
- No constraints.

### 2. **Improved MVO**
- Shrinkage-based covariance estimation (Ledoit-Wolf)
- Portfolio optimization via convex programming:
  - Long-only
  - Max 20% allocation per asset
  - Objective: Maximize expected return minus risk penalty

### 3. **Equal-Weighted Benchmark**
- Passive strategy with equal allocation across all assets.

### 4. **Machine Learning-Based Allocation**
#### a. **Random Forest**
- Predicts next-month returns using a rolling 3-month window of lagged returns.
- Weights based on predicted next-period return vector.

#### b. **XGBoost**
- Same setup as Random Forest but using boosted decision trees.

---

## Performance Metrics

- **Annualized Return**
- **Annualized Volatility**
- **Sharpe Ratio**

Results are visualized via cumulative return plots and summarized in a comparison table.

---

## Visualization

- Line plot of cumulative returns across all strategies
- Printed table of performance metrics

---
