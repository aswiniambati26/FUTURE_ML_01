# FUTURE_ML_01

## Sales & Demand Forecasting for Businesses
A machine learning project that predicts future sales using historical retail data — built to help businesses make smarter decisions around inventory, staffing, and planning.

## What This Project Does
This project takes real store sales data and uses it to forecast how much a business is likely to sell over the next 30 days. Instead of just training a model and calling it done, the goal here was to make the output actually useful — something you could show to a store owner or business manager and have them immediately understand.

## Dataset

(https://www.kaggle.com/competitions/store-sales-time-series-forecasting)

The project uses the Store Sales — Time Series Forecasting dataset from Kaggle. 

It contains sales records from a chain of grocery stores in Ecuador, including:

Daily sales across 54 stores and 33 product families
Store details (city, type, cluster)
Daily transaction counts
Oil prices (relevant since Ecuador's economy is oil-dependent)
National holidays and events


## How It Works

Steps Followed
## 1. Data Loading

Loaded 5 CSV files — train, stores, transactions, oil, holidays
Merged them all into one clean dataset

## 2. Data Cleaning

Filled missing oil prices using forward fill
Filled missing transaction values with 0
Flagged national holidays

## 3. Feature Engineering

Extracted year, month, day, day of week from dates
Created lag features — sales from 1, 7, and 30 days ago
Added 7-day and 30-day rolling averages

## 4. Model Training

Linear Regression
Random Forest
XGBoost
ARIMA
Exponential Smoothing
Prophet

## 5. Model Evaluation

Compared all models using MAE, RMSE, and R²
XGBoost performed best

## 6. Forecasting

Used XGBoost to predict sales for the next 30 days
Visualised results in a clear chart

## Results

Best Model: XGBoost
Forecast Window: 30 days
Most Important Feature: 7-day rolling average (recent sales are the best predictor of future sales)
Weekend Effect: Sales consistently spike on Saturdays and Sundays
