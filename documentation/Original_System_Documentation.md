# Taj Bites — Original Restaurant Tracking System

## 1. Purpose and Overview

Before the historical analytics project was developed, Taj Bites operated using a manually maintained Excel-based tracking system.

Each operating day was recorded in a separate Excel workbook. The system was designed to provide the restaurant with a daily view of:

* Inventory consumption
* Raw-material usage
* Product-level costs
* Packaging and operating-material costs
* Product/category sales
* Gross profit
* Employee costs
* Rent
* Utility and other bills
* Net profit

The system effectively functioned as a lightweight operational accounting and inventory-tracking system for a restaurant that did not have a dedicated POS or centralized business analytics platform.

The historical source directory contained **387 daily Excel workbooks** covering the available operating period from December 2022 through December 2023.

The original system was designed primarily for **daily operational use**, rather than historical business analysis. The later Excel analytics project therefore preserved the underlying business logic while transforming the historical records into an analytical dataset.

---

# 2. Daily Workbook Structure

Each operating day was maintained in a separate Excel workbook.

Files were named according to the operating date, for example:

```text
01 Apr 2023.xlsx
02 Apr 2023.xlsx
03 Apr 2023.xlsx
```

The workbook contained multiple product and operational sections.

Examples included:

* Fries
* Zinger Burger
* Zinger Roll
* Afghani Burger
* Fried Chicken
* Loaded Cheese Fries
* Cold Drinks
* Packaging/materials
* Other food and operating items

The workbook combined operational measurements with financial calculations.

The general structure was:

```text
Inventory / Material Measurements
            ↓
     Consumption Calculation
            ↓
       Cost Calculation
            ↓
      Product-Level Cost
            ↓
          Sales
            ↓
     Product-Level Profit
            ↓
      Daily Aggregation
            ↓
       Gross Profit
            ↓
      Fixed Operating Costs
            ↓
         Net Profit
```

---

# 3. Inventory Measurement System

The primary inventory mechanism was based on measuring the quantity of an item before and after the day's operations.

For measurable ingredients and materials, the workbook recorded values such as:

| Field          | Purpose                                           |
| -------------- | ------------------------------------------------- |
| Measure Before | Quantity available at the beginning of operations |
| Measure After  | Quantity remaining after operations               |
| Total Used     | Quantity consumed during the day                  |
| Price Per Unit | Cost assigned to one unit                         |
| Used Price     | Estimated cost of the quantity consumed           |

The fundamental consumption calculation was:

```text
Total Used = Measure Before - Measure After
```

### Example

If:

```text
Measure Before = 37.300
Measure After  = 30.185
```

Then:

```text
Total Used = 37.300 - 30.185
           = 7.115
```

This approach allowed the restaurant to estimate daily consumption without requiring every individual ingredient transaction to be recorded separately.

The ending quantity from one operating day could then become the starting quantity for the following day.

---

# 4. Daily Inventory Carry-Forward Process

The original system used a continuous inventory flow from one day to the next.

The basic process was:

```text
Day 1
Measure Before
      ↓
Daily Operations
      ↓
Measure After
      ↓
Day 2 Measure Before
      ↓
Daily Operations
      ↓
Day 2 Measure After
      ↓
Day 3 Measure Before
```

This meant that the previous day's closing measurement became the next day's opening measurement.

This was an important feature of the original system because it allowed consumption to be estimated from physical inventory measurements rather than relying exclusively on theoretical recipe quantities.

---

# 5. Cost Calculation

After the quantity consumed was determined, the workbook calculated the corresponding cost.

The general calculation was:

```text
Used Price = Total Used × Price Per Unit
```

### Example

If:

```text
Total Used      = 7.115
Price Per Unit  = PKR 50
```

Then:

```text
Used Price = 7.115 × 50
           = PKR 355.75
```

The costs of individual ingredients and materials were then aggregated within their respective product or category sections.

This allowed the system to determine the estimated direct cost associated with producing each product/category.

---

# 6. Product and Category Structure

The original workbook separated operational costs according to the products or categories they supported.

For example, the Fries section could include:

* Potatoes
* Cooking oil
* Seasonings
* Sauces
* Gas/cylinder allocation
* Packaging
* Other associated materials

A Zinger-related section could include:

* Chicken
* Flour/maida
* Sauces
* Seasonings
* Packaging
* Tissue
* Other associated materials

Other products followed the same general concept.

This structure allowed the restaurant to move beyond a single total-cost figure and estimate the cost and profitability of individual products or categories.

---

# 7. Sales Tracking

The daily workbook also recorded sales for products and categories.

