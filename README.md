# lhind
lhindtechtask
# Hybrid Time Series Sales Forecasting

This project implements a **hybrid forecasting pipeline** for sales data using ARIMA for baseline modeling and XGBoost/Random Forest for residual learning. It covers the full data science lifecycle from EDA to model evaluation and final test set prediction, suitable for business forecasting or as a portfolio showcase.

---

## Project Structure

- **Data**
  - `train.csv` — Historical sales data with `Date`, `store`, `product`, and `number_sold`
  - `test.csv`  — Unseen future data for prediction/evaluation

- **Codebase**
  - EDA (Exploratory Data Analysis)
  - Baseline Modeling (ARIMA)
  - Feature Engineering
  - Hybrid Modeling (XGBoost, RF)
  - Hyperparameter Tuning (GridSearch, HyperOpt)
  - Model Evaluation & Visualizations
  - Test Set Forecasting & Final Metrics

---

## Workflow

### 1. **Data Loading & EDA**
- Import datasets using PySpark.
- Assess missing values, outliers, and statistical summaries.
- Visualize trends, seasonality, and sales distributions (e.g., line charts, heatmaps).

### 2. **Baseline Modeling: ARIMA**
- Fit ARIMA models to each store-product series to predict baseline sales trend.
- Residuals are used for further modeling.

### 3. **Feature Engineering**
- Generate calendar features (`dayOfWeek`, `month`, `is_month_start`, etc.).
- Vectorize for downstream ML models.

### 4. **Hybrid Regression Models**
- Train XGBoost and Random Forest to model residuals from ARIMA.
- Use cross-validation and hyperparameter search (GridSearchCV, HyperOpt).

### 5. **Model Evaluation**
- Compare models using MAE, RMSE, MAPE, and R².
- Visualize actual vs predicted sales, residual distributions, and feature importances.

### 6. **Test Set Prediction**
- Retrain the best model on all training data.
- Generate predictions on `test.csv`.
- Calculate and report final metrics.

---

## Results

- **Test MAE**:`45.42`
- **Test RMSE**: `60.80`
- **Test R²**: `0.918`
- **Test MAPE**:`6.39%`

The hybrid model delivers strong test accuracy, outperforming baseline approaches and generalizing well to unseen data.

---

## Key Visualizations

- Average monthly sales by store-product (heatmap)
- Residual error distribution (histogram)
- Feature importances (bar chart)

---

## Model Choices & Rationale

- **ARIMA**: Captures time-based trend and seasonality.
- **XGBoost/RF**: Models complex, non-linear relationships in the residuals, leveraging calendar and categorical features.
- **Hybrid approach**: Combines strengths of classical and machine learning forecasting.

---

## How to Run

1. Upload `train.csv` and `test.csv` to your Spark/Databricks environment.
2. Run the pipeline in order: EDA → ARIMA → Feature Engineering → Hybrid Model → Evaluation → Test Forecast.
3. Results (including test predictions) are saved as CSV and visualized in notebook/dashboards.

---

## Requirements

- PySpark
- Pandas, Numpy
- scikit-learn, xgboost, matplotlib, seaborn
- HyperOpt for advanced tuning

---

## Author

Project by Albina Hoxha
linkedin.com/in/albina-h-781b11167 | albinahxa@gmail.com



