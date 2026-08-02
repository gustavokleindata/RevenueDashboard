# 📊 E-Commerce & Customer Performance Dashboard (2025)

A comprehensive, business-driven sales performance and customer target analytics dashboard developed in Power BI. This project simulates a highly realistic corporate scenario where **no historical data from previous years is available**, challenging the engineer to develop time intelligence and trend analytics using purely current-year data (2025).

## 💡 Business Problem & Technical Challenge

A growing e-commerce operation needed to closely monitor its main financial and logistics KPIs for the fiscal year 2025. The core technical hurdle of this project was the **complete absence of historical data (2024 or earlier)**, making traditional *Year-over-Year (YoY)* growth metrics impossible to compute.

To overcome this limitation and still deliver deep trend and seasonality insights to the executive board, advanced data modeling techniques and statistical calculations were applied using solely the active year's data.

## 🖥️ Report Architecture (Page Breakdown)

The dashboard consists of 4 complementary and strategic views, utilizing a premium **Dark Mode** concept to reduce visual fatigue and maximize readability:

### 1. Overview (Executive View)
* **Objective:** Deliver the main operational and financial KPIs at a single glance for high-level decision-making.
* **Core Metrics:** Total Revenue, Average Ticket, Valid Orders, and Cancellation Rate.
* **UX Highlight:** A collapsible left-side navigation filter panel designed to streamline user experience, allowing quick slicing by Date, Region (State/City), and Product Category without cluttering the main screen.

<img width="1396" height="784" alt="image" src="https://github.com/user-attachments/assets/e998aa1e-3788-4b03-87ed-37403e7ba43f" />

### 2. Time Intelligence (Trend Analytics)
* **Objective:** Pinpoint sales acceleration, peaks, and market seasonality throughout the months of 2025.
* **Handling Missing History:** Implemented a **3-Month Moving Average** to smooth out monthly anomalies and clearly identify macro trends, alongside a running total calculation (**Revenue YTD**).
* **MoM Analysis:** Developed a dynamic Month-over-Month (MoM) column chart with automated conditional coloring (green for growth, red for decline) for immediate performance scanning.
* **Interactivity:** Integrated a native *"Switch View"* toggle button using field parameters/bookmarks, allowing users to alternate between bar and line chart formats for Revenue vs. Valid Orders.

<img width="1395" height="784" alt="image" src="https://github.com/user-attachments/assets/14e01f76-66f6-4849-9176-3e6711de6895" />

### 3. Product Analysis (Portfolio Management)
* **Objective:** Evaluate the commercial performance and market share of product categories and individual items.
* **Data Governance & Adaptation:** Turned a data constraint into an analytical asset. Due to the lack of unit price and quantity fields in the raw dataset, the business rule was pivoted to analyze **frequency of occurrence** and average items per order, maintaining the integrity of business insights.
* **Advanced Visuals:** Features a Waterfall Chart to visualize the cumulative impact of each product category on total sales volume, alongside cross-business market analysis.

<img width="1392" height="785" alt="image" src="https://github.com/user-attachments/assets/ea4faa1c-c739-459c-a810-2bfb14d530f2" />

### 4. Customer Analysis (Target & Portfolio Management)
* **Objective:** Cross-examine real revenue against commercial goals and evaluate revenue concentration.
* **Advanced Matrix Reporting:** Built a context-rich, modern table visual leveraging Power BI’s latest features, including embedded **Sparklines** for individual customer sales trends and **Status Indicators (KPI flags)** for target achievement levels.
* **Pareto / ABC Curve Concept:** Utilized a Customer Revenue Rate chart to map financial dependency risks and identify top-tier accounts.

<img width="1396" height="785" alt="image" src="https://github.com/user-attachments/assets/f39d9146-f6bc-4c38-a9dd-2ea9cafc6bc6" />


## 📐 Data Modeling & Architecture

The back-end database schema was engineered strictly around standard corporate data warehousing principles to guarantee sub-second query performance and robust maintenance.

<img width="1254" height="785" alt="image" src="https://github.com/user-attachments/assets/e03b4452-ab22-442d-a772-0c9123d1c093" />

*(Note: Ensure you upload your model image to your GitHub repository and update this URL if necessary)*

### 1. Robust Star Schema Design
The project maps dimension tables (`dim_date`, `dim_user`, `dim_items`) directly into operational fact tables. This decoupled topography ensures clear calculation paths and optimized database querying.

### 2. Dual-Fact Architecture (Resolving Granularity Conflict)
* **The Constraint:** The transactional dataset possessed an inherent granularity conflict. The `revenue` metric was strictly recorded at the unique order header level. Propagating total revenue down into a single item-level table would artificially multiply and heavily distort the absolute sales metrics.
* **The Solution:** Engineered a segregated dual-fact architecture:
  * `fact_orders`: Captures singular order headers, maintaining accurate overall revenue figures, user mappings, and cancellation states.
  * `fact_order_items`: Captures itemized product rows nested within each master order.

### 3. Proxy Analytics for Missing Metrics
Due to the complete absence of unit price or individual item volume records, `fact_order_items` was strategically leveraged as an alternative analytics engine. Business indicators were calculated using **item frequency of occurrence** and **transactional volume distributions**, successfully delivering operational clarity despite baseline schema constraints.

### 4. Conformed Dimensions (Preventing Many-to-Many Mappings)
Cross-filtering workflows between `fact_orders` and `fact_order_items` flow safely through conformed dimensions (`dim_date` and `dim_user`). This setup forces traditional $1:*$ relationships, intentionally **eliminating complex Many-to-Many ($*:*$) dependencies** or bidirectional performance drops.

### 5. Denormalized 1:1 Target Integration
Commercial goals were integrated directly into the `dim_user` structure. Because the business goals were provided as fixed baseline numbers per client (lacking monthly variance or historical shifts), merging them via a clean $1:1$ architecture streamlined model footprint size and lowered DAX processing overhead.

### 6. Dynamic Visual Slicing (Disconnected Parameter Tables)
The model leverages a disconnected parameter schema (`Exhibition mode`). This advanced configuration stores metadata fields and values completely independent of the core schema. It serves as an isolated toggle engine, letting users switch entire visual fields dynamically without triggering heavy data modifications.

### 7. Governance Focused Measure Containers (`_Measures`)
To enforce strict deployment standards and keep physical tables organized, all calculation logic is completely isolated from physical fields. A specialized, clean folder container hosts all functional DAX indicators, establishing a neat single source of truth.


## 🛠️ Tech Stack & Applied Concepts

* **Advanced DAX:** Built dynamic Time Intelligence measures (`YTD`, `3-Month Moving Average`, `Month-over-Month %`).
* **UX/UI Design:** Fluid button navigation, a cohesive color palette (Yellow/Dark Theme), strict typography hierarchy, and clean horizontal button slicers.
* **Data Constraint Problem-Solving:** Applied tailored business logic to extract maximum strategic value from datasets with missing dimensions or structural limits.
* **Field Parameters:** Dynamic metric switching to boost report interactive flexibility without compromising model processing performance.

## 🚀 How to View the Project

1. You can download and execute the power bi file.
2. Move seamlessly between the four analytical pages using the custom navigation menus located on the top and side panels.

Developed with analytical excellence by **Gustavo Klein**. Connect with me on [LinkedIn](https://www.linkedin.com/in/gustavokleindata/).
