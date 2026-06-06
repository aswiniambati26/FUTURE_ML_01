# FUTURE_ML_01

## Sales & Demand Forecasting for Businesses
A machine learning project that predicts future sales using historical retail data — built to help businesses make smarter decisions around inventory, staffing, and planning.

## What This Project Does
This project takes real store sales data and uses it to forecast how much a business is likely to sell over the next 30 days. Instead of just training a model and calling it done, the goal here was to make the output actually useful — something you could show to a store owner or business manager and have them immediately understand.

## Dataset

https://www.kaggle.com/competitions/store-sales-time-series-forecasting/data?select=train.csv

The project uses the Store Sales — Time Series Forecasting dataset from Kaggle. 

It contains sales records from a chain of grocery stores in Ecuador, including:

Daily sales across 54 stores and 33 product families
Store details (city, type, cluster)
Daily transaction counts
Oil prices (relevant since Ecuador's economy is oil-dependent)
National holidays and events


## How It Works

1. Data Preparation
All five CSV files are loaded and merged into one clean dataset. Missing oil prices are filled forward, and holiday dates are flagged so the model knows when special events happened.


3. Feature Engineering
Raw dates are broken down into year, month, day, and day of week. On top of that, lag features are created — basically telling the model "here's what sales looked like 1 day ago, 7 days ago, and 30 days ago." Rolling averages over 7 and 30 days are also added to capture recent trends.


5. Model Training
Six different forecasting approaches are trained and compared:
ModelTypeLinear RegressionML baselineRandom ForestEnsemble MLXGBoostGradient boosting (best performer)ARIMAClassical time-seriesExponential SmoothingClassical time-seriesProphetFacebook's forecasting library


7. Model Selection
XGBoost came out on top based on RMSE and R² scores. ARIMA and Exponential Smoothing struggled because the data is aggregated across 54 stores, making it too noisy for simple univariate models.


9. 30-Day Forecast
The best model is used to predict total daily sales for the next 30 days, with results visualised in a clean two-panel chart showing both the historical trend and the upcoming forecast.

## Results

Best Model: XGBoost
Forecast Window: 30 days
Most Important Feature: 7-day rolling average (recent sales are the best predictor of future sales)
Weekend Effect: Sales consistently spike on Saturdays and Sundays
