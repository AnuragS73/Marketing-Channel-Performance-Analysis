# Marketing-Channel-Performance-Analysis

> **Which platform delivers superior performance, and what is the optimal budget allocation strategy between Facebook and AdWords to maximize conversions while achieving the highest return on investment (ROI)?**  
> A full data analysis project comparing two marketing campaigns run throughout 2019.

---

## Project Overview

This project analyses a full year (Jan - Dec 2019) of daily ad campaign data from two platforms  **Facebook Ads** and **Google AdWords**. The objective is to identify which platform delivers higher conversions at lower cost, supported by statistical evidence rather than intuition.

This project covering the pipeline: data cleaning → EDA → statistical testing

---

## Business Problem

The company was spending budget on both Facebook and AdWords at the same time, but had no clear answer to:

- Which platform generates higher conversions overall?
- Is the difference in performance statistically significant or due to random variation?
- Which platform is more cost-efficient in terms of cost per conversion?
- How stable and consistent is each platform’s performance over time?
- Should we keep splitting budget 50/50, or shift more to one platform?

---

## Dataset Description

- **Source:** Facebook Ads and Google AdWords marketing campaign dataset from Kaggle
- **Period:** January 1, 2019 - December 31, 2019
- **Rows:** 365 (one row per day)
- **Columns:** 17

| Column | Description |
|---|---|
| Date | Calendar date |
| Facebook Ad Campaign | The name of the Facebook ad campaign |
| Facebook Ad Views | Number of times the Facebook ad was seen |
| Facebook Ad Clicks | Number of clicks on the Facebook ad |
| Facebook Ad Conversions | Number of sales/sign-ups from Facebook |
| Cost per Facebook Ad | Daily spend on Facebook ($) |
| Facebook Click-Through Rate (Clicks / View) | Click-through rate in (%) |
| Facebook Conversion Rate (Conversions / Clicks) | % of clicks that became conversions |
| Facebook Cost per Click (Ad Cost / Clicks) | Cost per click in ($) |
| AdWords Ad Campaign | The name of the AdWords campaign |
| AdWords Ad Views | Number of times the AdWords ad was seen |
| AdWords Ad Clicks | Number of clicks on the AdWords ad |
| AdWords Ad Conversions | Number of sales/sign-ups from AdWords |
| Cost per AdWords Ad | Daily spend on AdWords ($) |
| AdWords Click-Through Rate (Clicks / View) | Click-through rate in (%) |
| AdWords Conversion Rate (Conversions / Click) | % of clicks that became conversions |
| AdWords Cost per Click (Ad Cost / Clicks) | Cost per click in ($) |

---

## Notebook Includes

The notebook is structured as a complete end-to-end analysis:

**1. Setup & Data Loading**
- Import all required libraries
- Load the raw CSV file
- First look at shape, columns, data types

**2. Data Cleaning**
- Convert `Date` column from string to datetime
- Strip `$` from all monetary columns so they become numbers
- Strip `%` from all rate columns so they become numbers
- Create new time features: `Month`, `DayOfWeek`, `Quarter`
- Create key derived metric: `Cost per Conversion` for both platforms

**3. Exploratory Data Analysis (EDA)**
- Campaign-level summary table (all KPIs side by side)
- Distribution plots : are clicks and conversions normally spread?
- Boxplots : checking for outliers
- Scatter plots : do more clicks lead to more conversions?
- Monthly trend analysis : which months perform best?
- Day-of-week patterns : which days drive most conversions?

**4. Hypothesis Testing (A/B Test)**
- Normality check using **Shapiro-Wilk test**
- Primary test: **Mann-Whitney U test** (non-parametric, since data is not normally distributed)
- Supporting test: **Welch's t-test** (robust at n=365 due to Central Limit Theorem)
- **Effect size**: Rank-Biserial Correlation (measures how big the difference actually is)

**5. Business Insights & Final Recommendation**
- Summary of all findings in plain language
- Clear recommendation on budget allocation

---

## Key Metric

| Metric | Facebook | AdWords | Winner |
|---|---|---|---|
| Total Conversions | 4,286 | 2,183 | Facebook |
| Total Ad Spend | $32,040 | $49,266 | Facebook |
| Cost per Conversion | $7.48 | $22.57 | Facebook |
| Avg. Conversion Rate | 27.2% | 10.2% | Facebook |
| Avg. CTR | 2.20% | 1.30% | Facebook |
| Clicks → Conv. Correlation | r = 0.87 | r = 0.45 | Facebook |
| Statistical Test p-value | p < 0.001 | — | Facebook |
| Effect Size | 0.92 (Large) | — | Facebook |

---

## Tools and Technologies


**Python** : Main programming language 

**pandas** : Data loading, cleaning, aggregation 

**numpy**  : Numerical calculations 

**matplotlib / seaborn** : Charts and visualisations 

**scipy.stats** :  Hypothesis testing (Mann-Whitney, Shapiro-Wilk, t-test) 

---

## Business Recommendations 

- **Shift 60–70% of the AdWords budget to Facebook** : same total spend would generate roughly 6,500 more conversions per year
- **Schedule Facebook ads for Monday–Wednesday** : highest conversion days
- **Increase Facebook spend in October–December** : historically highest conversion months
- **Do not cut AdWords completely** : audit keywords and improve targeting quality first
- **February is the worst month for cost efficiency** : reduce spend or test new creatives

---

## Author
**Anurag Sarkar**  
Email : sarkaranurag73@gmail.com     
[LinkedIn](www.linkedin.com/in/anusarsarkar73/)  
 [GitHub](github.com/AnuragS73)


---
