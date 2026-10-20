# HR & Workforce Analytics Dashboard — Excel Portfolio Project

## Overview

This project analyses a fictional mid-sized technology company, **NexaCore Technologies Pvt. Ltd.**, using a fully synthetic employee dataset covering **1 January 2019 to 31 December 2025**. It demonstrates an end-to-end Excel workflow for an entry-level Business Analyst / Data Analyst: raw-data assessment, cleaning, KPI definition, formula-driven analysis, dashboard reporting, and business recommendations.

> **Data notice:** All employee records and company details are synthetic and created for portfolio demonstration. They do not describe a real organisation or real employees.

## Business objectives

- Monitor active headcount against approved department targets.
- Analyse FY2025 attrition and historical cohort attrition using clearly defined denominators.
- Compare hiring volume, exits, and retention across recruitment sources.
- Examine tenure, overtime, performance ratings, salary-band positioning, and retention-risk flags.
- Identify workforce segments for further investigation and propose data-supported actions.

## Workbook and dataset

- **Raw dataset:** 1,485 rows, including 35 intentional duplicate records; reference sheets provide department budgets, job-level salary bands, manager records, and anomaly guidance.
- **Cleaned analytical cohort:** 1,450 unique employee IDs, with documented cleaning and enrichment logic.
- **Dashboard workbook:** eight sheets — `Dashboard`, `KPI_Calculations`, `Pivot_Analysis`, `Cleaned_Data`, `Employee_Lookups`, `Raw_Data`, `Data_Dictionary`, and `Methodology_QA`.

### Main KPIs (reporting cutoff: 31 December 2025)

| KPI | Result | Definition |
|---|---:|---|
| Active headcount | 1,042 | Employees active at the reporting cutoff |
| Approved headcount target | 1,095 | Sum of department targets |
| Headcount variance | -53 | Active headcount minus approved target |
| FY2025 hires | 221 | Employees with hire year 2025 |
| FY2025 exits | 102 | Employees with exit year 2025 |
| FY2025 attrition rate | 10.38% | FY2025 exits ÷ average of starting and ending headcount (102 ÷ 982.5) |
| Historical cohort attrition | 28.14% | Historical exits ÷ unique employees hired during 2019–2025 (408 ÷ 1,450) |
| Average active tenure | 2.70 years | Mean tenure for active employees at the cutoff |
| Active overtime participation | 36.47% | Active employees flagged for overtime ÷ active headcount (380 ÷ 1,042) |
| Average performance rating | 3.19 / 5 | Average among 1,420 employees with a completed rating |
| High-retention-risk active employees | 203 | Active employees meeting the documented overtime/performance/compa-ratio rule |
| Weighted cost per hire | ₹59,812 | Sum of recruitment-source hires × standard cost per hire, divided by total hires |

## Selected findings

1. **Recruitment-source comparison:** External agencies have the highest standard cost per hire (₹145,000) and the highest cohort attrition (40.4%); employee referrals cost ₹42,000 per hire and have 20.0% cohort attrition. This is an association in synthetic data, not proof of causation.
2. **Overtime and turnover:** Enterprise Sales has 52.2% active overtime participation and 15.1% FY2025 attrition; Customer Operations has 51.2% overtime participation and 37.1% cohort attrition. These patterns warrant workload and exit-interview investigation.
3. **Entry-level retention:** L1 employees have 34.9% cohort attrition (205 exits among 587 L1 hires) and 261 of 408 total exits occurred within the first year. Structured 30-60-90 day onboarding is a suggested intervention to test.

## Excel skills demonstrated

- `SUMIFS`, `COUNTIF` / `COUNTIFS`, `AVERAGEIF` / `AVERAGEIFS`, `SUMPRODUCT`
- `VLOOKUP`, `INDEX/MATCH`, and `XLOOKUP` (with a compatible calculation path for compa-ratio)
- `IF`, nested `IF`, `AND`, `OR`, `IFERROR`, `ISBLANK`
- Text cleaning and extraction with `TRIM`, `PROPER`, `UPPER`, `LEFT`, `RIGHT`, `MID`, and `VALUE`
- Duplicate detection, lookup enrichment, Excel Tables, filters, data validation, conditional formatting, and native charts
- Formula-driven cross-tab summaries and department/year dropdown filters

## Dashboard preview

Open `Excel Workbook/HR_Workforce_Analytics_Dashboard.xlsx` in desktop Excel. The workbook contains four native charts and two dropdown filters. After opening and confirming the dashboard renders correctly, add genuine screenshots to `Screenshots/` using the suggested filenames below:

- `dashboard-overview.png` — executive dashboard with KPI cards, department scorecard, and charts
- `recruitment-analysis.png` — recruitment-source cost and retention analysis
- `workforce-analysis.png` — department, job-level, tenure, and overtime analysis
- `data-quality-and-methodology.png` — cleaned-data structure and methodology/QA sheet

Do not add mockups or generated images in place of workbook screenshots.

## Repository structure

```text
HR-Workforce-Analytics/
├── Dataset/
│   └── HR_Workforce_Analytics_Dataset.xlsx
├── Excel Workbook/
│   └── HR_Workforce_Analytics_Dashboard.xlsx
├── Screenshots/
│   ├── 01-hr-executive-dashboard-1.png
│   ├── 02-hr-executive-dashboard-2.png
│   ├── 03-department-workforce-analysis.png
│   ├── 04-recruitment-retention-analysis.png
│   ├── 05-cleaned-employee-data.png
│   └── 06-data-dictionary-qa.png
├── README.md
└── Validation_Report.md
```

## Folder Contents

-Dataset/ — Original synthetic HR dataset, including raw employee records, reference tables, and documented data-quality anomalies.

-Workbook/ — Analytical Excel workbook containing cleaned data, lookup tables, KPI calculations, department-level analysis, and the executive dashboard.

-Screenshots/ — Visual evidence of the dashboard, workforce analysis, data preparation, QA methodology, and recruitment analysis.

-README.md — Project overview, business problem, methodology, KPI definitions, findings, recommendations, and instructions.

-Validation_Report.md — Data-quality checks, calculation reconciliation, validation results, and known technical limitations.

## Methodology and limitations

- The `Cleaned_Data` sheet preserves a separate raw-data baseline and records cleaned/enriched values and formula-derived fields.
- Attrition metrics use two different denominators: FY2025 exits divided by average FY2025 headcount, and cumulative exits divided by the 1,450-person historical cohort. Do not compare them as if they were the same measure.
- The workbook uses formula-driven summary matrices rather than embedded native PivotTables. Dropdowns are used for dashboard filtering; they are not slicers.
- The workbook includes Power Query M and VBA examples in `Methodology_QA` for optional learning. They are not an embedded Power Query refresh pipeline or an enabled VBA macro.
- See [`Validation_Report.md`](Validation_Report.md) for independent checks, formula recalculation notes, and remaining limitations.

## Tools

Microsoft Excel-compatible `.xlsx` workbooks, spreadsheet formulas, data cleaning, KPI analysis, dashboard charts, and synthetic data validation. The workbook was programmatically generated and recalculated in LibreOffice for an additional formula-engine check; final appearance and dropdown behaviour should also be confirmed in desktop Microsoft Excel before screenshots are captured.

## Author

**Sarthak Jaykar** — [GitHub profile](https://github.com/sarthak-jaykar)
