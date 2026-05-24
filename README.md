# FINC6028 Assignment 3 — G48

**Unit:** FINC6028
**Track:** A — Investment / Hedge Fund Pitch

This is the group repository for Assignment 3, submitted by G48.

US large-cap equity long-short strategy. Each week, stocks in the S&P 500 universe are ranked using a machine learning classifier trained on momentum, risk, liquidity, and technical features. The strategy goes long the top 20% and short the bottom 20%, rebalanced at the Friday close with a 5 bps one-way transaction cost assumption.

## Models

A logistic regression baseline and an XGBoost improved model are evaluated side-by-side under identical walk-forward conditions (training: 2015–2018, OOS: 2018–2026). A third extended XGBoost model adds five technical features: RSI, rolling beta, idiosyncratic volatility, 52-week high proximity, and volume momentum.

## Evaluation

Strict walk-forward design with no look-ahead bias. Performance reported gross and net of costs, benchmarked against SPY and an equal-weight universe. Robustness checks include cost sensitivity, quantile threshold variation, feature group ablation, and a label-shuffle falsification test.

## How to Run

Open `FINC6028_A3_v1.ipynb` in Google Colab. Upload `a3_frozen_universe_2026-05-22.csv` to the working directory, then run all cells top-to-bottom. The `shap` package is installed automatically in the first cell.

## Notes

The universe is based on current S&P 500 constituents (not point-in-time membership), which introduces survivorship bias. This is acknowledged throughout the notebook and discussed in the limitations section.
