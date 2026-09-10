Python Data Quality Analysis Report

Project: Data Cleaning and Validation
Analysis Tool: Python
Dataset: "Messy_Employee_dataset.csv"

1. Project Overview

The purpose of this project was to assess the quality of employee data using Python.

The analysis focused on identifying missing values, checking data uniqueness, validating selected fields, and detecting data quality issues that could affect further data processing and analysis.

The analysis was performed on the original "Messy_Employee_dataset.csv" file using Python. The original dataset was preserved without modification.

Python was used as an independent data quality analysis and validation tool. The results were saved as CSV reports and compared with the results of the Excel-based analysis.

2. Dataset Structure

The dataset used for the analysis was "Messy_Employee_dataset.csv".

The dataset contained 1,020 employee records and 12 columns.

The columns were:

- "Employee_ID"
- "First_Name"
- "Last_Name"
- "Age"
- "Department_Region"
- "Status"
- "Join_Date"
- "Salary"
- "Email"
- "Phone"
- "Performance_Score"
- "Remote_Work"

The original dataset was kept unchanged and used as the source for the Python analysis.

3. Python Analysis

Python was used to perform an independent data quality assessment of the employee dataset.

The analysis included:

- checking the number of rows and columns,
- checking missing values,
- checking the number of unique values,
- checking repeated values in individual columns,
- validating selected data fields,
- checking date values,
- validating email addresses,
- validating phone numbers,
- checking allowed values for "Status", "Performance_Score" and "Remote_Work",
- identifying the main data quality problems,
- creating CSV reports with the analysis results.

The analysis was performed using the Python standard library and the original CSV dataset.

4. Completeness Analysis

The completeness analysis checked all 12 columns for missing values.

The analysis identified missing values only in the "Age" column.

A total of 211 records had a missing "Age" value. This represents approximately 20.69% of all employee records.

All other columns contained no blank values.

The missing "Age" values were not filled during the cleaning process because there was no reliable source available to determine the correct employee ages. No values were fabricated.

5. Uniqueness Analysis

The uniqueness analysis was used to check the number of unique values in each column and to identify potential duplication issues.

The "Employee_ID" column contained 1,020 unique values for 1,020 employee records. No duplicate "Employee_ID" values were detected.

The dataset also contained no duplicate complete records.

Some columns contained repeated values, for example "First_Name", "Last_Name", "Status" and "Performance_Score". These repetitions were considered expected because the same names, statuses and performance ratings can occur for multiple employees.

The uniqueness analysis therefore did not identify duplicate employee records or duplicate "Employee_ID" values as data quality problems.

6. Data Validation

The Python analysis included validation of several fields according to predefined data quality rules.

The "Age" field was validated against the expected range of 18–70 years. The analysis found 809 valid values, 0 invalid values and 211 missing values.

The "Salary" field was checked to identify valid numeric values. The analysis found 996 valid values and 24 invalid "N/A" values.

The "Join_Date" field was checked for valid date values. All 1,020 records contained valid dates, and an additional calendar validation confirmed the results.

The "Email" field was checked using a basic email format validation. All 1,020 values passed the validation.

The "Phone" field was validated by checking the number of digits after removing the "-" separator and spaces. The analysis identified 928 valid phone numbers and 92 invalid values.

The "Status" field contained only the expected values: "Active", "Pending" and "Inactive".

The "Performance_Score" field contained only the expected categorical values: "Excellent", "Good", "Average" and "Poor".

The "Remote_Work" field contained only the expected Boolean values: "TRUE" and "FALSE".

7. Detected Data Quality Issues

The Python analysis identified three main data quality issues in the dataset.

Age

There were 211 missing "Age" values. No invalid ages outside the 18–70 range were detected among the populated values.

Salary

There were 24 "N/A" values in the "Salary" column. These values were treated as invalid for numerical analysis because they could not be interpreted as numeric salary values.

Phone

There were 92 invalid phone numbers.

The invalid phone numbers were classified according to the number of missing digits:

- 78 values were missing 1 digit,
- 12 values were missing 2 digits,
- 2 values were missing 3 digits.

No missing phone values were detected.

The missing phone digits were not reconstructed because there was no reliable source for determining the correct values.

8. Data Cleaning Performed by Python

The Python cleaning process was performed on a copy of the dataset. The original raw dataset was preserved unchanged.

Age

The 211 missing "Age" values were left blank because there was no reliable source for determining the correct ages.

Salary

The 24 "N/A" values in the "Salary" column were converted to blank values. Valid salary values were retained for numerical analysis.

Phone

The "-" separator was removed from the phone numbers to standardize their format. Invalid phone numbers were retained without adding or guessing missing digits.

The cleaning process focused on standardization and safe handling of missing or invalid data without fabricating information.

9. Final Results

The Python analysis provided an independent assessment of the quality of the employee dataset.

The main issues identified were:

- 211 missing "Age" values,
- 24 invalid "Salary" values represented as "N/A",
- 92 invalid "Phone" values.

No duplicate "Employee_ID" values or duplicate complete records were detected.

The "Join_Date", "Email", "Status", "Performance_Score" and "Remote_Work" fields passed the implemented Python validation checks.

The analysis results were exported to CSV files:

- "data_quality_report.csv" — summary of the main data quality problems,
- "full_data_quality_report.csv" — completeness and uniqueness results for all columns.

A cleaned copy of the dataset was also created while preserving the original raw dataset.

10. Skills Demonstrated

This project demonstrates the following skills:

- Python programming for data analysis
- CSV file handling
- Data quality assessment
- Data completeness analysis
- Data uniqueness analysis
- Data validation
- Missing value identification
- Data cleaning and standardization
- Basic data validation rules
- Phone number validation and error classification
- CSV report generation
- Working with raw and cleaned datasets
- Data quality reporting
- Independent verification of data using Python

11. Conclusion

The Python analysis provided a structured assessment of the employee dataset and identified the main data quality issues before further processing.

The analysis demonstrated that Python can be used to automate repetitive data quality checks, validate selected fields, classify errors and generate structured reports.

The results provide an independent verification of the data quality assessment performed in Excel and can be used as a basis for further data cleaning and analysis.

12. Project Structure

The project is organized into separate folders for raw data, quality control, data quality assessment, cleaned data, cleaning documentation and Python analysis.

03-Data-Cleaning-and-Validation/
├── Raw/
├── Quality-Control/
├── Data-Quality-Assessment/
├── Cleaned-Data/
├── Cleaning-Log/
├── Python-Analysis/
│   ├── analiza.py
│   ├── data_quality_report.csv
│   └── full_data_quality_report.csv
└── REPORTS/

The raw dataset is preserved separately from the cleaned data. The Python analysis and generated reports are stored in the "Python-Analysis" folder.