# Marketing Campaign Performance Analysis & Optimization

*(Evaluating Ad Effectiveness through Campaign Analytics & Insights)*

---

## Introduction:
The business has executed several campaigns across **Email, SEO, Display Ads, and Social Media** channels.  
Each campaign had a defined budget and generated impressions, clicks, and conversions.  
This project aims to evaluate campaign effectiveness, forecast ROI, and deliver actionable marketing insights.

---

## Problem Statement:
Despite running multiple campaigns across various digital channels, it's unclear which campaigns are most effective at generating conversions relative to cost and impressions.  
We need to assess overall campaign performance and uncover optimization opportunities, levers model future ROI trends.

---

## Objectives:
- Identify top-performing campaigns by **CTR**, **CR**, and **cost-effectiveness**  
- Rank campaigns using custom KPIs (e.g., **CR/Cost** or **CR × CTR**)  
- Understand discrepancies between engagement (CTR) and actual conversions (CR)  
- Build and evaluate a machine learning regression model to forecast ROI and conversion performance. 
- Compute and interpret Linear Regression coefficients and Mean Absolute Error (MAE) for model accuracy. 
- Develop automated scripts for recurring analysis and reporting.
- Generate **actionable insights and recommendations**  

---

## Dataset Handling:

### Raw Data:
The full datasets used in this project are **not stored in this repository** (due to file size and confidentiality).  
They consist of **2 years of marketing campaign data**, split into two CSV files.

### Sample Data:
For reference and reproducibility, **sample slices (a few rows)** will be included in `/data/sample/`.  
These samples are only for structure and schema validation, **not for full analysis**.

### Reproducibility:
All cleaning, feature engineering, and analysis steps are implemented in scripts (under `/scripts/` and `/notebooks/`).  
Anyone with access to the full dataset can reproduce the results by running these scripts.

### Data Access:
Full raw datasets are stored separately:  
- Currently stored **locally**  
- Will be moved to **cloud storage (Google Drive)** in the future  
- Access may be shared **privately upon request** (still in progress)  

---

## Documentation:

- [**Data Dictionary**](docs/data_dictionary.md): Detailed overview of dataset fields, types, and descriptions  
- [**Data Documentation**](docs/data_documentation.md): Project-level documentation covering data sources, assumptions, and workflow

---

## Project Approach:

| Step | Description |
|------|--------------|
| **1. Data Ingestion** | Load raw datasets, standardize headers, and validate schema. |
| **2. Data Quality & Cleaning** | Handle missing values, duplicates, and inconsistent date formats. |
| **3. Feature Engineering** | Compute derived KPIs (CTR, CR, CPC, ROI) and campaign-level aggregates. |
| **4. Exploratory Data Analysis (EDA)** | Visualize KPI distributions, identify outliers, correlations, and channel trends. |
| **5. Data Transformation & Modeling (dbt)** | the dbt layer in this project ensures that ML models operate on validated, production-grade data, improving reliability, interpretability, and long-term scalability of the analytics pipeline. |
| **6. Regression & Forecasting** | Build predictive models (Linear Regression) to forecast ROI, measure coefficients, and calculate MAE for performance evaluation. |
| **7. Automation Scripts** | Develop modular Python scripts to run each pipeline stage automatically (e.g., `data_cleaning.py`, `feature_engineering.py`, `ml_forecast.py`). |
| **8. Reporting** | Generate executive summaries, charts, and insight-ready visuals for stakeholders. |

---
## Data Transformation & Modeling (dbt)
after features preparation and EDA in python, this project will use dbt (data build tool) as an analytics engineering layer for further Transformation and testing in order to standardize, validate, and productionize teh dataset before machine learning and reporting.

Utilization of duckdb as Local analytical warehouse storing transformed datasets for this project.

| Step | Description |
|------|-------------|
| **1. Staging Models** | Ingest cleaned CSV outputs into DuckDB and standardize column names, data types, and formats. |
| **2. Intermediate Models** | Apply reusable business rules, deduplication logic, filtering, and intermediate aggregations. |
| **3. Gold Models** | Produce analytics-ready datasets and KPIs (CTR, CR, CPC, ROI) for modeling and reporting. |
| **4. Data Quality Tests** | Enforce constraints such as `not_null`, `unique`, accepted values, and schema validation. |
| **5. Documentation & Lineage** | Automatically generate model documentation and lineage graphs via `dbt docs`. |
| **6. ML Data Source** | Serve dbt gold tables as the single source of truth for machine learning pipelines. |


---
## Machine Learning & Forecasting:
The analytical modeling component of this project focuses on building a predictive regression pipeline to forecast campaign performance metrics such as ROI and conversion rate.

