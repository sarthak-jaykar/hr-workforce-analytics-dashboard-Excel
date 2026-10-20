# Validation Report — HR & Workforce Analytics

## Scope and environment

The source dataset and dashboard workbook were inspected independently. Workbook formulas were recalculated in **LibreOffice Calc 25.2.3.2** on a test copy. This is an additional spreadsheet-engine check, not a claim of testing in Microsoft Excel desktop. The original dataset and workbook are included in this repository; the dashboard copy has been polished for chart layout, filter clarity, and department-specific variance labelling.

## Data integrity checks

| Check | Result | Evidence |
|---|---|---|
| Source row count | PASS | `Raw_Employee_Data` contains 1,485 data rows. |
| Duplicate employee IDs | PASS | 35 duplicate rows; 1,450 unique IDs remain after deduplication. |
| Raw data consistency across files | PASS | The first 19 source columns in workbook `Raw_Data` match the dataset source rows in order. |
| Cleaned cohort uniqueness | PASS | `Cleaned_Data` contains 1,450 rows and 1,450 unique employee IDs. |
| Employment status reconciliation | PASS | 1,042 Active + 265 Voluntary Exit + 143 Involuntary Exit = 1,450. |
| Department active headcount reconciliation | PASS | Department totals sum to 1,042 active employees. |
| Department historical exits reconciliation | PASS | Department totals sum to 408 exits. |
| FY2025 stock-flow identity | PASS | 923 starting headcount + 221 hires − 102 exits = 1,042 ending headcount. |

## Independently recalculated metrics

| Metric | Recalculated result |
|---|---:|
| FY2025 average headcount | 982.5 |
| FY2025 attrition rate | 102 ÷ 982.5 = 10.3817% (displayed as 10.38%) |
| Historical cohort attrition | 408 ÷ 1,450 = 28.1379% (displayed as 28.14%) |
| Active average tenure | 2.6975 years (displayed as 2.70) |
| Active overtime participation | 380 ÷ 1,042 = 36.4683% (displayed as 36.47%) |
| Rated employee count / mean rating | 1,420 / 3.1866 (displayed as 3.19) |
| Active employees flagged High Risk | 203 |
| Weighted standard cost per hire | ₹59,811.72 (displayed as ₹59,812) |

## Formula and dashboard checks

- The recalculated test copy opened successfully in LibreOffice and returned formula results for the dashboard, KPI calculation, and analysis sheets.
- No spreadsheet error values such as `#REF!`, `#DIV/0!`, or `#NAME?` were found in the recalculated workbook.
- The workbook contains four native charts, an Excel Table named `tbl_Cleaned_HR`, formula-driven summary matrices, and two dashboard dropdown controls.
- Dashboard dropdown validation is represented with named ranges for department and reporting year. Confirm dropdown operation in desktop Excel before capturing screenshots.
- The department target subtitle was corrected to show the selected department's own headcount variance rather than displaying the organization-wide gap for every department.
- Chart sizes were reduced to prevent the four charts from overlapping; the dashboard was set to landscape, one-page A3 print/export layout.

## Definitions and limitations

- **FY2025 attrition:** FY2025 exits divided by the mean of FY2025 starting and ending headcount.
- **Historical cohort attrition:** historical exits divided by unique employees hired in the 2019–2025 cohort.
- **Weighted cost per hire:** sum of recruitment-source hire counts multiplied by each source's standard cost per hire, divided by total hires. This is ₹59,811.72, not ₹61,450; the README uses the recalculated value.
- Findings come from synthetic data and are suitable for demonstrating analytical reasoning only. Correlations between overtime, recruitment source, and exits do not establish causation.
- Native PivotTables, PivotCharts, and slicers are not embedded. `Pivot_Analysis` contains formula-driven cross-tabulations; dashboard dropdowns simulate filter selection but are not slicers.
- Power Query M and VBA examples are provided as learning material in `Methodology_QA`; they are not verified, embedded automated refresh/macro features.
- Final appearance and interactivity should be checked in desktop Microsoft Excel. Do not describe the workbook as Excel-desktop-tested unless that check has been completed.
