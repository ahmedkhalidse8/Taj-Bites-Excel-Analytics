# Taj Bites — Restaurant Business Performance Analytics

**Excel Flagship Project | Power Query | Excel Formulas | PivotTables | PivotCharts | Business Intelligence**

> An Excel-based business analytics system built from real operational data for a restaurant that did not have a conventional POS-based analytics system.

---

# 1. Project Overview

**Taj Bites — Restaurant Business Performance Analytics** is an Excel flagship analytics project built using real daily operational records from a restaurant.

The project began with an existing operational tracking system consisting of individual daily Excel workbooks. The original system was designed primarily for day-to-day restaurant operations, including inventory measurement, product costs, sales, expenses, and profitability.

The source directory contains **387 Excel workbooks**, while the final analytical dataset represents **381 operating days** covering:

**December 2022 – December 2023**

The purpose of rebuilding the project was to transform the original operational system into a professional **Excel-based business analytics solution**, while preserving the original business logic and demonstrating the full range of Excel capabilities relevant to data analytics.

The project deliberately positions:

* **Excel as the primary analytics platform**
* **Power Query as the data ingestion and transformation pipeline**
* **Formulas as the business-logic and analytical layer**
* **PivotTables and PivotCharts as the aggregation and visualization layer**
* **The dashboard as the executive reporting layer**
* **Data quality and validation as an explicit part of the workflow**

The analytical workflow is:

```text
387 Daily Excel Workbooks
          ↓
      Power Query
          ↓
Data Cleaning & Transformation
          ↓
    Historical Dataset
          ↓
   Formula Analysis
          ↓
      PivotTables
          ↓
    Business Insights
          ↓
   Executive Dashboard
```

The final solution allows management to understand:

* Overall business profitability
* Total sales
* Gross profit
* Net profit
* Profit margins
* Monthly profitability
* Weekday performance
* Profitable vs. loss-making days
* Business performance patterns
* Areas requiring further investigation

---

# 2. Project Background

The restaurant originally operated using manually maintained daily Excel workbooks.

Each day's operations were recorded in a separate workbook containing information related to:

* Product costs
* Product sales
* Product-level profit
* Raw material consumption
* Packaging/material usage
* Employee costs
* Rent
* Bills
* Daily operating costs
* Gross profit
* Net profit

The original workbook was therefore more than a simple sales spreadsheet. It functioned as a basic operational accounting and inventory-tracking system.

The original operational system is documented separately in:

```text
documentation/
└── Original_System_Documentation.md
```

That document explains the original workflow, inventory measurement process, product costing, sales calculations, fixed costs, gross profit, and net profit calculations.

---

# 3. Business Problem

The restaurant's historical operational data existed across hundreds of individual Excel workbooks.

This created several analytical challenges.

### Original challenges

* Data was distributed across individual daily files.
* The files followed an operational rather than analytical structure.
* Historical analysis required combining information from many workbooks.
* Manual consolidation would be time-consuming and error-prone.
* Business performance was difficult to evaluate across long periods.
* Profitability patterns were not immediately visible.
* There was no centralized executive-level analytical dashboard.

The project therefore focused on answering a fundamental business question:

> **How can historical restaurant operations be transformed into a reliable Excel-based business intelligence system that allows management to understand profitability and operating performance?**

---

# 4. Project Objectives

The project was designed to demonstrate practical Excel analytics skills while solving a genuine business problem.

### Primary objectives

1. Consolidate historical operational data using Power Query.
2. Clean and standardize the resulting analytical dataset.
3. Establish a structured Excel-based analytical workflow.
4. Apply Excel formulas to support business analysis.
5. Demonstrate conditional business logic.
6. Create PivotTables for multidimensional analysis.
7. Create PivotCharts and management-level visualizations.
8. Analyze profitability across time and operating days.
9. Identify important business trends and performance patterns.
10. Build an executive-level dashboard.
11. Document data-quality issues and validation procedures.
12. Produce a portfolio-ready Excel analytics project.

---

# 5. Dataset

## Source Workbooks

The source directory contains **387 `.xlsx` workbooks**.

