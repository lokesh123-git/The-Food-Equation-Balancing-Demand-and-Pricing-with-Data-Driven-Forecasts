# Data Folder

This folder contains all the datasets and related information used in the capstone project **"The Food Equation: Balancing Demand and Pricing with Data-Driven Forecasts."** The data has been meticulously collected, processed, and structured to facilitate demand forecasting and pricing analysis.

---

## Data Collection
The datasets were sourced from two authoritative government organizations:
1. **Bureau of Labor Statistics (BLS)**:
   - **Dataset**: Labor Force Statistics.
   - **Source**: [BLS Labor Force Statistics](https://www.bls.gov).
   - **Description**:
     - Includes key economic indicators such as labor force, employment, and unemployment rates.
     - Covers national, regional, and metropolitan-level data from 2012 to 2018.

2. **U.S. Department of Agriculture, Economic Research Service (USDA ERS)**:
   - **Dataset**: Food-at-Home Monthly Area Prices.
   - **Source**: [USDA ERS Monthly Area Prices](https://www.ers.usda.gov/data-products/food-at-home-monthly-area-prices).
   - **Description**:
     - Provides monthly food pricing data for 90 food categories across U.S. metro areas and regions.
     - Includes unit prices, weighted purchase quantities, and price indexes.

---

## Data Integration Process
The following flowchart illustrates how the data was merged and processed for analysis:

![Data Flow Chart](data_flow_chart.png)

- **Merge Criteria**:
  - Shared keys: `City`, `Region`, `Year`, and `Month`.
  - Aligned food pricing data with economic indicators.

- **Segmentation**:
  - Divided into **National**, **Regional**, and **Metro-Regional** datasets for granular analysis.

- **Filtering**:
  - Focused on the top 10 food categories based on highest demand.

---

## Dataset Description
The final cleaned dataset contains the following key variables:

![Dataset Description](dataset_description.png)

---

## Files in This Folder
1. **`FMAP_Socioeconomic_dataset.csv`**:
   - Comprehensive dataset after preprocessing and merging.
   - Contains data across all regions and food categories.
   - Key features include:
     - Purchase quantities (`Purchase_grams_wtd`).
     - Economic indicators (e.g., `Labor Force`, `Unemployment`).
     - Price indexes and unit values.

2. **`metroregion_filtered_data.csv`**:
   - Filtered dataset focusing on:
     - Top 10 metropolitan regions based on consumption volume.
     - Top 10 high-demand food categories.
   - Used for focused analysis, including demand forecasting and elasticity studies.

3. **`dataset_description.png`**:
   - Image providing detailed descriptions of the variables in the dataset.

4. **`data_flow_chart.png`**:
   - Flowchart depicting the data integration and processing pipeline.

5. **Key Variables Explanation Image**:
   - Refer to the image below for an explanation of key variables:

   ![Key Variables](key_variables_image.png)

---

## Data Usage
The cleaned datasets are used for:
- **Demand Forecasting**:
  - Predicting future purchase trends for food categories.
- **Price Elasticity Analysis**:
  - Quantifying how price changes impact consumer demand.
- **Seasonality Studies**:
  - Understanding recurring patterns in demand across seasons.

---

## License
The datasets are publicly available under the respective licenses of the **Bureau of Labor Statistics (BLS)** and **USDA ERS**. Ensure compliance with their usage terms if repurposing the data.

