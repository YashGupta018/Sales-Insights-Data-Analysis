# Sales Insights Data Analysis Project

**Project Overview**  
This project demonstrates a real-time sales analytics dashboard for a computer hardware business facing dynamic market challenges. The Power BI dashboard provides actionable insights to drive data-driven decisions, simulating a real-world data analysis workflow used in large enterprises.

---

## 📁 Repository Contents

1. **Database Dumps**  
   - `db dump.sql`: Initial MySQL database schema & sales data (customers, transactions, markets, products, dates).  
   - `db dump v2.sql`: Updated version of the database schema with potential enhancements.  

2. **Power BI Reports**  
   - `sales insights.pbix`: Core Power BI report with visualizations for sales trends, customer behavior, and market performance.  
   - `sales insights v2.pbix`: Refined version of the dashboard with additional features or optimizations.  

---

## 🛠️ Technologies Used  
- **Power BI**: Dashboard creation, data visualization, and real-time insights.  
- **SQL**: Database management and querying (MySQL).  
- **Data Analysis**: Sales trend analysis, revenue tracking, and market segmentation.  

---

## 🔑 Key Features of the Dashboard  
- Real-time sales performance tracking.  
- Market-wise revenue and profit analysis.  
- Customer segmentation by type (Brick & Mortar vs. E-Commerce).  
- Year-over-year (YoY) and month-over-month (MoM) growth metrics.  
- Interactive filters for dynamic data exploration.  

---

## 🚀 How to Use  
1. **Database Setup**:  
   - Import `db dump.sql` or `db dump v2.sql` into a MySQL server to replicate the database.  
2. **Power BI**:  
   - Open `sales insights.pbix` or `sales insights v2.pbix` in Power BI Desktop.  
   - Connect to your MySQL database to refresh data sources.  

---

## Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`

---

## 📈 Project Value  
This project mimics industry-standard workflows, making it ideal for aspiring data analysts to:  
- Practice end-to-end data analysis (ETL, visualization, reporting).  
- Learn Power BI dashboard design and SQL integration.  
- Gain insights into sales optimization strategies.  

---

**Note**: Ensure Power BI Desktop and MySQL are installed to interact fully with the files.
