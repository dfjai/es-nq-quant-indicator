# Multi-Timeframe Futures Signal Model

A rule-based market analysis project built in Pine Script to study directional bias, structure, and execution quality across ES and NQ futures.

## Overview

This repository contains a custom TradingView indicator framework designed to support structured, multi-timeframe market analysis rather than purely discretionary execution. The project combines higher-timeframe bias, price location, volume context, EMA structure, and quantile-style regression logic into a single workflow for analyzing index futures.

The broader goal of the project is to build a repeatable decision framework that reduces emotional execution, improves context awareness, and creates a clearer process for aligning bias, setup, and trade timing.

## Research Objective

The central research question behind this project is:

> How can higher-timeframe structure, lower-timeframe confirmation, and rule-based signal scoring be combined into a more disciplined intraday futures execution model?

The project is intentionally iterative. It is not presented as a finished "black box" strategy. Instead, it is a signal-design and model-refinement project built around observing market behavior, identifying failure modes, and revising the logic over time.

## Instruments Covered

- ES / MES
- NQ / MNQ

## Timeframe Framework

The model uses a top-down workflow:

- **4H** for directional bias and market narrative
- **15m** for setup development and confirmation
- **5m** for execution timing

This structure is meant to prevent lower-timeframe trades from being taken without higher-timeframe context.

## Model Components

The framework combines the following elements:

- **200 EMA** for long-term structural trend
- **50 EMA** for intermediate directional trend
- **VWAP** for intraday value and price-location context
- **Quantile-style regression bands** for stretch, trend envelope, and mean reversion context
- **Volume-state logic** for participation and pressure
- **Signal scoring** for setup alignment
- **Session-aware context** for intraday market behavior

## Dashboard Definitions

The indicator uses a compact dashboard with these fields:

- **Sig**: current signal state such as `Scanning`, `BUY EARLY`, `BUY A+`, `SELL EARLY`, or `SELL A+`
- **Conf**: confidence score derived from internal alignment
- **Vol**: volume condition such as `Bull Vol`, `Bear Vol`, or `Normal Vol`
- **Z**: relative stretch from the model mean / structure
- **Daily**: higher-timeframe directional state
- **Loc**: price location relative to value / structure
- **Sigs**: number of aligned internal conditions
- **WR**: reserved placeholder for future tracked signal win-rate metrics

## Workflow

Typical use of the model follows this process:

1. Determine directional context on the 4H chart
2. Watch the 15m chart for structure and setup alignment
3. Use the 5m chart for execution timing
4. Avoid low-confidence, weak-location, or low-alignment conditions
5. Review post-session signal quality and revise the model where needed

## Interpretation Guide

- **4H = Bias**
- **15m = Setup**
- **5m = Entry**

Higher-quality long conditions typically include:

- `BUY A+`
- confidence above 70%
- above-value location
- supportive bullish volume context
- strong internal signal alignment

Higher-quality short conditions typically include:

- `SELL A+`
- confidence above 70%
- below-value location
- supportive bearish volume context
- strong internal signal alignment

Conditions generally avoided include:

- conflicting higher-timeframe bias
- weak signal count
- unclear price location
- low-confidence setups
- chasing extended price away from structure

## Repository Structure

```text
.
├── README.md
├── indicator/
│   ├── es_main_flow_bias_map_v3.pine
│   └── nq_main_flow_bias_map_v3.pine
├── docs/
│   └── signal-definitions.md
├── research/
│   ├── methodology.md
│   └── revision-log.md
├── results/
│   └── weekly-review-template.md
└── examples/
    └── README.md
```

## Why This Project Matters

This project reflects an interest in:

- rule-based market analysis
- signal design
- multi-timeframe structure
- systematic refinement
- quantitative reasoning applied to market behavior
- turning observed chart behavior into testable model revisions

For internship and portfolio purposes, the project is meant to demonstrate independent technical work, structured market research, and iterative model improvement.

## Current Development Themes

Current areas of focus include:

- improving higher-timeframe bias flips
- reducing late entries
- aligning ES and NQ logic for cross-instrument comparison
- making targets more realistic for intraday behavior
- improving dashboard readability
- refining confidence and signal-compilation logic

## Limitations

This project is still under active iteration. Current limitations include:

- signal quality has not yet been benchmarked with a complete tracked dataset
- some thresholds remain instrument-specific and require further testing
- ES and NQ do not always respond well to identical sensitivity settings
- the current `WR` field is a placeholder, not a validated historical performance metric

These limitations are important because they define the next phase of research rather than being hidden weaknesses.

## Future Work

Planned next steps include:

- formal signal journaling
- setup-type performance review
- ES vs NQ comparative analysis
- false-bias-flip tracking
- more formal outcome logging and review
- cleaner documentation of version changes and lessons learned

## Disclaimer

This project is for educational, research, and portfolio purposes only. It is not financial advice, not a solicitation to trade, and not a guarantee of future performance.
