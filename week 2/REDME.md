
---

## Problem Overview

Financial markets are inherently dynamic, with relationships between price, momentum, and volatility changing over time. Static models often fail to adapt to these shifts.

In this assignment, a **Kalman Filter–based framework** is used to:
- Estimate time-varying latent parameters governing stock price behavior
- Integrate machine learning for predictive modeling
- Generate algorithmic buy/sell signals
- Backtest the resulting trading strategy and evaluate its performance

---

## Notebook Overview

### Buy/Sell Strategy using LSTM + Kalman Filter
**Notebook:** `Buy_sell_using_LSTM_along_with_kalman_filter.ipynb`

This notebook implements the complete trading pipeline:

#### 1. Data Collection
- Historical daily price data for **MSFT** fetched from Yahoo Finance
- Long enough time horizon to capture different market regimes

#### 2. Feature Engineering
Constructed features include:
- Moving averages over multiple windows
- Log returns and lagged returns
- Momentum and rate-of-change indicators
- Rolling volatility measures

These features are used to model price dynamics more robustly.

#### 3. Kalman Filter Modeling
- A state-space model is defined where latent states represent **time-varying regression coefficients**
- The Kalman Filter recursively updates these parameters as new data arrives
- Assumptions about process noise and observation noise are explicitly stated

#### 4. Machine Learning Integration
- Kalman-filtered states are used as inputs to an **LSTM-based model**
- The model predicts future price movement / price ratio
- This hybrid setup allows both temporal learning and adaptive parameter estimation

#### 5. Trading Signal Generation
- Buy and sell signals are generated using threshold-based rules on predicted values
- Signals are strictly causal (no future data leakage)
- Risk controls such as position logic and thresholds are incorporated

#### 6. Backtesting & Evaluation
- Strategy performance is simulated over historical data
- Key metrics evaluated include:
  - Cumulative returns
  - Sharpe ratio
  - Maximum drawdown
  - Win/loss ratio
- Performance is compared against a **buy-and-hold benchmark** for MSFT
- Equity curves and signal plots are included for visual analysis

---


December 2025

