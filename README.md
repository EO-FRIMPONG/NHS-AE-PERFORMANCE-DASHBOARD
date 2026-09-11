# NHS A\&E Performance Dashboard (Apr 2025 – Mar 2026)

An Excel dashboard which analysed NHS England Accident \& Emergency (A\&E) performance at trust level from official monthly published data. The project focuses on the 4-hour A\&E waiting time standard, extreme waits which was 12+ hours, and how performance varies by trust and region.

!\[Dashboard Preview](A\&E\_dashboard\_preview.png)



## Objective

The main objective was to identify which NHS trusts and regions are struggling most against the 4-hour A\&E target, and to explore whether attendance volume is a driver of poor performance whiles using the kind of reporting and analysis an NHS data/performance analyst would carry out.



## Data Source

* **NHS England A\&E Attendances and Emergency Admissions (Monthly Situation Reports)**
https://www.england.nhs.uk/statistics/statistical-work-areas/ae-waiting-times-and-activity/
* 11 monthly trust-level CSV files, covering April 2025 – March 2026.
* Published under NHS England's open data releases.
* 

## Tools Used

* **Excel** — Power Query, Pivot Tables, Pivot Charts, Data Model
* Chart types: line, horizontal bar, combo (clustered column + line, secondary axis).
* 

## Process

1. **Data combination** — Combined 11 separate monthly CSVs into a single table using Power Query's Get Data From Folder.
2. **Data cleaning**:

   * Removed pre-aggregated TOTAL summary rows present in each monthly file, which would have caused double-counting in pivot calculations.
   * Converted the Period text field (e.g. `MSitAE-APRIL-2025`) into a proper Date field for correct chronological sorting and charting.
   * Trimmed text fields (Org Code, Parent Org, Org name) to remove hidden whitespace.
   * Standardised and shortened column headers for a cleaner, more usable field list.
   * Filtered "booked appointments" columns not required for this analysis, to keep the dataset focused.
3. **Calculated fields** (built in Power Query):

   * Total\_Attendances and Total\_Over4h — summed across attendance types (Type 1/2/3)
   * Pct\_Within\_4h — overall % of attendances seen within 4 hours
   * Pct\_Within\_4h\_T1 — % within 4 hours for major A\&E (Type 1) departments specifically
4. **Data quality handling**:

   * Excluded organisations with zero recorded attendances which were mainly specialist/community trusts and GP out-of-hours services that don't operate general A\&E departments.
   * Left null percentage values as genuine nulls (rather than 0) where a metric didn't apply, so averages weren't skewed.
5. **Analysis** — Built four PivotTables answering distinct questions: monthly trend, trust-level ranking, regional comparison, and volume vs. performance.
6. **Dashboard** — Assembled a single-page Excel dashboard combining KPIs, a trend line, a ranked bar chart, a dual-axis regional comparison, and a volume-vs-performance combo chart.
7. 

## Key Findings

1. **National performance sits well below the NHs standard target -** Only 81% of attendances were seen within 4 hours across the year, against the NHS's 95% standard.
2. **A small group of trusts show a persistent, structural problem** **not just a bad month** **-** East Cheshire NHS Trust (47%) and The Shrewsbury and Telford Hospital NHS Trust (52%) sit far below the rest of the bottom 10.
3. **High attendance volume doesn't generally mean poor performance -** Among the ten busiest trusts nationally, 4-hour performance varied widely and stayed broadly comparable to the national average which suggested that trust-specific operational factors matter more than raw demand.
4. **Regional performance varies by 9 percentage points** **-** from NHS England North West (76%) to NHS England South East (85%).
5. **The region with the best standard-target performance isn't the one with the worst extreme-wait problem -** NHS England Midlands recorded the highest number of 12+ hour waits nationally, despite mid-table 4-hour performance indicating the headline 4-hour metric can mask a more severe issue elsewhere.
6. **12+ hour waits are concentrated in a handful of large trusts -** The top 10 trusts for 12+ hour waits account for roughly 26% of the national total, led by Royal Free London NHS Foundation Trust.
7. 

## Dashboard Contents

* **KPI strip** **—** National average % within 4 hours, total attendances, total 12+ hour waits.
* **Monthly trend** **—** % within 4 hours, April 2025 – March 2026.
* **Bottom 10 trusts** **—** ranked by % within 4 hours, with the two most severe outliers highlighted.
* **Regional comparison** **—** % within 4 hours vs. 12+ hour waits by NHS England region (combo chart).
* **Top 10 by volume** **—** attendance volume vs. % within 4 hours for the busiest trusts.
* 

## Skills Demonstrated

* Combining and cleaning multiple raw public sector data files using Power Query.
* Identifying and resolving real data quality issues such as duplicate totals, non-applicable metrics, inconsistent formats.
* Building calculated fields and handling nulls appropriately.
* PivotTable and PivotChart design, including dual-axis combo charts.
* Translating raw data into a clear, decision-ready dashboard narrative.
* Communicating findings in plain language for non-technical stakeholders.



## Author

Enoch Osei Frimpong — MSc Artificial Intelligence and Data Science

