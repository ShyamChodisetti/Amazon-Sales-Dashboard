# Amazon-Sales-Dashboard



# 📊 Amazon Sales Dashboard – 2025 (Power BI)

This Power BI dashboard presents a comprehensive analysis of Amazon's sales data for the year **2025**, focusing on customer behavior, product performance, payment trends, and geographic insights.

## 🔗 Dashboard Link
👉 [Click here to view the dashboard](#)  
*(Replace `#` with your Power BI Service or portfolio link)*

---

## 📦 Dataset Overview

The dataset includes the following fields:

- `Order ID`
- `Date`
- `Product`
- `Category`
- `Price`
- `Quantity`
- `Total Sales`
- `Customer Name`
- `Customer Location`
- `Payment Method`
- `Status` (Delivered, Cancelled, Returned, etc.)

---

## 📊 Key Insights & Features

| 🔍 Insight Area             | 📈 Visual Type               |
|----------------------------|------------------------------|
| Total Sales, Orders, Quantity | KPI Cards                    |
| Sales Over Time            | Line Chart                   |
| Top Products & Categories  | Bar Chart, Donut Chart       |
| Sales by Payment Method    | Pie Chart                    |
| Order Status Breakdown     | Stacked Column / Pie Chart   |
| 📍 Sales by Location        | Map Visual & Bar Chart       |
| Filters                    | Slicers (Date, Category, Status) |

---

## 🧮 DAX Measures Used

```dax
Total Sales = SUM('Sales'[Total Sales])

Total Orders = DISTINCTCOUNT('Sales'[Order ID])

Total Quantity = SUM('Sales'[Quantity])

Average Order Value = DIVIDE([Total Sales], [Total Orders])

Cancelled Orders = 
CALCULATE(
    DISTINCTCOUNT('Sales'[Order ID]),
    'Sales'[Status] = "Cancelled"
)

Return Rate = 
DIVIDE(
    CALCULATE(COUNTROWS('Sales'), 'Sales'[Status] = "Returned"),
    [Total Orders]
)
