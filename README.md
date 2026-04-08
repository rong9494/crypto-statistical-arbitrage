# Statistical Arbitrage in Cryptocurrencies

A quantitative research project exploring **momentum** and **mean-reversion (reversal)** strategies in the cryptocurrency market.

## Project Overview

This research applies systematic trading techniques from quantitative hedge funds to the cryptocurrency market, using daily OHLCV data from **Binance** (April 2024 – April 2026) across a universe of 10 large-cap crypto assets.

### Strategies Researched

| Strategy | Approach | Gross Sharpe |
|----------|----------|-------------|
| Cross-Sectional Momentum | Rank assets by N-day trailing return; long winners, short losers | ~1.0 |
| Mean Reversion | Z-score signal; long oversold, short overbought | ~0.3 |

### Key Themes

- **Signal Construction**: Cross-sectional ranking and z-score normalization
- **Execution Cost Modeling**: 7 bps (limit orders)
- **Portfolio Optimization**: Convex optimization (cvxpy) for strategy weighting
- **Performance Evaluation**: Returns, volatility, Sharpe ratio, max drawdown, alpha/beta vs. BTC

## Asset Universe

`BTCUSDT` · `ETHUSDT` · `BNBUSDT` · `SOLUSDT` · `XRPUSDT` · `ADAUSDT` · `DOTUSDT` · `AVAXUSDT` · `LINKUSDT` · `MATICUSDT`

## Data Source

Live data pulled from the [Binance public API](https://python-binance.readthedocs.io/) — no API key required for historical klines.

## Requirements

```bash
pip install pandas numpy matplotlib scipy cvxpy python-binance
```

## How to Run

1. Clone the repository
2. Install dependencies
3. Open `Statistical_Arbitrage_in_Cryptocurrencies.ipynb` in Jupyter
4. Run all cells top-to-bottom

> **Note**: The notebook fetches live data from Binance on execution. An internet connection is required.

## Notebook Structure

| Section | Content |
|---------|---------|
| 1 | Imports & Setup |
| 2 | Data Collection (Binance API) |
| 3 | Exploratory Data Analysis |
| 4 | Strategy 1 – Cross-Sectional Momentum |
| 5 | Strategy 2 – Mean Reversion |
| 6 | Performance Summary & Alpha/Beta Analysis |
| 7 | Convex Optimization for Strategy Combination |
| 8 | Execution Cost Analysis |
| 9 | Final Results & Conclusion |

## Key Findings

- **Momentum** is strongest at medium-term horizons (>11 days; optimal ~20 days), consistent with sustained investor herding in crypto
- **Reversal** shows weak signal after costs due to high turnover

## Reference

Methodology inspired by:
- *Statistical Arbitrage in Cryptocurrencies* — [Part 1](https://medium.com/@johnnya12399/statistical-arbitrage-in-cryptocurrencies-part-1-7ed626ed9629) · [Part 2](https://medium.com/@johnnya12399/statistical-arbitrage-in-cryptocurrencies-part-2-cb146c95737b) · [Part 3](https://medium.com/@johnnya12399/statistical-arbitrage-in-cryptocurrencies-part-3-f11e1fe21d5c)
- The Wall Street Quants Course — *Momentum, Reversal, and Backtesting* modules

---

*For educational and research purposes only. Not financial advice.*
