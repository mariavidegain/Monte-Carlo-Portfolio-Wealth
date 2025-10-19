# Monte-Carlo-Portfolio-Wealth
This notebook simulates the performance of a simple portfolio composed of equity (SPY), bonds (IEF), and a small allocation to cash (3m Tbill).
The goal is to model possible future paths of portfolio value over time, understand the dispersion of outcomes, and estimate basic risk metrics.

# Approach
Monthly data is downloaded from Yahoo Finance (2005–2025) for SPY and IEF and from FRED database (2005-2025) for 3m Tbill.
Monthly simple returns are calculated for each asset.
The portfolio maintains fixed target weights of 60% equity, 35% bonds, and 5% cash, with monthly rebalancing.
Monthly expected returns and the covariance matrix are estimated using the historical data.
A **Monte Carlo simulation** then generates 10,000 possible 10-year (120-month) scenarios assuming returns follow a multivariate normal distribution.
Each simulated path represents a potential evolution of portfolio wealth over time, starting from an initial value of 1.
The notebook visualizes a sample of 20 simulated wealth paths, the terminal-wealth distribution, and computes the median maximum drawdown and 1-year 95% VaR.

# Assumptions
Monthly returns are assumed i.i.d. (independent and identically distributed) and jointly normal.
The portfolio is rebalanced monthly to maintain the target weights.
The cash return comes from the 3-month US Treasury Bill rate.
Returns are expressed as simple monthly percentages rather than log returns, since they’re easier to interpret and combine across assets, and the difference from log returns at a monthly frequency is practically negligible
The model excludes transaction costs, taxes, and fees.

# Limitations
The normality assumption ignores fat tails, and extreme market moves.
Correlation and volatility are assumed constant over time, which is unrealistic in stressed markets.
The simulation doesn’t account for liquidity constraints or rebalancing costs.
Interest rates, bond duration effects, and inflation aren’t modelled explicitly.
