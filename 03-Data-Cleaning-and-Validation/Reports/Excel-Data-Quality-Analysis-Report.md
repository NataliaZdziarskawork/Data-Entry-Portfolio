Excel Data Quality Analysis Report

Project: Data Cleaning and Validation
Analysis Tool: Microsoft Excel
Dataset: "Messy_Employee_dataset.csv"

1. Project Overview

The purpose of this project was to assess the quality of an employee dataset using Microsoft Excel.

The analysis focused on identifying missing values, checking data uniqueness, evaluating data consistency and data types, validating selected fields, and identifying data quality issues that could affect further data processing and analysis.

The analysis was performed on the original "Messy_Employee_dataset.csv" file. The raw dataset was preserved before the cleaning process.

Several Excel worksheets were created to document the data quality assessment, including completeness, consistency, data types, uniqueness, validity and pre-cleaning quality control.

The identified data quality issues were documented in a cleaning log, and appropriate cleaning actions were applied without fabricating missing or unreliable information.

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

The original dataset was preserved separately from the cleaned dataset and used as the source for the data quality assessment.

3. Completeness Analysis

The completeness analysis checked all 12 columns for missing values.

Only the "Age" column contained missing values.

A total of 211 "Age" values were missing out of 1,020 employee records. This represents approximately 20.69% of all employee records.

The remaining 11 columns contained no blank values.

The completeness audit therefore identified:

- Total records: 1,020
- Total columns: 12
- Columns with missing values: 1
- Total missing cells: 211
- Affected column: "Age"
- Missing rate: 20.69%

The missing "Age" values were retained as blank during cleaning because there was no reliable source available to determine the correct ages.

4. Consistency Analysis

The consistency analysis evaluated whether values were represented in a consistent format across the dataset.

The following checks passed:

- "First_Name" — spacing was consistent.
- "Last_Name" — spacing was consistent.
- "Department_Region" — the "-" separator was used consistently.
- "Department_Region" — 36 combinations were identified.
- "Status" — values followed a consistent representation.
- "Email" — the expected "example.com" domain was present in the checked values.
- "Phone" — the checked values followed the expected representation.
- "Performance_Score" — categorical values were consistent.
- "Remote_Work" — Boolean values were consistently represented.
- "Employee_ID" — identifier length was consistent.
- "First_Name" and "Last_Name" — capitalization was consistent.

The "Join_Date" field failed the consistency check because the text representations had different lengths: 8, 9 and 10 characters.

The "Salary" field also failed the consistency check because the text representations had different lengths: 7, 8 and 9 characters.

These findings indicated that the fields required standardization before being used for further analysis.

5. Data Types Analysis

The data type analysis compared the expected type of each field with its actual representation.

The following fields matched the expected data types:

Field| Expected Type| Result| Status
"Employee_ID"| Text| Correct| PASS
"First_Name"| Text| Correct| PASS
"Last_Name"| Text| Correct| PASS
"Age"| Number| Correct| PASS
"Department_Region"| Text| Correct| PASS
"Status"| Text| Correct| PASS
"Email"| Text| Correct| PASS
"Performance_Score"| Text| Correct| PASS
"Remote_Work"| Boolean| Correct| PASS

The following fields did not match the expected data types:

Field| Expected Type| Result| Status
"Join_Date"| Date| Stored as text| FAIL
"Salary"| Number| Stored as text| FAIL
"Phone"| Text| Required format standardization| FAIL

The incorrect data types could affect sorting, filtering, calculations and further data analysis.

6. Uniqueness Analysis

The uniqueness analysis checked the employee identifiers and complete records for duplication.

The results were:

- Total records: 1,020
- Empty "Employee_ID" values: 0
- Duplicate "Employee_ID" values: 0
- Duplicate complete records: 0

The "Employee_ID" field therefore provided a unique identifier for every employee record.

The absence of duplicate complete records confirmed that the dataset did not contain identical employee records.