The workbooks are organized by month:

```text
raw-data/

├── Dec 2022/
├── Jan 2023/
├── Feb 2023/
├── ...
├── Dec 2023/
└── ...
```

Each workbook represents an individual daily operational record.

Example:

```text
raw-data/
└── Apr 2023/
    ├── 01 Apr 2023.xlsx
    ├── 02 Apr 2023.xlsx
    ├── 03 Apr 2023.xlsx
    └── ...
```

## Analytical Coverage

The final analytical dataset represents:

* **Reporting period:** December 2022 – December 2023
* **Operating days:** 381
* **Source workbooks:** 387

The difference between source workbook count and operating-day count reflects the underlying source-file structure and data-quality/reconciliation process.

---

# 6. Data Architecture

The original data was organized around individual daily operational workbooks.

The project transformed this operational structure into an analytical workflow.

## Source Layer

```text
raw-data/

│
├── Dec 2022/
│   ├── 02 Dec 2022.xlsx
│   ├── 03 Dec 2022.xlsx
│   └── ...
│
├── Jan 2023/
│   ├── ...
│
└── ...
```

## Analytical Workflow

```text
Raw Daily Workbooks
        │
        ▼
   Power Query
        │
        ▼
Data Cleaning / Transformation
        │
        ▼
 Historical Dataset
        │
        ├──────────────► Data Quality
        │
        ├──────────────► Formula Analysis
        │
        └──────────────► PivotTables
                              │
                              ▼
                       Business Insights
                              │
                              ▼
                      Executive Dashboard
```

---

# 7. Historical Data Pipeline — Power Query

Power Query is the primary data ingestion and transformation layer of the project.

Instead of manually opening hundreds of daily workbooks, the project uses a folder-based Power Query process.

## Pipeline Architecture

```text
387 Daily Excel Workbooks
          ↓
      Power Query
          ↓
     Read Workbook
          ↓
     Access Sheet1
          ↓
     Extract Required Fields
          ↓
    Apply Business Logic
          ↓
     Sort by Date
          ↓
    Historical Dataset
```

The Power Query process performs several important tasks.

### Folder-based ingestion

Power Query reads the source files directly from the `raw-data` directory.

### Workbook extraction

Each workbook is opened programmatically through Power Query and the required `Sheet1` data is extracted.

### Date extraction

The operating date is derived from the workbook filename.

### KPI extraction

Required historical measures are extracted from the fixed workbook structure, including:

* Fries cost
* Fries sales
* Fries profit
* Zinger cost
* Zinger sales
* Zinger profit
* Loaded food cost
* Loaded food sales
* Loaded food profit
* Drinks cost
* Drinks sales
* Drinks profit
* Daily operational cost
* Total daily sales
* Gross profit
* Net profit

### Historical business logic

The source workbook structure changed during the operating period.

The Power Query transformation therefore includes date-based logic to correctly extract values before and after the structural change on:

**17 August 2023**

This is important because the analytical dataset is not simply a raw concatenation of identical tables. The transformation preserves the underlying business logic of the original operational system.

### Refreshability

The main advantage of the Power Query approach is that the historical dataset can be refreshed from the source folder rather than manually rebuilding the dataset from hundreds of workbooks.

---

# 8. Power Query Evidence

Screenshots documenting the Power Query implementation are included in:

```text
outputs/

├── power_query.png
└── Power Query Editor with Applied Steps.png
```

These screenshots provide visual evidence of:

* The Power Query workflow
* Source connection
* Transformation steps
* Applied steps
* Historical data extraction

---

# 9. Excel Workbook Architecture

The final Excel workbook is organized into dedicated analytical layers.

The workbook is stored in:

```text
excel_dashboard/
└── Taj_Bites_Business_Analytics.xlsx
```

The workbook contains dedicated sections for:

* Historical / Power Query Data
* Data Dictionary
* Data Quality
* Data Analysis
* Formula Analysis
* PivotTables
* Business Insights
* Executive Dashboard

Each sheet serves a specific analytical purpose rather than duplicating the same analysis.

---

# 10. Historical Data / Power Query Sheet

