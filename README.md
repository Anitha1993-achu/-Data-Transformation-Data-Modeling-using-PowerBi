# Power BI Project – Data Import, Transformation and Data Modeling

## 1. Project Overview

This project focuses on importing, cleaning, transforming, merging, and modeling three datasets using **Microsoft Power BI and Power Query Editor**.

The main objective is to prepare clean and structured data for accurate analysis and reporting.

## 2. Dataset Description

Three datasets are used in this project.

### A. List of Orders
Contains customer and order information.

**Columns:**
- Order ID
- Order Date
- Customer Name
- City
- State
- Category
- Amount
- Profit

### B. Order Details
Contains detailed product and order information.

**Columns:**
- Order ID
- Category
- Sub-Category
- Quantity
- Amount
- Profit

### C. Sales Target
Contains monthly sales targets for each category.

**Columns:**
- Category
- Month of Order Date
- Target

## 3. Data Import and Transformation

All three CSV files were imported into Power BI using the **Get Data → Text/CSV** option.

The Transform Data option was used to open the Power Query Editor.

## 4. Row Limiting and Data Types

The following transformations were performed:

- Restricted the List of Orders table to the first 500 rows.
- Changed Order Date to the Date data type.
- Changed Amount to Fixed Decimal Number.
- Changed Target to Fixed Decimal Number.

**Purpose:** To maintain correct data formats and improve data accuracy.

## 5. Text Formatting

The Customer Name column was transformed using Proper Case.

**Purpose:** To maintain consistent capitalization of customer names.

## 6. Column Creation

Two new columns were created in Power Query Editor.

### A. Location

City and State columns were merged to create a new column named Location.

**Format:**

`City, State`

Example: Ahmedabad  Gujarat
### B. Profit Margin

A custom column named Profit Margin was created.

**Formula:**

`Profit Margin = (Profit / Amount) * 100`

**Purpose:** To calculate the percentage of profit earned from sales.

Note: If Amount is zero or null, the calculation should return null to avoid errors.

## 7. Conditional Column – Profit Status

A conditional column named Profit Status was created based on the Profit column.

| Condition | Profit Status |
|---|---|
| Profit < 0 | Loss |
| Profit = 0 | Break-Even |
| Profit > 0 | Profit |

**Purpose:** To identify whether an order generates a profit, loss, or break-even result.

## 8. Merging Data (Joins)

The List of Orders and Order Details tables were merged using the Order ID column.

**Steps:**
1. Select the List of Orders table.
2. Choose Home → New Merge Queries.
3. Select the Order Details table.
4. Select Order ID in both tables.
5. Choose Left Outer Join.
6. Expand the required columns.
7. Name the merged output table as Orders Data.

**Purpose:** To combine customer order information with detailed product information.

## 9. Handling Missing Data and Duplicate Data

### A. Missing Values

Missing values were checked across all three tables.

The following strategies were considered:
The three tables are:
1. List of Orders Table
2. Order Details Table
3. Sales Target Table
1. Select the List of Orders Table in Power Query Editor.
2. Go to the View tab.
3. Enable Column Quality.
4. Enable Column Distribution.
5. Enable Column Profile.
6. Check each column for Valid, Error and Empty values.
7. 7. Above the same method using Remaining two Tables (Order Details and
Sales Target).
8. Finally, no Missing Values finded in the three (list of order, order details, sales Target)
Datasets

### B. Duplicate Data

Duplicate rows were identified in all three tables.
1. Select the List of Order table.
2. Select all columns using Ctrl + A (when the table grid is active).
3. Go to the Home tab. Click Remove Rows.
4. Select Remove Duplicates.
5. Above the same method using Remaining one Tables (Order Details).
6. Finally, Duplicate Values are cleared in the Datasets.
   
**Handling strategy:**
- Remove completely identical duplicate rows.
- Check duplicate Order IDs carefully before removing records.

**Purpose:** To avoid incorrect records and maintain data accuracy.

## 10. Sorting and Filtering Data

The Orders Data table was sorted using the Order Date column in descending order.

**Descending Order:** Latest date to oldest date.

A State filter was also applied to analyze orders from Tamil Nadu.

**Purpose:** To analyze recent orders and focus on a specific geographical region.

## 11. Grouping and Aggregating Data

### A. Order Details – Duplicate Table

The Order Details table was duplicated, and the following aggregations were performed:

1. **Count of Order ID:** Counts the order ID records in each group.
2. **Average Profit by Category:** Calculates the average profit for each category.
3. **Total Amount by Sub-Category:** Calculates the total sales amount for each sub-category.

### B. Sales Target – Duplicate Table

The Sales Target table was duplicated.

The total Target was calculated by grouping the Month of Order Date column.

**Purpose:** To analyze monthly sales targets.

## 12. Data Modeling and Relationships

Relationships were established between the tables using Manage Relationships.

### Relationship 1: List of Orders and Order Details

- First Table: List of Orders
- Second Table: Order Details
- Common Column: Order ID

Relationship: One-to-Many (1:*) when Order ID is unique in List of Orders.

### Relationship 2: Order Details and Sales Target

- First Table: Order Details
- Second Table: Sales Target
- Common Column: Category

Relationship: Usually Many-to-Many if Category repeats in both tables.

For a better data model, a separate Category dimension table can be created to connect both tables using One-to-Many relationships.

**Purpose:** To establish proper connections between datasets and support accurate reporting.

## 13. Final Outcome

The project successfully demonstrates the following Power BI concepts:

- Importing multiple CSV datasets.
- Data cleaning and transformation.
- Changing column data types.
- Proper case text formatting.
- Creating custom and conditional columns.
- Merging tables using Order ID.
- Handling missing values and duplicates.
- Sorting and filtering records.
- Grouping and aggregating data.
- Creating relationships using Manage Relationships.

## 14. Conclusion

This project provides practical experience in data preparation and data modeling using Power BI.

The three datasets were imported, cleaned, transformed, and connected to prepare structured data for further analysis.

These steps help improve data quality, ensure consistency, and create a reliable foundation for building interactive Power BI reports and dashboards.
