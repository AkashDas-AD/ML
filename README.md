# Rossmann Retail Sales Prediction
Sales forecasting is an approach retailers use to anticipate future sales by analyzing past sales, identifying trends, and projecting data into the future. Because retailers generate enormous amounts of data, machine learning technology quickly proves its value. When a machine learning system is fed data—the more, the better—it searches for patterns. Going forward, it can use the patterns it identifies within the data to make better decisions. For example, a company looked at their historical data for the last three years and found that sales have increased by 20% each year. Based on this information, they projected that sales would increase by 20% this year.

## Project Overview

The Rossmann Retail Sales Prediction project focuses on forecasting daily sales for Rossmann stores across different locations. The goal is to help Rossmann optimize sales strategies by predicting future sales based on historical data.

## Project Workflow

### 1. Data Loading and Exploration

**Data fields:**
- **Id**: Represents a (Store, Date) duple within the test set.
- **Store**: A unique Id for each store.
- **Sales**: The turnover for any given day (target variable).
- **Customers**: The number of customers on a given day.
- **Open**: Indicator for whether the store was open (0 = closed, 1 = open).
- **StateHoliday**: Indicates a state holiday:
  - `a` = public holiday
  - `b` = Easter holiday
  - `c` = Christmas
  - `0` = None
- **SchoolHoliday**: Indicates if the (Store, Date) was affected by the closure of public schools.
- **StoreType**: Differentiates between 4 different store models: `a`, `b`, `c`, `d`.
- **Assortment**: Describes assortment level:
  - `a` = basic
  - `b` = extra
  - `c` = extended
- **CompetitionDistance**: Distance in meters to the nearest competitor store.
- **CompetitionOpenSince[Month/Year]**: Approximate month and year when the nearest competitor was opened.
- **Promo**: Indicates whether a store was running a promo on that day.
- **Promo2**: Continuing and consecutive promotion for some stores (0 = not participating, 1 = participating).
- **Promo2Since[Year/Week]**: Year and calendar week when the store started participating in Promo2.
- **PromoInterval**: Months when Promo2 is renewed (e.g., "Feb,May,Aug,Nov").

### 2. Data Preprocessing

- Handled missing values.
- Feature engineering (e.g., extracting year, month, day).

### 3. Exploratory Data Analysis (EDA)

- Visualized sales trends across stores and dates.
- Analyzed the impact of promotions and holidays on sales.

### 4. Model Building

- Split data into training and validation sets.
- Implemented the following models:
  - **Linear Regression**
  - **Random Forest**
  - **LARS Lasso Regression**
- Evaluated model performance using **RMSPE** and **MAPE**.

**Results:**

| Model                   | Training RMSPE | Test RMSPE | Training MAPE | Test MAPE |
|------------------------|----------------|------------|---------------|-----------|
| **Linear Regression**   | 3.550759       | 1.132323   | 14.529856     | 14.529823 |
| **Random Forest**       | 0.067905       | 0.164829   | 5.314279      | 13.289991 |
| **LARS Lasso Regression** | 4.984096    | 1.238996   | 14.528668     | 14.528301 |

## Conclusion

- **Random Forest:** Exhibits the lowest errors on both the training and test sets but shows signs of overfitting due to the large gap between training and test performance, particularly in MAPE.
- **Linear Regression & LARS Lasso Regression:** Both models exhibit similar performance with relatively high errors but demonstrate consistent behavior across training and test datasets.