Repeated values in other fields, such as names, statuses or performance ratings, were not treated as duplicate records because these values can legitimately occur for multiple employees.

7. Validity Analysis

The validity analysis checked selected fields against predefined validation rules.

Age

The "Age" field contained:

- 0 values outside the expected range of 18–70 years.

The populated age values therefore passed the defined range check.

The separate completeness analysis identified 211 missing "Age" values.

Department_Region

The "Department_Region" field contained 36 unique combinations.

The values passed the implemented validity check.

Status

The "Status" field contained 0 invalid values.

The accepted categories were:

- "Active"
- "Pending"
- "Inactive"

Join_Date

The "Join_Date" field failed the Excel validity check because the dates were stored as text rather than as Excel date values.

The underlying date values were retained and later converted to valid Excel Date values during cleaning.

Salary

The "Salary" field failed the validity check because the values were not stored as numerical values.

The column also contained 24 "N/A" values.

Valid salary values were converted to numbers during cleaning, while unavailable "N/A" values were not fabricated.

Email

All 1,020 email values contained the "@" character.

The implemented email check therefore passed.

Phone

The Excel validity check recorded 11 digits in the checked sample.

A more detailed review documented in the cleaning log identified 92 invalid phone values:

- 78 values missing 1 digit,
- 12 values missing 2 digits,
- 2 values missing 3 digits.

There were no missing phone values.

Performance_Score

The field contained the categorical values:

- "Excellent"
- "Good"
- "Average"
- "Poor"

The Excel validity worksheet flagged this field because the implemented rule also referred to a numerical 1–5 range, while the actual field contains categorical text values.

The categorical values themselves were consistent and were not changed during cleaning.

Remote_Work

The field contained only Boolean values represented as "TRUE"/"FALSE".

The validity check passed.

8. Pre-Cleaning Quality Control

A pre-cleaning quality control check was performed before the cleaning process.

The results were:

Control| Result| Status
Age outside 18–70| 0| PASS
Valid Status values| 1,020| PASS
Department_Region| 36 combinations| PASS
Email| 1,020| PASS
Performance_Score| 267 / 267 / 270 / 216| PASS
Remote_Work| 1,020| PASS
Duplicate complete records| 0| PASS

Dataset information:

- Dataset: "Messy_Employee_dataset"
- Stage: Pre-Cleaning
- Total records: 1,020
- Total columns: 12

The pre-cleaning quality control confirmed that the dataset had no duplicate complete records and that the main categorical fields contained expected values.

9. Data Cleaning Performed

The cleaning process was performed on a separate copy of the original dataset.

The raw dataset was preserved unchanged.

Employee_ID

No issues were detected.

No changes were required because all "Employee_ID" values were complete and unique.

First_Name

No issues were detected.

No changes were required.

Last_Name

No issues were detected.

No changes were required.

Age

There were 211 missing "Age" values.

The missing values were retained as blank.

No ages were fabricated because there was no reliable source available to determine the correct values.

Department_Region

No issues were detected.

The values were complete and consistent, so no changes were required.

Status

No issues were detected.

All values matched the accepted categories.

No changes were required.

Join_Date

The "Join_Date" values were originally stored as text.

They were converted to valid Excel Date values.

This was necessary for proper date sorting, filtering and further analysis.

Salary

The "Salary" column was originally stored as text and contained 24 "N/A" values.

Valid salary values were converted to numbers.

The 24 "N/A" values were retained as blank values because there was no reliable information available to replace them.

Email

No issues were detected.

No changes were required.

Phone

The cleaning log identified 92 invalid phone values:

- 78 values missing 1 digit,
- 12 values missing 2 digits,
- 2 values missing 3 digits.

The "-" separator was removed from the phone numbers to standardize their format.

Invalid phone numbers were retained without adding or guessing missing digits.

This standardized the phone number representation without altering or fabricating the underlying digits.

Performance_Score

No data cleaning was required.

The existing categorical values were retained.

Remote_Work

No data cleaning was required.

