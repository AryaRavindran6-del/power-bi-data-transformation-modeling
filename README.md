# Power-BI-data-transformation-modeling
E-commerce sales analysis using Power BI, Power Query, data transformation, data merging, aggregation, and relational data modeling.

# Power BI – Data Transformation & Data Modeling

## Overview

This project is part of the **Program in AI-Driven Data Analytics** course from Entri App. The assignment focuses on performing **E-Commerce Sales Analysis using Power BI**, with emphasis on data transformation, data cleaning, data merging, aggregation, and data modeling.

The project uses three datasets:

- **List of Orders**
- **Order Details**
- **Sales Target**

The data was imported into Power BI and transformed using **Power Query Editor** before establishing relationships and preparing the data for analysis.

## Objectives

- Import and transform multiple CSV datasets using Power Query.
- Clean and standardize the data.
- Create calculated and conditional columns.
- Merge order-related datasets using `Order ID`.
- Handle missing and duplicate data.
- Sort and filter data for analysis.
- Perform grouping and aggregation.
- Build relationships between tables using `Order ID` and `Category`.

## Data Transformation

The following transformations were performed:

1. Restricted **List of Orders** to the first 500 rows.
2. Converted **Order Date** to the `Date` data type.
3. Converted **Amount** and **Target** to `Fixed Decimal Number`.
4. Applied **Proper Case** formatting to `CustomerName`.
5. Created a **Location** column in the format `City, State`.
6. Created a **Profit Margin** custom column.
7. Created a **Profit Status** conditional column.
8. Merged **List of Orders** and **Order Details** into an `Orders Data` table using `Order ID`.

## Formulas / Expressions Used

### Profit Margin

The custom column was calculated as:

```text
[Profit] / [Amount]
```

This calculates the profit generated relative to the order amount.

### Profit Status

A conditional column was created using the following logic:

```text
If Profit < 0 → "Loss"
If Profit = 0 → "Break-Even"
If Profit > 0 → "Profit"
```

### Location

The `City` and `State` fields were merged using a comma and space separator:

```text
City, State
```

## Data Quality

The datasets were checked for missing and duplicate records.

- Missing values were checked using Power Query column filters.
- Duplicate rows were checked.
- Repeated `Order ID` values in **Order Details** were retained because they represent multiple detail records belonging to the same order rather than duplicate records.

## Sorting & Filtering

The `Orders Data` table was analyzed using:

- **Order Date – Descending:** to identify recent orders.
- **State – Tamil Nadu:** to perform regional analysis.

## Grouping & Aggregation

Power Query **Group By** was used to perform:

- Count of each `Order ID`
- Average Profit by `Category`
- Total Amount by `Sub-Category`
- Total Target Amount by `Month of Order Date`

## Data Modeling

The following relationships were established:

| Table          | Related Table | Key        |
| -------------- | ------------- | ---------- |
| List of Orders | Order Details | `Order ID` |
| Order Details  | Sales Target  | `Category` |

The `Order ID` relationship connects order-level information with order-detail information, while the `Category` relationship connects order details with sales target information.

## Tools Used

- **Microsoft Power BI**
- **Power Query Editor**
- **Power BI Model View**
- **CSV datasets**

## Key Learning Outcomes

Through this assignment, I practiced:

- Data import and transformation using Power Query
- Data type management
- Data cleaning and validation
- Custom and conditional columns
- Query merging
- Sorting and filtering
- Grouping and aggregation
- Relationship creation and data modeling
- Preparing structured data for business analysis

## Project Files

- `Power BI Assignment- Data Transformation & Data Modeling.pbix` – Completed Power BI project
- `List of Orders.csv` – Order-level data
- `Order Details.csv` – Order detail data
- `Sales target.csv` – Sales target data

## Conclusion

This project demonstrates a complete Power BI data preparation workflow, starting from raw CSV files and progressing through **data transformation, cleaning, merging, aggregation, and relational modeling** to prepare the dataset for e-commerce sales analysis.
