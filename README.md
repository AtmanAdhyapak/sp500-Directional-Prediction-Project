S&P 500 Directional Prediction with Machine Learning

This project builds a machine learning pipeline to predict the next-day direction (up/down)of the S&P 500 using historical market data. A Random Forest classifier is trained with engineered time-series features and evaluated using realistic rolling backtests and risk-aware performance metrics.

The objective is to demonstrate feature engineering, probability-based decision making, and proper model evaluation, rather than to outperform buy-and-hold returns.

Data & Features
- Daily S&P 500 data retrieved via yfinance
- Engineered features include:
  - Overnight returns (close-to-open gaps)
  - Rolling price ratios, trends, and volatility across multiple horizons
  - Daily returns for strategy evaluation

Model & Thresholding
- Random Forest classifier trained on engineered features
- Model outputs probabilities for upward movement
- Final predictions use a custom probability threshold (0.55) selected via precision–recall curve analysis

Backtesting & Evaluation
- Rolling backtest with an expanding training window to avoid look-ahead bias
- Strategy enters the market only when predicted probability exceeds the threshold
- Performance compared against a buy-and-hold baseline

Results (Approximate)
- Precision (holdout test): ~0.69
- Precision (rolling backtest): ~0.56
- Strategy exhibits lower drawdowns and volatility than buy-and-hold
- Buy-and-hold achieves higher total return, as expected

Key Takeaways
- Holdout results overestimate real-world performance
- Rolling backtests provide a more realistic evaluation
- Probability thresholds improve risk control
- Short-term market direction remains inherently noisy

Potential Improvements
- Incorporate macroeconomic or sentiment indicators
- Explore regime-aware or multi-day prediction targets
- Compare against alternative ensemble models
