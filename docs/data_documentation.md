\# Data Documentation



\## Dataset Overview

\- \*\*Source\*\*: Company Marketing Campaign Data (internal system export).

\- \*\*Coverage\*\*: 2 years (2021–2022).

\- \*\*Files\*\*: 2 CSV files (`campaign\_data\_2021.csv`, `campaign\_data\_2022.csv`).

\- \*\*Volume\*\*: ~500k rows per year.

\- \*\*Granularity\*\*: Daily campaign-level performance.



\## Purpose

The dataset is used to analyze and optimize marketing campaigns by studying:

\- Impressions, clicks, conversions

\- Cost efficiency (CPC, ROI)

\- Trends over time



\## Known Limitations

\- Some missing `conversion` values.

\- Dates are not standardized in source (need cleaning).

\- ROI not always directly available, must be computed.



\## Notes

Data has been split by year for parallel processing, then will be concatenated for analysis.

