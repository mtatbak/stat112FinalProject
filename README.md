
# Trendyol Sales Data Cleaning and Analysis

This repository contains the steps and Python scripts used to clean, process, and analyze the Trendyol sales dataset from 2010 to 2023. The objective of this project is to uncover meaningful insights from the data to improve sales strategies and enhance customer satisfaction.

## **Project Overview**

### **1. Dataset Information**
The dataset contains the following variables:

| Variable Name       | Description                                   | Data Type   |
|---------------------|-----------------------------------------------|-------------|
| `Year`              | Year of sale                                 | Categorical |
| `Month`             | Month of sale                                | Categorical |
| `City`              | City where the sale occurred                 | Categorical |
| `Category`          | Product category                             | Categorical |
| `Payment_Method`    | Method of payment                            | Categorical |
| `Device_Type`       | Type of device used in purchase              | Categorical |
| `Promotion_Used`    | Whether promotion was used                   | Categorical |
| `Customer_segment`  | Customer segment (new or returning)          | Categorical |
| `Order_Value`       | Total value of the order in TL               | Continuous  |
| `Items_Sold`        | Number of items sold                         | Continuous  |
| `Shipping_Cost`     | Cost of shipping                             | Continuous  |
| `Delivery_Time`     | Delivery time in days                        | Continuous  |
| `Product_Rating`    | Customer satisfaction with the product       | Continuous  |
| `Discount`          | Discount applied                             | Continuous  |

### **2. Libraries Used**
- **NumPy**: For numerical computations
- **Pandas**: For data manipulation
- **Matplotlib & Seaborn**: For data visualization
- **Missingno (msno)**: For missing data visualization
- **KNN Imputer**: For imputing missing values

## **Steps in the Data Cleaning Process**

1. **Initial Examination and Data Types**
   - Inspected the dataset with `.head()` and `.tail()`.
   - Corrected incorrect data types (e.g., `Shipping_Cost` changed from object to float).

2. **Column Names and Structural Adjustments**
   - Standardized column names using string functions like `.strip()`.
   - Removed irrelevant columns.
   - Combined `Year` and `Month` into a single `Date` column using `pd.to_datetime()`.

3. **Data Cleaning**
   - Removed duplicate rows using `df.drop_duplicates()`.
   - Standardized text values (lowercased, stripped whitespace).
   - Ensured categorical variable values were unique and consistent.
   - Detected and handled outliers using:
     ```python
     for i in [x * 0.1 for x in range(990, 1000)]:
         print("The {:.1f}th percentile value is {:.2f}".format(i, np.percentile(df['Shipping_Cost'], i)))
     ```
     Outliers were replaced with the column mean if they exceeded set thresholds.

4. **Handling Missing Values**
   - Used the K-Nearest Neighbors (KNN) imputer for numeric columns.
   - Imputed missing values in categorical columns with their mode.

## Key Features

  - **Line Charts**: Used to visualize trends over time, such as the number of transactions across years by payment method.
  - **Heatmaps**: Used for showing correlations between numerical variables and for visualizing the relationship between city, category, and average discount.
  - **Violin Plots**: Used to analyze the distribution of product ratings across different cities and customer segments.
  - **Regplot**: Used to show the relationship between discount percentage and order value.
  - **Jointplot**: Used to explore the relationship between discount and order value, with the influence of promotion status.

## Visualizations

Below is a summary of the key visualizations in this repository:

1. **Top 2 Payment Methods Over the Years**: A line chart showing the trend of the most commonly used payment methods by year.
2. **Average Discount by City and Product Category**: A heatmap visualizing the average discount offered based on the city and product category.
3. **Effect of Promotions on Items Sold**: A violin plot to show how promotions impact the number of items sold.
4. **Relationship Between Shipping Cost and Order Value**: A scatter plot with a regression line to visualize how shipping costs affect the order value.
5. **Product Ratings by City**: A violin plot for product ratings across the top 5 cities by number of orders.