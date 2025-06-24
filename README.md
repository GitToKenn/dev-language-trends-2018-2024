# 📊 Stack Overflow Developer Language Trends (2018–2024)

This project explores the usage trends of programming languages over time using the Stack Overflow Developer Surveys from 2018 to 2024. It focuses on data cleaning, multi-valued categorical transformation, and visual storytelling using Python and pandas.

🔗 **Featured on LinkedIn**: [View Post](https://www.linkedin.com/posts/syifa-alia-balqis_dataanalytics-programmingtrends-languagetrends-activity-7343273416835088384-srW6?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAADnQ7pMBVWGhjXpj9_dswWCCHQQgDVd7MLo)  
🛠️ **Status**: first version completed\
🔒 **Repo**: Public

---

## 📌 Project Goals

- Analyse and visualise programming language usage trends from 2018 to 2024
- Identify stable, rising, and declining languages across 7 years
- Highlight analyst-relevant languages like Python, SQL, and R
- Showcase storytelling via pandas and matplotlib with consistent branding
- Practise clean GitHub structuring and meaningful commit writing

---

## 🗂️ Project Structure

- [README.md](README.md) – Project overview and documentation  
- [language_insights_report.md](language_insights_report.md) – Final report with key findings and chart visuals  
- [data/](data/) – Dataset files  
  - *(Raw dataset excluded from repo — see License section)*  
  - [`all_languages_2018_2024_cleaned_2025-06-14.xls`](data/cleaned/all_languages_2018_2024_cleaned_2025-06-14.xls) ← Cleaned dataset  
- [chart/](chart/) – Exported visuals from Jupyter Notebook (Chart 01–09 PNGs)  
- [notebook/](notebook/) – Analysis notebooks  
  - [`01_data_cleaning.ipynb`](notebook/01_data_cleaning.ipynb) ← Raw dataset wrangling and preparation  
  - [`02_language_trend_analysis.ipynb`](notebook/02_language_trend_analysis.ipynb) ← Chart creation and percentage table  
  - [`03_insights_and_key_findings.ipynb`](notebook/03_insights_and_key_findings.ipynb) ← Commentary and exploratory notes (not final report)  
- [.gitignore](.gitignore) – Tracks excluded files and temporary system artifacts  


--- 

### 🗂️ Folder Tree

```
root/
├── README.md ← Project overview and documentation
├── language_insights_report.md – Final report with visual insights and key findings
├── .gitignore
├── data/
│   ├── cleaned/
│   │   └── all_languages_2018_2024_cleaned_2025-06-14.xls ← Cleaned dataset
│   └── raw/ (excluded from repo)
├── chart/ ← Visual outputs from analysis notebooks
│   └── *.png ← Exported figures (Chart 01–09)
├── notebook/
│   ├── 01_data_cleaning.ipynb ← Initial raw data wrangling
│   ├── 02_language_trend_analysis.ipynb ← Chart generation + trends
│   └── 03_insights_and_key_findings.ipynb ← In-notebook commentary (not the main report)
```
---

### 📊 Completed Charts

| **Chart** | **Description** | **Filename** |
|-----------|-----------------|--------------|
| **Chart 01** | Most Used Programming Languages by Developer Count (2024) | [chart_01_most_used_by_count](chart/chart_01_most_used_by_count_2025-06-20_13-56-21.png) |
| **Chart 02** | Most Used Programming Languages by Percentage (2024) | [chart_02_most_used_by_percentage](chart/chart_02_most_used_by_percentage_2025-06-20_13-56-21.png) |
| **Chart 03** | Percentage Trends of the Top 10 Programming Languages (2018–2024) | [chart_03_percentage_trends_top10](chart/chart_03_percentage_trends_top10_2025-06-20_13-56-21.png) |
| **Chart 04** | Multi-Bar Chart of Top 5 Language Trends (2018–2024) | [chart_04_percentage_trends_top5_avg](chart/chart_04_percentage_trends_top5_avg_2025-06-20_13-56-21.png) |
| **Chart 05** | Line Chart of Top 5 Language Trends (2018–2024) | [chart_05_percentage_trends_top5](chart/chart_05_percentage_trends_top5_2025-06-20_13-56-21.png) |
| **Chart 06** | SAS Trend Line (2018–2024) with Zero-Entry Handling | [chart_06_sas_rise_and_fall](chart/chart_06_sas_rise_and_fall_2025-06-20_13-56-21.png) |
| **Chart 07** | Line Chart of 5 Most Declining Languages (2018–2024) | [chart_07_declining_top5](chart/chart_07_declining_top5_2025-06-20_13-56-21.png) |
| **Chart 08** | Top 10 Fossilised Languages by Decline Percentage | [chart_08_declining_top10](chart/chart_08_declining_top10_2025-06-20_13-56-21.png) |
| **Chart 09** | Analyst Tools: Python vs. SQL vs. R Trends | [chart_09_python_sql_vs_r_trends](chart/chart_09_python_sql_vs_r_trends_2025-06-20_13-56-21.png) |


---

## 📊 Dataset Overview

- Source: Stack Overflow Developer Survey data (2018–2024)
- Total Size: ~2.76 million language entries (post-explode)
- Years Covered: 2018–2024
- Languages Tracked: 58 distinct programming languages

---

### 👥 Respondents (Before Explode)

| Year | Respondents |
|------|-------------|
| 2018 | 78,334      |
| 2019 | 87,569      |
| 2020 | 57,378      |
| 2021 | 82,357      |
| 2022 | 70,975      |
| 2023 | 87,140      |
| 2024 | 59,745      |

---

### 🧾 Total Language Entries (After Explode)

| Year | Language Entries |
|------|------------------|
| 2018 | 435,593          |
| 2019 | 446,505          |
| 2020 | 288,004          |
| 2021 | 442,560          |
| 2022 | 367,821          |
| 2023 | 466,157          |
| 2024 | 322,233          |

---

## 🧹 Cleaning & Processing Summary

- Processed Stack Overflow survey data from **2018 to 2024**, resulting in **2.76M+ exploded language–respondent entries**
- Focused on the `LanguageHaveWorkedWith` (or equivalent) column to extract multi-valued categorical data:
  - Split semicolon-separated strings and applied `.explode()` for long-format normalisation  
  - Trimmed whitespace and standardised language names for consistency  
  - Added `Year` column and generated a unique `GlobalRespondentID` per entry  
- Concatenated all seven years into a unified DataFrame for trend analysis
- **Calculated yearly language popularity** by normalising total language mentions per year (post-explode), rather than per-respondent, to better reflect tool presence across developer stacks

--- 

### ⚠️ Special Handling for 2018 Dataset

In 2018, `HTML` and `CSS` were listed as separate options, unlike the `"HTML/CSS"` grouping introduced from 2019 onwards.  
To maintain consistency across years:

- Applied a **conditional `.apply()`** logic to merge co-occurring `"HTML"` and `"CSS"` into a single `"HTML/CSS"` entry  
- Ensured data integrity by testing alternative strategies in a **dedicated Git branch** before merging

This prevented double-counting and ensured accurate year-over-year comparisons.

---

## ✨ Recent Additions

- ✅ 📣 Project findings shared in a public [LinkedIn post](https://www.linkedin.com/posts/syifa-alia-balqis_dataanalytics-programmingtrends-languagetrends-activity-7343273416835088384-srW6?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAADnQ7pMBVWGhjXpj9_dswWCCHQQgDVd7MLo)
- ✅ Added `language_insights_report.md` as the main analyst report (migrated from Notebook 3)
- ✅ Exported charts as high-resolution PNGs for GitHub and reporting
- ✅ Summarised top language trends, including Python, SQL, and R movements
- ✅ Investigated SAS anomaly with explanation and certificate context
- ✅ Updated folder structure, README, and internal links for consistency

---

## 🛡️ Descalimer

- This project uses publicly available data from the [**Stack Overflow Developer Survey Archive**](https://survey.stackoverflow.co/), covering the years **2018 to 2024**.
- All datasets were downloaded directly from the official site and are provided under the **Open Database License (ODbL)**.  
  *(Accessed on 13 June 2025)*
- Any inconsistencies in schema (such as separate "HTML" and "CSS" fields in 2018) were handled with documented preprocessing to ensure accurate multi-year trend analysis.

---