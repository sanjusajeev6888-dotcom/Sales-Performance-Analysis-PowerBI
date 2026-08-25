# 📊 Sales Performance Analysis – Power BI

## 📌 Project Overview

This project presents an interactive **Sales Performance Analysis Dashboard** built using **Microsoft Power BI**.

The dashboard analyzes sales data across products, categories, salespersons, customers, regions, and time periods to identify important business trends, measure performance, and support data-driven decision-making.

The project demonstrates the complete Power BI workflow, including:

- Data loading
- Data cleaning and transformation
- Power Query
- Data modeling
- Relationship creation
- Date table creation
- DAX calculations
- KPI development
- Interactive dashboards
- Slicers and filters
- Sales analysis
- Customer analysis
- Product analysis
- Category analysis
- Salesperson analysis
- Regional analysis
- Time-based analysis
- Business insights
- Data visualization


---

# 🎯 Business Objectives

The main objectives of this project are:

- Analyze overall sales performance
- Track total sales and total orders
- Analyze total sales quantity
- Analyze customer purchasing behavior
- Identify top-performing products
- Identify low-performing products
- Compare category-wise sales performance
- Evaluate salesperson performance
- Analyze regional sales performance
- Analyze monthly sales trends
- Analyze sales growth
- Calculate average order value
- Analyze salesperson contribution to total sales
- Identify important business trends
- Provide an interactive dashboard for business decision-making


---

# 🗂️ Dataset

The project uses the same relational sales dataset used for the SQL and Excel analysis projects.

The dataset consists of the following tables:

### 1. Customers

Contains customer-related information.

Important fields include:

- CustomerID
- CustomerName
- Region
- Other customer attributes


### 2. Products

Contains product information.

Important fields include:

- ProductID
- ProductName
- CategoryID
- UnitPrice


### 3. Categories

Contains product category information.

Important fields include:

- CategoryID
- CategoryName


### 4. Salespersons

Contains salesperson information.

Important fields include:

- SalespersonID
- SalespersonName
- Region


### 5. Orders

Contains transactional sales information.

Important fields include:

- OrderID
- OrderDate
- CustomerID
- ProductID
- SalespersonID
- Quantity
- UnitPrice
- SalesAmount


### 6. Date Table

A dedicated Date Table was created inside Power BI using DAX for accurate time-based analysis.

The Date Table contains fields such as:

- Date
- Year
- Month
- Month Number
- Month-Year
- Quarter
- Day
- Day Name

The Date Table is connected to the Orders table through the `OrderDate` field.


---

# 🏗️ Data Model

The Power BI data model consists of:

- Customers
- Products
- Categories
- Salespersons
- Orders
- Date Table

The tables are connected using their relevant primary and foreign key fields.

### Main Relationships

```text
Customers
    │
    │ CustomerID
    ▼
Orders ◄──────── Date Table
    │                 │
    │                 │ Date
    │
    ├──────────────► Products
    │                    │
    │                    │ CategoryID
    │                    ▼
    │                Categories
    │
    └──────────────► Salespersons
```
# 📅 Date Table

A dedicated Date Table was created in Power BI using DAX to support accurate time-based analysis.

The Date Table contains the following columns:

- Date
- Year
- Month
- Month Number
- Month-Year
- Quarter
- Day
- Day Name

### Date Table DAX

```DAX
DateTable =
ADDCOLUMNS(
    CALENDAR(
        MIN(Orders[OrderDate]),
        MAX(Orders[OrderDate])
    ),
    "Year", YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month", FORMAT([Date], "MMMM"),
    "Month-Year", FORMAT([Date], "MMM YYYY"),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Day", DAY([Date]),
    "Day Name", FORMAT([Date], "dddd")
)
```
# 🧹 Data Preparation & Power Query

The data was prepared and transformed using **Power Query** before creating the Power BI dashboard.

The main data preparation steps included:

- Imported the Customers table
- Imported the Products table
- Imported the Categories table
- Imported the Salespersons table
- Imported the Orders table
- Checked column names
- Checked and corrected data types
- Verified date fields
- Checked numeric fields such as Quantity, UnitPrice, and SalesAmount
- Checked for missing or blank values
- Checked for duplicate records
- Prepared the tables for data modeling
- Verified the relationships between the tables

The `OrderDate` column was prepared as a Date field for time-based analysis.

The cleaned and prepared data was then used to create the Power BI data model, DAX measures, KPIs, and interactive dashboard visuals.

