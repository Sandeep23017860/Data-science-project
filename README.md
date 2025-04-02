# Stock Market Time Series Analysis and Forecasting

NAME: Sandeep Mannavarapu
Course:Data Science
ID: 23017860


## Table of Contents

1.  project-goal
2.  features
3.  models-compared
4.  technology-stack
5.  dataset
6.  project-structure
7.  setup-and-installation
8.  usage---running-the-code
9.  evaluation-metrics
10. results-summary
11. visualizations
12. limitations
13. future-work
14. license

---

## Project Goal

The primary goal of this project is to predict future stock market trends (specifically, the next day's closing price) using historical stock data for a list of 100 diverse stocks. A key objective is to implement, train, and rigorously compare the performance of three advanced deep learning architectures:
*   Long Short-Term Memory Networks (LSTM)
*   Temporal Convolutional Networks (TCN)
*   Transformer Networks (Encoder-based)

The project aims to determine which model provides the most accurate and reliable predictions for this task based on standard evaluation metrics.

---

## Features

*   Fetches historical OHLCV (Open, High, Low, Close, Volume) data for 100 stocks using the `yfinance` library.
*   Includes comprehensive data preprocessing steps: cleaning, scaling (MinMaxScaler), and sequence generation suitable for time series models.
*   Implements three distinct deep learning models: LSTM, TCN, and a simplified Transformer Encoder.
*   Trains separate models for each stock to potentially capture stock-specific dynamics.
*   Utilizes a chronologically correct Train/Validation/Test split to prevent data leakage.
*   Employs `EarlyStopping` during training to prevent overfitting.
*   Evaluates models using standard regression metrics: Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and Mean Absolute Percentage Error (MAPE).
*   Provides clear visualizations for:
*   Historical stock prices.
*   Model training history (loss curves).
*   Atual vs. Predicted prices on the test set.
*   Cmparative performance across models (e.g., box plots of metrics).
*   Organized code structure, primarily using Jupyter Notebooks.

---

## Models Compared

1.  LSTM (Long Short-Term Memory): A type of Recurrent Neural Network (RNN) well-suited for sequence data, capable of learning long-range dependencies.
2.  TCN (Temporal Convolutional Network): Uses causal convolutions with dilations, allowing for large receptive fields while maintaining computational efficiency and non-recurrent processing.
3.  Transformer (Encoder): Based on the self-attention mechanism, allowing the model to weigh the importance of different past time steps when making a prediction. A simplified encoder-only architecture is used for this sequence-to-value regression task.

---

## Technology Stack

*   Language: Python 3.8+
*   Core Libraries:
    *   TensorFlow (>=2.x) / Keras: For building and training deep learning models.
    *   Pandas: For data manipulation and analysis.
    *   NumPy: For numerical operations.
    *   Scikit-learn: For data scaling (`MinMaxScaler`) and evaluation metrics (`mean_squared_error`, `mean_absolute_error`).
    *   yfinance: For downloading historical stock data.
    *   Matplotlib & Seaborn: For data visualization.
    *   keras-tcn (or equivalent TCN implementation): Specific library for TCN layers.
    *   Environment: Google Colab.

---

## Dataset

*   Source: Yahoo Finance (`yfinance` library).
*   Tickers: A list of 100 US stocks (see `tickers.txt` or defined within the code). The list includes major companies across various sectors and index ETFs like SPY.
*   (Initial List provided in project description, cleaned for duplicates and standard tickers like 'KR' for Kroger).
*   Time Period:** Historical daily data from a specified start date (e.g., `1997-01-01`) up to the date of execution.
*   Features Used (Primary): 'Close' price.
*   Features Used (Exploratory):  'Close' engineered features like Moving Averages, Returns, Volatility.
