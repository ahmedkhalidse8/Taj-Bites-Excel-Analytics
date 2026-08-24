# Taj Bites — Python Business Analytics

**Python Analytics Project | Pandas | NumPy | Matplotlib | OpenPyXL | Data Validation | Exploratory Data Analysis**

> A Python-based business analytics project built from real operational data from Taj Bites, a restaurant business without a conventional POS-based analytics system.

## Project Overview

This project analyzes daily sales, profitability, product-category performance, and business trends for Taj Bites, a food-service business.

The analysis covers **381 daily records** from **December 2022 through December 2023**.

This repository represents the **Python-based analytics implementation** of the Taj Bites project. The focus is on programmatic workbook auditing, data extraction, cleaning, validation, exploratory data analysis, data-quality investigation, and business performance analysis.

The project follows a complete Python analytics workflow:

```text
Raw Excel Workbooks
        ↓
Python Workbook Audit
        ↓
Data Extraction
        ↓
Data Cleaning
        ↓
Data Validation
        ↓
Data-Quality Investigation
        ↓
Exploratory Data Analysis
        ↓
Business Performance Analysis
        ↓
Analytical Outputs
        ↓
Excel Dashboard
```

The project demonstrates how Python can be used to transform fragmented operational Excel files into a structured analytical dataset and business reporting workflow.

---

# Business Objectives

The analysis was designed to answer the following questions:

* How much revenue and net profit did the business generate?
* Which months delivered the strongest and weakest performance?
* Which product categories generated the most sales?
* Which days of the week performed best?
* How consistently was the business profitable?
* Were there any data-quality issues that could affect business conclusions?

---

# Key Results

* **Total Sales:** Rs. 4,772,545
* **Total Gross Profit:** Rs. 1,170,606
* **Total Net Profit:** Rs. 602,639
* **Gross Profit Margin:** 24.53%
* **Net Profit Margin:** 12.63%
* **Profitable Days:** 300 out of 381
* **Profitable-Day Rate:** 78.74%
* **Best Sales Month:** August 2023, with Rs. 507,125 in sales
* **Best Net Profit Month:** August 2023, with Rs. 99,336 in net profit
* **Highest-Sales Product Category:** Main Food
* **Highest Average-Sales Day:** Friday

---

# Key Business Insights

1. Taj Bites generated Rs. 4.77 million in sales and Rs. 602,639 in net profit during the analysis period.
2. The business was profitable on approximately 79% of recorded days, although 81 days generated net losses.
3. August 2023 was the strongest month for both sales and net profit.
4. Friday generated the highest average daily sales, while Tuesday generated the lowest average daily sales.
5. Net profit margin declined significantly toward the end of 2023, reaching 2.86% in December.
6. Main Food was the largest revenue-generating category, while Fries delivered a stronger reported profit margin.
7. The reported Additional Food profit values were identified as unreliable and excluded from category-profit comparisons.

---

# Tools and Technologies

### Python

Primary programming language used for the analytical workflow.

Used for:

* Workbook auditing
* Data extraction
* Data cleaning
* Data validation
* Exploratory data analysis
* Business analysis
* Automated quality checks
* Analytical output generation

### Pandas

Used for:

* Data manipulation
* Data cleaning
* Aggregation
* Dataset transformation
* Business-performance analysis

### NumPy

Used for numerical calculations and analytical operations.

### Matplotlib

Used to generate analytical visualizations covering:

* Monthly sales
* Monthly net profit
* Profit margins
* Product-category performance
* Weekday performance
* Daily trends

### OpenPyXL

Used for programmatic interaction with the source Excel workbooks.

### Microsoft Excel

Used as:

* The original operational data format
* The final dashboard/reporting environment

### Excel PivotTables and Charts

Used in the resulting business dashboard for management-oriented reporting.

---

# Project Structure

```text
Taj-Bites-Python-Analytics/
│
├── analysis/
│   ├── 01_audit_workbooks.py
│   ├── 02_inspect_workbook.py
│   ├── 03_check_calculated_values.py
│   ├── 04_extract_daily_summary.py
│   ├── 04_validate_daily_summary.py
│   ├── 05_validate_cleaned_data.py
│   ├── 06_remove_duplicate_dates.py
│   ├── 07_exploratory_data_analysis.py
│   ├── 08_investigate_category_profit.py
│   └── 09_final_business_analysis.py
│
├── audit/
│   └── workbook_audit.csv
│
├── excel_dashboard/
│   └── Taj_Bites_Business_Dashboard.xlsx
│
├── excel_pipeline/
│   ├── Taj_Bites_Historical_Data.xlsx
│   └── Taj_Bites_Historical_Data_Repaired.xlsx
│
├── outputs/
│   ├── business_insights.txt
│   │
│   ├── charts/
│   │   ├── 01_monthly_sales.png
│   │   ├── 02_monthly_net_profit.png
│   │   ├── 03_monthly_profit_margin.png
│   │   ├── 04_category_sales.png
│   │   ├── 05_category_profit.png
│   │   ├── 06_day_of_week_sales.png
│   │   ├── 07_day_of_week_profit.png
│   │   ├── 08_daily_sales_trend.png
│   │   └── 09_daily_net_profit_trend.png
│   │
│   └── tables/
│       ├── category_performance.csv
│       ├── day_of_week_performance.csv
│       ├── kpi_summary.csv
│       ├── monthly_performance.csv
│       └── reliable_category_profit.csv
│
├── processed_data/
│   ├── taj_bites_daily_summary_clean.csv
│   └── taj_bites_monthly_summary.csv
│
└── README.md
```