# 🧮 DAX Measures

DAX measures were created in Power BI to calculate the main business KPIs and support the dashboard analysis.

### Total Sales

```DAX
Total Sales =
SUM(Orders[SalesAmount])
```

### Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(Orders[OrderID])
```

### Total Quantity

```DAX
Total Quantity =
SUM(Orders[Quantity])
```

### Total Customers

```DAX
Total Customers =
DISTINCTCOUNT(Orders[CustomerID])
```

### Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders],
    0
)
```

These measures were used to create KPI cards and support the dashboard's sales, customer, order, quantity, and average order value analysis.
# 📊 KPI Cards

KPI cards were created in Power BI to provide a quick overview of the main sales performance indicators.

The dashboard includes the following KPIs:

- **Total Sales**
- **Total Orders**
- **Total Customers**
- **Total Quantity**
- **Average Order Value**

The KPI cards provide a quick summary of business performance and update dynamically when users interact with the available slicers and filters.

# 📊 Dashboard Pages

The Power BI dashboard is organized into multiple pages, with each page focusing on a specific area of sales performance analysis.

## 1️⃣ Sales Performance Overview

The overview page provides a high-level summary of the overall sales performance.

It includes:

- Total Sales
- Total Orders
- Total Customers
- Average Order Value
- Sales trends
- Category performance
- Interactive filters and slicers

This page provides a quick view of the overall business performance.

---

## 2️⃣ Product Analysis

The Product Analysis page focuses on product-level performance.

The analysis includes:

- Product-wise sales
- Top-performing products
- Lowest-performing products
- Product quantity
- Product performance comparison

This helps identify products that contribute significantly to overall sales.

---

## 3️⃣ Category Analysis

The Category Analysis page evaluates sales performance across different product categories.

The analysis includes:

- Category-wise sales
- Category comparison
- Category performance
- Category contribution

This helps identify high-performing and low-performing categories.

---

## 4️⃣ Salesperson Analysis

The Salesperson Analysis page evaluates the performance of individual salespersons.

The analysis includes:

- Salesperson sales
- Total orders
- Total quantity
- Average Order Value
- Salesperson contribution
- Salesperson comparison

This helps identify high-performing salespersons and compare their performance.

---

## 5️⃣ Customer Analysis

The Customer Analysis page focuses on customer purchasing behavior.

The analysis includes:

- Customer sales
- Customer orders
- Customer quantity
- Customer contribution
- Customer performance comparison

This helps understand customer purchasing behavior and identify important customers.

---

## 6️⃣ Time & Sales Trend Analysis

The Time & Sales Trend Analysis page focuses on sales performance over time.

The analysis includes:

- Monthly sales trends
- Yearly sales analysis
- Sales growth
- Time-based comparisons
- Date-based filtering
- Trend visualization

The dedicated Date Table is used to support the time-based analysis.

# 🎯 7. Regional Analysis

Regional analysis was included to compare sales performance across different regions.

The regional analysis includes:

* Region-wise sales
* Region-wise order performance
* Regional comparison
* Regional contribution to total sales
* Interactive regional filtering

The regional analysis helps identify stronger and weaker performing markets and provides additional context for evaluating sales performance.

---

# 🎛️ 8. Interactive Features

The dashboard was designed as an interactive Business Intelligence report rather than a collection of static charts.

The following interactive features were implemented:

### Slicers

Slicers allow users to filter the dashboard based on relevant business dimensions such as:

* Year
* Month
* Category
* Region
* Product
* Salesperson
* Customer

The available slicers vary by dashboard page according to the type of analysis being performed.

### Cross-Filtering

Selecting a category, product, salesperson, customer, region, or time period dynamically updates the relevant dashboard visuals.

### Dynamic KPI Cards

The KPI cards update according to the selected filters, allowing users to analyze sales performance for specific segments.

### Interactive Charts

Users can select data points within charts to investigate relationships between different business dimensions.

---

# 📊 9. Visualizations Used

The project uses multiple Power BI visualizations to present the analysis clearly.

The main visualizations include:

* KPI Cards
* Line Charts
* Clustered Bar Charts
* Column Charts
* Donut Charts
* Tables
* Slicers

### KPI Cards

Used to display:

* Total Sales
* Total Orders
* Total Customers
* Average Order Value

### Line Charts

Used for:

* Monthly sales trends
* Sales growth
* Time-based analysis

### Bar and Column Charts

