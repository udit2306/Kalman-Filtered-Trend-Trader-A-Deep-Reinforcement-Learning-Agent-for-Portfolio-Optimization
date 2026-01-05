# Week 2 – Kalman Filtered Trading System

This folder contains **Week 2 WiDS assignment**, where theory transitions into a **full-fledged adaptive trading model** using **Kalman Filters and Machine Learning**.

The goal is to model **non-stationary financial markets** realistically.

---

## Problem Statement

Traditional regression assumes fixed parameters:
\[
r_t = X_t^T \beta
\]

However, market dynamics change over time.  
To address this, we model **time-varying coefficients** using a **Kalman Filter**.

---

## Core Components

### 1️ Feature Engineering
- Log returns
- Lagged returns (mean reversion & momentum)
- Momentum indicators
- Volatility regimes
- Volume-based activity measures

All features are **lagged or rolling** → no forward-looking bias.

---

### 2️ Kalman Filter Model

**State Equation**
\[
\beta_t = \beta_{t-1} + w_t
\]

**Observation Equation**
\[
r_t = X_t^T \beta_t + \epsilon_t
\]

- Coefficients evolve smoothly
- Process noise controls adaptability
- Filter balances prior belief and new data

---

### 3️ Machine Learning Integration

- Kalman-filtered predictions are combined with raw features
- Ridge Regression is used to:
  - Reduce overfitting
  - Handle multicollinearity
  - Stabilize predictions

---

### 4️ Trading Strategy

- Long / Short / Neutral signals
- Threshold-based execution
- Transaction costs included
- Position shifted to avoid look-ahead bias

---

### 5️ Backtesting & Evaluation

- Equity curve comparison
- Drawdown analysis
- Sharpe ratio
- Benchmark: Buy & Hold (MSFT)

---

## Key Insights

- Strategy performs best in **volatile regimes**
- Buy & Hold dominates long bull markets
- Kalman coefficients reveal **regime shifts**
- Lower downside risk than passive exposure

---

## Learning Outcome

This week bridges:
- **Theory to Practice**
- **Statistics to Filtering**
- **ML to Trading**
- **Static to Adaptive systems**

It forms the **core foundation** for extending into **reinforcement learning–based portfolio optimization**.

