\# Data Dictionary



This document describes the dataset fields used in the Marketing Campaign Analysis and Optimization project.

Two CSVs represent 2 years of campaign data. Columns are consistent across both files.



---





| Column Name        | Type    | Description                                   | Example             |

|--------------------|---------|-----------------------------------------------|---------------------|

| campaign\_id        | int     | Unique ID of the campaign                     | 10234               |

| date               | date    | Date of record (YYYY-MM-DD)                   | 2022-05-01          |

| impressions        | int     | Number of times ad was shown                  | 12,340              |

| clicks             | int     | Number of user clicks                         | 530                 |

| conversions        | int     | Number of purchases/leads from campaign       | 42                  |

| spend\_usd          | float   | Money spent on campaign in USD                | 1200.50             |

| ctr                | float   | Click-through rate (clicks/impressions)       | 0.043               |

| cr                 | float   | Conversion rate (conversions/clicks)          | 0.079               |

| cpc                | float   | Cost per click (spend/clicks)                 | 2.26                |

| revenue\_usd        | float   | Revenue generated from conversions            | 3400.00             |

| roi                | float   | Return on investment ((revenue-spend)/spend)  | 1.83                |



---

\*\*Notes:\*\*

* Dataset spans 2 years across 2 CSVs (split by year).
* Columns ctr, conversion\_rate, cpc, and roi can be derived if not present.
* Missing values \& outliers will be handled in the data cleaning step.
* Additional engineered features (e.g., campaign duration, cost per conversion) will be added later.



