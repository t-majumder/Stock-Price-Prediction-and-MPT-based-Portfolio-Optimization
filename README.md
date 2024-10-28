# Stock-Price-Prediction-and-MPT-based-Portfolio-Optimization
Here’s the modified project description with your result table incorporated:

## Project Overview
This project combines **Long Short-Term Memory (LSTM)** neural networks and **Modern Portfolio Theory (MPT)** to optimize stock portfolio allocation for individual investors. By predicting stock trends with LSTM and applying MPT for diversification, this approach balances maximizing returns with minimizing risks. This model is designed as a tool for risk-averse investors aiming for a low-risk portfolio with satisfactory returns.

### Objectives
The core objectives of this project include:
- **Stock Selection**: Using predicted performance to filter stocks, mitigating downside risk.
- **Prediction with LSTM**: Forecasting stock prices with LSTM to capture complex temporal patterns in the market.
- **Portfolio Optimization**: Applying MPT to the selected stocks for an efficient portfolio with the best risk-return tradeoff.

## Methodology

1. **Stock Data Collection and Preparation**:
   - Real-time stock data was collected via Yahoo Finance, ensuring updated values instead of static historical data. 
   - Data preprocessing included handling missing values, scaling, and preparing for LSTM model training.

2. **LSTM Prediction for Stock Selection**:
   - **LSTM Architecture**: LSTM’s ability to capture long-term dependencies and seasonality made it ideal for time-series forecasting of stock prices.
   - **Adam Optimizer**: The model was optimized with the Adam optimizer, reducing training time while maintaining predictive accuracy.
   - **Prediction Evaluation**: The LSTM model’s accuracy was validated by achieving low RMSE values (e.g., 2.646 for ONGC), confirming its reliability in trend prediction.
   - **Stock Selection Criteria**: Only stocks exceeding a certain predicted performance threshold were chosen, reducing the likelihood of risky investments.

3. **Markowitz Portfolio Optimization (MPT)**:
   - **Variance and Covariance Calculation**: For selected stocks, MPT calculated variance, covariance, and correlations to quantify interdependencies.
   - **Efficient Frontier and Sharpe Ratio**: 5000 randomized portfolio weights generated a plot of the Efficient Frontier, identifying the optimal tradeoff points.
   - **Optimal Portfolio Selection**: By analyzing annual return rate, volatility, and Sharpe Ratio, MPT provided portfolios that achieved the highest Sharpe ratio, lowest risk, and highest return.

## Results and Portfolio Selection

The following table summarizes the results for each optimized portfolio strategy:

| Portfolio                  | Annual Return Rate (%) | Volatility (%) | Sharpe Ratio |
|----------------------------|------------------------|----------------|--------------|
| Randomly Assigned Weights  | 22.69                 | 18.75         | 1.156        |
| **Highest Return**         | 29.75                 | 26.13         | 1.100        |
| **Lowest Risk**            | 21.05                 | 16.29         | 1.230        |
| **Maximum Sharpe Ratio**   | 23.94                 | 17.31         | 1.325        |

- **Highest Return Portfolio**: Achieves an annual return of 29.75% with a higher volatility of 26.13%, suitable for investors prioritizing returns over stability.
- **Lowest Risk Portfolio**: Prioritizes stability with the lowest volatility of 16.29%, resulting in a slightly lower return of 21.05% but a higher Sharpe ratio of 1.230.
- **Maximum Sharpe Ratio Portfolio**: Balances return and risk effectively, achieving an annual return of 23.94% with volatility at 17.31% and a Sharpe Ratio of 1.325, ideal for risk-averse investors seeking moderate growth.

## Use Cases
1. **Individual Investor Portfolio Management**: Provides a diversified, low-risk portfolio with adaptive, data-driven allocations.
2. **Investment Advisors**: Equips advisors with a reliable tool for creating and justifying portfolio strategies.
3. **Automated Trading Systems**: With real-time data from Yahoo Finance and LSTM’s predictive capability, this model can support automated, high-frequency trading.

## Monitoring Plan

The following strategy guides the monitoring and continual validation of portfolio performance:

1. **Real-time Market Data Integration**:
   - Continuously update stock data from Yahoo Finance, ensuring real-time alignment of predictions with market movements.
   
2. **Daily Prediction Verification**:
   - Track daily stock performance against LSTM predictions, removing or re-evaluating stocks that deviate from expectations.

3. **Market Event-Based Portfolio Adjustments**:
   - Reapply MPT optimization following market events or company-specific news, maintaining a portfolio aligned with risk-return objectives.

4. **Efficient Frontier Tracking**:
   - Recompute and plot new Efficient Frontiers as the market shifts, ensuring the portfolio remains within the optimal risk-return profile.
