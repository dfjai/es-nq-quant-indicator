# Methodology

## Objective

The objective of this project is to design a rule-based framework for analyzing intraday futures markets through a combination of higher-timeframe context and lower-timeframe execution logic.

## Core Idea

The model uses a top-down structure:

- 4H chart for directional bias
- 15m chart for setup development
- 5m chart for execution timing

This structure is intended to reduce random entries and improve consistency by forcing alignment between broader market narrative and local execution.

## Main Inputs

The system uses a combination of:

- 200 EMA for long-term structural trend
- 50 EMA for intermediate directional bias
- VWAP for fair value and intraday location
- quantile-style regression bands for trend envelope and stretch
- volume participation logic
- signal-alignment scoring
- session-based context

## Research Direction

This project is being developed as an iterative market-structure model rather than a fixed finished strategy. The research process includes observing false positives, identifying late entries, testing bias-flip behavior, comparing ES and NQ differences, and refining thresholds through observation.
