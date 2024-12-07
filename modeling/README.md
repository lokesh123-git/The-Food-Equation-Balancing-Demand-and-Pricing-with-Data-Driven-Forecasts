# Modeling

This folder contains Jupyter Notebooks that implement and evaluate machine learning and statistical models for the capstone project: **"The Food Equation: Balancing Demand and Pricing with Data-Driven Forecasts."**

---

# Seasonality Analysis

This notebook investigates seasonal trends and patterns in consumer purchasing behavior for various food categories across 10 metropolitan regions. It leverages time-series decomposition and statistical techniques to derive meaningful insights.

---

## Objective

The goal of the seasonality analysis is to:
- Identify and analyze seasonal trends for high-consumption food categories.
- Explore regional variations in purchasing behavior across metro regions.
- Detect recurring patterns that impact demand.

---

## Methodology

### Data Preparation:
- Input dataset: `metroregion_filtered_data.csv`.
- Preprocessed columns to convert `Year` and `Month` into a single `Date` column.
- Added a `Season` column to classify months into **Winter**, **Spring**, **Summer**, and **Fall**.

### Group Analysis:
- Grouped data by food category (`EFPG_name`), metro region (`Metroregion_name`), and season (`Season`).
- Calculated total weighted purchase quantities (`Purchase_grams_wtd`) for each group.

### Visualizations:
- Generated grouped bar charts to illustrate regional and seasonal purchase variations for selected food categories.
- Highlighted differences in consumption patterns across metro regions and seasons.

### Seasonal Decomposition:
- Applied **Additive Decomposition** using `statsmodels` to break down time-series data into:
  - **Trend**: Long-term movement in data.
  - **Seasonality**: Recurring patterns at regular intervals.
  - **Residual**: Irregular fluctuations after removing trend and seasonality.
- Plotted observed, trend, seasonal, and residual components.

### Stationarity Checks:
- Conducted the **Augmented Dickey-Fuller (ADF)** test to assess stationarity.
- Applied differencing to transform non-stationary data into stationary for further analysis.

---

## Key Insights

### Regional Trends:
- Highly populated metro areas, such as New York and Los Angeles, dominate food consumption volumes.
- Smaller regions like Detroit and Philadelphia show preferences for specific food categories.

### Seasonal Patterns:
- **Winter**: Staples like milk and eggs peak due to holiday consumption.
- **Summer & Spring**: Alcohol and beverages see a boost in consumption.
- **Fall**: Packaged foods like frozen meals peak during back-to-school and stockpiling periods.

### Food-Specific Observations:
- Low-calorie beverages peak during warmer months in regions like Miami and Los Angeles.
- Alcohol consumption shows consistent demand with holiday peaks.

---

## Outputs
- Grouped bar charts for regional and seasonal purchase quantities.
- Decomposed time-series plots showing observed, trend, seasonal, and residual components.
- Stationarity results and plots for Auto-Correlation Function (ACF) and Partial Auto-Correlation Function (PACF).

---

## Applications

This seasonality analysis provides a foundation for:
- Developing time-series models for demand forecasting.
- Crafting regional and seasonal marketing strategies.
- Optimizing inventory to align with seasonal trends.

---

---

# Demand Prediction and Price Elasticity

### Overview
This notebook focuses on building supervised machine learning models to predict consumer demand for selected food categories and analyzing price elasticity to understand how changes in price affect demand. The insights gained help in making informed pricing and inventory decisions.

---

## Objectives
#### Demand Prediction:
- Develop predictive models to estimate purchase quantities based on socioeconomic and pricing variables.
- Identify significant factors influencing consumer demand.

#### Price Elasticity Analysis:
- Calculate price elasticity coefficients for various food categories.
- Understand the sensitivity of demand to price changes.

---

## Methodology

### 1. Data Preparation
- **Dataset Used**: `metroregion_filtered_data.csv`.
- **Data Cleaning**:
  - Handled missing values and outliers.
  - Converted categorical variables using one-hot encoding (e.g., `Metroregion_name`, `EFPG_name`).

### 2. Feature Engineering
- **Feature Selection**:
  - Selected relevant features such as:
    - **Economic Indicators**: `Labor_force`, `Unemployment`.
    - **Pricing Variables**: `Unit_value_mean_wtd`, `Price_index_GEKS`, `Number_stores`.
    - **City name**: `Metroregion_name`.
    -  - **Food Product name**: `EFPG_name`.
- **Target Variable**:
  - `Purchase_grams_wtd`: The weighted purchase quantity to be predicted.

### 3. Exploratory Data Analysis (EDA)
- Analyzed correlations between features and the target variable.
- Visualized data distributions and identified patterns.

