# S&P 500 Monte Carlo Risk Modelling

This project analyses simulated S&P 500 downside risk using Normal GBM, Student-t shocks, and GARCH-t volatility modelling.
## Research Question

How sensitive are simulated S&P 500 downside-risk estimates to assumptions about return distributions and volatility dynamics?
## Methodology

- Downloaded approximately 10 years of historical SPY data.
- Calculated daily returns and historical volatility.
- Built a Normal GBM Monte Carlo model with 10,000 one-year simulated price paths.
- Replaced normal shocks with Student-t shocks to model fat tails.
- Fitted a GARCH(1,1)-t model to capture time-varying volatility and volatility clustering.
- Compared the models using maximum drawdown probabilities.
- ## Key Results

| Model | 20%+ Drawdown | 30%+ Drawdown | Median Max Drawdown |
|---|---:|---:|---:|
## Interpretation

The results suggest that moderate downside-risk estimates are relatively similar across the three models, while extreme tail-risk estimates are much more sensitive to volatility assumptions. In particular, the GARCH-t model produced a much higher probability of 30%+ drawdowns because it allows volatility to change over time and cluster after large shocks.
## Limitations

- The models are calibrated using historical SPY data, so future market behaviour may differ from the historical sample.
- Normal GBM assumes constant volatility and normally distributed shocks.
- Student-t GBM allows fatter tails but still assumes constant volatility.
- GARCH-t captures volatility clustering, but it still does not model every feature of real markets, such as sudden structural breaks, liquidity shocks, or regime changes.
- The simulated probabilities are model-dependent estimates, not forecasts of what the S&P 500 will actually do.
- ## Tools Used

Python, NumPy, Pandas, Matplotlib, SciPy, yfinance, and the `arch` package for GARCH modelling.
