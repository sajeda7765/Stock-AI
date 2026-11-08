# Stock-AI
# Stock Market Prediction Using Machine Learning


A machine learning project that analyzes historical S&P 500 stock data
and predicts **future stock returns over a 3-day horizon**. The project
explores how historical price and volume information, together with
technical indicators, can support short-term return prediction.

## Project Overview

Stock prices are influenced by many factors and can change rapidly. This
project uses historical market data to build and compare regression
models that estimate the future return of a stock.

The workflow covers: - Data understanding and cleaning - Exploratory
data analysis (EDA) - Feature engineering and technical indicators -
Model training and comparison - Evaluation using regression metrics -
Actual-versus-predicted analysis

## Dataset

-   **Dataset:** S&P 500 Historical Stock Data
-   **Original size:** 619,040 rows and 7 columns
-   **After cleaning:** 619,029 rows
-   **After feature engineering:** 607,414 rows and 23 columns

The dataset contains historical stock-market information, including
dates, stock symbols, opening/high/low/closing prices, and trading
volume.

## Data Preprocessing

The preprocessing stage included: - Inspecting the dataset structure and
data types - Checking missing values and duplicates - Handling missing
records - Converting the date column to the appropriate datetime
format - Sorting records by stock symbol and date to preserve
chronological order

## Feature Engineering

Additional features were created to capture price movement, momentum,
volatility, and trend information.

Examples include: - **Daily Change** and **Price Range** - **1-day and
5-day Returns** - **Price Slope** - **Moving Averages** - **RSI
(Relative Strength Index)** - **MACD (Moving Average Convergence
Divergence)** - **Bollinger Band Width (`BB_Width`)** - **ATR (Average
True Range)**

The target variable is **`Target_Return`**, representing the future
stock return over the next **3 trading days**.

Adding technical indicators such as RSI and MACD improved model
performance compared with using raw OHLC price data alone.

## Machine Learning Models

The project compares the following regression models:

1.  Random Forest Regressor
2.  CatBoost Regressor
3.  XGBoost Regressor
4.  Voting Ensemble Regressor
5.  Ridge Regression

## Model Evaluation

Models were evaluated using:

-   **MAE (Mean Absolute Error):** average absolute difference between
    actual and predicted returns.
-   **RMSE (Root Mean Squared Error):** gives greater weight to larger
    prediction errors.

### Results

  Model                         MAE           RMSE
  ------------------ -------------- --------------
  Random Forest        **0.015404**   **0.023091**
  Voting Ensemble          0.015582       0.023269
  XGBoost                  0.015714       0.023444
  CatBoost                 0.015789       0.023545
  Ridge Regression         0.016040       0.023865

**Best-performing model: Random Forest Regressor**, based on the lowest
MAE and RMSE among the evaluated models.

The Voting Ensemble also performed competitively and outperformed the
individual linear baseline (Ridge Regression), but it did not exceed
Random Forest in the final evaluation.

## Key Findings

-   Technical indicators, including RSI and MACD, added useful
    information beyond raw OHLC features.
-   Random Forest achieved the lowest MAE and RMSE in the model
    comparison.
-   The Voting Ensemble provided competitive results by combining
    predictions from multiple models.
-   Actual-versus-predicted plots were used to inspect how closely model
    predictions followed the observed 3-day returns.

## Tools and Technologies

-   Python
-   Pandas and NumPy
-   Matplotlib and Seaborn
-   Scikit-learn
-   XGBoost
-   CatBoost
-   Google Colab

## Future Work

Potential improvements include: - Integrating NLP-based sentiment
analysis from financial news. - Exploring deep learning approaches such
as LSTM and Temporal Fusion Transformers (TFT). - Incorporating
additional market and macroeconomic information. - Testing model
performance across different time periods and market conditions.

## Disclaimer

This project is for educational and research purposes only. It is not
financial advice and should not be used as the sole basis for investment
decisions.

## Repository Contents

Upload the project notebook or source code, dataset reference (rather
than a large raw dataset where appropriate), and any presentation or
supporting files alongside this README.

------------------------------------------------------------------------

**Project:** Stock Market Prediction Using Machine Learning\
**Dataset:** S&P 500 Historical Stock Data\
**Prediction Horizon:** 3 Trading Days
