# Opening Range Breakout Research

## Purpose

Study whether early-session price action and unusually high volume can identify candidates for an intraday breakout strategy.

## Implemented approach

The reviewed script requests a Nifty 500 universe, builds daily ATR and volume context, examines the first five minutes of trading and ranks eligible stocks by relative volume. It selects up to 15 candidates, sizes positions using stop distance and an exposure cap, and monitors model positions during the session.

ATR measures recent price movement. Relative volume compares current activity with prior sessions. These inputs are hypotheses to test, not evidence that the strategy is profitable.

## Issues to resolve before using results

- Entry fills are recorded at the trigger even when the observed price is already beyond it. Stop fills similarly assume the stop price. Both can make results optimistic.
- The reviewed implementation does not deduct a complete execution-cost model from reported PnL.
- A hard-coded local environment-file path must be replaced with portable configuration.
- Scheduling, recovery and persistence need validation across full sessions. The monitoring loop does not run the scheduler inside its main intraday branch.

## Scope

Research implementation with paper trade monitoring. Full code and credentials are excluded. No verified performance figures or production deployment claim is published. See [results](../../RESULTS.md).
