# Portfolio Management (12/19/2024)

## Overview

This project explores various techniques for portfolio management and optimization. It aims to construct efficient portfolios by implementing, analyzing, and comparing different quantitative models used in financial portfolio management. These models include the Black-Litterman Model, Mean-Variance Optimization, and others. The focus is on balancing risk and return, incorporating investor views, and testing the performance of these strategies in real-world scenarios.

## Stakeholders
- Financial Analysts: Use these techniques to optimize client portfolios.
- Investors: Gain insights into how portfolios are constructed to maximize returns while managing risk.
- Students and Researchers: Learn advanced portfolio management techniques.
- Quants and Data Scientists: Explore quantitative methods for financial optimization.

## KPI

Compare the metrics such as return and risk(volatility) of the portfolio among each model and with the base model of equal weights. 

## Models Implemented

1. **Equal Weight Portfolio**:
- Simple strategy where equal weights are assigned to all assets.
- Used as a baseline for comparison.
  
2. **Monte Carlo Simulation**:
- Simulates a range of potential portfolio outcomes based on random sampling of asset returns.
- Used to evaluate the probability of achieving specific investment goals.

3. **Mean-Variance Optimization (Markowitz Model)**:
- Identifies the efficient frontier by optimizing portfolios based on expected returns and risk.
- Assumes that investors are rational and risk-averse.

4. **Capital Asset Pricing Model (CAPM)**:
- Calculates the expected return of assets based on their beta and market risk premium.
- Serves as a foundational model for estimating risk-adjusted returns.
 
5. **Black-Litterman Model**:
- Combines market equilibrium (implied returns) with investor views to produce intuitive and stable portfolio allocations.
- Uses Bayesian methods to incorporate confidence levels in views.

## Data
Historical asset prices and returns were sourced from Yahoo Finance for the tickers ['AAPL', 'MSFT', 'GOOGL', 'AMZN', 'TSLA'] over the past five years starting from today(12/19/24).

<img src="https://github.com/user-attachments/assets/7edbf10c-1f2d-4d98-912a-fb520377eef6" alt="stock_prices" width="500">