The Historical Data sheet contains the analytical dataset loaded through Power Query.

This sheet acts as the primary data layer for downstream Excel analysis.

Its purpose is to provide:

* One structured historical dataset
* Consistent field names
* Standardized dates
* Extracted financial metrics
* A refreshable connection to the source workbooks

The sheet separates the **data preparation layer** from the **analysis and presentation layers**.

---

# 11. Data Dictionary

The Data Dictionary documents the analytical fields used within the project.

The purpose is to make the dataset understandable and maintainable.

A data dictionary is particularly important when transforming an operational workbook into an analytical model because field names and business definitions need to be explicit.

The documentation explains the meaning and analytical purpose of the main fields used in the historical dataset.

---

# 12. Data Quality

Data quality was treated as an explicit component of the project.

The project does not assume that operational data is automatically perfect.

Instead, potential issues were investigated through:

* Record-level checks
* Duplicate checks
* Missing-value checks
* Calculation checks
* Anomaly investigation
* Source-to-output comparisons
* Sampling-based QA

Examples of issues investigated during the project included:

* Duplicate dates
* Duplicate or misplaced files
* Inconsistent records
* Calculation anomalies
* Product-level calculation discrepancies
* Unusual profitability values

The purpose of this section is not simply to report that the data is "clean."

It demonstrates an analytical approach to:

> **Data validation and quality assurance**

A visual summary of the data-quality analysis is included in:

```text
outputs/
└── data_quality.png
```

---

# 13. Formula Analysis

The Formula Analysis sheet demonstrates Excel's analytical and business-logic capabilities.

The project deliberately uses formulas to solve practical business questions rather than adding formulas simply to demonstrate Excel functions.

## XLOOKUP

Used where structured reference tables require related information to be retrieved dynamically.

## SUMIFS

Used for conditional aggregation such as:

* Sales by period
* Profit by category
* Sales by weekday
* Category-level totals

## AVERAGEIFS

Used for conditional averages such as:

* Average daily sales
* Average profit
* Weekday performance
* Period-level performance

## IF / IFS

Used for business classification logic, including profitability classification.

For example:

```text
Net Profit > 0
      ↓
  Profitable

Net Profit <= 0
      ↓
    Loss
```

## Variance / Comparison Logic

The analytical framework also supports comparisons between actual performance and reference values such as:

* Average sales
* Average profit
* Expected performance
* Reference-period performance

The purpose of the formula layer is to demonstrate that Excel can function as a business logic and analytical tool, not merely as a data-entry application.

A visual example is included in:

```text
outputs/
└── formula_analysis.png
```

---

# 14. PivotTable Analysis

PivotTables provide the primary aggregation layer for the business analysis.

The PivotTables summarize the historical dataset across multiple dimensions.

Key analyses include:

## Monthly Profitability

| Month     |   Sales | Gross Profit | Net Profit | Net Margin |
| --------- | ------: | -----------: | ---------: | ---------: |
| January   | 368,140 |   123,077.29 |  46,377.29 |     12.60% |
| February  | 272,495 |    89,891.16 |  29,691.16 |     10.90% |
| March     | 301,720 |    93,414.00 |  22,680.67 |      7.52% |
| April     | 287,200 |    96,993.56 |  27,493.56 |      9.57% |
| May       | 409,160 |   126,438.96 |  54,622.29 |     13.35% |
| June      | 369,535 |   100,944.38 |  38,394.38 |     10.39% |
| July      | 370,380 |   121,542.18 |  65,942.18 |     17.80% |
| August    | 552,920 |   172,557.64 | 103,240.97 |     18.67% |
| September | 540,310 |   162,105.18 | 101,905.18 |     18.86% |
| October   | 495,990 |   129,914.76 |  63,264.76 |     12.76% |
| November  | 398,215 |    90,298.08 |  25,798.08 |      6.48% |
| December  | 357,470 |    72,239.81 |   5,589.81 |      1.56% |

A visual summary of the PivotTable analysis is included in:

```text
outputs/
└── pivot_analysis.png
```

---

# 15. Business Insights

