# Kalman Filtered RL Portfolio Agent

An experimental project exploring the use of Kalman Filtering to denoise financial time series before feeding them into a Deep Reinforcement Learning (PPO) agent for portfolio allocation.

The core motivation is that raw market prices are highly noisy and often lead to unstable or overfitted RL policies. By preprocessing price, trend, and volatility using a Kalman Filter, the agent is exposed to a cleaner and more structured representation of the market state.

---

## Project Overview

- Objective: Optimize a multi-asset portfolio for risk-adjusted returns
- RL Algorithm: Proximal Policy Optimization (PPO)
- RL Framework: Stable-Baselines3
- Environment: Custom Gymnasium trading environment

Assets:
- Bitcoin (BTC-USD)
- Nifty 50 Index (^NSEI)
- Gold Futures (GC=F)
- Cash (implicit allocation)

---

## State and Action Design

State Space (per asset):
- Kalman Level: Estimated latent price
- Kalman Velocity: Smoothed trend strength
- Kalman Volatility: Smoothed variance estimate
- Kalman Error: Deviation from filtered level
- RSI: Momentum indicator

Action Space:
- Continuous portfolio weights in range [0, 1]
- One weight per asset plus cash
- Portfolio normalized at every timestep

---

## Reward Function

The agent optimizes log returns with penalties for risk and transaction costs:


reward = portfolio_return \
         - (risk_aversion * portfolio_volatility) \
         - transaction_costs

         
##Training and Evaluation

Training period: 2015 to 2022
Testing period: 2023 to 2024

##Evaluation metrics:

Cumulative return vs Buy and Hold
Sharpe Ratio
Maximum Drawdown
Asset allocation heatmaps
