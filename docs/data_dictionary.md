# Data Dictionary

This document describes the dataset fields used in the **Marketing Campaign Analysis and Optimization** project.

Two CSVs represent two years of campaign data. Columns are consistent across both files.

---

## Campaign Dataset Fields

| Column Name      | Type          | Description                                                |
|------------------|---------------|------------------------------------------------------------|
| campaign_id      | int / string  | Unique identifier for each marketing campaign.             |
| start_date       | date          | Date when the campaign started.                            |
| end_date         | date          | Date when the campaign ended.                              |
| channel          | string        | Marketing channel (e.g., Email, Social Media, Paid Ads).   |
| impressions      | int           | Number of times the campaign was shown.                    |
| clicks           | int           | Number of clicks received.                                 |
| ctr              | float         | Click-through rate (Clicks ÷ Impressions).                 |
| conversions      | int           | Number of successful conversions (e.g., purchases, signups).|
| conversion_rate  | float         | Conversion rate (Conversions ÷ Clicks).                    |
| cost             | float         | Total cost of the campaign.                                |
| cpc              | float         | Cost per click (Cost ÷ Clicks).                            |
| revenue          | float         | Revenue generated from the campaign.                       |
| roi              | float         | Return on investment ((Revenue – Cost) ÷ Cost).            |

---

## Notes

- Dataset spans **2 years** across **2 CSVs** (split by year).  
- Columns `ctr`, `conversion_rate`, `cpc`, and `roi` can be derived if not present.  
- Missing values and outliers will be handled during **data cleaning**.  
- Additional engineered features (e.g., campaign duration, cost per conversion) will be added later.  

---

> **Tip:** This dictionary supports all analysis notebooks (data ingestion → visualization) by defining consistent variable naming and data types across both yearly datasets.



