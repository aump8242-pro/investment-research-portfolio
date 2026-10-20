# ETF Backtest Results

## Domestic ETF rotation

Period: **1 January 2021 to 1 October 2026**. Starting capital: **INR 10 lakh**. These are saved historical model results with estimated broker charges.

| Execution assumption | Ending equity | Total return | CAGR | Maximum drawdown | Sharpe at 0% risk-free rate |
| --- | ---: | ---: | ---: | ---: | ---: |
| Optimistic same-close reference | INR 45.68 lakh | 356.76% | 30.24% | 21.26% | 1.63 |
| Next open, no slippage | INR 44.24 lakh | 342.37% | 29.51% | 20.69% | 1.59 |
| Next open, 5 bps per side | INR 43.31 lakh | 333.12% | 29.04% | 20.81% | 1.57 |

The next-open + 5 bps case completed 118 positions with a 63.56% closed-position win rate and a 3.93 profit factor. Estimated charges were INR 29,333.70. Win rate and profit factor refer to completed holding episodes, including partial rebalances and their charges.

**The optimistic reference is theoretical:** its close is used to generate and fill signals. The saved validation marks signal-before-execution as false for this case. It should not be described as executable same-close performance.

**Liquidity matters:** the next-open + 5 bps case assumes full fills for two DIVOPPBEES orders at approximately 132% and 284% of daily volume; 102 orders exceed 1% of daily volume. These are uncapped model returns. Slippage does not resolve impossible full-volume fills.

The current 54-ETF universe is applied retrospectively; 19 ETFs qualify at the start. There is no pre-inception price backfill, but survivorship and universe-selection bias remain. Price adjustments are not a fully audited corporate-action ledger. Cash interest is zero; settlement delays and market impact beyond assumed slippage are omitted. Open end holdings are marked rather than liquidated, so final sale charges are excluded. Capital-gains taxes are excluded.

## Global ten-year extension

Period: **21 October 2016 to 20 October 2026**. Latest underlying Indian and US sessions are 19 October; the last dated EOD row includes a US close occurring on 20 October IST. Starting capital is INR 10 lakh.

| Metric | Global ETF model | NIFTYBEES buy-and-hold |
| --- | ---: | ---: |
| Ending equity | INR 42.83 lakh | INR 29.04 lakh |
| Total return | 328.28% | 190.38% |
| CAGR | 15.66% | 11.25% |
| Maximum EOD drawdown | 22.76% | 36.33% |

The model recorded 1,026 orders and 204 completed positions. Annualized volatility was 14.29%; Sharpe at zero risk-free rate was 1.08; closed-position win rate was 57.35%. Estimated Indian charges were INR 46,486.06, with 5 bps adverse slippage per side.

This uses a current global 54-ETF universe, which is different from the domestic universe; only 10 were eligible at the start. Momentum combines 21-, 63-, 126- and 252-session returns with 15%, 40%, 30% and 15% weights. It selects up to six ETFs, applies a 200-day moving-average entry filter, resizes monthly and evaluates entry/trailing stops on daily closes.

Signals precede execution; fills use daily-open proxies rather than observed intraday prices. USD prices are converted with strictly earlier-date USD/INR closes. There are **60 orders exceeding entire daily volume**, and 178 exceeding 5%; full fills remain optimistic. Dividends/distributions, US commissions, FX conversion spreads, remittance costs and investor capital-gains taxes are excluded. Current Indian tariff estimates are applied historically. This is price-return research, not a total-return or live execution record. The benchmark includes initial 5 bps slippage but no brokerage or forced liquidation, so cost treatment differs.

## Earlier global run

The separate global run for 1 January 2021 to 1 October 2026 ended at INR 30.96 lakh, a 209.61% total model return, with two pending orders. It is retained in the evidence file rather than being presented as the same strategy universe or run as the domestic cases.

## Verification performed for this publication

The saved equity curves independently reconcile ending equity, CAGR, maximum EOD drawdown and cumulative charges for all three domestic cases and the ten-year case. Cash is nonnegative and saved EOD holdings do not exceed six. The ten-year benchmark CAGR and drawdown also reconcile. Source files are identified by relative path and SHA-256 checksum in the evidence JSON.

This review checks saved output arithmetic; it does not independently rerun the complete strategy, audit all input prices or establish execution capacity. No new Yahoo Finance download or new backtest was performed for this update. Other equity/ORB implementations and the Greeks archive are not assigned these ETF results.
