# Influenza Forecasting Project -- README

## Project Goal
The purpose of this project is to build simple forecasting models for Influenza-Like Illness (ILI) and explore whether such forecasts could help hospitals anticipate periods of higher strain.

## Overview
This project uses national and California ILI data from public health sources (CDC FluView / ILINet and CDPH). We performed exploratory data analysis and tested several models, including:
- SARIMA (seasonal time-series model)
- Random Forest Regressor
- Auto-ARIMA

Model performance was compared using RMSE, and basic prediction intervals were created using conformal methods.

## Key Findings

- Random Forest achieved the best overall accuracy on national ILI data.
- SARIMA captured seasonality reasonably well but was less accurate in our tests.
- Auto-ARIMA performed the worst with the limited parameter search used.
- A simple 75th-percentile threshold was used to flag higher ILI weeks.
- National models transferred moderately well to California data.

## Methods (Brief)
1. Data Exploration: Visualization of time trends, seasonality, and regional differences.
2. Modeling Approaches:
   - SARIMA with weekly seasonality.
   - Random Forest with light hyperparameter tuning.
   - Prediction intervals via MAPIE (split conformal regression).
3. Evaluation: 
RMSE was used to compare model performance. Random Forest obtained an RMSE of approximately 0.16 on national data.

## Limitations
- Limited features (no vaccination rates, weather variables, etc.).
- Simple thresholding method for identifying higher-ILI periods.
- Minimal parameter tuning due to time and computational constraints.

## Summary
This project demonstrates that basic machine-learning approaches, especially Random Forests, can create useful short-term ILI forecasts. While not intended for clinical deployment, the results highlight how forecasting models could support hospitals in preparing for potential increases in flu activity.