The Business Insights sheet converts analytical outputs into management-level conclusions.

The analysis focuses on:

1. Executive profitability
2. Monthly profitability
3. Weekday profitability
4. Profitability status

A visual representation is included in:

```text
outputs/
└── business_insights.png
```

---

# 16. Executive KPIs

Across the complete 381 operating days, the restaurant generated:

| KPI                  |           Result |
| -------------------- | ---------------: |
| Total Operating Days |              381 |
| Total Sales          |    PKR 5,137,235 |
| Total Gross Profit   | PKR 1,494,351.27 |
| Total Net Profit     |   PKR 636,134.60 |
| Gross Profit Margin  |           29.09% |
| Net Profit Margin    |           12.38% |
| Profitable Days      |              300 |
| Loss Days            |               81 |
| Profitability Rate   |           78.74% |

These KPIs form the executive summary of the project.

---

# 17. Monthly Profitability Analysis

Monthly analysis reveals significant variation in profitability throughout 2023.

## Strongest Months

### August

* Sales: **PKR 552,920**
* Gross Profit: **PKR 172,557.64**
* Net Profit: **PKR 103,240.97**
* Net Margin: **18.67%**

### September

* Sales: **PKR 540,310**
* Gross Profit: **PKR 162,105.18**
* Net Profit: **PKR 101,905.18**
* Net Margin: **18.86%**

August and September were therefore the strongest profitability period in the 2023 operating data.

---

# 18. December Profitability

December 2023 requires particular attention.

The restaurant generated:

* Sales: **PKR 357,470**
* Gross Profit: **PKR 72,239.81**
* Net Profit: **PKR 5,589.81**
* Net Margin: **1.56%**

The key issue is that relatively substantial sales did not translate into comparable net profitability.

This makes December an important period for further operational investigation.

---

# 19. Weekday Profitability

The analysis also examined average daily performance by weekday.

| Day       |     Avg Sales | Avg Gross Profit | Avg Net Profit |
| --------- | ------------: | ---------------: | -------------: |
| Sunday    | PKR 14,049.07 |     PKR 4,007.41 |   PKR 1,764.51 |
| Monday    | PKR 13,009.45 |     PKR 3,564.78 |   PKR 1,320.54 |
| Tuesday   | PKR 12,551.09 |     PKR 3,393.54 |   PKR 1,127.48 |
| Wednesday | PKR 13,148.18 |     PKR 4,017.04 |   PKR 1,750.98 |
| Thursday  | PKR 12,887.50 |     PKR 3,743.54 |   PKR 1,481.50 |
| Friday    | PKR 14,479.73 |     PKR 4,479.76 |   PKR 2,235.22 |
| Saturday  | PKR 14,288.58 |     PKR 4,259.77 |   PKR 2,018.26 |

## Strongest Weekday

**Friday**

Friday had:

* Highest average sales: **PKR 14,479.73**
* Highest average gross profit: **PKR 4,479.76**
* Highest average net profit: **PKR 2,235.22**

## Weakest Weekday

**Tuesday**

Tuesday had:

* Lowest average sales: **PKR 12,551.09**
* Lowest average gross profit: **PKR 3,393.54**
* Lowest average net profit: **PKR 1,127.48**

---

# 20. Profitability Status

The business was profitable on most operating days.

| Profit Status |    Days |             Sales |         Net Profit |
| ------------- | ------: | ----------------: | -----------------: |
| Profitable    |     300 |     PKR 4,440,010 |     PKR 723,447.47 |
| Loss          |      81 |       PKR 697,225 |     -PKR 87,312.87 |
| **Total**     | **381** | **PKR 5,137,235** | **PKR 636,134.60** |

The business generated positive net profit on:

**300 of 381 operating days**

which represents a:

**78.74% profitability rate.**

The 81 loss-making days collectively generated:

**PKR 87,312.87 in negative net profit.**

This provides a more meaningful view of consistency than annual profit alone.

---

# 21. Executive Dashboard

The final Executive Dashboard is designed as the primary visual interface for management.

The dashboard contains:

## Executive KPI Cards

