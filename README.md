# Mohammed Khafagy

**Data Warehouse Architect | SQL Specialist | Analytics Developer**

📍 Damietta, Egypt | 📧 mohammedkhafagy045@gmail.com | 📱 +20 10 2739 2515

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat)](https://www.linkedin.com/in/mohammed-khafagy-7559aa272) 
[![GitHub](https://img.shields.io/badge/View%20Code-Explore-181717?style=flat)](https://github.com/mohammedkhafagy752000?tab=repositories)

---

## 💡 About Me

I design SQL Server data warehouses, build Python ETL pipelines, and develop real-time analytics systems. My focus: solving operational problems with schema architecture, query optimization, and automation—not just dashboards.

**Core Expertise:** Star Schema Design • Window Functions & CTEs • ETL Pipelines • Real-Time BI • Performance Optimization

---

## 🎯 Featured Projects

### **🥇 Logistics End-to-End Data Warehouse**
**Repository:** [`Logistics-End-to-End-Data-Warehouse-Project`](https://github.com/mohammedkhafagy752000/Logistics-End-to-End-Data-Warehouse-Project)

**The Business Problem:**
Fleet operations reported strong profitability but suffered from a critical operational failure: only 29.8% of orders were delivered on time (vs. 90% industry standard). The root cause was unknown, and management couldn't identify which operational factors were driving delays.

**What I Discovered:**
Through deep SQL analysis, I identified that the average detention time (time between pickup and delivery) was **183 minutes per trip**—revealing that warehouse delays, not routing inefficiency, were the primary cause. This single insight directly implied a solution: improve warehouse processes.

**What I Built:**

**Data Architecture:**
- **OLTP Database:** 14 normalized tables capturing trips, drivers, trucks, routes, maintenance, and incidents
- **Data Warehouse:** Star Schema with 4 Fact Tables (Trips, Fuel, Maintenance, Incidents) + 8 Dimension Tables
- **SCD Type 2 Implementation:** Historical tracking of dimension changes with `Is_Current` flag
- **Date Dimension:** Generated using T-SQL WHILE LOOP (2020-2030) with day names, quarters, weekend flags

**Advanced Analytics:**
- Window Functions: LAG/LEAD for driver performance trend detection, RANK/DENSE_RANK for regional benchmarking
- PIVOT for quarterly revenue analysis
- Role-playing dimensions (Facility as both Origin and Destination)
- Complex aggregations combining multiple fact tables

**Key Insights Uncovered:**

| Finding | Data Point | Business Implication |
|---------|-----------|----------------------|
| **Detention Time** | 183 min avg per trip | Direct actionable fix: optimize warehouse operations |
| **On-Time Delivery Gap** | 29.8% vs 90% standard | 60% improvement opportunity if detention resolved |
| **Incident Costs** | $840K+ from 60 incidents | ROI on driver training program justified |
| **Regional Concentration** | Texas & Washington = highest revenue | Geographic expansion into underserved regions |
| **Profitability Anomaly** | 67% profit ratio (unusual) | Possible incomplete cost allocation; deeper audit needed |

**Business Value:**
- Root cause identified (warehouse, not routing) enables targeted operational fix
- $840K incident cost justifies training investment
- Revenue concentration data guides expansion strategy

**Why This Project:**
Demonstrates data warehouse architecture design, complex ETL logic, and analytical rigor. Shows ability to move beyond dashboards and uncover root causes.

---

### **🥈 Walmart Retail Analytics - Real-Time Dashboard**
**Repository:** [`walmart-retail-analytics`](https://github.com/mohammedkhafagy752000/walmart-retail-analytics)

**The Business Problem:**
Retail chain with 100 branches had no real-time visibility into store performance. Daily reports were slow, offline analysis missed temporal patterns, and management couldn't make rapid decisions on staffing or inventory.

**What I Discovered:**
Peak transaction activity concentrated in a narrow 2-hour window: 3:00 PM (~1,190 transactions) and 4:00 PM (~1,150 transactions). This window alone represented 46% of daily transaction volume—meaning understaffing during these hours directly drove customer wait times and incomplete sales.

**What I Built:**

**ETL Pipeline:**
- Python (Pandas): Imported Walmart sales data, removed duplicates, handled nulls, validated transaction totals
- SQLAlchemy + PyODBC: Real-time connectivity to SQL Server for dynamic dashboard refresh
- Data Validation: Duplicate detection, revenue recalculation verification, integrity checks

**Real-Time Analytics System:**
- **Streamlit App:** 389-line interactive dashboard with dynamic branch filtering
- **SQL Analytics:** 5 advanced queries using CTEs for revenue aggregation, DATEPART for hourly bucketing, RANK for branch performance
- **Visualizations:** 5 Plotly charts (category revenue, payment distribution, peak hours trend, branch ranking, ratings)
- **KPI Cards:** Total Revenue, Transaction Count, Average Customer Rating

**Key Discoveries:**

| Discovery | Evidence | Business Action |
|-----------|----------|------------------|
| **Peak Hours Concentrated** | 3-4 PM = 46% of daily volume (~2,340 trans) | Increase staff 50% during 2-5 PM window |
| **Payment Preference Shift** | E-wallet 40.4% vs Credit Card 37.8% | Prioritize e-wallet infrastructure investment |
| **Top Branch Benchmark** | WALM017: $180 avg basket (+45% above mean) | Replicate WALM017 operations across underperformers |
| **Revenue Concentration** | $1.21M across 100 branches, 9,969 transactions | Identify and support underperforming locations |

**Dashboard Preview:**

<p align="center">
  <img src="walmart_Dashboard.png" width="1000" alt="Walmart Retail Analytics Dashboard">
</p>

**Features Shown:** KPI cards (Revenue, Transactions, Rating) • Peak hours visualization • Payment method distribution • Branch performance ranking • Category revenue breakdown

**Business Value:**
- Peak hour staffing optimization: estimated 15-20% labor cost reduction
- Payment infrastructure guidance: justifies e-wallet tech investment
- Branch benchmarking: enables performance management across network

**Why This Project:**
Full-stack analytics capability: Python ETL → SQL analytics → real-time Streamlit dashboard. Demonstrates modern data engineering and production-quality BI system.

---

### **🥉 E-Commerce Business Intelligence Analytics**
**Repository:** [`E-Commerce-Business-Intelligence-Analytics-Project`](https://github.com/mohammedkhafagy752000/E-Commerce-Business-Intelligence-Analytics-Project)

**The Business Problem:**
E-commerce platform with 54,000 orders ($7.4M revenue) lacked integrated analytics. Decision-makers couldn't identify revenue drivers, regional performance variations, or growth trends. Data was fragmented across CSV files.

**What I Discovered:**
2 product categories—Health & Beauty (25.26%) and Watches & Gifts (23.19%)—drove nearly half (48.45%) of total revenue. This concentration revealed an immediate opportunity: focus inventory and marketing investment on these categories while investigating underperformers for discontinuation or bundling.

**What I Built:**

**Star Schema Data Warehouse:**
- **Fact Table:** FACTOrders (sales transactions, quantities, payment values)
- **Dimension Tables:** DMCustomers, DMProducts, DMCategories, DIM_DATE, DMSellers, DMGeolocation
- **Optimization:** Surrogate keys for performance; schema designed for OLAP (read-optimized)

**ETL & Data Cleaning:**
- Imported 6 CSV datasets using T-SQL BULK INSERT
- Removed duplicates: ROW_NUMBER() PARTITION BY on customer IDs
- Handled missing values: Geographic averaging (AVG latitude/longitude), placeholder ZIP codes (9999)
- Large text handling: NVARCHAR(MAX) for customer reviews

**BI Dashboard:**
- Power BI with DAX measures for KPI calculations
- Multi-dimensional analysis: Product categories, Geographic regions, Time periods
- Interactive drill-through for stakeholder exploration

**Key Insights:**

| Finding | Data | Business Recommendation |
|---------|------|------------------------|
| **Revenue Concentration** | 2 categories = 48.45% | Prioritize inventory for Health & Beauty, Watches & Gifts |
| **Growth Momentum** | Sales +28.5%, Orders +29.1%, Payments +29.7% | All metrics trending upward; strong business health |
| **Geographic Risk** | São Paulo = $14M+ (40%+ of revenue) | Diversification strategy needed; explore other regions |
| **Customer Satisfaction** | 4.0 / 5 average rating | Quality baseline maintained; focus on consistency |
| **Delivery Efficiency** | 99% success rate, 5-day average | Logistics performing well; maintain current standards |

**Dashboard Preview:**

<p align="center">
  <img src="Ecommerce_Dashboard.png" width="1000" alt="E-Commerce Power BI Dashboard">
</p>

**Features:** Category performance ranking • Regional sales heatmap • Growth trend analysis • Payment method breakdown • Delivery efficiency metrics

**Business Value:**
- Category strategy: Concentrate inventory on top 2 categories
- Geographic expansion: Identify underserved regions for growth
- Performance baseline: 99% delivery sets operational standard

**Why This Project:**
Complete BI pipeline: Raw data → Star Schema → Power BI dashboard. Demonstrates SQL expertise, data modeling, and business insights communication.

---

## 🧠 Advanced Analytics & Research

### Time-Series Forecasting & Deep Learning (Master's Research)

**Research Focus:** Commodity price prediction using event-aware neural networks

**Problem:** Traditional forecasting models miss the impact of supply disruptions, geopolitical events, and market shocks. Can deep learning capture these complex temporal patterns?

**Models Developed:**
- **LSTM (Long Short-Term Memory):** Captures long-range dependencies in price sequences
- **CNN (Convolutional Neural Networks):** Detects momentum and pattern changes
- **Hybrid Architecture:** Combines domain expertise (lagged prices, trading volume) with deep learning

**Technical Approach:**
- Feature Engineering: Time-based lags, rolling averages, event-based signals
- Evaluation Metrics: MAE, RMSE, MAPE for forecast accuracy assessment
- Validation Strategy: Time-series split (avoid future data leakage)
- Implementation: Python + TensorFlow/Keras

**Business Application:**
Enables accurate commodity price forecasting for supply chain planning and procurement strategy. Reduces forecasting error compared to baseline models.

**Status:** Active Master's thesis research

---

## 🛠 Technical Skills

**SQL & Data Warehousing:**
- T-SQL: Window Functions (LAG, LEAD, RANK, DENSE_RANK, ROW_NUMBER), CTEs, PIVOT, complex aggregations
- SQL Server: Database design, Star Schema architecture, query optimization, indexing strategy
- ETL: BULK INSERT, data validation, referential integrity, SCD Type 2 implementation
- Performance: Query optimization, execution plan analysis

**Python & Data Engineering:**
- Pandas: Data cleaning, transformation, missing value handling, duplicate removal
- SQLAlchemy + PyODBC: Database connectivity, dynamic SQL query generation, connection pooling
- TensorFlow/Keras: Deep learning model development (LSTM, CNN)
- Jupyter Notebooks: Exploratory analysis, documentation, reproducible research

**Business Intelligence:**
- Power BI: DAX measures, Power Query transformations, interactive dashboards, drill-through analytics
- Streamlit: Web application development, real-time data refresh, interactive filtering
- Plotly: Interactive visualizations (line, bar, pie, heatmap)
- Excel: Pivot Tables, Power Pivot, advanced formulas

**Analytics & Problem-Solving:**
- KPI definition and calculation
- Root cause analysis (identifying detention time in logistics)
- Gap analysis (identifying revenue concentration)
- Multi-dimensional analysis (geographic, temporal, categorical)
- Data quality validation and business rule enforcement

---

## 💻 Code Samples & Technical Depth

See implementation details in repositories:

- **Star Schema Design:** [E-Commerce DW Creation](https://github.com/mohammedkhafagy752000/E-Commerce-Business-Intelligence-Analytics-Project/blob/main/SQL_Scripts/003_DATAWAREHOUSE%20CREATION.sql)
- **Window Functions & Analytics:** [Logistics Analytical Queries](https://github.com/mohammedkhafagy752000/Logistics-End-to-End-Data-Warehouse-Project)
- **ETL Pipeline:** [Walmart Data Processing](https://github.com/mohammedkhafagy752000/walmart-retail-analytics/blob/main/Dashboard.py)
- **Real-Time Dashboard:** [Streamlit Implementation](https://github.com/mohammedkhafagy752000/walmart-retail-analytics/blob/main/Dashboard.py)

---

## 📚 Education

**Master of Computer Science** (Data Science Specialization)  
Damietta University | Oct 2022 – Present  
**Focus:** Time-series forecasting, deep learning, event-aware predictive systems

**Bachelor of Computer Science**  
Damietta University | GPA: 3.34/4.0 | **Top of Class 2022**

---

## 📜 Certifications

- **SQL Advanced** – HackerRank (Feb 2026)
- **Transact-SQL Queries** – Mahara Tech (Feb 2026)
- **Intermediate SQL Server** – DataCamp (Nov 2024)
- **Power BI** – 365 Data Science (Nov 2024)
- **Exploratory Data Analysis in Python** – DataCamp (Nov 2024)
- **Python for Data Science** – Coursera (Aug 2024)

---

## 📊 Portfolio Summary

| Metric | Value |
|--------|-------|
| **Data Analyzed** | 54K orders + 9,969 transactions + logistics trips |
| **Revenue Tracked** | $7.4M + $1.21M = $8.61M+ |
| **Databases Designed** | 3 (E-Commerce DW, Logistics DW, Walmart SQL Server) |
| **SQL Techniques** | Window Functions, CTEs, PIVOT, Star Schema, SCD Type 2 |
| **BI Systems Built** | Power BI dashboard + Streamlit real-time app |
| **Key Insights** | Root causes identified (logistics detention, retail peaks, revenue drivers) |

---

## 👋 Let's Connect

Interested in architecting data systems, optimizing SQL performance, and building BI solutions that drive business decisions.

📧 **Email:** mohammedkhafagy045@gmail.com  
📱 **Phone:** +20 10 2739 2515  
🔗 **LinkedIn:** [Mohammed Khafagy](https://www.linkedin.com/in/mohammed-khafagy-7559aa272)

---
