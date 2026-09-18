# Ecommerce Sales Analysis – Power BI Dashboard

## 📌 Live Dashboard Link

https://app.powerbi.com/view?r=eyJrIjoiOTI0YjE2NzctNDE1Yi00MTlmLWIyYmMtODdjNjg4Nzk4ZGFkIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9

## 📊 Dashboard Pages

### 1. Sales Analysis Page

The main dashboard provides an interactive view of ecommerce sales performance, vendor contribution, item performance, sales trends and period-based analysis.

### 2. Vendor Details

A vendor-level drillthrough page containing dedicated KPIs, vendor performance visuals and detailed vendor analysis.

---

## 📌 Project Overview

This project focuses on analyzing the sales performance of a large ecommerce platform selling 25,000+ products through multiple vendors nationwide.

The dashboard was developed to:

- Track overall sales performance.
- Analyze vendor-wise and item-wise contribution.
- Identify underperforming products.
- Visualize sales trends and distribution patterns.
- Compare vendor and item performance across selected periods.
- Provide detailed vendor-level analysis through drillthrough.

The dashboard was built using three Excel datasets:

1. **2021Sales.xls** – Order data including OrderID, Date, ItemID, Quantity and Sales Amount.
2. **Item-Vendor.xls** – Mapping of items to vendors.
3. **Vendor-Manager.xls** – Mapping of vendors to sales managers.

---

## 🗂 Data Model

A clean **star schema** was developed consisting of:

- **Fact Table** – Sales transactions.
- **Dimension Tables** – Vendors, Items and Sales Managers.
- Relationships connected using ItemID and VendorID.

Data is transformed and prepared for analysis before being loaded into Power BI.

---

## 🎯 Key Features & Functionality

### 🔹 Dynamic Slicers

Interactive slicers allow users to analyze the report by:

- Vendor
- Sales Manager
- Date Range
- Period selection

The selected filters dynamically affect the relevant dashboard visuals.

### 🔹 14-Day Moving Average

A time-series analysis compares daily sales with a 14-day moving average.

The moving-average analysis is designed to:

- Show daily sales movement.
- Smooth short-term fluctuations.
- Respond to relevant report selections.

**DAX calculation:**

```DAX
14-Day Moving Avg =
AVERAGEX(
    DATEADD('Date'[Date], -14, DAY),
    [Total Sales]
)
```

### 🔹 Period Slicer – 7 / 14 / 28 Days

A dedicated period-selection analysis provides short-term sales trends for:

- 7 days
- 14 days
- 28 days

The calculation uses filter-removal logic such as `REMOVEFILTERS` and `ALL` to isolate the period-based analysis from other report filters where required.

### 🔹 Vendor Sales Distribution

A box-plot visual is used to analyze the distribution of daily vendor sales, including:

- Minimum
- Maximum
- Median
- Quartiles
- Overall spread

This helps compare the distribution and variation of vendor performance.

### 🔹 Second Best-Selling Item Per Vendor

A custom calculated table uses `RANKX` to identify the second-best-selling item for each vendor.

The ranking logic evaluates item-level sales within the vendor context and returns records with rank equal to 2.

This functionality was manually validated against Excel.

### 🔹 Drillthrough Reporting

A dedicated Vendor Details page provides:

- Vendor-level KPIs.
- Vendor performance visuals.
- Detailed vendor analysis.
- Back navigation to the main dashboard.

### 🔹 Dynamic Page Titles

Dynamic titles are used to make report headings respond to the selected vendor, period or analysis context.

---

## 🧮 DAX Calculations

DAX is used for KPI calculations, ranking, moving averages, period analysis and dynamic report behavior.

Key DAX functionality used in the project includes:

- `RANKX` – Vendor/item ranking and second-best-item identification.
- `AVERAGEX` – Moving-average calculation.
- `DATEADD` – Date-based moving-window analysis.
- `REMOVEFILTERS` – Removing selected filters for isolated calculations.
- `ALL` – Controlling filter context.
- Filter/context functions – Supporting dynamic period and vendor analysis.

### Key Measures

- `Total Sales`
- `Period Sales`
- `Items Sold`
- `Moving Average`
- `Is last 3 Months`
- `Dynamic card title`
- `Dynamic line chart title`
- `Dynamic vendor card`

---

## 🧰 Techniques & Power BI Skills Used

- Data Modeling & Star Schema Design.
- Advanced DAX.
- `RANKX`, `REMOVEFILTERS`, `ALL`, `AVERAGEX` and `DATEADD`.
- Time-Series Analysis.
- Moving-Average Analysis.
- Dynamic Period Selection.
- Dynamic Page Titles.
- Drillthrough and Navigation.
- Dynamic and Responsive Visuals.
- Custom Box Plot Visual Integration.
- Interactive Slicers and Filtering.
- Vendor-level performance analysis.

---

## 📊 KPIs Built

- Total Sales Revenue.
- Total Quantity Sold.
- Vendor Contribution.
- Item Performance.
- Period Sales.
- Moving Average Trends.
- Second-Best Item by Vendor.
- Items Sold.

---

## 📈 Business Analysis Covered

| Area | Analysis |
|---|---|
| **Sales** | Overall sales, period sales and sales trends |
| **Vendor** | Vendor contribution and vendor-level performance |
| **Product/Item** | Item performance and second-best-selling item by vendor |
| **Time Analysis** | Daily trends, moving averages and selected-period analysis |
| **Management** | Vendor-manager filtering and detailed vendor reporting |

---

## 💻 Tools Used

- **Power BI Desktop** – Data modeling, DAX, visualization and dashboard development.
- **DAX** – Business calculations, ranking, time-series and filter-context analysis.
- **Power Query** – Data preparation and transformation.
- **Excel** – Source data and validation of calculated results.

---

## 🙌 Author

**Moulishkumar**  
Data Analyst | Power BI | SQL | DAX
