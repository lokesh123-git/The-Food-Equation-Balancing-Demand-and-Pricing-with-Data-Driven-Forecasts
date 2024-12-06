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

![Picture3](https://github.com/user-attachments/assets/68338e51-4021-4b82-a344-2e3d35209f50)

- **Merge Criteria**:
  - Shared keys: `City`, `Region`, `Year`, and `Month`.
  - Aligned food pricing data with economic indicators.

- **Segmentation**:
  - Divided into **National**, **Regional**, and **Metro-Regional** datasets for granular analysis.

- **Filtering**:
  - Focused on the top 10 food categories based on highest demand:
    1. Alcohol  
    2. All other caloric beverages  
    3. Frozen and refrigerated ready-to-heat foods  
    4. Beef, pork, lamb, veal, and game, fresh  
    5. Bacon, sausage, and lunch meats  
    6. Cheese  
    7. Canned soups  
    8. Non-caloric beverages  
    9. Milk, fresh  
    10. Eggs  

  - Focused on the following top 10 metropolitan regions:
    1. New York-Newark-Jersey City, NY-NJ-PA  
    2. Los Angeles-Long Beach-Anaheim, CA  
    3. Chicago-Naperville-Elgin, IL-IN-WI  
    4. Dallas-Fort Worth-Arlington, TX  
    5. Atlanta-Sandy Springs-Roswell, GA  
    6. Miami-Fort Lauderdale-West Palm Beach, FL  
    7. Philadelphia-Camden-Wilmington, PA-NJ-DE-MD  
    8. Houston-The Woodlands-Sugar Land, TX  
    9. Detroit-Warren-Dearborn, MI  
    10. Washington-Arlington-Alexandria, DC-VA-MD-WV

 
![Picture2](https://github.com/user-attachments/assets/00c624c9-fcbd-41cf-98e2-74a08477b345)

---

## Dataset Description
The final cleaned dataset contains the following key variables:

![Screenshot 2024-12-02 002703](https://github.com/user-attachments/assets/59b81b54-773c-482b-a064-dd93048fe56a)

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


---

## Data Usage
The cleaned datasets are used for:
- **Seasonality Studies**:
  - Analyzing recurring demand patterns across different times of the year to identify peak periods for high-demand food categories.
- **Demand Prediction Models**:
  - Building supervised learning models (e.g., Decision Trees, Random Forest) to predict purchase quantities based on economic and food pricing data.
- **Time Series Forecasting**:
  - Applying models like ARIMA and Exponential Smoothing to forecast future demand trends for selected food categories.
- **Price Elasticity Analysis**:
  - Quantifying how price changes impact consumer demand using machine learning techniques and economic data.


---

### **Dataset Scope and Potential**

The dataset utilized in this project provides a comprehensive view of food consumption patterns across 10 metropolitan regions and 90 food categories, offering valuable insights into urban markets. This dataset forms a robust foundation for analyzing trends, seasonal patterns, and price elasticity, ensuring wide-ranging coverage of consumer behavior.

While the focus on 10 cities enables detailed and actionable insights, expanding the analysis to additional regions would enhance the scope and applicability of the findings. However, obtaining access to datasets for additional cities often requires permissions or collaborations with data providers and governmental organizations, as such data may be restricted or not publicly available. Overcoming this limitation could unlock new opportunities for broader and more impactful analyses.

---
## License
The datasets are publicly available under the respective licenses of the **Bureau of Labor Statistics (BLS)** and **USDA ERS**. Ensure compliance with their usage terms if repurposing the data.