* Total Sales
* Gross Profit
* Net Profit
* Net Margin
* Profitable Days
* Profitability Rate

## Monthly Net Profit — 2023

A column chart displaying monthly net profit from January through December 2023.

The visualization highlights:

* Strong performance in August
* Strong performance in September
* Significant deterioration in December

## Average Net Profit by Weekday

A weekday performance visualization showing average net profit across Sunday through Saturday.

This makes Friday's stronger performance and Tuesday's weaker performance immediately visible.

## Profitability Status

A summary of:

* Profitable days
* Loss days
* Sales generated on profitable days
* Sales generated on loss days
* Net profit contribution

A screenshot of the final dashboard is included in:

```text
outputs/
└── dashboard.png
```

---

# 22. Key Business Findings

## Finding 1 — Overall profitability was positive

The restaurant generated approximately:

**PKR 636K net profit**

from:

**PKR 5.14M in sales**

resulting in a:

**12.38% net profit margin.**

---

## Finding 2 — Most operating days were profitable

The restaurant was profitable on:

**300 of 381 operating days**

or:

**78.74% of operating days.**

However, 81 days generated losses, showing that profitability consistency can still be improved.

---

## Finding 3 — August and September were the strongest months

August generated:

**PKR 103,240.97 net profit**

while September generated:

**PKR 101,905.18 net profit.**

These were the two strongest monthly net-profit results in 2023.

---

## Finding 4 — December profitability deteriorated significantly

December generated:

**PKR 357,470 in sales**

but only:

**PKR 5,589.81 in net profit**

for a:

**1.56% net margin.**

This indicates that sales volume alone did not guarantee strong profitability.

---

## Finding 5 — Friday was the strongest weekday

Friday produced the highest average:

* Sales
* Gross profit
* Net profit

with average net profit of approximately:

**PKR 2,235 per operating day.**

---

## Finding 6 — Tuesday was the weakest weekday

Tuesday produced the lowest average:

* Sales
* Gross profit
* Net profit

with average net profit of approximately:

**PKR 1,127 per operating day.**

---

# 23. Data Quality & Validation

Data quality was treated as an explicit component of the project rather than assuming that operational data was automatically reliable.

The validation process included manual sampling and cross-checking of analytical outputs against source records.

The project investigated issues such as:

* Duplicate dates
* Duplicate or misplaced source files
* Missing or inconsistent records
* Calculation mismatches
* Unusual product-level results
* Profitability anomalies

The project used a **sampling-based QA approach** to validate the Power Query and analytical results against selected source records.

This helped establish confidence that the transformed dataset and downstream analyses were consistent with the underlying operational records.

---

# 24. Inventory Analysis — Final Scope Decision

Inventory analysis was considered during the original project roadmap.

However, it was intentionally **not included as a separate final analytical module**.

The reason is that the final project is focused on building a coherent **restaurant business performance analytics system**, with profitability and business performance as the primary analytical themes.

Rather than adding an incomplete inventory module simply to increase the number of features, the final project prioritizes:

* Data preparation
* Data quality
* Formula analysis
* Profitability analysis
* PivotTables
* Business insights
* Executive reporting

The original inventory and consumption methodology remains documented in:

```text
documentation/
└── Original_System_Documentation.md
```

---

# 25. Python Validation — Final Scope Decision

Python was considered as a separate validation stage during the broader project roadmap.

However, the final version of this project intentionally does not depend on Python for its analytical workflow.

The historical Excel data was subjected to manual sampling-based QA, while the primary objective of this project is to demonstrate **Excel business analytics capability**.

Therefore:

> **Excel is intentionally the star of this project.**

Python may be used as a supporting analytical or validation tool in other projects, but it is not required for the final Taj Bites Excel workflow.

---

# 26. Tools & Technologies

## Microsoft Excel

The primary analytical platform.

Used for:

* Data analysis
* Formula calculations
* PivotTables
* PivotCharts
* Dashboard development
* Business reporting
* KPI development
* Business insights

## Power Query

Used as the data ingestion and transformation layer.

Key capabilities demonstrated:

