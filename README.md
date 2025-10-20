# Monte-Carlo-Portfolio-Wealth
This project simulates the performance of a simple portfolio composed of equity (SPY), bonds (IEF), and a small allocation to cash (3M T-Bill).  
The goal is to model possible future portfolio paths, and estimate basic risk metrics.

We start by downloading monthly price data for SPY and IEF from Yahoo Finance (2005–2025), and the 3M Treasury Bill rate from the FRED database.  
Monthly simple returns are calculated for each asset. The portfolio keeps fixed target weights of 60% equity, 35% bonds, and 5% cash, with monthly rebalancing.

We estimate monthly average returns and the covariance matrix from historical data.  
A Monte Carlo simulation then generates 10,000 different 10-year (120-month) paths, assuming returns follow a multivariate normal distribution. Each path represents a potential evolution of portfolio wealth over time, starting from an initial value of 1.

The simulation shows:
- 50 sample simulated portfolio paths  
- The terminal wealth distribution  
- The median maximum drawdown  
- The 1-year 95% Value-at-Risk (VaR)

### Assumptions
- Monthly returns are i.i.d. and jointly normal.  
- Portfolio is rebalanced monthly to maintain target weights.  
- The cash return is based on the 3M US Treasury Bill rate.  
- Returns are calculated as simple monthly percentages instead of log returns.  
- Transaction costs, taxes, and fees are excluded.

### Limitations
- Normality assumption ignores fat tails and extreme events.  
- Correlation and volatility are assumed constant over time.  
- Liquidity constraints and rebalancing costs are not considered.  
- Interest rate and inflation dynamics are not explicitly modelled.
