# Quantitative Finance Trading Pipeline (BTC-USD)

An execution-ready Machine Learning pipeline that uses a Random Forest Regressor to forecast asset directional shifts and backtests an active strategy against a passive Buy-and-Hold benchmark.

##  How to Run the Project
1. Open Google Colab or a local Jupyter environment.
2. Upload the `Quant_Task_3.ipynb` file.
3. Run the cells to pull live data via `yfinance` and execute the pipeline.

##  Features Engineered (No Raw Prices Used)
- **Trend Momentum**: 10/50 SMA Trend Ratio
- **Volatility Profile**: 20-Day Bollinger Band Bandwidth
- **Market Velocity**: 14-Day Relative Strength Index (RSI)
- **Volume Dynamics**: 15-Day Volume Moving Average Ratio
- **Target Variable**: Next-Day Forward Return (shifted by 1 day to strictly eliminate lookahead bias)

##  Pipeline Guardrails Implemented
- **Stationarity**: Used percentage returns instead of absolute price drift.
- **Data Leakage Check**: Enforced a strict chronological 80/20 train-test split instead of random shuffling.
- **Overfitting Prevention**: Bounded tree depth and leaf nodes to prevent the model from memorizing market noise.