| Task | Detail |
|------|--------|
|Model Type |	Linear Regression (baseline predictive model) |
|Targets |	ROI, Conversions, and CR per campaign |
|Features|	Impressions, Clicks, spend_usd, CTR, Channel Type, and Campaign Duration |
|Evaluation Metrics |	Mean Absolute Error (MAE), R² Score, Residual Analysis |
|Interpretability |	Linear Regression Coefficients to understand variable influence |
|Automation |	Implemented as modular script ml_forecast.py under /scripts/ |
|Output |	Predicted ROI trends and channel-level performance forecasts |


-The model provides a quantifiable, interpretable understanding of which features most impact campaign performance, enabling marketing teams to optimize spend allocation proactively.

---

## Tools & Technologies Used:

| Category | Tools / Libraries |
|-----------|-------------------|
| **Languages** | Python |
| **Libraries** | pandas, numpy, matplotlib, seaborn, scikit-learn|
| **Modeling & Forecasting** | Linear Regression, MAE evaluation metrics, LR Coef |
| **Data Storage** | CSV, Local |
| **Version Control** | Git, GitHub |
| **Transformation** | dbt |
| **Warehouse** | duckdb |
| **Development Environment** | Jupyter lab/Notebook, Git(CLI) |
| **Automation & Workflow** | PowerShell, Python scripts |
| **Documentation** | Markdown, GitHub, GitHub Projects |
| **Visualization** | Matplotlib, Seaborn, Plotly |

---

## Repository Contents Overview:

| Folder | Description |
|:--------|:-------------|
| [**docs/**](./docs) |  Project documentation including data dictionary, pipeline design, and methodology notes. |
| [**data/**](./data) |  Contains all datasets used in this project. Includes **sample raw data** and **processed outputs** for analysis and modeling. |
| [**notebooks/**](./notebooks) |  Jupyter notebooks covering each stage of the project: data ingestion, cleaning, quality checks, feature engineering, and exploratory data analysis (EDA). |
| [**scripts/**](./scripts) |  Python scripts for data processing, transformations, and automation tasks derived from notebook workflows. |
| [**reports/**](./reports) |  Generated reports and visual summaries, including key findings and analytics insights. |
| [**.gitignore**](./.gitignore) |  Specifies intentionally untracked files to be ignored by Git (e.g., large data files, checkpoints, credentials). |
| [**README.md**](./README.md) |  The main documentation file providing overview, structure, and setup instructions. |

---

Repository Structure:

<pre>marketing_campaign_analysis/
├── docs/
│   ├── data_dictionary.md
│   └── data_documentation.md
│
├── warehouse/
│	└── marketing_warehouse.duckdb
│
├── data/
│   ├── raw
│   │	├── marketing_campaign_2024_sample
│   │	├── marketing_campaign_2025_sample
│   │	└── marketing_campaign_jul_dec_2024
│   ├── processed
│	├── marketing_campaign_2024_raw_labeled
│	├── marketing_campaign_2025_raw_labeled
│	├── marketing_campaign_all_interim
│	├── marketing_campaign_2024_clean
│	├── marketing_campaign_2025_clean
│  	├── marketing_campaign_2024_2025_processed
│ 	└── marketing_campaign_all_clean
│ 
├── notebooks/
│   ├── 01_data_ingestion.ipynb
│   ├── 02_data_quality.ipynb
│   ├── 03_data_cleaning.ipynb
│   ├── 04_feature_engineering.ipynb
│   ├── 05_EDA.ipynb
│   ├── 06_visualizations.ipynb
│   └── 07_mlmodeling.ipynb
│
├── dbt/
│   ├── models
│   │   ├── staging
│   │   ├── intermediate
│   │   └── gold
│   └── dbt_project.yml
│ 
├── scripts/
│   ├── data_cleaning.py
│   ├── feature_engineering.py
│   ├── eda.py
│   └── ml_forecast.py
│
├── reports/
│   ├── executive_summary.md
│   └── final_report.pdf
│
├── .gitignore
│ 
└── README.md</pre>




---

## Next Steps:

- [x] Set up `README.md`  
- [x] Set up `.gitignore`  
- [x] Create branches: **main** and **dev**  
- [x] Create Dictionary & Data Documentation
- [x] Configure project management: **Kanban and Tasks**  
- [x] Load raw data into `/data/`  
- [x] Perform initial data quality checks (`notebooks/01_data_quality.ipynb`) 
- [x] Perform Data Cleaning 
- [x] Develop feature engineering pipeline  
- [ ] Conduct EDA 
- [ ] build visualizations (Draft insights + recommendation)
- [ ] ML Modeling
- [ ] Forecasting
- [ ] Reporting (Final Report & Executive Summary)

---






