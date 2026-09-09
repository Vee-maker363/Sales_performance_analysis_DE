# DE — Annual Sales Performance Report

An Excel + Power BI analytics project that turns eight years of raw global sales
records into a decision-ready, boardroom-style performance report — built and
presented the way a data analyst would deliver it to a business owner.

---

## Overview

This project analyzes **Digital Echoes'** sales activity from **2010 to 2017**:
100 order records spanning **7 regions**, **76 countries**, and **12 product
categories**. Starting from a raw sales export, the project cleans the data,
answers 10 specific business KPIs, models the results in Power BI, and
packages the findings into a presentation-ready report.

It's a small dataset by design — the goal isn't "big data," it's demonstrating
the full path from **raw records → validated numbers → a report a business
owner can actually act on.**

## Why This Project Matters

Most raw sales exports are not directly useful to a business owner — they're
inconsistent, undocumented, and answer no specific question on their own. The
value an analyst adds isn't just building a chart; it's:

- Catching and documenting **data quality issues before they become wrong
  conclusions** (a mis-cast date field or an unstandardized text column can
  silently corrupt every KPI built on top of it).
- Translating **open-ended business questions** ("how are we doing regionally?")
  into **specific, measurable KPIs**.
- Presenting findings so that **the story is legible in five minutes**, not
  buried in a dense reference table.

This project is a compact demonstration of that whole loop, not just the
visualization step at the end of it.

## The Data

| File | Description |
|---|---|
| `DE_SalesRecord.xlsx` | Raw sales records, the pre-existing data cleaning log ("Issues Log" tab), and pivot-table KPI calculations ("Data Summary" and "Test Cal." tabs). |
| `DE_BI.pbix` | The Power BI data model and interactive report — clustered bar, donut, and combo-chart visuals plus pivot-table views, one per KPI. |
| `DE_Annual_Sales_Performance_Report.pptx` | The final presentation deliverable: a 15-slide report summarizing every KPI with narrative insight, styled for a non-technical audience. |

**Headline numbers:** $137.3M total revenue · $44.2M total profit · 32.2% blended margin · 2010–2017.

## Key Performance Indicators

The analysis was scoped to 10 KPIs, each tied to a specific business question:

1. Total revenue and profit across regions
2. Total revenue made annually
3. Total quantity sold year by year, by item type
4. Revenue contribution rate by region
5. Top 3 products by quantity sold
6. Total profit and profit margin by item type
7. Average annual profit
8. Top 4 and bottom 4 countries by revenue
9. Year-on-year revenue growth rate
10. Average Order Value (AOV) by year

## Methodology

**1. Data cleaning (Excel).**
The source workbook's own Issues Log documents the cleaning already applied
before analysis: Order Priority codes decoded from abbreviations to plain
labels, Order Date/Ship Date converted to proper date types, Sales Channel
casing standardized, numeric fields (units, prices, revenue, cost, profit)
corrected from text, and the dataset augmented with Order Year, Order Month,
and Days-to-Ship fields to support trend analysis.

**2. KPI calculation (Excel pivot tables).**
Each of the 10 KPIs was built as a pivot table directly against the cleaned
data — kept in Excel rather than a separate tool so every number in the final
report can be traced back to a formula, not a black box.

**3. Visualization (Power BI).**
The pivot-table outputs were rebuilt as an interactive Power BI report:
clustered bar charts for region-level revenue/profit, a donut chart for
revenue contribution share, pivot-table matrix visuals for the volume and
country breakdowns, and a combo chart (bar + line, dual axis) for profit
vs. margin by category.

**4. Reporting (PowerPoint).**
The Power BI visuals and Excel KPI outputs were synthesized into a
15-slide presentation: an executive summary, one slide per KPI with a
supporting insight callout, and a closing synthesis of cross-cutting
findings and recommendations. The deck was generated from the underlying
figures via a small build script rather than assembled slide-by-slide by
hand — see *Reproducing This Project* below.

## Key Findings (Snapshot)

- **Sub-Saharan Africa and Europe** together generate **53%** of total
  revenue — a concentration worth watching.
- **Cosmetics** leads on both volume (83,718 units) and profit ($14.6M);
  **Clothes** carries the highest margin of any category (67.2%).
- Revenue growth has been **volatile, not steady** — a +186.6% swing in 2012
  was followed by three consecutive years of decline.
- **Honduras** ($6.34M) and **Kuwait** ($4,870) mark the widest country-level
  revenue gap in the dataset — roughly 1,300×.
- Average Order Value dipped to $0.93M in 2011 and recovered to $1.67M by
  2017, tracking alongside the return to positive YoY growth.

*(Full detail, context, and caveats for every KPI are in the PowerPoint report.)*

## Tools Used

- **Microsoft Excel** — data cleaning documentation and pivot-table KPI calculations
- **Microsoft Power BI** — data modeling and interactive visualization
- **Microsoft PowerPoint** — final presentation deliverable
- **Node.js + pptxgenjs** *(behind the scenes)* — a small script used to
  generate the PowerPoint report programmatically from the underlying
  figures, so the deck can be rebuilt from source data rather than edited
  by hand slide-by-slide

## Repository Structure

```
digital-echoes-sales-performance-report/
├── README.md
├── data/
│   └── Digital_Echoes_SalesRecord.xlsx        # raw data + Issues Log + KPI pivot tables
├── dashboards/
│   └── Digital_Echoes_BI.pbix                 # Power BI model & interactive visuals
└── reports/
    └── Digital_Echoes_Annual_Sales_Performance_Report.pptx
```

## Reproducing This Project

- **To explore the interactive visuals:** open `DE_BI.pbix` in
  [Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/desktop) (free).
- **To see the KPI calculations and cleaning log:** open
  `DE_SalesRecord.xlsx` and check the "Data Summary," "Test Cal.,"
  and "Issues Log" tabs.
- **To regenerate the PowerPoint report from source:** the build script isn't
  included in this repo yet — available on request if you'd like to rerun or
  adapt the report generation yourself.

## Limitations & Notes

- The underlying sample is **100 order records** — findings are directional
  and illustrative of regional/category patterns, not population-level
  statistics for a business of any particular size.
- All figures are as reported in the source export; no external data was
  merged in.

## Author

*(Add your name, LinkedIn, and/or portfolio link here.)*
