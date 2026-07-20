# Multi-Timeframe Futures Signal Model

A custom TradingView indicator project built to study market bias, structure, and execution across ES and NQ futures using a rule-based, multi-timeframe framework.

## Project Overview

This project is a custom market analysis and execution model built in Pine Script for TradingView. It was designed to improve trading discipline by combining higher-timeframe directional bias, lower-timeframe setup logic, volume context, price location, and structured signal scoring into one repeatable framework.

The objective is not to predict every market move, but to create a cleaner process for understanding market conditions, aligning with directional structure, and executing with more consistency.

## What The Indicator Does

The model helps analyze:

- Higher-timeframe market bias
- Directional strength and weakness
- Volume participation
- Price location relative to value
- Trend structure using EMA and quant-style bands
- Lower-timeframe entry conditions
- Signal quality through internal scoring

It is currently used to study and compare:

- ES / MES
- NQ / MNQ

## Core Framework

The indicator follows a top-down process:

- **4H chart** for directional bias and market narrative
- **15m chart** for setup development and confirmation
- **5m chart** for execution timing

This structure helps reduce random entries by requiring lower-timeframe trades to align with higher-timeframe context.

## Main Components

The signal model uses a combination of:

- **200 EMA** for long-term structural trend
- **50 EMA** for intermediate trend direction
- **VWAP** for fair-value and location context
- **Quantile-style regression bands** for stretch and trend envelope
- **Volume state analysis** for participation and pressure
- **Signal scoring logic** for setup strength
- **Session-based context** for intraday behavior

## Dashboard Definitions

The indicator includes a compact dashboard with the following fields:

- **Sig**: current signal state such as `Scanning`, `BUY EARLY`, `BUY A+`, `SELL EARLY`, or `SELL A+`
- **Conf**: confidence score based on internal alignment
- **Vol**: volume condition such as `Bull Vol`, `Bear Vol`, or `Normal Vol`
- **Z**: relative stretch from the model mean / structure
- **Daily**: higher-timeframe directional context
- **Loc**: price location relative to value or structure
- **Sigs**: number of aligned internal conditions
- **WR**: placeholder for future win-rate tracking

## Project Purpose

This project was built to strengthen structured market analysis and remove more emotion from execution. Instead of relying only on discretionary reads, the system is designed to support decision-making through repeatable rules, multi-timeframe alignment, and ongoing observation.

The long-term goal is to keep refining the model through chart review, signal tracking, and comparative analysis between ES and NQ.

## Research Focus

This is an active research and iteration project. The main areas of development have included:

- improving higher-timeframe bias flips
- reducing late entries
- making take-profit targets more realistic
- simplifying chart visuals
- improving dashboard readability
- comparing ES and NQ signal behavior
- adjusting thresholds so ES and NQ can be studied side by side more effectively

## Current Workflow

The indicator is mainly used with this workflow:

1. Determine directional bias on the 4H chart
2. Watch the 15m chart for setup alignment
3. Use the 5m chart for execution timing
4. Avoid low-confidence or weak-alignment conditions
5. Review signal behavior and refine the model over time

## Fast Interpretation Guide

- **4H = Bias**
- **15m = Setup**
- **5m = Entry**

Best long conditions:

- `BUY A+`
- confidence above 70%
- above value
- bullish volume context
- strong signal count alignment

Best short conditions:

- `SELL A+`
- confidence above 70%
- below value
- bearish volume context
- strong signal count alignment

Avoid conditions such as:

- weak or conflicting bias
- low signal count
- unclear price location
- low-confidence setups
- chasing extended price moves

## Example Questions This Project Tries To Solve

- When should higher-timeframe bias remain active, and when should it flip?
- How should ES thresholds differ from NQ thresholds?
- What makes a setup early versus late?
- Which filters should block trades completely, and which should only reduce confidence?
- How can structure and probability be combined into a more disciplined execution model?

## Why This Project Matters

This project reflects an interest in:

- rule-based market analysis
- signal design
- multi-timeframe structure
- systematic refinement
- quantitative thinking applied to discretionary execution

It is being developed as both a practical tool and a research project to better understand market behavior through structured observation and iteration.

## Future Improvements

Planned next steps include:

- formal signal journaling
- performance review by setup type
- ES vs NQ comparative analysis
- better tracking of false bias flips
- clearer win-rate and signal outcome measurement
- continued refinement of confidence and signal-compilation logic

## Repository Contents

This repository will contain:

- Pine Script source files for ES and NQ versions
- screenshots of chart behavior
- revision notes and research observations
- testing ideas and review templates
- documentation for how the model is interpreted and used

## Disclaimer

This project is for educational, research, and portfolio purposes only. It is not financial advice, not a solicitation to trade, and not a guarantee of performance.