Sales were then compared with the calculated costs to determine product/category profitability.

The basic relationship was:

```text
Profit = Sales - Cost
```

### Example

If:

```text
Total Cost = PKR 410.25
Total Sales = PKR 1,000
```

Then:

```text
Profit = 1,000 - 410.25
       = PKR 589.75
```

The daily workbook therefore provided a product/category-level view of revenue, cost, and profit.

---

# 8. Variable-Price Fries Logic

Fries required additional treatment because they were sold in different quantities or serving configurations.

The original workbook therefore incorporated information such as:

* Cost
* Selling price
* Portion/quantity information
* Packaging
* Associated materials

Rather than assuming that every fries transaction had one identical cost, the workbook used the relevant quantity and selling configuration to determine the associated economics.

This was important because fries represented a significant operational category and their cost structure differed from simpler count-based products.

The historical analytical model preserved this logic when extracting the relevant profitability information.

---

# 9. Cold Drinks Inventory

Cold drinks were tracked differently from ingredients measured by weight or volume.

Drinks were generally tracked using physical counts.

The workbook included fields such as:

* Count Before
* Count After
* Total Used
* Price per pack
* Price per piece
* Used Price
* Sale Price
* Sales quantity/value

The basic consumption calculation remained:

```text
Total Used = Count Before - Count After
```

The resulting quantity was then used to estimate the cost associated with the drinks consumed or sold.

This allowed different drink products and sizes to be tracked separately.

---

# 10. Packaging and Operating Materials

The original system also accounted for materials required to operate and fulfill customer orders.

Examples included:

* Parcels
* Burger packaging
* Tissues
* Paper
* Card covers
* Sticks
* Other packaging materials

These items contributed to the operational cost of the restaurant and could therefore affect product-level and daily profitability.

This is an important characteristic of the original system because the cost model was not limited to major food ingredients.

---

# 11. Fixed Operating Costs

In addition to variable product and material costs, the system incorporated recurring operating expenses.

Major fixed-cost categories included:

* Employee costs
* Rent
* Bills/utilities

Where appropriate, monthly expenses were converted into daily costs.

The general approach was:

```text
Daily Fixed Cost = Monthly Cost / Number of Days
```

For example:

```text
Monthly Employee Cost / Operating Days
```

The resulting daily amounts were incorporated into the restaurant's daily profitability calculation.

---

# 12. Daily Operating Cost

The restaurant's total daily cost therefore consisted of multiple components.

Conceptually:

```text
Daily Operating Cost
=
Variable/Product Costs
+
Packaging/Material Costs
+
Other Variable Costs
+
Employee Cost
+
Rent
+
Bills
```

This distinction was important because product costs alone did not represent the full cost of operating the restaurant.

---

# 13. Gross Profit

Gross profit was calculated before subtracting the restaurant's fixed operating expenses.

The general relationship was:

```text
Gross Profit = Total Sales - Variable/Product Costs
```

Gross profit therefore represented the amount remaining from sales after accounting for the direct costs associated with the products/materials sold.

This metric was later used in the historical analytics project to evaluate overall business performance.

---

# 14. Net Profit

Net profit incorporated the additional fixed operating costs.

The general relationship was:

```text
Net Profit = Gross Profit - Daily Fixed Costs
```

or equivalently:

```text
Net Profit
=
Total Sales
-
Variable Costs
-
Fixed Operating Costs
```

Net profit therefore provided a more complete representation of the restaurant's daily profitability.

A day with positive gross profit could still produce a net loss if the remaining gross profit was insufficient to cover fixed operating expenses.

---

# 15. Daily Profitability Logic

The original system allowed each operating day to be classified according to its resulting net profit.

Conceptually:

```text
IF Net Profit > 0
    → Profitable
ELSE
    → Loss
```

This daily classification later became important in the historical analytics project.

It enabled analysis of:

* Number of profitable days
* Number of loss days
* Profitability rate
* Sales generated on profitable days
* Net profit generated on profitable days
* Losses generated on loss days

---

# 16. Complete Daily Workflow

The original restaurant tracking process can be summarized as follows:

### Step 1 — Open the previous day's workbook

The previous day's workbook contained the latest closing inventory measurements.

### Step 2 — Carry forward inventory

The previous day's ending measurements became the new day's starting measurements.

```text
Previous Day Measure After
          ↓
Current Day Measure Before
```

### Step 3 — Record new ending measurements

At the end of operations, the remaining inventory was measured and entered into the workbook.

### Step 4 — Calculate consumption

The system calculated the amount consumed:

```text
Total Used = Measure Before - Measure After
```

### Step 5 — Calculate material cost

