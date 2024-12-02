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
- Input dataset: `City_EFPG_filtered.csv`.
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
    - **Economic Indicators**: `Labor_force`, `Unemployment rate`, `Employment`.
    - **Pricing Variables**: `Unit_value_mean_wtd`, `Price_index_GEKS`.
    - **Temporal Variables**: `Year`, `Month`, `Season`.
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
- **Results**:
  - Compared model performances and selected the best-performing model.
  - Random Forest and Gradient Boosting showed superior performance due to their ability to capture nonlinear relationships.

### 6. Price Elasticity Calculation
- **Method**:
  - The calculations are broken down as follows:

#### Percentage Change in Demand:

\[
\text{Percentage Change in Demand} = \frac{\text{Predicted Demand (Dec 2018)} - \text{Actual Demand (Nov 2018)}}{\text{Actual Demand (Nov 2018)}} \times 100
\]

#### Percentage Change in Price:

\[
\text{Percentage Change in Price} = \frac{\text{Price (Dec 2018)} - \text{Price (Nov 2018)}}{\text{Price (Nov 2018)}} \times 100
\]

#### Price Elasticity of Demand (PED):

\[
\text{PED} = \frac{\text{Percentage Change in Demand}}{\text{Percentage Change in Price}}
\]

---

## Key Insights

### Significant Predictors:
- `Unit_value_mean_wtd` (price per 100 grams) is a crucial factor influencing demand.

### Price Elasticity Findings:
- **Staple Foods**: Inelastic demand (e.g., milk, eggs).
- **Luxury Items**: Elastic demand (e.g., alcohol).

---

---

# Time Series Forecasting

### Overview
This notebook applies time-series forecasting techniques to predict future demand for selected food categories in various metropolitan regions.

---

### Objectives
- Forecast purchase quantities for the next 6 to 12 months.
- Analyze seasonal trends using ARIMA and Exponential Smoothing models.
