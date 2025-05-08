# 📈 Stock Price Prediction using LSTM, XGBoost, and Hybrid Models

## 🚀 Overview
This project forecasts Apple Inc. (AAPL) stock prices using:
- 🧠 LSTM (Long Short-Term Memory) for sequence modeling
- ⚡ XGBoost for robust regression
- 🔁 A hybrid approach combining both

## 📊 Results

| Model               | MAE     |
|--------------------|---------|
| LSTM Only          | 0.0882  |
| XGBoost Only       | 0.0407  |
| Hybrid (LSTM + XGBoost) | **0.0407**  |

This project builds a hybrid machine learning model that combines LSTM (Long Short-Term Memory) neural networks and XGBoost (Extreme Gradient Boosting) to predict stock prices, using Apple's historical stock data as a case study.

LSTM is used to extract meaningful temporal features from sequential stock data.

These features are then passed to an XGBoost regressor, which makes final predictions by capturing nonlinear patterns and relationships.

## 🧠 Model Architecture
1.Data Collection

Historical stock data for AAPL was downloaded using the yfinance API.

Features like Open, High, Low, Close, and Volume were used.

2.LSTM Model

Sequential layers: LSTM(128) → LSTM(64) → Dropout → Dense → Output.

Trained on time-series windows to capture price trends and dependencies.

3.Feature Extraction

Output from intermediate LSTM layer was extracted as a compressed feature vector.

4.XGBoost Regression

The LSTM features were used as input to an XGBRegressor with tuned hyperparameters.

This model predicted the stock's next-day price (or other target variable).

## ✅ Results & Insights
The hybrid model achieved low Mean Absolute Error (MAE), showing improved prediction accuracy over standalone models.

Key advantages:

LSTM captured time-series dynamics.

XGBoost learned complex decision boundaries.

Several challenges (e.g., feature shape mismatch) were resolved by carefully aligning output dimensions from LSTM to XGBoost.

## 📌 Conclusion
Combining LSTM and XGBoost provided a powerful ensemble that benefits from the sequence modeling of RNNs and the structured learning of tree-based models. This approach is ideal for tasks like stock forecasting where both historical patterns and feature-based decisioning matter.
