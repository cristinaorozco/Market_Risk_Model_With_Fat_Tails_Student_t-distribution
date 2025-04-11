# Market Risk Model (FORD) – Fat Tails via Student t-Distribution

This project applies a Mandelbrot-inspired approach to market risk modeling using historical data from Ford Motor Company. It simulates potential price paths with a fat-tailed return distribution, and calculates the Value at Risk (VaR) and Conditional Value at Risk (CVaR) to evaluate extreme downside risk.

# Motivation

Traditional financial models often assume that asset returns follow a normal distribution. However, this assumption underestimates the probability of extreme market events. Inspired by Benoît Mandelbrot’s theories on fat tails and market turbulence, this model uses a Student's t-distribution to simulate returns with higher kurtosis, providing a more realistic view of tail risk.

# Methodology

- Downloads 5 years of daily price data for Ford (F) from Yahoo Finance using `yfinance`.
- Computes daily returns and extracts the most recent 1,000.
- Simulates 1,000 daily returns using a Student t-distribution with low degrees of freedom (df = 3).
- Transforms simulated returns into prices using exponential compounding.
- Calculates:
  - VaR (95%): Threshold of the worst 5% simulated returns.
  - CVaR (95%): Average return of that worst 5% — a more complete tail risk measure.
- Visualizes the distribution of simulated returns and risk thresholds.

# Results

- Value at Risk (VaR 95%): ~6.32%
- Expected Shortfall (CVaR 95%): ~10.1%

These results confirm the presence of heavy tails in financial returns: when losses exceed VaR, they tend to be significantly larger, just as Mandelbrot predicted.

# Python libraries

- `yfinance` – for data collection
- `pandas`, `numpy` – for data processing
- `matplotlib` – for visualization
- `scipy.stats.t` – for simulating Student t-distributed returns

# Theoretical Inspiration

- Benoît B. Mandelbrot
- Risk metrics: VaR, CVaR (Expected Shortfall)


# Author:
Cristina Orozco.
Linkedin: www.linkedin.com/in/cristina-orozco
