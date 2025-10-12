# Data Documentation

## Dataset Overview

- **Source:** Internal Marketing Campaign Management System  
- **Coverage:** 2 years (2021–2022)  
- **Files:**  
  - `campaign_data_2021.csv`  
  - `campaign_data_2022.csv`  
- **Volume:** ~500,000 rows per year  
- **Granularity:** Daily campaign-level performance  

---

## Purpose

This dataset is designed to:

- Evaluate marketing campaign effectiveness  
- Analyze cost efficiency (CPC, ROI)  
- Study conversion and engagement trends  
- Support optimization of budget allocation  

---

## Data Structure

The dataset is structured as **tabular data** with:

| Element | Description |
|----------|--------------|
| **Entity** | Marketing campaign |
| **Time Dimension** | Daily records |
| **Measures** | Impressions, clicks, conversions, spend, revenue |
| **Derived Metrics** | CTR, CR, CPC, ROI |

---

## Known Issues & Limitations

- Some missing values in `conversions` and `revenue_usd` columns  
- Date formats need standardization across files  
- ROI not always directly available and must be computed  
- Seasonal effects not explicitly encoded  

---

## Usage Notes

- Always clean and preprocess data before analysis  
- Aggregate by **campaign** or **time period** (weekly, monthly) for insights  
- Use derived KPIs (**CTR**, **CR**, **ROI**) for modeling and optimization tasks  

---

_Last updated: {{today’s date}}_
