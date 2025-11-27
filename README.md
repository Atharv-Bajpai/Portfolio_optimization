# Quantitative Modeling: NIFTY 50 Price Prediction

## Project Overview
This project explores the application of **Supervised Machine Learning** to financial time-series data. The objective was to determine the predictive power of short-term trend indicators—specifically Simple Moving Averages (SMA)—on the future price movement of the NIFTY 50 index.

Using **Multiple Linear Regression**, the model establishes a linear relationship between past moving averages and the next day's closing price.

## Methodology
The analysis follows a standard data science pipeline:

1.  **Data Ingestion:** Sourced 5 years of historical OHLC data for `^NSEI` (NIFTY 50) via the YFinance API.
2.  **Feature Engineering:**
    * **SMA_3 (3-Day Moving Average):** Captures immediate short-term momentum.
    * **SMA_9 (9-Day Moving Average):** Captures the slightly longer short-term trend.
    * **Target Variable:** The Closing Price shifted by -1 (Next Day's Close).
3.  **Modeling:**
    * Algorithm: Ordinary Least Squares (OLS) Linear Regression.
    * Split: 80% Training / 20% Testing (Time-series split, non-shuffled).

## Results
The model demonstrates a high degree of correlation between the selected SMA indicators and the target price.

| Metric | Result |
| :--- | :--- |
| **R-Squared ($R^2$)** | **> 99%** |
| **Relationship** | Strong positive linear correlation established. |

### Interpretation
The high $R^2$ score confirms that short-term moving averages are mathematically significant predictors of the immediate future price in a linear context. The visualization below illustrates the model's ability to track the index trend closely.

*(Insert Chart Here)*

## Technical Stack
* **Python:** Core programming language.
* **Scikit-Learn:** Used for model initialization, training, and metric evaluation.
* **Pandas/NumPy:** Data manipulation and feature construction.
* **Matplotlib:** Visualizing the Actual vs. Predicted regression lines.

## Usage
To replicate this analysis:
```bash
pip install yfinance scikit-learn pandas matplotlib
python nifty_prediction.py