Used for:

* Product comparison
* Category comparison
* Salesperson performance
* Regional performance
* Order comparison

### Donut Charts

Used to show category or regional contribution to total sales.

### Tables

Used to provide detailed information at product, customer, salesperson, or category level.

---

# 💡 10. Key Business Insights

The analysis produced several important business insights.

### Overall Sales Performance

The dashboard contains approximately:

* **500 Orders**
* **99 Customers**
* **11.00M Total Sales**
* **22.00K Average Order Value**

These KPIs provide a high-level view of overall business performance.

### Product Performance

**Skipping Rope** was identified as the highest-selling product, generating approximately **568,866.59** in sales.

**Dumbbell Set** was the lowest-selling product, generating approximately 25,977.04 in sales.

This indicates a significant difference in sales contribution between products.

### Category Performance

**Electronics** was identified as the highest-selling category, generating approximately **1,681,954.10** in sales.

This indicates that Electronics made a significant contribution to overall revenue.

### Salesperson Performance

**Salesperson 03** recorded the highest number of orders, with **33 orders**.

This indicates strong transactional performance and provides an opportunity to study the sales practices of high-performing sales representatives.

### Time-Based Performance

**April 2025** was identified as the strongest sales month, generating approximately **1,292,670.81** in sales.

The analysis also identified **August 2025** as a month with approximately **48.71% month-over-month sales growth**.

These results demonstrate the importance of monitoring sales performance over time.

---

# 📈 11. Business Recommendations

Based on the dashboard analysis, the following recommendations can be considered:

### 1. Focus on High-Performing Products

High-performing products such as Skipping Rope should receive appropriate inventory, promotional, and sales attention to maintain strong performance.

### 2. Review Low-Performing Products

Products with relatively low sales should be reviewed based on:

* Customer demand
* Pricing
* Product positioning
* Promotional activity
* Inventory strategy

### 3. Prioritize Strong Categories

High-performing categories such as Electronics should continue to receive appropriate business attention and investment.

### 4. Learn From High-Performing Salespeople

The performance of successful salespersons can be studied to identify effective sales practices that could be applied across the wider sales team.

### 5. Investigate High-Growth Periods

Periods with significant sales growth should be investigated to understand the factors contributing to the increase.

These factors could include:

* Product demand
* Promotional campaigns
* Seasonal demand
* Sales activity
* Regional performance

### 6. Monitor Regional Performance

Regional performance should be monitored regularly to identify strong markets and regions requiring additional attention.

---

# 🛠️ 12. Tools & Technologies

The project was developed using the following tools and technologies:

* **Microsoft Power BI**
* **Power Query**
* **DAX**
* **Microsoft Excel**
* **SQL / MySQL**
* **GitHub**

### Power BI

Used for:

* Data modeling
* DAX calculations
* KPI development
* Dashboard creation
* Data visualization
* Interactive reporting

### Power Query

Used for:

* Data loading
* Data cleaning
* Data transformation
* Data type validation
* Data preparation

### DAX

Used for:

* Sales calculations
* Order calculations
* Customer calculations
* Average Order Value
* Time-based calculations
* Growth analysis

### SQL / MySQL

Used as part of the broader sales analysis project for querying and analyzing the underlying relational sales data.

### Microsoft Excel

Used for the initial sales data analysis and dataset preparation.

### GitHub

Used to organize and present the project files and documentation.

---

# 📁 13. Project Structure

The project repository is organized as follows:

```text
Sales-Performance-Analysis-PowerBI/
│
├── README.md
│
└── Power BI Project/
    │
    ├── Sales_Performance_Analysis.pbix
    │
    └── Screenshots/
        ├── Screenshot 2026-08-25 184543.png
        ├── Screenshot 2026-08-25 184610.png
        ├── Screenshot 2026-08-25 184629.png
        ├── Screenshot 2026-08-25 184648.png
        ├── Screenshot 2026-08-25 184704.png
        └── Screenshot 2026-08-25 184727.png
```

The repository contains the Power BI report, dashboard screenshots, and project documentation.

---

# 🖼️ 14. Dashboard Screenshots

The project includes screenshots of the completed Power BI dashboard pages.

### Executive Sales Overview

![Executive Sales Overview](Power%20BI%20Project/Screenshots/Screenshot%202026-08-25%20184543.png)

### Product Analysis

![Product Analysis](Power%20BI%20Project/Screenshots/Screenshot%202026-08-25%20184610.png)