The consumed quantity was multiplied by its applicable unit cost:

```text
Used Price = Total Used × Price Per Unit
```

### Step 6 — Aggregate product/category costs

Ingredient, packaging, and associated material costs were combined within their relevant product/category sections.

### Step 7 — Record sales

Daily sales were entered for the relevant products/categories.

### Step 8 — Calculate product/category profit

The workbook compared sales against the associated costs:

```text
Profit = Sales - Cost
```

### Step 9 — Calculate daily fixed costs

Employee costs, rent, bills, and other applicable fixed operating costs were allocated to the day.

### Step 10 — Calculate gross profit

```text
Gross Profit = Sales - Variable/Product Costs
```

### Step 11 — Calculate net profit

```text
Net Profit = Gross Profit - Daily Fixed Costs
```

### Step 12 — Save the daily workbook

The completed workbook was saved using the operating date and became part of the historical record.

The following day then used the previous day's ending inventory as its starting point.

---

# 17. Original System Architecture

The complete original process can therefore be represented as:

```text
                    DAILY OPERATIONS
                           │
                           ▼
                Physical Inventory
                Measurements
                           │
                ┌──────────┴──────────┐
                ▼                     ▼
          Measure Before        Measure After
                │                     │
                └──────────┬──────────┘
                           ▼
                    Quantity Used
                           │
                           ▼
                  Unit Cost Applied
                           │
                           ▼
                    Product Costs
                           │
                           ├───────────────┐
                           │               │
                           ▼               ▼
                        Sales         Packaging/
                           │            Materials
                           │               │
                           └───────┬───────┘
                                   ▼
                            Gross Profit
                                   │
                                   ▼
                         Fixed Operating Costs
                    ┌──────────┬──────────┬──────────┐
                    ▼          ▼          ▼          ▼
                Employees     Rent      Bills      Other
                    │          │          │          │
                    └──────────┴──────────┴──────────┘
                                   │
                                   ▼
                              Net Profit
                                   │
                                   ▼
                         Daily Profitability
                                   │
                                   ▼
                         Historical Record
```

---

# 18. Strengths of the Original System

Despite being manually maintained, the original system had several useful characteristics.

### 18.1 Operationally grounded

The system was based on actual daily restaurant operations rather than a synthetic dataset.

### 18.2 Inventory-driven

Physical before/after measurements provided a mechanism for estimating actual material consumption.

### 18.3 Product-level costing

Costs were organized according to products/categories rather than being recorded only as one total expense.

### 18.4 Included fixed operating costs

The system went beyond food costs by incorporating employee costs, rent, and bills.

### 18.5 Daily profitability

The system ultimately produced a daily net-profit figure that could be used to assess whether the restaurant was profitable on a given operating day.

---

# 19. Limitations of the Original System

The system was designed for daily operations, not large-scale historical analysis.

Its main limitations included:

* Hundreds of separate Excel workbooks
* Manual data entry
* Repetitive workbook structure
* No centralized historical analytical table
* Limited historical reporting
* Manual aggregation across dates
* Potential for inconsistent records
* Difficulties identifying duplicates or missing records
* Limited interactive analysis
* No centralized dashboard
* No automated historical reporting layer

These limitations created the need for the next stage of the project.

---

# 20. Why the Analytics Project Was Built

The original system successfully captured the restaurant's daily operations, but the historical information was fragmented across hundreds of workbooks.

The analytics project therefore transformed the existing operational records into a centralized business analytics solution.

The transformation was:

```text
Original Daily Workbooks
        ↓
387 Historical Excel Files
        ↓
Power Query
        ↓
Centralized Analytical Dataset
        ↓
Data Quality Checks
        ↓
Excel Formula Analysis
        ↓
PivotTables / PivotCharts
        ↓
Business Insights
        ↓
Executive Dashboard
```

The objective was **not to replace the original business logic**.

Instead, the objective was to preserve the underlying operational logic while making the historical data easier to analyze, validate, summarize, and communicate.

---

# 21. Transition to the New Analytics System

The original Taj Bites workbook system is therefore the foundation of the entire project.

The subsequent Excel analytics solution builds on this foundation by introducing:

* Power Query
* Centralized historical data
* Data cleaning
* Data-quality validation
* Excel analytical formulas
* Conditional logic
* PivotTables
* PivotCharts
* KPI analysis
* Profitability analysis
* Business insights
* Executive dashboard

This creates a progression from:

**Manual daily operational tracking**

to:

**Structured historical business analytics.**

The final solution demonstrates how an existing real-world Excel process can be transformed into a professional analytics system without losing the operational context behind the data.
