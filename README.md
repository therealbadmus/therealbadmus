# Church Attendance Analysis (Excel)

An end-to-end Excel analysis of multi-campus church attendance data: from a messy raw dataset to a cleaned, validated dataset and an interactive dashboard.

## Project Overview
- **Dataset:** weekly Sunday Service attendance records for CCI, roughly 2,291 rows across 45 campuses in Nigeria, North America, and Europe
- **Fields:** date of service, campus, continent, service type, male adults, female adults, teenagers, kids, overall total, comments
- **Tool:** Microsoft Excel (PivotTables, slicers, lookup formulas, conditional formatting)
- **Goal:** clean the data so it can be trusted, then build a dashboard showing attendance trends, campus performance, and audience composition

## Data Quality Issues Found
| Issue | How it was handled |
|---|---|
| Dates stored as text, inconsistent formats | Converted to real date values; verified with `ISNUMBER()` |
| Category counts not matching the total | Added a Match/Mismatch validation column and highlighted mismatches with conditional formatting |
| Blanks, negative numbers, and text in numeric columns | Recalculated only where the value could be derived from the other figures in the row; otherwise left blank and documented |
| Hidden characters (e.g., "Sunday Service" appearing twice in the slicer) | Diagnosed with `EXACT()`, corrected the affected cells |
| Blank campus names | Labelled "Unspecified" |
| Duplicate records | Checked on Date + Campus + Service Type, not on numeric columns |
| Campuses missing a continent | Built a Campus-to-Continent lookup table |

> Principle followed: no data was invented. Values that could not be derived were left blank and flagged, not guessed.

## What I Built
- Campus-to-Continent mapping table with lookup formulas
- Derived columns: Month, Quarter, Year
- PivotTables for attendance trends, campus comparison, continent comparison, and demographic breakdown
- Interactive dashboard with slicers (Campus, Continent, Service Type, Date, Month, Quarter, Year), KPI cards, and charts

## Key Insights

1. 3 lagos campuses (Ikeja, Yaba and Ago) Campus has the highest attendance suggesting that we maintain and provide more resources to sustain growth
2. Female adults make up 52% of the attendance while teenagers are critically low at less than 3% suggesting that we engage more men and teenagers while sustaining the female adult attendance. Probably launch a dedicated youth program. 
3. November and April recorded the hghest and lowest attendance respectively which suggests that we investigate April attendance.
4. Boston, Oshawa and barrie are significantly lower suggesting that we investigate why and develop a North America growth strategy

## Limitations
- Some records have missing values that could not be recovered, so they are excluded from breakdowns where the relevant field is blank
- Campuses differ in size and maturity, so comparing totals across continents is not like-for-like

## Repository Contents
```
/data           cleaned dataset (Excel)
/screenshots    dashboard and PivotTable images
/docs           data cleaning notes
README.md
```

## Skills Demonstrated
Data cleaning and validation, lookup tables (VLOOKUP/XLOOKUP), PivotTables, slicers, conditional formatting, dashboard design, documentation

## Author
Badmus Omotayo Oluwabusayomi | Data Analyst (entry-level) | Lagos, Nigeria
