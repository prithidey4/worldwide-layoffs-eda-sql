# worldwide-layoffs-eda-sql

## Project Overview
This SQL-based data analytics project analyzes a comprehensive dataset of 2,362 company layoff records spanning 2020 to 2023. The dataset covers diverse industries—including technology, retail, healthcare, finance, and media—and contains key attributes such as company names, industries, geographic locations, layoff counts, percentages laid off, funding raised, and company funding stages. The project aims to uncover global patterns and drivers behind layoffs using advanced SQL queries and relational database operations, providing actionable business insights.

---

## Contents

- [Database Setup and Data Import](#database-setup-and-data-import)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Deeper Analytical Drills](#deeper-analytical-drills)
- [Key Insights and Business Implications](#key-insights-and-business-implications)
- [Appendix: Visualization Code](#appendix-visualization-code)

---

## Database Setup and Data Import

1. Created the `world_layoffs` database.
2. Imported the `layoffs.csv` dataset (2,362 records) into a table named `layoffs`.
3. Created a staging table `layoffs_staging` to enable safe data cleaning without modifying the raw data.

---

## Data Cleaning

- Removed duplicate rows by assigning row numbers and deleting duplicates (rows where `row_num > 1`).
- Standardized company names by trimming whitespace.
- Unified industry names (e.g., all variants of ‘Crypto’ consolidated).
- Standardized country names to remove trailing periods and inconsistencies.
- Converted the `date` column from text to proper SQL `DATE` format for time-series analysis.
- Converted blank industry entries to `NULL` and backfilled missing industry data where possible by matching company and location.
- Removed rows lacking layoff data (both `total_laid_off` and `percentage_laid_off` were `NULL`).
- Dropped helper columns used during cleaning.

---

## Exploratory Data Analysis (EDA)

- **Date Range:** Layoff data spans from March 11, 2020, to March 6, 2023, capturing pandemic onset and aftermath.
- **Maximum Layoffs:** Largest single layoff event was 12,000 employees; some had 100% workforce layoffs.
- **Top Companies by Layoffs:** Amazon (18,150), Google (12,000), Meta (11,000), Salesforce (10,090), Microsoft (10,000).
- **Industry Impact:** Consumer (45,182 layoffs), Retail (43,613), Transportation (33,748), Finance, Healthcare, and Food sectors heavily affected.
- **Geographic Trends:** US led layoffs with 256,559; followed by India, Netherlands, Sweden, Brazil.
- **Funding Stage:** Post-IPO firms experienced the most layoffs (204,132), followed by unknown-stage and acquired companies; mid-stage startups saw moderate layoffs.

---

## Deeper Analytical Drills

- **Yearly Layoff Trends:** Peak layoffs in 2022 and early 2023; lowest layoffs in 2020.
- **Monthly Layoff Trends:** April 2020 spike coinciding with COVID lockdowns; ongoing fluctuations thereafter.
- **Cumulative Layoffs:** Steady growth in layoffs across pandemic years.
- **Funding vs Layoffs:** Weak to moderate correlation—higher funding doesn’t guarantee workforce stability.
- **Industry and Country Yearly Trends:** Varied layoff counts highlight sector-specific and regional differences.
- **Company Shock Detection:** Firms like Uber (2020), Meta and Google (2022), Amazon and Microsoft (multiple years) experienced major layoff waves.

---

## Key Insights and Business Implications

- Layoff peaks reflect global economic uncertainty and sector shifts post-pandemic.
- Technology and retail industries bore the brunt of layoffs; consumer-facing sectors were hardest hit.
- Large funding rounds do not ensure employment stability—operational discipline is critical.
- Geographic disparity underscores varying economic resilience and industry concentration.
- Mature and post-IPO companies face heightened layoff risk due to profitability pressures.
- Repeat layoffs signal ongoing strategic recalibrations in major firms.

### Recommendations

- **For Companies:** Develop agile workforce plans, scenario analysis, and invest in operational efficiency beyond reliance on funding.
- **For Job Seekers:** Target financially stable companies with sustainable growth rather than solely seeking those with large funding.
- **For Investors:** Evaluate companies on burn rate, runway, and management’s crisis readiness, beyond headline funding.

---
