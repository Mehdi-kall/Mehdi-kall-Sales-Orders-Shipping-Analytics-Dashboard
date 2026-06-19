# Sales, Orders & Shipping Analytics Dashboard

End-to-end Business Intelligence project covering ETL, data modeling, DAX analytics, and Power BI dashboard design across three business domains: **Sales**, **Orders**, and **Shipping & Delivery**.

---

## 📊 Overview

This project builds a complete BI pipeline — from raw data to interactive, decision-ready dashboards — using **SQL Server, SSIS, and Power BI**.

| Page | Focus |
|---|---|
| **Sales** | Revenue trends, category/brand performance, geographic ranking, YoY growth |
| **Orders** | Order status breakdown, payment methods, device/gender analysis, cancellation risk |
| **Shipping & Delivery** | Logistics KPIs, fulfillment performance, delivery time analysis |

---

## 🗂️ Repository Structure

```
/sales-orders-dashboard
├── README.md
├── /SQL
│   └── dim_date.sql              # Date dimension table generation script
├── /SSIS
│   └── etl_package.dtsx          # ETL package: extraction, cleansing, loading
├── /PowerBI
│   └── dashboard.pbix            # Full Power BI file
├── /screenshots
│   ├── sales_dashboard.png
│   ├── orders_dashboard.png
│   └── shipping_dashboard.png
└── /docs
    └── dax_measures.md           # Documented DAX measures
```

---

## 🔧 Tech Stack

- **SQL Server** — data storage, Dim_Date generation
- **SSIS** — ETL pipeline (extraction, transformation, loading)
- **Power BI / DAX** — data modeling, analytics, dashboard design

---

## ⚙️ ETL (SSIS)

- Structured Data Flows for cleansing, transformation, and loading across multiple fact tables
- Used **Conditional Split**, **Derived Column**, and **Aggregate** transformations for data cleansing and deduplication
- Error handling considerations for production-grade reliability

---

## 🧮 Data Modeling

- Custom **Dim_Date** table (2023–2026) with calculated `Year`, `Month`, `Quarter`, `Season`, and `Holiday Season` attributes
- Star schema design connecting Sales, Orders, and Shipping fact tables to shared dimensions (Date, Geography, Category)

---

## 📈 DAX & Analytics Highlights

- **Year-over-Year growth measures** — including a deep dive into how Power BI's filter context can silently break calculations when slicers are involved, solved through explicit year-based filtering
- **Dynamic ranking logic** that adapts to whatever filters the user applies on the dashboard
- **Tiered KPI classification** for risk metrics like *High-Value Loss Rate* and *Discounted Orders Rate*

Full measure documentation: [`/docs/dax_measures.md`](./docs/dax_measures.md)

---

## 🎨 Dashboard Design & UX

- 3 interconnected pages with consistent navigation
- **Bookmarks** for Focus Mode (toggle between chart view and detail table) — decoupled data state from display state to keep slicers fully interactive
- **Conditional formatting** for instant visual signal on risk metrics
- Synced slicers (Year, Month, City, Category) across pages

---

## 📸 Screenshots

### Sales Dashboard
![Sales Dashboard](./screenshots/sales_dashboard.png)

### Orders Dashboard
![Orders Dashboard](./screenshots/orders_dashboard.png)

### Shipping & Delivery Dashboard
![Shipping Dashboard](./screenshots/shipping_dashboard.png)

---

## 🔑 Key Learnings

Filter context in DAX is unforgiving — a single misplaced filter override can silently break YOY logic across an entire report. Debugging this taught more about evaluation context than any tutorial.

---

## 📬 Contact

Feel free to reach out for questions or feedback on this project.
