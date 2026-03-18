# 🔬 Semiconductor Supply Chain Performance Analysis
 
![Excel](https://img.shields.io/badge/Excel-Data%20Cleaning-green)
![Power%20Query](https://img.shields.io/badge/Power%20Query-ETL%20Pipeline-teal)
![SQL](https://img.shields.io/badge/SQL-MySQL-blue)
![Power%20BI](https://img.shields.io/badge/Power%20BI-Dashboard-yellow)
 
---
 
## 💡 What Is This Project About?
 
Imagine you are the head of supply chain at a semiconductor company. Every month, crores of rupees go out to suppliers — but costs keep rising, products keep failing quality checks, and shipments keep arriving late. Leadership is asking hard questions, and no one has clear answers.
 
**This project is the answer.**
 
Using real procurement data of **200 orders across 5 suppliers, 5 cities, and 3 product categories**, I built a complete analytics solution that investigates where the money is going, which suppliers are responsible for cost overruns, and what the business needs to do differently.
 
The entire project was built using **Excel → Power Query → Power BI → SQL** — the same toolkit used by data analysts at companies like Deloitte, Accenture, Infosys, and Tata.
 
---
 
## ❓ The Business Questions This Project Answers
  
---
 
### 💸 "Why is our supply chain cost high, and which suppliers are responsible for it?"
 
The total procurement spend was **₹23.47 lakhs** against a revenue of **₹29.36 lakhs** — meaning for every ₹100 earned, ₹80 went back out as cost. That is a dangerously thin margin.
 
The investigation revealed that **just 2 out of 5 suppliers (S4 and S5) consumed 57% of the entire procurement budget** — ₹13.48 lakhs between them. These are not small vendors; they are the core of the supply chain. But the data shows they are not earning that position.
 
---
 
### 📈 "Why are procurement costs increasing, and how can supplier performance be optimized?"
 
Costs are concentrated, not distributed. S5 alone accounts for **31.7% of all procurement spend**, yet it delivers the **worst quality** in the portfolio. There is no volume discount effect — cost scales linearly with quantity ordered, meaning the business is not negotiating better rates as it buys more.
 
The fix is clear: **renegotiate contracts with S4 and S5**, set measurable quality SLAs, and shift a portion of orders to S3 — the supplier that delivers faster and with fewer defects at a lower cost.
 
---
 
### 🏆 "Which suppliers are helping us grow, and which are hurting efficiency?"
 
| Supplier | Revenue Generated | Defect Rate | Avg Lead Time | Verdict |
|---|---|---|---|---|
| S1 | ₹3.08 L | 2.91% | 28.7 days | Neutral |
| S2 | ₹5.77 L | 3.20% | 28.6 days | Watch |
| S3 | ₹3.66 L | 2.90% | 26.8 days | ✅ Best Performer |
| S4 | ₹7.59 L | 3.22% | 29.6 days | ❌ High Risk |
| S5 | ₹9.27 L | 3.23% | 29.2 days | ❌ High Risk |
 
**S3 is the hidden gem** — fastest delivery, lowest defect rate, and lower cost. Yet it receives one of the smallest shares of the procurement budget. **S4 and S5 are the problem** — highest cost, highest defects, and slowest delivery. The business is rewarding the wrong suppliers.
 
---
 
### 🚨 "Where are delays and quality issues occurring in our supply chain?"
 
This was the most alarming finding of the entire project.
 
Out of 200 orders placed, **only 72 passed quality inspection (36%)**. A staggering **87 orders failed (43.5%)**, and 41 are still pending review. Nearly half of all shipments are not meeting quality standards.
 
- **S4 is the slowest supplier** — averaging 29.6 days lead time vs. S3's 26.8 days
- **Microprocessors have the highest failure count** — the most expensive product category is also the most defect-prone
- **Mumbai has the highest procurement cost** (₹6.82 L) but **Bengaluru is the most efficient city** — spending ₹3.01 L to generate ₹3.74 L in revenue
 
---
 
### 💰 "Are we spending more money on suppliers who deliver better performance?"
 
**No — and this is the core problem.**
 
The data shows **zero positive correlation** between how much is spent on a supplier and how well they perform. The two highest-paid suppliers (S4 and S5) rank last on both quality and delivery speed. The best performer (S3) is underfunded. The business is paying a premium for underperformance.
 
---
 
## 📊 Project At a Glance
 
| Metric | Value |
|---|---|
| Total Orders Analyzed | 200 |
| Total Revenue | ₹29.36 Lakhs |
| Total Procurement Cost | ₹23.47 Lakhs |
| Suppliers Evaluated | 5 (S1 to S5) |
| Manufacturing Locations | 5 Cities |
| Product Categories | 3 (Microprocessors, Sensors, Logic ICs) |
| Orders That Failed Inspection | 87 out of 200 (43.5%) |
| Average Lead Time | 28.7 Days |
| Overall Defect Rate | 3.09% |
| Time Period | January – July 2025 |
 
---
 
## 🗂️ What Data Was Used?
 
The dataset contains **15 columns** covering the complete order-to-inspection lifecycle of a semiconductor supply chain:
 
- **Order Info** — Order ID, Date, SKU, Product Type, Quantity Ordered
- **Supplier Info** — Supplier name, Unit Cost, Total Cost
- **Delivery Info** — Supplier Lead Time, Manufacturing Lead Time, Average Lead Time
- **Quality Info** — Inspection Result (Pass / Fail / Pending), Defect Rate %
- **Financial Info** — Revenue and Total Cost per order
- **Location** — Which of the 5 cities received the order
 
---
 
## 🛠️ How Was This Project Built?
  
### Stage 1 — Excel : Cleaning the Raw Data
Before any analysis could happen, the raw data had to be made reliable. In Excel:
- Scanned all 200 rows for missing values, duplicates, and formatting errors
- Verified that no Order IDs were repeated and that all dates were in the correct format
- Checked that calculated fields like Total Cost matched the formula (Quantity × Unit Cost)
- Built summary Pivot Tables to cross-check supplier totals and inspection counts before moving forward
 
### Stage 2 — Power Query : Building the Data Pipeline
Power Query was used to create a clean, repeatable transformation process (like a mini data factory):
- Assigned correct data types to every column to prevent calculation errors
- Removed hidden spaces and inconsistent text formatting across supplier and location names
- Created new calculated columns: Gross Margin, Lead Time Band (Fast / Average / Slow), Quality Flag (High Risk / Acceptable), and Month-Year for time-series analysis
- Loaded the final clean dataset into Power BI for visualization
 
### Stage 3 — Power BI : Building the Dashboard
A three-page interactive dashboard was built to tell the supply chain story visually:
- **Page 1 (Executive Overview)** — KPI cards, revenue vs. cost by supplier, inspection donut chart, monthly revenue trend
- **Page 2 (Supplier Scorecard)** — Scatter plot to identify the best and worst suppliers, cost contribution breakdown, SKU coverage comparison
- **Page 3 (Location & Product View)** — City-level efficiency map, revenue by product type, cost-to-revenue ratio table
- All pages are connected with slicers so any stakeholder can filter by supplier, city, product, or month
 
### Stage 4 — SQL (MySQL) : Deep-Dive Querying
35 business questions were answered using MySQL queries, ranging from basic to advanced:
- **Basic** — Total orders, total cost, best and worst suppliers by revenue
- **Intermediate** — Month-wise trends, defect rate comparisons, lead time rankings
- **Advanced** — Window functions to rank suppliers, calculate running totals, find the top supplier within each product category, and flag vendors with high cost AND high defect rate simultaneously
 
---
 
## 📈 Dashboard Highlights
 
- **KPI Cards** — Instant snapshot of Revenue, Cost, Orders, Lead Time, and Defect Rate
- **Scatter Plot** — Shows which suppliers are in the "ideal zone" (fast delivery + low defects) and which are in the danger zone
- **Donut Chart** — Visually reveals the 43.5% inspection failure rate at a glance
- **Monthly Trend Line** — Tracks the revenue drop from March peak (₹5.42 L) to July low (₹2.46 L)
- **City Efficiency Table** — Ranks all 5 locations by cost-to-revenue ratio with data bars
- **Interactive Slicers** — Any stakeholder can filter the entire dashboard by supplier, city, product, or time period
 
---
 
## 💡 Key Findings
 
1. **The business is overpaying for underperformance.** S4 and S5 get the most money but deliver the worst quality and the slowest shipments.
2. **Nearly half of all orders are failing quality checks.** 87 out of 200 orders failed inspection — this is not a small problem, it is a company-wide risk.
3. **S3 is the best supplier nobody is investing in.** It is the fastest, cleanest, and most reliable — but receives a fraction of the budget that S4 and S5 receive.
4. **Microprocessors are both the biggest revenue source and the biggest quality risk.** The category generating 60% of revenue has the highest failure rate.
5. **Bengaluru runs the most efficient operation.** Every rupee spent there generates more revenue than any other city in the network.
6. **Revenue is falling fast in the second half of 2025.** From ₹5.42 L in March to ₹2.46 L in July — a 55% drop that needs urgent investigation.
 
---
 
## 🚀 What Should the Business Do Next?
 
1. **Renegotiate with S4 and S5** — tie contract renewals to quality SLA targets (max 3.0% defect rate, max 28-day lead time)
2. **Increase orders to S3** — it is the only supplier delivering speed, quality, and value simultaneously
3. **Fix the inspection failure crisis** — 43.5% fail rate means hidden rework costs that are not visible in the headline numbers
4. **Investigate the July revenue drop** — a 55% fall in four months is a demand signal that needs a root cause analysis
5. **Replicate the Bengaluru model** — study what that location does differently and apply it to Mumbai and Coimbatore
 
---
 
## 🧠 What Skills Does This Project Demonstrate?
 
| Area | What Was Done |
|---|---|
| Data Cleaning | Deduplication, type formatting, formula validation, Pivot cross-checks in Excel |
| Data Transformation | ETL pipeline in Power Query with derived columns and conditional logic |
| SQL Querying | 35 queries across basic aggregation, subqueries, date functions, and window functions |
| Data Visualization | 3-page Power BI dashboard with 15+ visual types and DAX measures |
| Business Thinking | Translated raw data into a cost story with supplier verdicts and actionable recommendations |
| Communication | Structured insights for non-technical stakeholders in plain, decision-ready language |
 
---
 
## 🤝 Connect With Me
 
- I would love feedback, suggestions, or discussions around data analytics, supply chain, and BI projects
- Feel free to connect or explore more of my work on GitHub
 
