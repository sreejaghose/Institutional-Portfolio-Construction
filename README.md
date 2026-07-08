# Institutional Portfolio Construction using Long-Term Capital Market Assumptions

Comparing **Schur Complement Allocation**, **Mean-Variance Optimization (MVO)**, and **Hierarchical Risk Parity (HRP)** under realistic institutional portfolio constraints.

---

## Overview

This project evaluates three portfolio optimization techniques using **J.P. Morgan Long-Term Capital Market Assumptions (LTCMA)** as forward-looking inputs. Rather than relying solely on historical estimates, the models incorporate institutional investment constraints representative of **endowments** and **pension funds**.

The objective is to compare how different optimization methods perform when balancing expected returns, diversification, turnover, and practical allocation limits over a ten-year backtest.

---

## Motivation

Traditional portfolio optimization often suffers from unstable estimates of expected returns and covariance matrices. This project explores whether more robust allocation methods can improve portfolio construction while remaining practical for institutional investors.

Specifically, the project compares:

- **Mean-Variance Optimization (MVO)** — return-driven optimization using expected returns and covariance.
- **Hierarchical Risk Parity (HRP)** — diversification-driven allocation using hierarchical clustering.
- **Schur Complement Allocation** — a hybrid approach that combines the robustness of minimum variance with the diversification benefits of hierarchical allocation.

---

## Data

### Long-Term Capital Market Assumptions

The optimization models use **J.P. Morgan Long-Term Capital Market Assumptions (2016–2026)**, including:

- Expected returns
- Expected volatility
- Correlation matrices

These assumptions provide more stable forward-looking estimates than historical return averages.

### Backtesting Data

Portfolio performance is evaluated using quarterly **Total Return Indexes** spanning **2016–2026**.

---

## Investable Universe

The portfolio consists of **14 asset classes** across three major categories.

### Equity

- U.S. Large Cap
- U.S. Small Cap
- Emerging Markets

### Fixed Income

- U.S. Cash
- U.S. TIPS
- U.S. Treasuries
- U.S. Investment Grade Corporates
- U.S. High Yield

### Alternatives

- Private Equity
- U.S. REITs
- Macro Hedge Funds
- Relative Value Hedge Funds
- Commodities
- Gold

---

## Optimization Methods

### Mean-Variance Optimization (MVO)

- Maximizes expected utility
- Uses expected returns and covariance matrix
- Produces the highest expected return
- Sensitive to estimation error

---

### Hierarchical Risk Parity (HRP)

- Clusters assets by correlation
- Allocates risk recursively
- Does not require expected return estimates
- Produces diversified portfolios with lower turnover

---

### Schur Complement Allocation

- Uses block covariance structure
- Incorporates cross-cluster relationships
- Bridges minimum variance and hierarchical approaches
- Designed to improve robustness while maintaining diversification

---

## Portfolio Constraints

Two institutional investor profiles were considered.

### Endowment Portfolio

| Constraint | Limit |
|------------|------:|
| Maximum Equity | 55% |
| Minimum Fixed Income | 5% |
| Maximum Alternatives | 40% |
| Maximum Private Equity | 25% |
| Maximum Single Asset | 20% |

---

### Pension Fund Portfolio

| Constraint | Limit |
|------------|------:|
| Maximum Equity | 40% |
| Minimum Fixed Income | 30% |
| Maximum Alternatives | 15% |
| Maximum Private Equity | 10% |
| Maximum Single Asset | 15% |

---

## Rebalancing Framework

Portfolios are rebalanced quarterly using a gradual adjustment process.

Features include:

- Annual optimization using updated LTCMA assumptions
- 5% drift threshold before rebalancing
- Partial rebalancing to reduce turnover
- Institutional allocation constraints
- Different risk-aversion parameters for endowments and pension funds

---

## Results

### Key Findings

- Mean-Variance Optimization achieved the highest annualized return and Sharpe ratio.
- HRP generated the lowest turnover through stable diversification.
- Schur Complement Allocation provided a balance between diversification and robustness.
- Institutional allocation constraints reduced the achievable efficient frontier.
- Turnover constraints had relatively little effect on long-term performance.

---

## Performance Summary

### Endowment Portfolio

| Model | Return | Volatility | Sharpe |
|------|-------:|-----------:|--------:|
| Mean-Variance | 7.11% | 6.84% | 0.68 |
| Schur | 6.39% | 7.19% | 0.54 |
| HRP | 6.15% | 7.16% | 0.51 |

---

### Pension Portfolio

| Model | Return | Volatility | Sharpe |
|------|-------:|-----------:|--------:|
| Mean-Variance | 6.99% | 7.20% | 0.63 |
| Schur | 6.00% | 7.05% | 0.50 |
| HRP | 6.02% | 7.59% | 0.47 |

---


## Future Improvements

Potential extensions include:

- Black-Litterman expected return estimation
- Robust covariance estimation
- Transaction cost modeling
- Dynamic risk budgeting
- Regime-switching optimization
- Bayesian portfolio optimization
- Alternative rebalancing policies

---

## References

- J.P. Morgan Long-Term Capital Market Assumptions
- Peter Cotton (2024), *Schur Complementary Allocation: A Unification of Hierarchical Risk Parity and Minimum Variance Portfolios*
- Marcos López de Prado (2018), *Advances in Financial Machine Learning*
- skfolio Portfolio Optimization Library
