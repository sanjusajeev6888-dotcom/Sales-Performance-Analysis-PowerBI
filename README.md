# 📊 Sales Performance Analysis – Power BI

## 📌 Project Overview

This project presents an interactive **Sales Performance Analysis Dashboard** built using **Microsoft Power BI**.

The dashboard analyzes sales data across products, categories, salespersons, customers, regions, and time periods to identify important business trends, measure performance, and support data-driven decision-making.

The project demonstrates the complete Power BI workflow, including:

- Data loading
- Data cleaning and transformation
- Data modeling
- Relationship creation
- Date table creation
- DAX calculations
- KPI development
- Interactive dashboards
- Slicers and filters
- Business insights
- Data visualization


---

# 🎯 Business Objectives

The main objectives of this project are:

- Analyze overall sales performance
- Track total sales and total orders
- Analyze customer purchasing behavior
- Identify top-performing products
- Identify top-performing categories
- Evaluate salesperson performance
- Analyze regional sales performance
- Analyze monthly sales trends
- Analyze sales quantity
- Calculate average order value
- Calculate salesperson contribution to total sales
- Identify important business trends
- Provide an interactive dashboard for business decision-making


---

# 🗂️ Dataset

The project uses a relational sales dataset consisting of the following tables:

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

A dedicated Date Table was created in Power BI using DAX for accurate time-based analysis.

The Date Table contains:

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
    │ SalespersonID
    ▼
Salespersons
