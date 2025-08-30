# Customer Retention & Cohort Analysis (SQL + Tableau)

## Project Overview
This project analyzes customer retention using the **[Online Retail II dataset](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci)**.  
I built a SQL data pipeline in DuckDB to transform raw online shopping data into a clean analytical tables, and then created an interactive Tableau dashboard to view cohort retention and key business KPIs.

**Business / Learning Question:**  
How do customer cohorts behave over time, and where does churn occur?

---

## Tools & Skills
- **SQL (DuckDB):** staged, cleaned, and modeled tables 
- **Python (Jupyter):** SQL execution, double check data, CSV export  
- **Tableau Public:** cohort retention heatmap, retention curves, KPI trendlines, dashboard storytelling  

---

## Project Structure
    project-root/
    │── data/                   
    │   │── raw/                        # Original Data Set
    │   │── processed/                  # Exported Tables for Tableau
    │       │── retention_monthly.csv 
    │       │── kpit_timeseries.csv 
    │── retention-project.ipynb           # Jupyter Notebooks with SQL pipeline
    │── deliverables
    │   │── dashboard.png               # Dashboard Screenshot
    │   │── executive_summary           # Brief Summary of findings
    │── README.md                       # Project documentation (this file)
    │── requirements.txt                # Python dependencies


## Pipeline Steps
1. **Raw Staging:** load CSV → `base_table`  
2. **Cleaned Table:** clean + enrich → `real_table`  
   - dropped null customer IDs
   - calculated revenue and month markers
3. **Retention Table:** cohort definitions → `cohort_ret_metrics`  
   - first purchase month = cohort_month  
   - calculated retention % by cohort & months since purchase  
4. **KPI Table:** overall active users & revenue → `kpi_timeseries`  
5. **Export:** CSVs for Tableau processing and presentation

---

## Tableau Dashboard
👉 [View Interactive Dashboard on Tableau Public](https://public.tableau.com/views/RetentionProject-Dashboard/CustomerRetentionKPIOverview?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

**Dashboard Features:**
- **Cohort Heatmap:** rows = cohort months, columns = months since first purchase, color = retention %  
- **Retention Curves:** cohort-by-cohort retention drop-off trends  
- **KPI Trends:** active customers and revenue over time  
- **Executive Summary:** key insights on customer churn  

![Dashboard Screenshot](deliverables/dashboard.png)

---

## Key Insights
- **Month 1 drop-off:** ~80% of customers churn after the first month  
- **By Month 3:** average retention steadies at 15-20%  
- **Cohort comparison:** newer cohorts did not retain better than older ones
- **Revenue trend:** rising revenue and new users were powered by new aquisitions, not more retention

---

## Executive Summary
Customer retention analysis reveals that the majority of churn occurs immediately after the first purchase. 
Across cohorts from 2009-2011, retention of customers after their first month of purchase falls to about 20% by the second month. After 3 months retention stabilizes at around 10-15%. New cohorts did not retain better than earlier ones, suggesting growth was driven more by acquisition than loyalty. 
These findings indicate that onboarding customers into being repeat shoppers, and early re-engagement strategies, would likely have the greatest impact on long term customer retention. 

---
