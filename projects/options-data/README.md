# Options Greeks and Premium Behaviour Research

**Status: In development**  
**Author: Aum K. Patel**  
**Tools: Python, pandas, NumPy, Upstox API, Streamlit and Plotly**

## What I am building

I am developing an algorithmic research dashboard that interprets changes in option Greeks alongside premiums, implied volatility, open interest and underlying-index prices. The goal is to monitor how option prices behave as market conditions change, and to turn a complex option chain into a clearer view of intraday conditions.

The current implementation covers **Nifty 50, Bank Nifty and Sensex**. It is a research and monitoring application; a validated trading-performance record has not yet been established.

## Why Greeks matter to this project

| Input | What I monitor |
| --- | --- |
| Delta | How an option's sensitivity to the underlying changes as the index moves |
| Gamma | How quickly delta changes, particularly near the money and expiry |
| Theta | Changes in sensitivity to the passage of time |
| Vega and implied volatility | Changes in volatility sensitivity and quoted volatility |
| Premium and underlying price | Whether price movements coincide with changes in the above measures |
| Open interest and its change | Strike concentrations and changes in outstanding contracts |

The application analyses **broker-supplied Greeks**. Its custom combinations and signal thresholds are research indicators, rather than independently calibrated pricing models or probabilities.

## Implemented components

### 1. Background data collector

- Fetches option-chain and index-price data concurrently for three indices.
- Selects the nearest available expiry and extracts call/put Greeks, premiums, IV and open interest.
- Filters a delta band for aggregate indicators and identifies contracts closest to +0.20 and -0.20 delta.
- Computes open-interest ratios, an ATM put-versus-call IV difference, strike concentrations, rolling scores and price momentum.
- Saves dated sessions with atomic file replacement and supports Excel exports.

The loop waits 15 seconds after processing. Actual observation intervals also include API latency and processing time; this is not tick-by-tick exchange data.

### 2. Interactive research dashboard

- Displays put-versus-call Greek curves, price momentum and rolling signal indicators.
- Shows strike-level open interest and a detailed option-chain matrix.
- Combines indicators into experimental bullish, bearish and sideways regime scores.
- Monitors a changing 20-delta premium corridor and proximity to its selected strikes.
- Provides historical-session selection, audio alerts, chart controls and session exports.

## How the analysis works

**Collect data → organise option-chain observations → calculate indicators → compare with premium and index movements → review charts and recorded sessions.**

For example, an option premium can move while the underlying changes only modestly. The dashboard helps investigate whether IV, volatility sensitivity, time sensitivity or the selected contract mix changed alongside it. This is a way to investigate behaviour, not proof that a Greek-based signal predicts the next move.

## What I am working on next

1. Track fixed option contracts from entry to exit, preserving expiry, strike and option type.
2. Record stale observations and use elapsed-time windows rather than assuming perfectly spaced samples.
3. Compare forward premium changes after each signal across multiple recorded sessions.
4. Add bid/ask spreads, execution costs and explicit exit rules before evaluating trade P&L.
5. Evaluate signals on separate development and holdout sessions.

## Research boundaries

- Regime percentages are normalised heuristic scores, not calibrated probabilities.
- Open interest alone does not identify institutional traders or distinguish opening buyers from opening sellers.
- The existing changing-strike premium comparison is a monitor, not valid fixed-position strangle P&L.
- Retrospective centred chart smoothing must remain separate from causal signal evaluation.
- Hard-coded success-rate labels in the prototype are not presented here as verified results.
- No accuracy, return, win-rate or production-readiness claim is made.

## Public showcase

This page describes the project and its current research direction. Full source code, credentials and raw session files are kept out of the public repository. The implementation reviewed consists of a background collector and a Streamlit viewer.

## Resume description

Developing a Python options analytics dashboard for Nifty 50, Bank Nifty and Sensex, combining broker-supplied Greeks, implied volatility, premiums and open interest to monitor intraday option-price behaviour through interactive charts and rule-based indicators.
