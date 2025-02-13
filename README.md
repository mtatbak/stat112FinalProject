# Trendyol Sales Data Analysis Project

## Project Overview
This project focuses on cleaning, processing, and analyzing Trendyol sales data from 2010 to 2023. The goal is to uncover insights that can help improve sales strategies and enhance customer satisfaction. Python libraries such as Pandas, NumPy, Matplotlib, Seaborn, KNN Imputer, and Missingno were used to clean the dataset, perform exploratory data analysis (EDA), and generate meaningful visualizations.

## Table of Contents
1. [Dataset Description](#dataset-description)
2. [Data Cleaning Process](#data-cleaning-process)
3. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4. [Key Findings](#key-findings)
5. [References](#references)

## Dataset Description
The dataset contains information about transactions on Trendyol, including:
- Payment methods
- Device types
- Shipping details (cost and delivery time)
- Purchase dates
- Product ratings
- Promotions used

### Summary Statistics:
- **Rows:** 1000
- **Columns:** 13 (8 numerical, 5 categorical)
- **Key Insights:**
  - Top city: Ankara
  - Top category: Clothing
  - Most used payment method: Credit card
  - Most used device: Desktop
  - Promotion usage: 56% of purchases include promotions

## Data Cleaning Process
### 1. Initial Examination and Data Types
- Used `.head()` and `.tail()` to understand the structure.
- Corrected data types (e.g., Shipping Cost converted from `object` to `float`).

### 2. Column Name Standardization
- Standardized column names using string functions (`.strip()`, `.lower()`).
- Merged `Month` and `Year` columns into a single `Date` column.

### 3. Handling Duplicates and Outliers
- Removed duplicates using `df.drop_duplicates()`.
- Detected outliers using box plots and replaced extreme values with column means.

### 4. Missing Values
- **Numeric Variables:** Imputed using KNN Imputer.
- **Categorical Variables:** Filled missing values with mode.

## Exploratory Data Analysis (EDA)
EDA was performed to answer the following research questions:

### 1. Relationship Between Numerical Variables
- A strong positive correlation (0.77) exists between shipping costs and order value.
- Discounts positively correlate with order value (0.59).
- No significant correlation between product ratings and discounts (-0.03).

### 2. Order Value vs. Discount
- Larger discounts encourage higher order values.
- Scatterplots reveal a positive trend between discount percentages and order values.

### 3. Impact of Promotions on Discounts and Order Value
- Promotions are often paired with higher discounts, boosting order values significantly.

### 4. Effect of Promotions on Items Sold
- While promotions occasionally boost sales, their overall effect on the number of items sold is minimal.

### 5. City-wise and Category-wise Discounts
- Discounts vary by city and category.
  - **Konya:** Highest average discount in electronics (90.65).
  - **Adana & Izmir:** Consistently lower discounts across categories.

### 6. Product Ratings by Top 5 Cities
- Gaziantep has the highest median product ratings.
- Antalya has the lowest ratings, possibly due to differences in purchase patterns or delivery times.

### 7. Promotions' Effect on Product Types
- Promotions significantly increase sales in categories like Clothing, Home, and Toys.
- No noticeable impact on categories like Electronics and Beauty.

## Key Findings
- Strong correlation between order value, shipping costs, and discounts.
- Discounts and promotions play a significant role in boosting sales.
- Cities exhibit unique patterns in discount and purchase behavior.
- Promotions generally increase total order value but have varying effects on different product categories.

## References
1. GeeksforGeeks. (n.d.). [How to automate data cleaning in Python](https://www.geeksforgeeks.org/how-to-automate-data-cleaning-in-python/).
2. Gluck, C. (2021, May 13). [Working with pandas: Fixing messy column names](https://medium.com/@chaimgluck1/working-with-pandas-fixing-messy-column-names-42a54a6659cd). Medium.
3. GeeksforGeeks. (n.d.). [Handling missing data with KNN imputer](https://www.geeksforgeeks.org/handling-missing-data-with-knn-imputer/).

---

### Note:
This README is generated as part of the Trendyol sales data analysis project and summarizes key details for reference.