---

# Data Cleaning and Validation

The raw source files were audited and consolidated into a daily business-performance dataset.

The Python validation process checked:

* Required columns
* Missing values
* Duplicate dates
* Negative sales values
* Total-sales calculations
* Gross-profit calculations
* Net-profit calculations
* Negative-profit records
* Zero-sales records

Six duplicate dates were identified and removed.

The final cleaned dataset contains **381 records**, with no remaining duplicate dates and no missing values.

Small Rs. 0.01 differences in some profit calculations were treated as normal rounding differences.

The validation process was designed to establish confidence in the analytical dataset before downstream business analysis was performed.

---

# Data-Quality Finding

The **Additional Food** category showed reported profit values substantially greater than sales on multiple dates.

Because these values produced unrealistic profit margins, Additional Food profit was excluded from category-profit comparisons.

The source data was preserved, and the issue was documented rather than silently changing the original values.

This demonstrates an important analytical principle:

> Data-quality problems should be investigated and documented before they are used to support business conclusions.

---

# Python Analysis Workflow

The analysis scripts were developed as separate stages so that the workflow could be inspected and validated progressively.

### 01 — Workbook Audit

`01_audit_workbooks.py`

Audits the collection of source Excel workbooks and establishes an initial understanding of the available files and workbook structure.

### 02 — Workbook Inspection

`02_inspect_workbook.py`

Inspects workbook contents and structure to identify the relevant worksheets, columns, rows, and operational data layout.

### 03 — Calculated-Value Validation

`03_check_calculated_values.py`

Checks calculated values within the source workbooks and investigates potential calculation inconsistencies.

### 04 — Daily Summary Extraction

`04_extract_daily_summary.py`

Extracts relevant daily business metrics from the operational workbooks into a structured analytical dataset.

### 04 — Daily Summary Validation

`04_validate_daily_summary.py`

Validates the extracted daily summary against the underlying source records.

### 05 — Cleaned Data Validation

`05_validate_cleaned_data.py`

Performs additional checks against the cleaned analytical dataset.

### 06 — Duplicate Date Removal

`06_remove_duplicate_dates.py`

Identifies and removes duplicate-date records from the analytical dataset.

### 07 — Exploratory Data Analysis

`07_exploratory_data_analysis.py`

Performs exploratory analysis of:

* Sales
* Profitability
* Monthly performance
* Product categories
* Weekday performance
* Daily trends

### 08 — Category Profit Investigation

`08_investigate_category_profit.py`

Investigates unusual category-level profit values and identifies the Additional Food data-quality issue.

### 09 — Final Business Analysis

`09_final_business_analysis.py`

Produces the final business-performance analysis and analytical output tables.

---

# Dashboard

The resulting Excel dashboard provides a management-oriented view of the business performance.

The dashboard includes:

* Total Sales
* Total Gross Profit
* Total Net Profit
* Net Profit Margin
* Profitable Days
* Loss-Making Days
* Monthly Sales Trend
* Monthly Net Profit Trend
* Sales by Product Category
* Key Business Insights

The dashboard represents the reporting layer built from the validated analytical dataset.

---

# Analytical Outputs

The project generates structured outputs for downstream reporting and interpretation.

### KPI Summary

`kpi_summary.csv`

Contains the primary business KPIs for the analysis period.

### Monthly Performance

`monthly_performance.csv`

Contains monthly sales and profitability metrics.

### Category Performance

`category_performance.csv`

Contains product-category performance metrics.

### Reliable Category Profit

`reliable_category_profit.csv`

Contains category-profit analysis after excluding the unreliable Additional Food profit values.

### Day-of-Week Performance

`day_of_week_performance.csv`

Contains weekday-level performance metrics.

### Business Insights

`business_insights.txt`

Contains the final management-level findings generated from the analysis.

---

# How to Run

1. Clone the repository.

2. Install the required Python packages:

```bash
pip install pandas numpy matplotlib openpyxl
```

3. Ensure the source Excel workbooks are available in the expected raw-data location.

4. Run the analysis scripts in numerical order.

5. Review the generated analytical outputs.

6. Open the Excel dashboard:

```text
excel_dashboard/Taj_Bites_Business_Dashboard.xlsx
```

---

# What This Project Demonstrates

This project demonstrates practical Python data-analytics capabilities across the complete analytical lifecycle.

### Data Engineering / Preparation

