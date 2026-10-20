# ETF Momentum and Portfolio Analytics

## Investment question

Can a rules-based rotation across ETFs combine momentum selection with risk controls and clear portfolio reporting?

## Research highlights

- Domestic next-open test with 5 bps slippage: **29.04% model CAGR**, **20.81% maximum drawdown**, 2021 to 1 October 2026.
- Optimistic same-close reference: **30.24% CAGR**; theoretical signal-close fills.
- Separate global ten-year extension: **15.66% CAGR versus 11.25% NIFTYBEES**, 2016 to 20 October 2026.

These are uncapped historical simulations with liquidity and data limitations, not live or production performance. The domestic and global universes differ. See the [full comparison](../../RESULTS.md) before interpreting the headline figures.

## Portfolio process

The ten-year global model combines short- and long-horizon momentum, selects up to six ETFs, checks a 200-day moving-average entry filter, resizes monthly and evaluates daily-close stops. Eligibility grows with available history. A model portfolio records cash, holdings, charges and trade activity.

## Dashboard

The reviewed server refreshes domestic history through Upstox, accesses global ETF and FX data through a separate adapter, and passes prices to the portfolio engine. It uses a SQLite-backed store interface, background refresh, market-data validation, pause/resume controls and CSV exports. Its backtest endpoint reads saved comparison and equity files.

## Evidence and scope

[Metrics, annual returns and verification](../../evidence/etf-backtest-summary.json) support the published figures. Indian histories are Upstox-primary with Yahoo supplements. A full Yahoo-only replay was not performed for this update.

Full implementation code and raw datasets are excluded from the public showcase. This repository provides research documentation and aggregate evidence, not a runnable deployment.
