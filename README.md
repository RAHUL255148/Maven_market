# 📊 Maven Market | Power BI Dashboard

An interactive business intelligence dashboard for **Maven Market**, built using Power BI. This report analyzes sales, profits, customer behavior, product returns, and store performance across the US, Canada, and Mexico during 1997–1998.

---

## 🧩 Project Highlights

- 🔄 **End-to-End ETL** using Power Query  
- 📐 **Star-Schema Modeling** with clear table relationships  
- 💡 **DAX Measures** for dynamic KPIs and time intelligence  
- 📈 **Visual Dashboards** with drill-throughs, filters, and slicers  
- 🌎 **Regional Insights** by country, store, and customer demographics  

---

## 🚀 Features & Insights

| 🔍 Area              | 📌 Focus                                                   |
|---------------------|------------------------------------------------------------|
| **Topline Metrics** | Transactions, Revenue, Profit, Return Rate, Profit Margin |
| **Sales Trends**    | Monthly and Yearly comparisons                             |
| **Product View**    | Top Brands, Product Returns, Discount Analysis             |
| **Customer Insights** | High-value customers, Membership, Demographics          |
| **Geo Analysis**    | Sales performance by Country, Region, Store               |

---

## 📁 File Details

- `first_BI_project.pbix` → Power BI file containing all transformations, models, DAX, and visuals

---

## 🛠️ How to Run

1. **Clone the repository**:

```bash
git clone https://github.com/RAHUL255148/Maven_market.git
cd Maven_market


## 📊 DAX Measures

:contentReference[oaicite:25]{index=25}

```DAX
Total Transactions = COUNTROWS(Transaction_Data)
Total Returns = COUNTROWS(Return_Data)
Total Revenue = SUMX(Transaction_Data, quantity * RELATED(Products[product_retail_price]))
Total Cost = SUMX(Transaction_Data, quantity * RELATED(Products[product_cost]))
Total Profit = [Total Revenue] - [Total Cost]
Return Rate = DIVIDE([Quantity Returned], [Quantity Sold], 0)
Profit Margin = DIVIDE([Total Profit], [Total Revenue], 0)
Last Month Transactions = CALCULATE([Total Transactions], PREVIOUSMONTH(Calendar[date]))
Last Month Profit = CALCULATE([Total Profit], PREVIOUSMONTH(Calendar[date]))
Last Month Returns = CALCULATE([Total Returns], PREVIOUSMONTH(Calendar[date]))
Average Transaction per Customer = DIVIDE([Total Transactions], DISTINCTCOUNT(Customers[customer_id]))