### Category Analysis

![Category Analysis](Power%20BI%20Project/Screenshots/Screenshot%202026-08-25%20184629.png)

### Salesperson Analysis

![Salesperson Analysis](Power%20BI%20Project/Screenshots/Screenshot%202026-08-25%20184648.png)

### Customer Analysis

![Customer Analysis](Power%20BI%20Project/Screenshots/Screenshot%202026-08-25%20184704.png)

### Time & Sales Trend

![Time & Sales Trend](Power%20BI%20Project/Screenshots/Screenshot%202026-08-25%20184727.png)
# 📖 15. How to Use

### Step 1 — Open the Power BI Report

Open:

```text
Sales_Performance_Analysis.pbix
```

using Microsoft Power BI Desktop.

### Step 2 — Navigate Between Pages

Use the page navigation tabs to access:

* Executive Sales Overview
* Product Analysis
* Category Analysis
* Salesperson Analysis
* Customer Analysis
* Time & Sales Trend

### Step 3 — Apply Filters

Use the available slicers to filter the dashboard by dimensions such as:

* Year
* Month
* Category
* Region
* Product
* Salesperson
* Customer

### Step 4 — Explore the Visuals

Select data points in charts to interact with the other visuals on the page.

### Step 5 — Analyze KPIs

Use the KPI cards to monitor the selected segment's:

* Total Sales
* Total Orders
* Total Customers
* Average Order Value

The dashboard can therefore be used to explore overall performance as well as specific business segments.

---

# ⭐ 16. Project Highlights

* Built an interactive Sales Performance Dashboard using Power BI.
* Created a structured relational data model.
* Prepared and transformed data using Power Query.
* Created a dedicated Date Table using DAX.
* Developed DAX measures for business KPIs.
* Created interactive KPI cards.
* Analyzed product performance.
* Analyzed category performance.
* Analyzed customer performance.
* Analyzed salesperson performance.
* Analyzed regional performance.
* Performed time-based sales analysis.
* Implemented interactive slicers and filtering.
* Identified important business trends.
* Converted sales data into actionable business insights.
* Integrated SQL, Excel, and Power BI skills into a complete analytics project.

---

# 💼 17. Business Value

The dashboard provides management with a centralized view of sales performance.

Instead of manually reviewing large amounts of transactional data, users can quickly identify:

* Overall sales performance
* High-performing products
* Low-performing products
* Strong categories
* Customer performance
* Salesperson performance
* Regional performance
* Sales trends
* Periods of significant growth

The interactive dashboard can support business decisions related to sales strategy, product prioritization, inventory planning, customer management, salesperson performance, and regional strategy.

---

# 🎯 18. Project Purpose

The purpose of this project is to transform raw transactional sales data into an interactive Business Intelligence dashboard using Microsoft Power BI.

The project demonstrates how data can be:

**Loaded → Cleaned → Transformed → Modeled → Analyzed → Visualized → Converted into Business Insights**

The primary objective is to provide a clear and interactive view of sales performance across products, categories, customers, salespersons, regions, and time periods.

The project also demonstrates the application of SQL, Excel, Power Query, DAX, data modeling, and data visualization skills within a practical business analytics scenario.

---

# 🧠 19. Skills Demonstrated

## Technical Skills

* Microsoft Power BI
* Power Query
* DAX
* Data Cleaning
* Data Transformation
* Data Modeling
* Relationship Management
* Date Table Creation
* Time Intelligence
* KPI Development
* Dashboard Design
* Data Visualization
* Interactive Reporting
* Slicers and Filters
* SQL
* Microsoft Excel

## Analytical Skills

* Sales Performance Analysis
* Product Analysis
* Category Analysis
* Customer Analysis
* Salesperson Analysis
* Regional Analysis
* Trend Analysis
* Growth Analysis
* KPI Analysis
* Business Insight Generation
* Data-Driven Decision Making

## Business Skills

* Performance Monitoring
* Sales Strategy Analysis
* Product Performance Evaluation
* Customer Performance Analysis
* Salesperson Performance Evaluation
* Regional Performance Analysis
* Business Recommendation Development

---

# 👤 20. Author

**Sanju Sajeev**

MBA – Data Science & Artificial Intelligence

### Project

**Sales Performance Analysis – Power BI**

This project demonstrates practical skills in data analysis, business intelligence, data visualization, SQL, Excel, Power Query, and Power BI.
