# Results and verification

## Current evidence

The supplied source files describe strategy implementations, not completed backtest outcomes. No completed ETF momentum comparison report, equity trade report or ORB performance report was located during preparation of this showcase. No new backtest was run for this publication.

| Item | Evidence | What can be concluded |
| --- | --- | --- |
| ETF dashboard | Server routes, data handling and imports | Designed to display portfolio and backtest data; performance figures unavailable |
| Equity baseline | Position lifecycle and charge accounting | Paper-execution logic is implemented; realised investment performance unverified |
| Equity experimental variant | Risk sizing and position-limit constants | Design differs from the baseline; no demonstrated improvement |
| ORB strategy | Entry, sizing and monitoring logic | Research hypothesis implemented; current fill assumptions can overstate results |
| Greeks archive | 14 pickle session files | Session files exist; their contents and analytical accuracy were not evaluated |

## How future results will be presented

Publish the complete evaluation period and strategy variants, not only the best window. Identify the benchmark, instruments, data source, signal timing, execution timing, capital and exposure assumptions. State whether fees, spread, slippage, taxes, dividends and currency conversion are included. Show return alongside volatility, maximum drawdown, turnover and trade count. Separate historical backtests, forward paper results and any independently documented live results.

An optimistic scenario can be shown as a labelled sensitivity analysis with explicit assumptions. It is not a substitute for the observed base case.

## Verification limits

The uploaded files were reviewed as source evidence. Dependent modules and full applications were not executed end to end. Parameter settings are not performance results or guarantees of realised risk. No claim is made of production readiness or a profitable trading strategy.
