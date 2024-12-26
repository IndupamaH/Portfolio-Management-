# Portfolio Management (12/20/2024)

## Overview

This project explores various techniques for portfolio management and optimization. It aims to construct efficient portfolios by implementing, analyzing, and comparing different quantitative models used in financial portfolio management. These models include Monte Carlo method, Mean Variance Optimization method, Capital Asset Pricing method, and Black Litterman method. The focus is on balancing risk and return, incorporating investor views, and testing the performance of these strategies in real-world scenarios.

## Stakeholders
- Financial Analysts: Use these techniques to optimize client portfolios.
- Investors: Gain insights into how portfolios are constructed to maximize returns while managing risk.
- Students and Researchers: Learn advanced portfolio management techniques.
- Quants and Data Scientists: Explore quantitative methods for financial optimization.

## KPI

Compare the metrics such as return and risk(volatility) of the portfolio among each model and with the base model of equal weights. 

## Models Implemented

1. **Equal Weight Portfolio**:
- In this model, equal weights are assigned to all assets and is used as a baseline for comparison.
  
2. **Monte Carlo Simulation**:
- This method simulates random sampling of asset weights to generate a range of potential portfolio outcomes. It identifies the portfolio with the maximum Sharpe ratio, which optimizes return relative to risk, and the minimum volatility portfolio, which minimizes risk for stability. These portfolios are highlighted on the efficient frontier, illustrating optimal trade-offs between risk and return.

3. **Mean-Variance Optimization (Markowitz Model)**:
- Identifies the efficient frontier by optimizing portfolios based on expected returns and risk. Here, I found the optimal  weights for the portfolio with maximum SHarpe ratio and minimum volatility.
- The model assumes that investors are rational and risk-averse.

4. **Capital Asset Pricing Model (CAPM)**:
- Calculates the expected return of assets based on their beta and market risk premium. Then, included only the assets with actual return higher than predicted expected return based on maximum Sharpe ratio.
- Serves as a foundational model for estimating risk-adjusted returns.
 
5. **Black-Litterman Model**:
- Combines market equilibrium (implied returns) with investor views to produce intuitive and stable portfolio allocations.
- Past stock prices are used along with short and long term moving averages to come up with investor views. Then, the optimal portfolio weights that maximize the Sharpe ratio are found using the adjusted expected return and covariance matrix. 

## Data
Historical asset prices and returns were sourced from Yahoo Finance for the tickers ['AAPL', 'MSFT', 'GOOGL', 'AMZN', 'TSLA'] over the past five years starting from today(12/20/24).

<img src="https://github.com/user-attachments/assets/7edbf10c-1f2d-4d98-912a-fb520377eef6" alt="stock_prices" width="500">

## Results

|Method|Portfolio Return|Portfolio Risk|Sharpe Ratio|Weights|
|---|---|---|---|---|
|Equal Weights|0.37|0.32|1.08||
|Monte Carlo (Max Sharpe)|0.52|0.41|1.19|<img src="https://github.com/user-attachments/assets/81e5ee11-4732-4e4a-b0ec-55ff5e797047" width="150"/><br />[0.41, 0.  , 0.11, 0.02, 0.46]|
|Monte Carlo (Min_Volatility)|0.28|0.28|0.87|<img src="https://github.com/user-attachments/assets/4fb0ae07-2f46-4e09-8ee6-e2356a198f6f" width="150"/><br />[0.31, 0.14, 0.25, 0.3 , 0.  ]|
|MVO (Max Sharpe)|0.52|0.41|1.19|<img src="https://github.com/user-attachments/assets/d8d39671-9591-46bb-b605-8c2909f5b624" width="150"/><br />[0.42, 0.  , 0.12, 0.  , 0.45]|
|MVO (Min_Volatility)|0.28|0.28|0.88|<img src="https://github.com/user-attachments/assets/aabecb8c-d092-415d-9dd9-1417f6e27707" width="150"/><br />[0.33, 0.13, 0.24, 0.31, 0.  ]|
|CAPM (Max Sharpe)|0.52|0.41|1.19|<img src="https://github.com/user-attachments/assets/14ff9f0f-3b21-44fa-8f68-ce0c6af0db19" width="150"/><br />[0.43, 0, 0.12, 0, 0.45]|
|BL|0.24|0.37|0.58|<img src="https://github.com/user-attachments/assets/67eb5eb9-f56d-4d0b-845b-c4641b78de72" width="150"/><br />[0.06, 0.09, 0.  , 0.51, 0.34]|

## Graphs

**efficient frontier - Monte Carlo simulation**    

<img src="https://github.com/user-attachments/assets/e0d48a01-1f40-4b8f-b3d0-294be5f03633" width="500"/> 


**efficient frontier - MVO**

<img src="https://github.com/user-attachments/assets/e683483a-9ed5-43da-bc1e-613264945d05" width="500"/>

## Conclusion

* The equal-weighted portfolio provides a moderate return and risk. This method is simple and does not consider market dynamics or optimization, leading to a Sharpe Ratio lower than optimized portfolios.
* The models, Monte Carlo, MVO, and CAPM approach show similar results in terms of maximizing the Sharpe Ratio giving almost same portfolio weights. methods provided the highest return and Sharpe ration among all methods, but the risk level is higher than the equal-weighted portfolio.
* Further, the methods that minimized the portfolio risk are also closely aligned in terms of the portfolio return, risk and weights. These models excluded the Tesla stock in the portfolio due to its high volatility, however, resulted in a lower return.
* BL method delivers the lowest Sharpe Ratio, likely due to its reliance on subjective views or priors that may have dampened returns. While it offers a more balanced perspective, it underperforms compared to other methods optimized for risk-adjusted returns.


**Max Sharpe Methods (Monte Carlo, MVO, CAPM):**

These approaches are the most effective for investors aiming to maximize return per unit of risk. They deliver the highest Sharpe Ratio (1.19), making them suitable for portfolios seeking aggressive but efficient growth.

**Min Volatility Methods (Monte Carlo, MVO):**

Suitable for risk-averse investors, these methods provide the lowest risk but at the cost of reduced returns. MVO achieves a slightly better Sharpe Ratio than Monte Carlo in this project. 

**Black-Litterman:**

This method underperforms in this setup, possibly due to overly conservative views or priors. It is better suited for investors who want to incorporate subjective market perspectives.

**Portfolio Optimization Summary:**

* For maximizing returns per unit of risk, Monte Carlo (Max Sharpe), MVO (Max Sharpe), and CAPM (Max Sharpe) are the top choices.
* For risk minimization, MVO (Min Volatility) offers better Sharpe Ratios than its Monte Carlo counterpart.
Investors should choose the method based on their risk tolerance and investment objectives.



