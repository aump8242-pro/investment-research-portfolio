# ETF Momentum and Portfolio Analytics

## Purpose

Provide a single workspace for monitoring an ETF model portfolio, reviewing allocation activity and exporting investment reports.

## How it works

1. Load cached market history and map instruments.
2. Refresh domestic ETF data through Upstox and obtain global ETF inputs through a separate data adapter.
3. Pass history and quotes to the portfolio engine.
4. Save portfolio state and serve a local browser dashboard.
5. Export trade and equity records for review.

## Implementation evidence

The reviewed server implements a SQLite-backed store interface, background refresh, market-data validation, pause/resume controls and CSV exports. It also has a backtest endpoint that expects `comparison.json` and model-level `equity.csv` files. Those result files were not provided.

The data path includes historical USD/INR conversion and aligning global observations with the domestic trading calendar. Broker calls in the reviewed server use GET requests; trading is modelled by a paper engine.

## What makes it useful

It connects portfolio construction concepts with the practical work of collecting data, maintaining state and communicating investment activity.

## Scope

This is a documentation-only showcase of a research implementation. The strategy, engine and frontend are separate dependencies and are not published here. Full-system execution and live investment performance have not been verified. See [results](../../RESULTS.md).