All values were valid Boolean values.

10. Cleaning Results

The Excel cleaning process addressed the identified formatting and data type issues while preserving unreliable or missing information.

The main cleaning actions were:

Field| Issue| Cleaning Action
"Age"| 211 missing values| Missing values retained
"Join_Date"| Stored as text| Converted to Excel Date
"Salary"| Stored as text; 24 "N/A" values| Valid values converted to Number; "N/A" retained as blank
"Phone"| 92 invalid values and inconsistent separator| "-" separator removed; invalid lengths retained

No changes were required for:

- "Employee_ID"
- "First_Name"
- "Last_Name"
- "Department_Region"
- "Status"
- "Email"
- "Performance_Score"
- "Remote_Work"

The cleaning process followed a conservative approach: missing or unreliable information was not invented.

11. Final Data Quality Assessment

After the cleaning process, the dataset had improved formatting and data type consistency.

The "Join_Date" field was converted from text to valid Excel Date values.

Valid "Salary" values were converted to numerical values.

The 24 unavailable "Salary" values were retained as blank rather than being replaced with fabricated values.

Phone numbers were standardized by removing the "-" separator.

The 92 invalid phone values remained identifiable because missing digits were not reconstructed.

The 211 missing "Age" values remained blank because there was no reliable source for determining the correct ages.

The raw dataset remained unchanged, preserving the original data for traceability.

12. Documentation

The data quality assessment was documented using separate Excel worksheets:

- "Completeness.xlsx"
- "Consistency.xlsx"
- "Data-Types.xlsx"
- "Uniqueness.xlsx"
- "Validity.xlsx"
- "Pre-Cleaning-QC.xlsx"

The cleaning decisions for all 12 fields were documented in:

"Cleaning-Log.xlsx"

The documentation provides a record of the issues identified, actions taken, before-and-after states, and reasons for each cleaning decision.

13. Skills Demonstrated

This project demonstrates the following skills:

- Microsoft Excel
- Data quality assessment
- Data completeness analysis
- Data consistency analysis
- Data type validation
- Data validity checks
- Data uniqueness analysis
- Duplicate detection
- Missing value identification
- Data cleaning
- Data standardization
- Date formatting and conversion
- Numerical data conversion
- Phone number validation
- Data quality control
- Cleaning documentation
- Working with raw and cleaned datasets
- Data quality reporting
- Safe handling of missing and unreliable data

14. Conclusion

The Excel analysis provided a structured assessment of the quality of the employee dataset before and during the cleaning process.

The main data quality issues identified were 211 missing "Age" values, text-based "Join_Date" values, text-based "Salary" values including 24 "N/A" entries, and 92 invalid phone values identified during detailed review.

The dataset contained no duplicate "Employee_ID" values and no duplicate complete records.

The cleaning process improved the consistency and usability of the dataset while preserving the original information. Missing and unreliable values were not fabricated, and the raw dataset was preserved separately from the cleaned version.

The project demonstrates a practical Excel-based data quality workflow involving assessment, validation, cleaning, quality control and documentation.

15. Project Structure

03-Data-Cleaning-and-Validation/
├── Raw/
│   └── Messy_Employee_dataset.csv
├── Quality-Control/
│   └── Pre-Cleaning-QC.xlsx
├── DATA-QUALITY-ASSESSMENT/
│   ├── Completeness.xlsx
│   ├── Consistency.xlsx
│   ├── Data-Types.xlsx
│   ├── Uniqueness.xlsx
│   └── Validity.xlsx
├── Cleaned-Data/
│   └── Massy_Employee_cleaned.csv
├── Cleaning-Log/
│   └── Cleaning-Log.xlsx
├── Python-Analysis/
└── REPORTS/
    └── Excel-Data-Quality-Analysis-Report.md

The project structure separates the raw dataset, quality control files, data quality assessment, cleaned data, cleaning documentation, Python analysis and reports.

This structure supports traceability and provides clear evidence of the data cleaning and validation workflow.