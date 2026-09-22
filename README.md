# Portfolio Optimization & Trading Workshops

A small collection of self-contained Jupyter notebooks exploring the basics of quantitative finance: portfolio construction, trading strategy backtesting, and risk metrics.

These notebooks started as workshop material for **Télécom Business & Finance**, the finance association of Télécom Paris — a way for students to get a hands-on, code-first introduction to market finance. This repository is a cleaned-up, English, fully-run version of that material.

## Notebooks

| Notebook | Topic |
|---|---|
| [`trading_workshop_1_portfolio_optimization.ipynb`](trading_workshop_1_portfolio_optimization.ipynb) | **Modern Portfolio Theory** — expected return & risk, the covariance matrix, Monte Carlo sampling of the efficient frontier, and a backtest of a periodic-rebalancing strategy. |
| [`trading_workshop_2_strategy_backtesting.ipynb`](trading_workshop_2_strategy_backtesting.ipynb) | **Trading strategy backtesting** — building indicator-based buy/sell signals (EMA, Bollinger Bands, RSI, MACD), backtesting them with [`backtesting.py`](https://kernc.github.io/backtesting.py/), and grid-searching strategy parameters. |
| [`trading_workshop_3_risk_metrics.ipynb`](trading_workshop_3_risk_metrics.ipynb) | **Risk & performance metrics** — Sharpe & Sortino ratios, maximum drawdown, historical/parametric Value at Risk, and CAPM alpha/beta, implemented from their formulas. |

Every notebook fetches live market data through [`yfinance`](https://github.com/ranaroussi/yfinance) (or, for workshop 2, the intraday CSVs bundled in [`data/`](data/)) and has already been fully run, so you can read it straight on GitHub — no execution needed. Numbers and charts will naturally differ if you re-run them later, since markets move.

## Running locally

```bash
python -m venv .venv
source .venv/bin/activate  # on Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

## Disclaimer

This is educational material, not investment advice. The strategies shown are intentionally simple (no transaction costs, no slippage, short backtest windows) and are meant to illustrate concepts, not to be traded.

Workshop 2 in particular optimizes its strategy parameters and evaluates them on the same data, with no train/test split — a textbook setup for overfitting. Its grid search is there to show *how* parameter optimization works, not as evidence that the resulting parameters would hold up on unseen data. The leverage used in that notebook (up to 10x) is likewise only there to make a $100 toy backtest move, not a realistic risk setting.

## License

[MIT](LICENSE) — reuse it, adapt it, just keep the credit.
