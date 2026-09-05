Task 3 - Data Cleaning and Preprocessing

Project Overview

This project demonstrates professional-level data cleaning by taking a deliberately messy customer dataset and systematically transforming it into a clean, analysis-ready dataset.

The cleaning process is documented step by step, with each decision justified in the Jupyter Notebook.

Objective

The main objectives of this task are to:

Assess the quality of the raw dataset

Handle missing values using column-appropriate strategies

Identify and remove duplicate rows

Standardise inconsistent text and date formats

Detect numerical outliers using the IQR method

Correct data types

Compare data quality before and after cleaning

Save the final analysis-ready dataset as a new CSV file

Dataset

The raw dataset contains 315 rows and 9 columns:

CustomerID

Name

Gender

Age

JoinDate

Department

Salary

PurchaseAmount

Email

The dataset intentionally contains common data-quality problems including missing values, duplicate records, inconsistent categorical formatting, multiple date formats, currency symbols, invalid age values, and extreme numerical values.

Data Quality Assessment

The initial inspection identified:

315 rows in the raw dataset

14 exact duplicate rows

Missing values in Age, JoinDate, Salary, and Email

Inconsistent Gender values such as M, male, MALE, F, and female

Inconsistent Department formatting and capitalization

Multiple JoinDate formats

Salary values containing currency symbols and commas

Invalid age values, including negative values

Extreme Salary and PurchaseAmount values

Missing Data Handling

Different strategies were used depending on the meaning of each column:

Age

Missing and invalid age values were replaced with the median age because Age is numerical and the median is less sensitive to extreme values.

Salary

Missing Salary values were filled using the department-wise median salary, because compensation can vary between departments.

JoinDate

Rows with missing JoinDate values were removed because there was no reliable date that could be inferred safely.

Email

Missing email values were replaced with not_provided rather than guessing an address.

Gender and Department

These fields did not require missing-value imputation. Their main issue was inconsistent formatting, which was standardised.

Duplicate Removal

The raw dataset contained 14 exact duplicate rows.

These duplicate rows were removed before further cleaning, leaving 301 rows before rows with missing JoinDate were removed.

Standardisation

Text and date values were standardised throughout the dataset.

Gender

Values such as:

M

male

MALE

Male

were converted to:

Male

Similarly, female values were converted to:

Female

Department

Department names were normalised for whitespace and capitalization, including standard forms such as:

IT

HR

Finance

Marketing

Sales

JoinDate

Multiple date formats were converted to the pandas datetime64[ns] type.

Salary

Currency symbols and commas were removed before converting Salary to a numeric floating-point type.

Outlier Detection

The Interquartile Range (IQR) method was used to identify outliers in:

Age

Salary

PurchaseAmount

Outlier results

Age: 0 IQR outliers after invalid ages were corrected

Salary: 11 IQR outliers

PurchaseAmount: 17 IQR outliers

Salary and PurchaseAmount outliers were capped instead of removed. This preserves customer records while limiting the influence of extreme values.

Invalid age values were treated separately because values outside a realistic age range are not meaningful customer records.

Data Type Correction

The final dataset uses appropriate data types:

Column

Final Type

CustomerID

string

Name

string

Gender

category

Age

int64

JoinDate

datetime64[ns]

Department

category

Salary

float64

PurchaseAmount

float64

Email

string

Before vs After Cleaning

Measure

Before Cleaning

After Cleaning

Row count

315

289

Total null values

51

0

Exact duplicate rows

14

0

Correct data types

3/9

9/9

The reduction from 315 to 289 rows is explained by removing 14 duplicate rows and 12 rows with missing JoinDate.

Final Validation

After cleaning:

Total null values: 0

Exact duplicate rows: 0

All 9 columns have the intended data types

Text values are standardised

Dates are stored as datetime

Numerical fields are stored as appropriate numeric types

Outlier handling has been documented

Output

The cleaned dataset is exported to a new CSV file:

clean_customer_data.csv

The original messy dataset remains unchanged.

Tools & Technologies

Python

Pandas

NumPy

Matplotlib

Jupyter Notebook

Key Skills Demonstrated

Data quality assessment

Missing-data handling

Duplicate detection and removal

Text standardisation

Date conversion

Numeric data cleaning

IQR-based outlier detection

Data type correction

Data validation

Before-and-after quality comparison

Exporting analysis-ready datasets

Notebook

The complete step-by-step implementation is available in:

Task_3_Data_Cleaning_Student_Style.ipynb

Conclusion

This project demonstrates a systematic approach to cleaning a deliberately messy customer dataset. Each data-quality issue was evaluated according to the nature of the field and handled using an appropriate strategy.

The final dataset contains 289 clean records, no missing values, no exact duplicate rows, and correct data types across all columns, making it suitable for downstream analysis.