* Folder-based data ingestion
* Combining multiple workbooks
* Workbook-level extraction
* Data transformation
* Column standardization
* Data-type handling
* Business-rule logic
* Data cleaning
* Refreshable analytical pipeline

## Excel Formulas

Key analytical functions include:

* XLOOKUP
* SUMIFS
* AVERAGEIFS
* IF
* IFS
* Conditional logic
* Calculated metrics
* Margin calculations
* Variance/comparison calculations

## PivotTables

Used for:

* Monthly analysis
* Weekday analysis
* Profitability analysis
* Aggregation
* Business performance summaries

## PivotCharts

Used to visualize:

* Monthly net profit
* Weekday net profit
* Business performance patterns

---

# 27. Skills Demonstrated

This project demonstrates practical experience with:

## Data Preparation

* Power Query
* Folder-based ingestion
* Combining workbooks
* Data transformation
* Data cleaning
* Data standardization
* Data validation

## Excel Analytics

* XLOOKUP
* SUMIFS
* AVERAGEIFS
* IF / IFS
* Conditional logic
* Calculated metrics
* Margin calculations
* Variance analysis

## Business Intelligence

* KPI development
* Profitability analysis
* Time-series analysis
* Weekday performance analysis
* Business performance segmentation
* Executive reporting

## Excel Visualization

* PivotTables
* PivotCharts
* Dashboard design
* KPI cards
* Executive summaries
* Business insights

## Data Quality

* Sampling-based QA
* Source-to-output validation
* Anomaly identification
* Calculation checks
* Duplicate detection

---

# 28. Repository Structure

The current project repository is organized as:

```text
Taj-Bites-Analytic/
│
├── README.md
│
├── documentation/
│   └── Original_System_Documentation.md
│
├── excel_dashboard/
│   └── Taj_Bites_Business_Analytics.xlsx
│
├── outputs/
│   ├── business_insights.png
│   ├── dashboard.png
│   ├── data_quality.png
│   ├── formula_analysis.png
│   ├── pivot_analysis.png
│   ├── power_query.png
│   └── Power Query Editor with Applied Steps.png
│
└── raw-data/
    ├── Dec 2022/
    ├── Jan 2023/
    ├── ...
    └── Dec 2023/
```

The `raw-data` directory contains the original daily operational workbooks.

The `excel_dashboard` directory contains the final Excel analytical workbook.

The `documentation` directory contains documentation of the original restaurant tracking system.

The `outputs` directory contains visual evidence of the analytical work and final dashboard.

---

# 29. Analytical Flow

The complete analytical process can be summarized as:

```text
                 SOURCE DATA

                     │
                     ▼

           387 Daily Excel Workbooks

                     │
                     ▼

                POWER QUERY

                     │
                     ▼

           Cleaning & Transformation

                     │
                     ▼

             Historical Dataset

                     │
          ┌──────────┼──────────┐
          ▼          ▼          ▼
    Data Quality  Formulas  Data Analysis
          │          │          │
          └──────────┼──────────┘
                     ▼
                PivotTables
                     │
                     ▼
              Business Insights
                     │
                     ▼
             Executive Dashboard
```

---

# 30. Business Impact

The project transforms a collection of operational Excel files into a structured business analytics solution.

Instead of requiring management to inspect individual daily workbooks, the final system provides a centralized view of:

* Revenue
* Gross profitability
* Net profitability
* Margins
* Operating-day performance
* Monthly trends
* Weekday performance
* Profitability consistency

This makes it possible to move from:

> **Raw operational records**

to:

> **Structured business information**

and finally to:

> **Actionable business insights.**

---

# 31. Example Management Questions Answered

The completed workbook can answer questions such as:

## Financial Performance

* How much did the restaurant sell?
* How much gross profit was generated?
* How much net profit was generated?
* What was the overall net margin?

## Time-Based Performance

* Which month generated the most net profit?
* Which month performed the worst?
* How did profitability change throughout 2023?

## Operating Performance

* How many days were profitable?
* How many days generated losses?
* What percentage of operating days were profitable?

## Weekday Performance