### 4. Model Building
- **Algorithms Implemented**:
  - Linear Regression
  - Decision Tree Regressor
  - Random Forest Regressor
  - Gradient Boosting Regressor
- **Model Training**:
  - Split data into training and test sets (e.g., 80% training, 20% testing).
  - Performed cross-validation to ensure model robustness.
- **Hyperparameter Tuning**:
  - Used grid search and random search techniques to optimize model parameters.

### 5. Model Evaluation
- **Metrics Used**:
  - Mean Absolute Error (MAE)
  - Mean Squared Error (MSE)
  - Root Mean Squared Error (RMSE)
  - R-squared (R²)
  ![Picture1](https://github.com/user-attachments/assets/e3929755-59e0-4a1a-a105-d54b33c606d8)

- **Results**:
  - Compared model performances and selected the best-performing model.
  - Random Forest and Gradient Boosting showed superior performance due to their ability to capture nonlinear relationships.

### 6. Price Elasticity Calculation
- **Method**:
  - The calculations are represented below:

![elas](https://github.com/user-attachments/assets/366269db-25e3-4836-aaec-59f7d9e72255)



---

## Key Insights

### Significant Predictors:
- `Unit_value_mean_wtd` (price per 100 grams) is a crucial factor influencing demand.

### Price Elasticity Findings:
- **Staple Foods**: Inelastic demand (e.g., milk, eggs).
- **Luxury Items**: Elastic demand (e.g., alcohol).

---

---

## Time Series Forecasting

### Overview
This notebook applies time-series forecasting techniques to predict future demand for selected food categories in various metropolitan regions. It focuses on capturing temporal patterns and trends to generate accurate forecasts.

---

### Objectives
- Develop time-series models to forecast future purchase quantities.
- Analyze model performance and select the best forecasting approach.
- Provide actionable insights for demand planning and resource allocation.

---

### Methodology
#### 1. Data Preparation
- **Dataset Used**: `metroregion_filtered_data.csv`.
- **Preprocessing**:
  - Converted `Year` and `Month` into a datetime index.
  - Ensured time-series data is sorted and has consistent frequency.

#### 2. Exploratory Time-Series Analysis
- **Trend Analysis**:
  - Plotted time-series graphs to observe trends over time.
  - Identified upward or downward trends in purchase quantities.
- **Seasonality Detection**:
  - Used seasonal decomposition to separate time-series components:
    - Trend
    - Seasonality
    - Residual

#### 3. Stationarity Testing
- Conducted the Augmented Dickey-Fuller (ADF) test to check for stationarity.
- Applied differencing to make the series stationary if required.

#### 4. Model Selection
- **Forecasting Models Used**:
  - ARIMA (AutoRegressive Integrated Moving Average)
  - SARIMA (Seasonal ARIMA)
  - Seasonal Naive
  - Exponential Smoothing

#### 5. Model Fitting
- **ARIMA/SARIMA**:
  - Identified optimal parameters `(p, d, q)` and seasonal components `(P, D, Q, s)` using ACF and PACF plots.
  - Fitted models to the stationary series.
- **Exponential Smoothing**:
  - Applied additive  models based on data characteristics.
  - Configured trend and seasonality components.

#### 6. Forecasting and Evaluation
- **Forecast Horizon**:
  - Generated forecasts for the next 6 months.
- **Model Evaluation Metrics**:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)
  - Akaike Information Criterion (AIC) for model comparison.
- **Visual Assessment**:
  - Plotted actual vs. forecasted values.
  - Analyzed residual plots to check for randomness.

---

### Key Insights
#### Model Performance:
- Seasonal Naive models generally performed better for data with strong seasonal components.
- Exponential Smoothing provided robust forecasts for certain categories.

#### Forecast Results:
- Predicted demand trends aligned with historical seasonal patterns.
- Identified periods of expected high demand for proactive planning.

---

### Outputs
- **Forecasted Demand**:
  - Numerical forecasts for future purchase quantities.
- **Visualizations**:
  - Time-series plots with historical data and forecasted values.
  - Decomposition plots showing trend, seasonality, and residuals.

---

### Applications
- **Demand Planning**:
  - Use forecasts to inform procurement and supply chain decisions.
  - Optimize inventory levels ahead of anticipated demand surges.
- **Resource Allocation**:
  - Allocate marketing and operational resources during forecasted peak periods.
- **Strategic Decision-Making**:
  - Support long-term planning with insights into future demand trajectories.

---

### Dependencies
- **Python Libraries**:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `statsmodels`
  - `scikit-learn` (for evaluation metrics)
