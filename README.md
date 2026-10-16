# Nashville-Housing-Analysis.
Excel Dashboard
# Nashville Housing Sales Analysis: Excel Dashboard

An end-to-end Excel analysis of 56,477 Nashville property sales (2013-2016): data cleaning, lookup and summary formulas, pivot tables, and a one-page interactive dashboard.

![Dashboard preview](images/dashboard.png)

## Key findings

| Question | Answer |
|---|---|
| How many sales, and what total value? | 56,477 sales worth about $18.48B |
| Which year was busiest? | 2015, with 16,829 sales and $6.71B (2013 had 11,292) |
| Is there a seasonal pattern? | Yes. June peaks at 6,593 sales and February is lowest at 2,778 |
| What do people buy? | 90.7% residential, 9.1% vacant land, 0.2% commercial/institutional. Single family alone is 60.5% |
| Which city has the highest average price? | City of Belle Meade (about $1.40M), then City of Forest Hills (about $858K) |
| Average or median price? | Average $327K, median $205K. The gap comes from a small number of very large sales |

## Dashboard contents

KPI cards (total sales, total sales value, average and highest sale price, highest average price by city), a land use share donut, a top property types donut, sales count and value by year, average price by land use and year as an index against 2013, monthly seasonality charts, and year and quarter slicers.

## Techniques used

| Area | Excel features |
|---|---|
| Land use grouping | Mapping table with XLOOKUP and INDEX/MATCH |
| Parcel history | XLOOKUP with search mode -1, MAXIFS, MINIFS, COUNTIF, DATEDIF |
| Price metrics | IF-based ratios that handle blank and zero divisors |
| District analysis | MEDIAN(IF()), AVERAGEIFS, XLOOKUP, outlier flag at 2x district median |
| Interactive lookup | Data validation drop-downs, property card with multi-column XLOOKUP |
| Reporting | Eight pivot tables (including Show Values As index against the first year), seven charts, slicers |

## Repository contents

| File | Description |
|---|---|
| `Nashville_Housing_Raw_Analysis__Excel_Dashboard.xlsx` | Cleaned data (`Sales_Clean`), pivot sheets and the `Dashboard Page` |
| `images/dashboard.png` | Dashboard screenshot |


## Data notes and limitations

- Sales cover 2013-2016. Two sales dated 2019 are excluded from trend charts because they are too few to show a pattern.
- Commercial / Institutional has only 105 sales, so its yearly averages are volatile and should be read with caution.
- The highest sale ($54,278,060) appears on 7 parcel records on the same date. It raises the average price, which is why the median is reported alongside it.
- Many records have blank `TotalValue` or `Acreage`. Ratio and per-acre columns return blank for those rows instead of zero.
- Land use values were standardised through a mapping table that merges misspelled and duplicate labels (for example, three spellings of vacant residential land).

## Author

[Your name] | [LinkedIn link] | [email]
