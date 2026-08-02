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


## 🛠️ Tech Stack & Applied Concepts

* **Advanced DAX:** Built dynamic Time Intelligence measures (`YTD`, `3-Month Moving Average`, `Month-over-Month %`).
* **UX/UI Design:** Fluid button navigation, a cohesive color palette (Yellow/Dark Theme), strict typography hierarchy, and clean horizontal button slicers.
* **Data Constraint Problem-Solving:** Applied tailored business logic to extract maximum strategic value from datasets with missing dimensions or structural limits.
* **Field Parameters:** Dynamic metric switching to boost report interactive flexibility without compromising model processing performance.


## 🚀 How to View the Project

1. You can download and execute the power bi file.
2. Move seamlessly between the four analytical pages using the custom navigation menus located on the top and side panels.

Developed with analytical excellence by **Gustavo Klein**. Connect with me on [LinkedIn](https://www.linkedin.com/in/gustavokleindata/).
