# 📊 Competitive Marketing Analysis Dashboard

This Power BI dashboard provides an in-depth analysis of sales and marketing performance across various channels — Online, Social Media, Outlet, and Stores. It includes KPIs, ROI metrics, sales trends, product and segment breakdowns, and customer sentiment distribution.

![Dashboard Preview](./Desktop/Screenshot 2025-04-29 at 1.11.18 PM.png]()
.png)

---

## 📁 Dataset Overview

The dataset used in this dashboard comes from Microsoft's [Power BI Learning Path: Competitive Marketing Analysis](https://learn.microsoft.com/en-us/training/modules/create-power-bi-reports/). It includes the following key tables:

- **SalesFact**: Contains quantitative measures like revenue, sales $, total units, and sentiment.
- **Date**: Calendar table for time-based analysis (Month, Year).
- **Product**: Product-specific attributes like category, manufacturer.
- **Geo**: Regional data for sentiment and geographic breakdown.
- **Channel**: Represents sales channels (Online, Social Media, Outlet, Store).

---

## 🧱 Dashboard Components

| Visualization                        | Purpose                                                  | Key Fields Used                                   |
|-------------------------------------|----------------------------------------------------------|--------------------------------------------------|
| **KPI Cards**                        | Show total sales per channel                             | `SalesFact[Revenue]` filtered by `Channel`       |
| **Sales by Channel (Donut Chart)**  | Proportion of total sales per channel                    | `SalesFact[Revenue]`, `Channel`                  |
| **Sales by Product & Channel**      | Compare product sales across each channel                | `Product[Name]`, `Channel`, `SalesFact[Revenue]` |
| **Units by Category**               | Show total units sold by product category                | `SalesFact[Total Units]`, `Product[Category]`    |
| **Category Volume by Segment**      | Visualize sales volume per product segment               | `SalesFact[Total Category Volume]`, `Segment`    |
| **Sentiment by Region**            | Pie chart of sentiment distribution                      | `SalesFact[Sentiment]`, `Geo[Region]`            |
| **Sales Over Time by Channel**     | Quarterly trend of sales across all channels             | `Date[Quarter]`, `Channel`, `SalesFact[Revenue]` |

---

## 🧮 DAX Measures Used

### ✅ Total Sales

```dax
Total Sales = SUM(SalesFact[Revenue])
