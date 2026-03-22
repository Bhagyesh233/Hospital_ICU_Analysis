# Hospital ICU Bed Analysis

A data analysis project examining ICU and SICU bed capacity across U.S. hospitals to identify optimal pilot sites for a new nursing program. Built in R using SQLite for data management.

## Overview

This project loads hospital bed data into a SQLite database and uses SQL queries to analyze ICU (bed_id = 4) and SICU (bed_id = 15) bed distribution across hospitals. The analysis identifies top-performing hospitals based on licensed, census, and staffed bed counts to support leadership decision-making.

## Authors

Bhagyesh Vaze, Samruddhi, Kajol, Om

## Dataset

Three CSV files loaded into a SQLite database (`hospital.db`):

| Table | Description |
|---|---|
| `bed_type` | Bed type codes and descriptions |
| `business` | Hospital names, IDs, and total bed counts |
| `bed_fact` | Per-hospital bed counts by type (license, census, staffed) |

## Analysis

### Summary Reports
Top 10 hospitals ranked by total ICU/SICU beds across three metrics:
- **Licensed Beds** — Phoenix Children's Hospital (247) and University of Maryland Medical Center (220) lead
- **Census Beds** — Shands Hospital at UF (167) and Dallas County Hospital Association (145) lead
- **Staffed Beds** — Vidant Medical Center (203) and Rady Children's Hospital (200) lead

### Drill-Down Investigation
Filtered to hospitals with **both** ICU and SICU units:
- **University of Maryland Medical Center** — 220 licensed, 127 census, 171 staffed beds
- **Shands Hospital at UF** — 167 beds consistently across all three metrics

## Recommendation

Based on the analysis, two hospitals are recommended for the nursing pilot program:

1. **University of Maryland Medical Center** — top choice; strong across all metrics with both ICU and SICU units
2. **Shands Hospital at the University of Florida** — consistent performance of 167 beds across all measures

## R Dependencies

```r
install.packages(c("tidyverse", "RSQLite", "DBI"))
```

## Usage

1. Place the three CSV files in the same directory as the `.Rmd` file
2. Open `Hopital_ICU_Bed_Analysis.Rmd` in RStudio
3. Knit the document — it will create `hospital.db` automatically

## Files

| File | Description |
|---|---|
| `Hopital_ICU_Bed_Analysis.Rmd` | Main R Markdown analysis file |
| `Hopital_ICU_Bed_Analysis.html` | Rendered HTML output |
| `bed_type-1.csv` | Bed type reference data |
| `business-1.csv` | Hospital business data |
| `bed_fact-1.csv` | Bed fact data |
| `hospital.db` | SQLite database (auto-generated) |
