# 📊 Sales Performance Analysis – Power BI

## 📌 Project Overview

This project presents an interactive **Sales Performance Analysis Dashboard** built using Microsoft Power BI.

The dashboard analyzes sales data across products, categories, salespersons, customers, and time periods to identify key business trends and performance indicators.

---

## 🎯 Business Objectives

- Analyze overall sales performance
- Identify top-performing products
- Analyze category-wise sales and quantity
- Evaluate salesperson performance
- Analyze customer purchasing behavior
- Track monthly and yearly sales trends
- Measure sales growth
- Create an interactive and professional Power BI dashboard

---

## 🗂️ Dataset

The project uses the same sales dataset used in the SQL and Excel analysis projects.

The dataset contains five related tables:

- **Customers** – Customer information and customer segments
- **Products** – Product details and unit prices
- **Categories** – Product category information
- **Salespersons** – Salesperson details including region and experience
- **Orders** – Transaction-level sales information

### Key fields include:

- Order ID
- Order Date
- Customer ID
- Product ID
- Salesperson ID
- Quantity
- Unit Price
- Discount Percentage
- Sales Amount
- Region

---

## 🛠️ Tools & Technologies

- Microsoft Power BI
- Power Query
- DAX
- Data Modeling
- Interactive Visualizations
- Slicers
- KPI Cards

---

## 📊 Dashboard Pages

### 1. Executive Sales Overview

Provides a high-level summary of overall business performance using:

- Total Orders
- Total Sales
- Total Customers
- Average Order Value
- Top Products
- Monthly Sales Trend
- Sales by Category

### 2. Product Analysis

Analyzes:

- Top Products by Sales
- Product Sales
- Product Quantity
- Product Orders
- Product-level performance

### 3. Category Analysis

Analyzes:

- Category Sales
- Category Quantity
- Category Orders
- Category-wise sales contribution

### 4. Salesperson Analysis

Analyzes:

- Salesperson Sales
- Salesperson Orders
- Total Quantity
- Average Order Value
- Salesperson Sales Percentage

### 5. Customer Analysis

Analyzes:

- Customer Sales
- Customer Orders
- Customer Quantity
- Top Customers
- Customer-level performance

### 6. Time & Sales Trend

Analyzes:

- Monthly Sales Trend
- Yearly Sales
- Monthly Orders
- Sales by Month
- Monthly Sales Growth

---

## 📈 Key KPIs

The dashboard includes interactive KPI measures such as:

- Total Sales
- Total Orders
- Total Customers
- Total Quantity
- Average Order Value
- Sales Growth
- Salesperson Sales %

---

## 🔄 Interactivity

The Power BI dashboard includes interactive slicers for:

- Product
- Category
- Salesperson
- Customer
- Date/Month

Users can select different values to dynamically analyze sales performance.

---

## 🔗 Data Model

The Power BI model follows a relational structure connecting:

```text
Customers
     │
     │
     ▼
   Orders ◄──── Products ◄──── Categories
     │
     │
     ▼
Salespersons

DateTable ─────► Orders
