# Equity Strategy Research

## Purpose

Compare a baseline equity strategy implementation with an experimental variant that changes position sizing and entry management.

## Baseline implementation

The reviewed front tester maintains available capital, open positions and transaction records. It includes transaction-charge accounting, breakeven calculations, partial-exit handling and persistent portfolio state. Signals and exit rules are imported from separate modules.

## Experimental variant

The Gann-labelled variant adds a structural-stop requirement, a planned risk budget of 0.25% of starting capital per stock, a 10% position-budget parameter and a 70% initial allocation of the entry budget. It also records additional signal features and supports a later addition to a position.

These are configured design parameters. Gaps, execution prices, costs and later position changes can make realised exposure or loss differ from a planned budget. The variant has not been shown to outperform the baseline.

## Fair comparison

Use the same instruments, timestamps, starting capital, transaction costs and executable price assumptions for both variants. Report losses and drawdowns as well as returns. Evaluate a separate period after choosing the rules.

## Scope

Both reviewed files implement paper portfolio accounting. Their signal, fee and execution dependencies are not included in this public showcase. No completed performance report or verified strategy advantage is available. See [results](../../RESULTS.md).
