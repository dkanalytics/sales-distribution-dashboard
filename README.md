# Sales Distribution Dashboard — Brackenfield Hardware & Supply Co

An Excel-based sales analytics dashboard built on a simulated year of transaction data, tracking performance against monthly targets and surfacing revenue concentration risk across regions, countries, and customers.

<img width="1711" height="711" alt="image" src="https://github.com/user-attachments/assets/4e2e1168-229d-4fc8-83d8-5cd5e99d5fd9" />

Slicer Demo - an interactive dashboard with monthly and regional filters.
<img width="1718" height="720" alt="Main-Screen-Shot-GIF" src="https://github.com/user-attachments/assets/051cb8fe-a820-496e-ab20-2b815b4d4a72" />

## The Scenario

Brackenfield Hardware & Supply Co. is a simulated distributor selling fasteners, fittings, and hardware across multiple regions. 

The brief: turn a year of raw transaction data into a one-page dashboard that shows whether the business is hitting its sales targets, where revenue is concentrated, and what to act on next.

## Process

**1. Cleaned and structured the raw data**
Converted the raw transaction log into a proper Excel Table (one row per sale), with consistent date, product, customer, and region fields.

**2. Replaced anonymized IDs with realistic names**
The source data used placeholder IDs (Customer01, Product01, etc.). Built a
separate mapping table and used XLOOKUP/VLOOKUP with absolute references to pull
in realistic customer and product names — then converted the formulas to static
values and pasted them back into the original columns, so the swap didn't break
any existing PivotTable relationships.

**3. Built PivotTables and PivotCharts**
Summarized the cleaned data by month, region, country, customer, and product to
drive every visual on the dashboard.

**4. Built a Target vs. Actual analysis**
A dedicated sheet compares each month's actual sales to its target, calculating
variance %, shortfall amount, and flagging months as above/below target.

**5. Assembled the dashboard**
- KPI cards: Total Sales, Number of Customers, Average Weekly Sales
- Top 3 Customers and Top 10 Products (ranked)
- Region breakdown (donut chart) and Country breakdown (ranked/funnel chart)
- Monthly Sales: Target vs. Actual (combo chart)
- Sales by Week (trend view)
- Slicers for Month and Region for interactive filtering

**6. Turned the numbers into a narrative**
Analyzed the PivotTable output to write a Key Insights and Action Items summary
— translating raw metrics (e.g. "Export = 54% of revenue") into plain-language
takeaways and concrete next steps, rather than leaving the dashboard as numbers
without conclusions.

**7. Iterated on visual design**
Refined the color palette, fixed low-contrast chart fills, filled in panels that
were originally left empty, and corrected a mislabeled chart segment.

**8. QA'd the workbook**
Went back through the formulas after the fact and caught a few real bugs along
the way — an off-by-one cell reference in a helper column, a hardcoded analysis
box that had drifted out of sync with the underlying data, and a couple of KPI
cards that were technically correct but mislabeled. Fixed each and used it as a
reminder to double check formula logic against raw source data, not just against
whether the dashboard "looks right."

## Skills Demonstrated

- Data cleaning: XLOOKUP/VLOOKUP-based ID-to-name mapping without breaking table relationships
- PivotTables & PivotCharts
- KPI calculation via GETPIVOTDATA
- Dashboard design: KPI cards, donut/funnel/combo charts, slicers
- Target-variance analysis (MoM-style tracking within a single year of data)
- Insight generation: translating metrics into a Key Insights / Action Items narrative
- Formula auditing and debugging

## Files

- `Sales-Distribution-Dashboard.xlsx` — full workbook (Dashboard, Key Insights, Pivots, Input Data, Target Analysis, Customer mapping)
- `dashboard-preview.png` — static preview image

## What I'd Improve Next

- Add a second year of data to enable true YoY comparisons alongside the current MoM/target tracking
- Rebuild the "highest shortfall" callout as a live formula instead of a manually typed value, so it can't drift out of sync again
