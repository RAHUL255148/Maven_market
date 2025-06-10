# Maven Market Power BI Dashboard (second_BI_project.pbix)

:contentReference[oaicite:1]{index=1}

---

## 📁 Project Overview

:contentReference[oaicite:2]{index=2}

- :contentReference[oaicite:3]{index=3}
- :contentReference[oaicite:4]{index=4}
- :contentReference[oaicite:5]{index=5}
- :contentReference[oaicite:6]{index=6} :contentReference[oaicite:7]{index=7}

---

## 🔄 Data Import & Transformation

:contentReference[oaicite:8]{index=8}

1. Import CSVs:
   - :contentReference[oaicite:9]{index=9}
   - :contentReference[oaicite:10]{index=10} :contentReference[oaicite:11]{index=11}
   - :contentReference[oaicite:12]{index=12}
   - :contentReference[oaicite:13]{index=13}
   - :contentReference[oaicite:14]{index=14}
   - :contentReference[oaicite:15]{index=15} :contentReference[oaicite:16]{index=16}

2. :contentReference[oaicite:17]{index=17}
   - :contentReference[oaicite:18]{index=18}  
   - :contentReference[oaicite:19]{index=19} :contentReference[oaicite:20]{index=20}

---

## 🛠️ Data Modeling

- :contentReference[oaicite:21]{index=21}
  - :contentReference[oaicite:22]{index=22} :contentReference[oaicite:23]{index=23}
- :contentReference[oaicite:24]{index=24}

---

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