* Which weekday generated the highest average sales?
* Which weekday generated the highest average net profit?
* Which weekday performed weakest?

## Management Decision Support

* Was the business consistently profitable?
* Which periods require additional investigation?
* Where should management investigate declining margins?
* Which operating patterns appear associated with stronger profitability?

---

# 32. Main Business Story

The most important story from the analysis is not simply that the restaurant generated **PKR 636K in net profit**.

The deeper story is:

> Taj Bites generated **PKR 5.14 million in sales and PKR 636K in net profit across 381 operating days**, achieving profitability on **78.74% of operating days**. Performance varied considerably throughout the year, with August and September producing the strongest profitability while December experienced a substantial decline in net margin. Weekday analysis also revealed meaningful differences, with Friday generating the strongest average net profit and Tuesday the weakest.

This demonstrates how fragmented operational records can be transformed into a business performance narrative using Excel.

---

# 33. Why This Project Is Portfolio-Ready

This project demonstrates more than the ability to create spreadsheets.

It demonstrates a complete analytical workflow:

```text
Data Ingestion
      ↓
Data Transformation
      ↓
Data Quality
      ↓
Analytical Dataset
      ↓
Formula-Based Analysis
      ↓
PivotTable Analysis
      ↓
Business Interpretation
      ↓
Executive Visualization
```

The project also uses **real operational business data**, rather than relying exclusively on a generic public dataset.

This provides an opportunity to demonstrate how analytical tools can be applied to a real business environment where data may be fragmented, inconsistent, and originally designed for operations rather than analytics.

---

# 34. Portfolio Positioning

This project should be positioned as:

## Restaurant Business Performance Analytics

**Excel + Power Query**

Rather than:

> "I made an Excel dashboard."

A stronger description is:

> **"I transformed 387 daily operational Excel workbooks representing 381 operating days into a refreshable Excel business analytics system using Power Query, formula-based analysis, PivotTables, PivotCharts, data-quality validation, and an executive profitability dashboard."**

This emphasizes the complete analytical workflow rather than only the final visualization.

---

# 35. Project Outcome

The final solution provides a structured Excel-based analytics framework for historical restaurant performance.

The completed system includes:

* Refreshable Power Query data ingestion
* Structured historical analytical data
* Data dictionary
* Data-quality analysis
* Formula analysis
* PivotTable analysis
* Profitability analysis
* Business insights
* Executive dashboard
* Supporting documentation of the original operational system

The project demonstrates how Excel can function as a practical business intelligence platform when combined with disciplined data preparation, analytical modeling, validation, and business-focused interpretation.

---

# 36. Conclusion

The Taj Bites project began with fragmented daily operational records and was rebuilt as a structured Excel business analytics solution.

The final result demonstrates the journey from:

**Operational Data → Analytical Dataset → Business Analysis → Executive Decision Support**

The primary analytical conclusion is that the business was profitable overall, but profitability was not uniform across time or operating days.

The strongest performance occurred during August and September, while December showed a significant deterioration in net profitability. Friday emerged as the strongest weekday, while Tuesday was the weakest.

The project therefore demonstrates not only how to calculate business metrics, but also how to use Excel to identify, investigate, and communicate the operational patterns behind those metrics.

---

# Project Classification

**Project Type:** Business Analytics / Excel Analytics

**Industry:** Restaurant / Food Service

**Primary Tool:** Microsoft Excel

**Data Pipeline:** Power Query

**Analysis:** Excel Formulas + PivotTables

**Visualization:** PivotCharts + Executive Dashboard

**Reporting Period:** December 2022 – December 2023

**Source Workbooks:** 387

**Operating Days:** 381

**Total Sales:** PKR 5,137,235

**Total Gross Profit:** PKR 1,494,351.27

**Total Net Profit:** PKR 636,134.60

**Net Profit Margin:** 12.38%

**Profitability Rate:** 78.74%

---

# Author

**Ahmed Khalid**

Data Analyst | Excel | SQL | Python | Power BI

This project is part of my analytics portfolio and demonstrates practical application of Excel, Power Query, business analysis, data validation, and data visualization to real operational data.
