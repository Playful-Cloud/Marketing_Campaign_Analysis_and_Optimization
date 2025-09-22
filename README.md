\# Marketing Campaign Performance Analysis \& Optimization

\* (Evaluating Ad Effectiveness through Campaign Analytics \& Insights)



\## Introduction

The business has executed several campaigns across Email, SEO, Display Ads, and Social Media channels. Each campaign had a defined budget and generated impressions, clicks, and conversions. The team wants to better understand the performance dynamics to guide future ad spend.



\##Problem Statement

Despite running multiple campaigns across various digital channels, it's unclear which campaigns are most effective at generating conversions relative to cost and impressions. We need to assess overall campaign performance and uncover optimization opportunities.





Objectives

&nbsp;	• Identify top-performing campaigns by CTR, CR, and cost-effectiveness

&nbsp;	• Rank campaigns using custom KPIs (e.g., CR/Cost or CR × CTR)

&nbsp;	• Understand discrepancies between CTR and CR

&nbsp;	• Generate actionable insights and recommendations


## Dataset Handling

### Raw Data
- The full datasets used in this project are **not stored in this repository** (due to file size and confidentiality).  
- They consist of **2 years of marketing campaign data** split into two CSV files.  

### Sample Data
- For reference and reproducibility, **sample slices** (a few rows) will be included in `/data/sample/`.  
- These samples are only for structure and schema validation, not for full analysis.  

### Reproducibility
- All cleaning, feature engineering, and analysis steps are implemented in scripts (under `/scripts/` and `/notebooks/`).  
- Anyone with access to the full dataset can reproduce the results by running these scripts.  

### Data Access
- Full raw datasets are stored separately.  
- for now locally but in the future on cloud Google Drive.  

In the future access may be shared privately upon request ; )
im still working on it so, im not sharing it yet



## Documentation

- [Data Dictionary](./data_dictionary.md)  
  Detailed overview of dataset fields, types, and descriptions.

- [Data Documentation](./data_documentation.md)  
  Project-level documentation covering data sources, assumptions, and workflow.



\## Repository Structure

Repository Structure:

"""
marketing_campaign_analysis/
├── docs/
│   ├── data_dictionary.md
│   └── data_documentation.md
│
├── data/
│   ├── raw
│   │	└── marketing_campaign_2024_sample
│   │	└── marketing_campaign_2025_sample
│   └── processed
│ 
├── notebooks/
│   ├── 01_data_quality.ipynb
│   ├── 02_feature_engineering.ipynb
│   ├── 03_EDA.ipynb
│   └── 04_visualizations.ipynb
│
├── reports/
│   ├── executive_summary.md
│   └── final_report.pdf
│
├── scripts/
│   ├── data_cleaning.py
│   ├── feature_engineering.py
│   └── eda.py
│
├── .gitignore
│ 
└── README.md
"""


\## 3. Next Steps

\- \[x] set up gitinore

\- \[x] set up Branch: main and dev

\- \[x] set up Project management: Kanban and Tasks

\- \[x] Load raw data into `/data`  

\- \[x] Perform initial data quality checks (`notebooks/01\_data\_quality.ipynb`)  

\- \[ ] Develop feature engineering pipeline  

\- \[ ] Conduct EDA and build visualizations  

\- \[ ] Rank campaigns using KPIs  

\- \[ ] Draft insights + final recommendations  







