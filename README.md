# Trader Behaviour & Market Sentiment Analysis

This project explores the relationship between Hyperliquid trader performance and Bitcoin market sentiment (Fear & Greed Index).

## Files included
- `analyze_trader_sentiment.ipynb` — main analysis script (auto-detects column names, aggregates daily, merges with Fear & Greed).
- `merged_daily_summary.csv` — generated daily aggregates merged with Fear & Greed (output).
- `per_account_summary.csv` — per-account summary (if `account` column present).
- `plot_sentiment_vs_pnl.png` — scatter: sentiment vs avg closed PnL (if generated).
- `time_series_pnl_sentiment.png` — time series plot (if generated).
- `outputs/` — (optional) folder with all saved outputs.

## How the script works (short)
1. Loads `historical_data.csv` and `fear_greed_index.csv`.
2. Auto-detects timestamp, closed PnL, classification/value and optional columns (leverage, size, account, symbol, side).
3. Creates `date_only`, aggregates trades to daily metrics (count, sum, mean, median, std for closed PnL; win rate; average leverage and size if present).
4. Merges daily aggregates with Fear & Greed dataset on date.
5. Computes Pearson and Spearman correlations and saves results.
6. Produces scatter and timeseries plots and per-account summary if available.

## How to run
1. Put `historical_data.csv` and `fear_greed_index.csv` in the same folder as the script.
2. Run:
```bash
Jupyter Notebook analyze_trader_sentiment.ipynb
