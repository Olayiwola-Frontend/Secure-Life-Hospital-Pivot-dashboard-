# Secure-Life-Hospital-Pivot-dashboard-
Hospital Patient Visits Dashboard – READ ME

# Purpose

A management dashboard built from the Hospital Patients Dataset (1,000 patient visits, admissions Jan 2024 – Dec 2025). It answers ten management questions with pivot-style summary tables and charts.


Unit of analysis: each row is one patient visit, not necessarily one unique patient. Patient IDs are unique per visit, but names repeat (684 distinct names across 1,000 rows), so some patients visited more than once.


# Files

File	What it is
Hospital_Patients_Dashboard.xlsx	The workbook: README, Dashboard, Pivot Tables and Data sheets
Hospital_Patients_Dashboard.pptx	A 13-slide PowerPoint version of the same results (static snapshot)
README.md	This file

# Sheets in the workbook


README – the same notes as this file.

Dashboard – six KPI tiles, 12 charts (one per question, labelled Q2–Q9) and the Q10 management-attention findings.

Pivot Tables – every summary table behind the charts (Q1–Q9). All cells are live COUNTIFS / SUMIFS / AVERAGEIFS formulas on the Data sheet, so they are pivot-style tables, not native Excel PivotTables.

Data – the original 12 columns plus 5 helper columns (teal headers, columns M–Q) added by formula: Length of Stay, Admission Month, Age Group (clean), Insurer-Covered Amount, Patient Share.


# Where each question is answered

Question	Dashboard	Pivot Tables table
Q1 Total patient visits	KPI tile	Q1
Q2 Visits by department	Column chart	Q2
Q3 Billing by department	Column chart	Q3
Q4 Average length of stay	Column chart	Q4
Q5 Paid / Pending / Partially Paid	Doughnut chart	Q5
Q6 Billed vs outstanding	KPI tiles, stacked chart	Q6, Q6b
Q7 Insurance by department and diagnosis	100% stacked chart, diagnosis chart	Q7a, Q7b, Q7c
Q8 Visits by age group	Column chart	Q8
Q9 Admissions and billing over time	Two line charts, year-over-year card	Q9
Q10 Areas for attention	Findings block at the bottom	–

# Definitions and assumptions


Total billed: sum of Total Bill Amount ($) across all visits.

Estimated outstanding: Pending bills (100% unpaid) plus a share of Partially Paid bills. The data has no amount-paid field, so that share is an assumption, 50% by default. It sits in a yellow cell on the Pivot Tables sheet (Q6); change it and all outstanding figures update.

Insurance coverage: average coverage is the simple mean of Insurance Coverage % per visit. Insurer-Covered Amount = bill × coverage %; Patient Share = bill − insurer-covered.

Length of stay: Discharge Date minus Admission Date, in days.

Age groups: derived from Age using the source labels (Under 18, 18–35, 36–50, 51–65, 66 & above). 8 source rows had a blank Age Category (all aged 66) and are counted in 66 & above.

Months: visits are assigned to the month of their Admission Date.


# Colour key (workbook)


Blue text on yellow fill: an editable assumption (outstanding share). Blue text also marks the one hardcoded source number (684 distinct names).

Teal column headers: helper columns on the Data sheet (formulas, do not overwrite).


# How to update with new data


Paste new rows into the Data sheet, columns A–L, in the same column order.

Copy the formulas in helper columns M–Q down to the new rows.

Important: the summary formulas read Data rows 2–1001. If you add rows, extend those ranges (find and replace $1001 with the new last row) on the Pivot Tables and Dashboard sheets.

New months, departments, diagnoses or age groups need a new row in the matching Pivot Tables table (copy a row above and change the label); chart ranges then need extending.

Row order inside each table reflects the current ranking and does not re-sort itself.


# Limitations


There is no amount paid, payment date or claim status, so outstanding balances and bill ageing are estimates or cannot be measured.

The Q10 findings text and the PowerPoint deck were written from the data as supplied and do not update automatically. Charts, KPI tiles and tables in the workbook do.


# Dashboard


