Customer Personality Analysis – Data Cleaning

Project Overview

This project demonstrates a complete data cleaning workflow on the Customer Personality Analysis dataset using Python and Pandas. The objective was to transform a raw dataset with inconsistencies into a clean, analysis-ready dataset by addressing missing values, correcting data types, standardizing categorical variables, and validating data quality.

This project was completed as Task 3 – Data Cleaning for my Data Analytics Internship.

---

 Objectives

- Assess the quality of the dataset.
- Handle missing values appropriately.
- Verify and remove duplicate records where necessary.
- Correct incorrect data types.
- Standardize inconsistent categorical values.
- Detect and evaluate outliers.
- Produce a clean dataset ready for analysis.

---
 Tools & Libraries

- Python
- Pandas
- NumPy
- Jupyter Notebook (Kaggle)

---

 Dataset Information

- Dataset: Customer Personality Analysis
- Rows: 2,240
- Columns: 29

---

 Data Cleaning Process

1. Initial Data Inspection

- Loaded the dataset.
- Examined dataset dimensions and structure.
- Reviewed column data types.
- Checked for missing values and duplicates.

2. Missing Values

- Found 24 missing values in the Income column.
- Filled missing values using the median, as income distributions are typically skewed and the median is less affected by outliers.

3. Duplicate Records

- Checked for duplicate rows.
- No duplicate records were found.

4. Data Type Corrections

Converted the following columns to more appropriate data types:

- "ID"
- "Year_Birth"
- "Dt_Customer"

5. Standardizing Categorical Values

Cleaned the Marital_Status column by grouping uncommon values such as:

- Absurd
- YOLO
- Alone

into more meaningful categories such as:

- Single
- Married
- Divorced
- Other

6. Outlier Detection

- Used the Interquartile Range (IQR) method to identify potential outliers.
- Excluded binary variables from outlier analysis.
- Retained identified outliers because they represented valid customer behaviour rather than data entry errors.

7. Export

Exported the cleaned dataset as:

"customer_personality_cleaned.csv"

---

 Data Quality Summary

Metric| Before Cleaning| After Cleaning
Rows| 2,240| 2,240
Columns| 29| 29
Missing Values| 24| 0
Duplicate Rows| 0| 0
Incorrect Data Types| 3| 0

---
 Key Takeaways

- Successfully handled missing values without removing records.
- Standardized categorical data for consistency.
- Corrected inappropriate data types.
- Evaluated outliers using statistical methods while preserving valid observations.
- Produced a clean, reliable dataset suitable for Exploratory Data Analysis (EDA) and Machine Learning.

---

 Repository Contents

├── data-cleaning-of-messy-dataset.ipynb
├── customer_personality_cleaned.csv
├── README.md

---

 Author

Akubueze Joshua

- GitHub: @Joshtheanalyst
- LinkedIn:https://www.linkedin.com/in/akubueze-joshua-0586b33b3/

