# Healthcare-assignment-3
# Assignment-3-Healthcare-Data-Analysis-and-Insights

* **Problem Description:** Analysed a healthcare dataset made up of three tables (Customer Names, Medical Examinations and Hospitalisation Details) to understand patient health profiles, medical history and healthcare charges. The work covers data cleaning, transformation, combining the tables, pivot-table analysis, charts and an interactive dashboard.
* **Handling Missing Values:** Counted the missing values marked with `?` in every column of the Medical Examinations and Hospitalisation Details tables. Missing values were found in: smoker (2), Customer ID (6), year (2), month (3), Hospital tier (1), City tier (1) and State ID (2). Original columns were kept untouched and the fixes were placed in separate `(Cleaned)` columns.
* **Month and Year Imputation:** Filled missing `month` values with Sep. Filled missing `year` values with the average year rounded to the nearest integer (1982.84 → 1983) using `AVERAGE` and `ROUNDUP`.
* **Mode Imputation:** Found the most frequent value using `COUNTIF` with a nested `IF`, and filled the missing values with it: Hospital tier = tier - 2, City tier = tier - 2 and smoker = No.
* **State ID:** Filled the 2 missing State IDs with "Unknown" so no blanks remain.
* **Splitting Names:** Split the `name` column (format `Last, Title. First`) into Title, First Name and Last Name using `MID`, `FIND`, `LEFT` and `LEN`. Example: "Hawks, Ms. Kelly" → Ms. | Kelly | Hawks.
* **NumberOfMajorSurgeries:** Converted the text "No major surgery" to 0 using `IF`, so the column is fully numeric.
* **Correcting Inconsistent Data:** Standardised mixed-case values such as "yes" / "Yes" in the `Heart Issues` and `smoker` columns using `PROPER`, so only Yes / No remain.
* **Weight Status:** Categorised BMI using nested `IF`: below 18.5 = Underweight, 18.5-24.9 = Normal Weight, 25.0-29.9 = Overweight, 30.0 and above = Obesity.
* **Diabetes Status:** Categorised HbA1c using nested `IF`: below 5.7 = Normal, 5.7-6.4 = Prediabetes, 6.5 and above = Diabetes.
* **Date of Birth:** Merged `year`, `month` and `date` into one Date of Birth column using `DATE`, `MATCH` (month name to month number) and `IF`. Formatted as `DD-MMM-YYYY`.
* **Age Calculation:** Calculated Age in completed years using `DATEDIF` with the data collection date 8 June 2023.
* **Number Formatting:** Formatted the `charges` column as currency ($).
* **Combining Tables:** Created the `Healthcare` sheet and combined all three tables using Customer ID as the common column with `VLOOKUP`. Used `IFERROR` for records that have no matching hospitalisation details. Retained the 17 required columns (Customer ID, First Name, BMI, HBA1C, Heart Issues, Any Transplants, Cancer history, NumberOfMajorSurgeries, smoker, Weight Status, Diabetes Status, Date of Birth, charges, Hospital tier, City tier, State ID, Age).
* **Cancer History vs Smoking (Pie Charts):** Built a pivot table (Cancer history by Smoker, Count of Customer ID) and created two pie charts, one for smokers and one for non-smokers.
* **Transplant Analysis (Donut Charts):** Built pivot tables on Any Transplants showing Sum of Number of Major Surgeries and HbA1c, and created two donut charts.
* **Charges by Weight and Diabetes Status (Column Charts):** Built pivot tables showing Average of charges by Weight Status and by Diabetes Status, and created column charts.
* **Charges by Hospital Tier and State (Clustered Column Chart):** Built a pivot table with State ID in rows, Hospital tier in columns and Average of charges as values.
* **Correlation Analysis (Scatter Plots):** Created scatter plots for Age vs BMI, Age vs HbA1c and Age vs Healthcare Charges to study the relationships between them.
* **Dashboard:** Built a `Dash Board` sheet that brings all 10 charts together on one page.
* **Slicers:** Added slicers for `Weight Status` and `Diabetes Status`, connected to the pivot tables, to filter the visualisations and compare health outcomes and charges.

