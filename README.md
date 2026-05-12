Hassan Hussain

DHC-9759


**Internship Task 2 — Stock Price Prediction using Machine Learning**

**Overview**
This project is the second task of an AI/ML Internship. It builds a Stock Price Prediction system using historical data from Apple Inc. (AAPL). Two machine learning models — Linear Regression and Random Forest Regressor — are trained and compared to predict the closing price of the stock.

**Dataset**
Source: Yahoo Finance via yfinance library  
Ticker Symbol: AAPL (Apple Inc.)  
Date Range: January 1, 2020 — December 31, 2024  
Type: Real-time historical stock market data

**Column**                   **Description**
Open	          Opening price of the stock
High	          Highest price during the trading day
Low	            Lowest price during the trading day
Close	          Closing price (target variable)
Volume	        Number of shares traded

**Technologies Used**
**Library**	                   **Purpose**
yfinance	       Download historical stock data from Yahoo Finance
pandas	         Data manipulation and feature engineering
numpy	           Numerical computations
scikit-learn	   Machine learning models and evaluation metrics
matplotlib	     Visualization of predictions vs actual prices

**Feature Engineering**
New features were created from raw stock data to improve model performance:

**Feature**                  	**Description**
Prev_Close	     Previous day's closing price (lag feature)
Price_Range 	   Daily range: `High - Low` (volatility indicator)
MA_5             5-day moving average of closing price
MA_10            10-day moving average of closing price
Vol_Change	     Percentage change in trading volume

Total features used for training: 9  
Target variable: Close price

**Models Used**
1. Linear Regression
Simple baseline model
Finds the best-fit linear relationship between features and target
Fast to train, interpretable
2. Random Forest Regressor
Ensemble model using 200 decision trees
Handles non-linear relationships well
Parameters: n_estimators=200, random_state=42, n_jobs=-1

**Train / Test Split**
Split ratio: 80% Training / 20% Testing
Used train_test_split from scikit-learn

**Evaluation Metrics**
**Metric**	                         **Description**
RMSE (Root Mean Squared Error)	  Measures average prediction error in USD — lower is better
R² Score	                        Measures how well the model explains variance — closer to 1.0 is better

**Visualizations**
Two scatter plots are generated and saved:
lr_plot.png — Actual vs Predicted closing prices using Linear Regression
rf_plot.png — Actual vs Predicted closing prices using Random Forest
Both plots show:
X-axis: Date
Y-axis: Close Price (USD)
Blue dots: Actual prices
Red dots: Model predictions


**Install required libraries**
pip install yfinance pandas numpy scikit-learn matplotlib

**Key Findings**
Random Forest significantly outperforms Linear Regression due to its ability to capture non-linear patterns in stock data
Feature engineering (moving averages, lag features) greatly improves prediction accuracy
Prev_Close is the most influential feature, as stock prices are highly autocorrelated
Both models are evaluated on unseen test data to ensure fair comparison