* Programmatic Excel workbook inspection
* Workbook auditing
* Data extraction
* Data transformation
* Data cleaning
* Dataset consolidation

### Data Quality

* Missing-value detection
* Duplicate detection
* Calculation validation
* Source-to-output validation
* Anomaly investigation
* Business-rule validation
* Data-quality documentation

### Exploratory Data Analysis

* Monthly trend analysis
* Daily trend analysis
* Product-category analysis
* Weekday analysis
* Profitability analysis
* Margin analysis

### Business Analytics

* KPI development
* Revenue analysis
* Gross-profit analysis
* Net-profit analysis
* Profitability consistency analysis
* Business performance segmentation
* Management-level insight generation

### Visualization

* Monthly sales visualization
* Monthly net-profit visualization
* Profit-margin visualization
* Category-sales visualization
* Category-profit visualization
* Weekday performance visualization
* Daily sales trends
* Daily net-profit trends

---

# Business Questions Answered

The completed analysis can answer questions such as:

### Financial Performance

* How much did the restaurant sell?
* How much gross profit was generated?
* How much net profit was generated?
* What was the overall net margin?

### Monthly Performance

* Which month generated the most sales?
* Which month generated the most net profit?
* Which month performed worst?
* How did profitability change throughout the year?

### Product Performance

* Which category generated the most sales?
* Which categories generated stronger reported profit?
* Were any category-level calculations unreliable?

### Operating Performance

* How many days were profitable?
* How many days generated losses?
* What percentage of operating days were profitable?

### Weekday Performance

* Which weekday generated the highest average sales?
* Which weekday generated the highest average profit?
* Which weekday performed weakest?

### Data Quality

* Were there duplicate dates?
* Were there missing records?
* Were calculations internally consistent?
* Were there suspicious profitability values?
* Could any data-quality issue materially affect business conclusions?

---

# Main Business Story

The most important story from the analysis is not simply that the restaurant generated **Rs. 602,639 in net profit**.

The deeper story is:

> Taj Bites generated Rs. 4.77 million in sales and Rs. 602,639 in net profit across 381 operating days, achieving profitability on 78.74% of recorded operating days. Performance varied throughout the year, with August 2023 producing the strongest sales and net-profit performance. Weekday analysis also revealed meaningful differences, with Friday producing the highest average daily sales while Tuesday produced the lowest. The analysis also identified a significant data-quality issue in reported Additional Food profit values, demonstrating the importance of validating operational data before using it for business decisions.

This moves the project beyond simply producing charts and demonstrates a complete analytical investigation.

---

# Project Outcome

The project transformed a collection of fragmented daily operational Excel workbooks into a structured analytical dataset and business-performance reporting workflow.

The final process covers:

```text
Operational Excel Files
        ↓
Python Workbook Audit
        ↓
Data Extraction
        ↓
Data Cleaning
        ↓
Data Validation
        ↓
Data-Quality Investigation
        ↓
Exploratory Data Analysis
        ↓
Business Performance Analysis
        ↓
Analytical Outputs
        ↓
Excel Dashboard
```

The resulting system provides a centralized view of:

* Revenue
* Gross profitability
* Net profitability
* Profit margins
* Product-category performance
* Monthly trends
* Weekday performance
* Profitability consistency
* Data-quality issues

---

# Project Scope

This repository is intentionally focused on the **Python implementation** of the Taj Bites analytics work.

The project demonstrates how Python can be used to perform the audit, extraction, validation, exploratory analysis, and business analysis stages of a real operational-data problem.

The Excel dashboard is included as the reporting output of this analytical workflow.

The project is therefore positioned primarily as a:

> **Python Data Analytics / Business Analytics Project**

rather than as an Excel-only dashboard project.

---

# Portfolio Positioning

This project should be viewed as a practical example of applying Python analytics to real operational business data.

Instead of starting with a clean public dataset, the project began with fragmented daily Excel workbooks that required:

* Workbook inspection
* Automated auditing
* Data extraction
* Data cleaning
* Validation
* Duplicate detection
* Data-quality investigation
* Exploratory analysis
* Business interpretation

The project demonstrates the ability to work with imperfect operational data and turn it into structured information suitable for business analysis.

---

# Project Classification

**Project Type:** Python Business Analytics / Data Analytics

**Industry:** Restaurant / Food Service

**Primary Tools:** Python, Pandas, NumPy, Matplotlib

**Supporting Tools:** OpenPyXL, Microsoft Excel

**Analysis:** Data Audit + Cleaning + Validation + EDA + Business Analysis

**Visualization:** Matplotlib + Excel Dashboard

**Reporting Period:** December 2022 – December 2023

**Operating Days:** 381

**Total Sales:** Rs. 4,772,545

**Total Gross Profit:** Rs. 1,170,606

**Total Net Profit:** Rs. 602,639

**Net Profit Margin:** 12.63%

**Profitability Rate:** 78.74%

---

# Author

**Ahmed Khalid**

Portfolio: https://ahmedkhalidse8.github.io
GitHub: https://github.com/ahmedkhalidse8
