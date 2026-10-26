# NYC-Trip-Commission
# NYC Yellow Taxi Demand & Revenue Forecasting

An end-to-end data engineering and machine-learning project that processes millions of NYC Yellow Taxi trip records to forecast hourly trip counts and total revenue across different taxi zones.

---

## 📊 Project Overview
This project leverages historical Yellow Taxi trip data from the NYC Taxi & Limousine Commission (TLC) covering May through July 2026[cite: 1]. By building a rigorous data pipeline, extracting rich temporal/spatial features, and applying advanced gradient-boosting models, this system accurately predicts local taxi demand to optimize resource allocation and revenue insights.

---

## 🚀 Key Features & Workflow

* **Data Ingestion & Filtering**: 
  * Loaded over 11.4 million raw trip records directly from monthly Parquet datasets.
  * Cleaned the data by removing records with zero/negative trip distances, invalid passenger counts, anomalous durations, and location IDs outside valid NYC taxi zones (1–263), yielding a refined dataset of over 8 million rows.
* **Advanced Feature Engineering**: 
  * Extracted temporal markers including pickup hour, day of the week, weekend indicators, trip duration, average speed (mph), and tip percentages[cite: 1].
  * Applied cyclical encoding (sine and cosine transforms) to continuous time features.
  * Engineered critical time-series features, including lag features (1h, 24h, and 168h lags) and rolling window statistics (24-hour and 7-day rolling means/standard deviations).
* **Exploratory Data Analysis (EDA)**: 
  * Aggregated revenue across pickup locations to isolate top-performing NYC zones.
  * Visualized spatiotemporal trends using custom Seaborn heatmaps mapping hourly revenue distribution by location.
* **Predictive Modeling & Evaluation**: 
  * Implemented a strict chronological train/validation/test split, reserving the final 7 days as an unseen test set.
  * Benchmarked multiple regression algorithms, including **Linear Regression**, **XGBoost**, and **LightGBM**.
  * Utilized **TimeSeriesSplit** cross-validation and **GridSearchCV** for hyperparameter tuning.

---

## 📈 Model Performance
Models were evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), Median Absolute Error (MdAE), and the Coefficient of Determination (R^2):
* **LightGBM** and **XGBoost** yielded superior performance, capturing complex non-linear temporal trends with test set $R^2$ scores exceeding **0.96**.

---

## 🛠️ Tech Stack
* **Language**: Python
* **Environment**: Google Colab
* **Data Manipulation & Analysis**: Pandas, NumPy
* **Machine Learning**: Scikit-Learn, XGBoost, LightGBM
* **Visualization**: Matplotlib, Seaborn

---
