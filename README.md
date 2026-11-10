# FMCG Sales Analytics on Databricks

A sales analytics project built on **Databricks**. It turns raw FMCG / sporting-goods sales data into an interactive **AI/BI dashboard** that helps business users see what is selling, who is buying, which channels perform best, and how revenue changes over time.

![Performance Overview Dashboard](images/dashboard-overview.png)

---

## Table of Contents

- [Project Overview](#project-overview)
- [Business Questions Answered](#business-questions-answered)
- [Features](#features)
- [Dashboard Walkthrough](#dashboard-walkthrough)
- [Data](#data)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Key Insights](#key-insights)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## Project Overview

Sales teams in FMCG companies work with large volumes of transactions across products, customers, markets and channels. Reading this data in raw tables makes it hard to spot trends or decide where to focus.

This project solves that by:

1. Loading the sales data into Databricks.
2. Writing SQL datasets that aggregate revenue, quantity, customers and pricing.
3. Building a single-page **Performance Overview** dashboard on top of those datasets.
4. Publishing the dashboard so it can be shared and exported (for example as a PDF).

---

## Business Questions Answered

- How much revenue and quantity are we selling, and at what average price?
- Which products and product variants earn the most?
- Which customers contribute the most revenue?
- How is revenue split between sales channels (Retailer vs Direct)?
- How does revenue change month over month?
- How does price relate to the quantity sold?

---

## Features

- **KPI cards** for Total Revenue, Total Quantity, Unique Customers and Average Selling Price
- **Global filters** for Year, Month, Quarter, Market, Channel and Category that update every chart at once
- **Six visuals** covering products, channels, trends, customers, variants and price behaviour
- **Published dashboard** that can be shared by link and downloaded as a PDF

---

## Dashboard Walkthrough

| Visual | Chart type | Purpose |
|---|---|---|
| Top 10 Products by Total Revenue | Horizontal bar | Ranks the best-selling products by revenue |
| Revenue by Channel | Donut | Shows the Retailer vs Direct revenue split |
| Monthly Revenue Trend | Area | Tracks revenue across the months of the year |
| All Customers by Revenue | Table | Lists customers with quantity and revenue, sortable by revenue |
| Top Variant by Revenue | Bar | Compares revenue across product variants and sizes |
| Product Price vs Quantity | Bubble / scatter | Shows how price points relate to units sold |

> The screenshot was taken with the `month_name = June` filter applied, so the KPI cards show June figures. Clear the filters with **Reset all to default** to see the full dataset.

---

## Data

The dashboard is built on a sales dataset with fields along these lines:

| Field | Description |
|---|---|
| `product` | Product name |
| `variant` | Product variant or size |
| `category` | Product category |
| `customer` | Customer name |
| `channel` | Sales channel (Retailer or Direct) |
| `market` | Sales market or region |
| `year`, `quarter`, `month_name` | Time dimensions used for filtering and trends |
| `quantity` | Units sold |
| `price` | Selling price per unit |
| `revenue` | Sales value (quantity x price) |

Update this table to match the exact column names in your own tables.

---

## Tech Stack

| Area | Tool |
|---|---|
| Platform | Databricks (Free Edition) |
| Dashboarding | Databricks AI/BI Dashboards |
| Querying | SQL |
| Storage | Delta tables |

---

## Getting Started

### Prerequisites

- A Databricks workspace (the Free Edition works)
- The sales data loaded as a table in your catalog

### Steps

1. **Load the data.** Upload your sales data to Databricks and create a table.
2. **Create the dashboard.** Go to **Dashboards**, click **Create dashboard**, and open the **Data** tab.
3. **Add datasets.** Write the SQL queries that aggregate revenue, quantity, customers and price.
4. **Build the visuals.** On the **Sales** tab, add the KPI cards and charts and connect them to the datasets.
5. **Add filters.** Add global filters for Year, Month, Quarter, Market, Channel and Category.
6. **Publish.** Click **Publish**, keep the default **Share data permission**, and confirm.
7. **Export (optional).** In the published view, open the **⋮** menu and choose **Download as PDF**.

---

## Key Insights

- Revenue is concentrated in a few top products, led by cricket and fitness equipment.
- The **Retailer** channel brings in roughly 77% of revenue, with **Direct** at about 23%.
- Revenue rises sharply in the last quarter of the year, peaking in December.
- A small group of customers accounts for a large share of total revenue.

---

## Future Improvements

- Build a full ETL pipeline with data-quality checks before the data reaches the dashboard
- Organise the data into Bronze, Silver and Gold layers
- Schedule automatic refreshes so the dashboard always shows current data
- Add year-over-year comparison and customer segmentation views

---

## Author

**Akhil**, Computer Science graduate (B.E. CSE, 2025) with working knowledge of Python, SQL and Spark, and an interest in reliable ETL and data-quality checks.

Feel free to open an issue or reach out with feedback.
