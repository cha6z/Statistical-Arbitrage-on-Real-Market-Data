# Statistical Arbitrage on Real Market Data  
Author: Chabod M.

## Overview

This project implements and evaluates systematic trading strategies using real market data. The focus is not the strategy itself, but the statistical validation framework used to assess robustness and significance.

---

## Trading Strategy Development Framework

1. In-Sample Optimization  
2. In-Sample Permutation Testing  
3. Walk-Forward Validation  
4. Walk-Forward Permutation Testing  

This layered validation structure reduces overfitting and enforces statistical discipline.

---

## Strategy Evaluation Methodology

To illustrate the process, consider a simple moving average crossover strategy.

### Signal Construction

- Compute a Fast Moving Average (FMA)  
- Compute a Slow Moving Average (SMA)  

Signal logic:

- If FMA > SMA, hold a long position  
- Otherwise remain flat  

The signal represents the position taken after the bar closes.

---

## Return Attribution

Close-to-close return:

r_t = (P_t − P_{t−1}) / P_{t−1}

Strategy return:

R_t = Signal_{t−1} × r_t

Returns are shifted forward one bar to eliminate look-ahead bias.  
This ensures returns are attributed only to positions that were actually held.

---

## Objective Functions

Using bar-level strategy returns, compute:

- Sharpe Ratio  
- Profit Factor  
- Maximum Drawdown  
- Sortino Ratio  
- Calmar Ratio  

Computing returns at bar granularity increases sample size and improves estimator stability, provided transaction costs and slippage are properly modeled.

---

## Statistical Robustness

To avoid false discovery:

- Apply permutation tests to the signal sequence  
- Validate parameters using walk-forward testing  
- Require consistent out-of-sample performance  

Only strategies that survive all validation layers are considered viable.

---

## Core Philosophy

A trading strategy is not validated by profitability alone.

It must demonstrate:

- Statistical significance  
- Parameter stability  
- Out-of-sample persistence  
- Robust risk-adjusted performance  

Granularity improves estimator reliability when noise and execution costs are properly controlled.
