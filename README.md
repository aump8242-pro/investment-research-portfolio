# Systematic Investment Research Portfolio

Investment research by Aum K. Patel, connecting ETF allocation, strategy evaluation and portfolio reporting.

## Featured result

**29.04% model CAGR and 20.81% maximum drawdown** in the domestic ETF momentum test from **1 January 2021 to 1 October 2026**, using prior-session signals, next-open fills, 5 bps slippage per side and estimated broker charges. INR 10 lakh grew to INR 43.31 lakh in this historical simulation.

These are uncapped model returns: two trades exceeded reported full-day volume. They are not live or capacity-validated returns. The optimistic same-close reference returned 30.24% CAGR, but assumes fills at the same close that generated the signal.

The separate global ten-year test returned **15.66% CAGR versus 11.25% for NIFTYBEES buy-and-hold**, with 22.76% versus 36.33% maximum EOD drawdown. Its instruments, dates and execution model differ from the domestic test.

## Projects

| Project | Focus |
| --- | --- |
| [ETF Momentum and Portfolio Analytics](projects/etf-momentum/README.md) | Momentum rotation, model portfolios and investment reporting |
| [Equity Strategy Research](projects/equity-strategies/README.md) | Entry rules, position sizing, costs and exit management |
| [Opening Range Breakout Research](projects/opening-range/README.md) | Early-session price and volume signals |
| [Options Data Collection](projects/options-data/README.md) | Recorded derivatives sessions for future analysis |

## Read the results

[Results, comparisons and assumptions](RESULTS.md) explain each scenario. [Numerical evidence](evidence/etf-backtest-summary.json) includes saved metrics, annual returns, source checksums and independent equity-curve checks.

This public showcase contains project documentation and aggregate results. Full implementation code, API credentials and raw market/session data are excluded. It is not a runnable application. Live deployment and production readiness have not been established.

## Project tools

Python, pandas, market-data APIs, SQLite, portfolio accounting and investment reporting. Historical datasets use Upstox with Yahoo supplements, rather than Yahoo Finance alone.
