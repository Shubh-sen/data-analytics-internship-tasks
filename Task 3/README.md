# Data Cleaning and Preprocessing - Task 3

## Project Overview

This project demonstrates professional-level data cleaning by transforming a deliberately messy customer dataset into a clean, analysis-ready dataset.

## Objective

- Identify missing values and data-quality issues
- Remove duplicate records
- Standardise inconsistent values and date formats
- Detect and handle numerical outliers
- Correct data types
- Compare data quality before and after cleaning
- Export the cleaned dataset

## Data Cleaning Process

The following techniques were used:

- Missing value handling using appropriate imputation or row removal strategies
- Duplicate detection and removal
- Standardisation of categorical and date values
- Outlier detection using the **IQR method**
- Data type correction for IDs, dates, and numerical values
- Before vs. after data-quality comparison

## Dataset

The dataset contains customer information such as:

- Customer ID
- Name
- Gender
- Age
- Join Date
- Department
- Salary
- Purchase Amount
- Email

## Results

| Metric | Before Cleaning | After Cleaning |
|---|---:|---:|
| Rows | 315 | 289 |
| Null Values | 51 | 0 |
| Duplicate Rows | 14 | 0 |
| Correct Data Types | 3/9 | 9/9 |

### Outliers

The IQR method was used to detect outliers in numerical columns.

- Salary outliers: **11**
- Purchase Amount outliers: **17**

Extreme values were handled appropriately while preserving valid customer records.

## Output

The final cleaned dataset was saved as:

`clean_customer_data.csv`

## Tools & Technologies

- Python
- Pandas
- NumPy
- Jupyter Notebook

## Key Skills Demonstrated

- Data Cleaning
- Missing Value Handling
- Duplicate Removal
- Data Standardisation
- Outlier Detection
- Data Type Correction
- Data Validation

## Conclusion

The dataset was successfully transformed into a clean and analysis-ready format with **289 records, zero missing values, zero duplicate rows, and correct data types**.
