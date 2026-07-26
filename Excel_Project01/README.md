# Superstore Sales Data Analysis

A hands-on data analysis project built in Excel, exploring sales, profit, and operational patterns across a retail "Superstore" dataset (~10,000 transactions) alongside a secondary product/category dataset (~50,000 rows) and a movie box-office dataset (~1,000 records) used for statistical practice.

## Overview

This project walks through real-world data analysis tasks a business or data analyst might face: cleaning messy data, calculating aggregate metrics, identifying outliers, and surfacing insights that go beyond simple averages. All analysis is performed using native Excel formulas — no external tools or add-ins required.

## Key Analyses Performed

- **Data Cleaning** — identifying and fixing structural issues, including a systemic Product-to-Category mismatch found in a 50,000-row dataset, resolved using a standardized lookup table and `XLOOKUP`/`VLOOKUP`.
- **Aggregation & Totals** — calculating total revenue across an entire dataset and filtered by specific categories (e.g., isolating Electronics-only revenue with `SUMIF`).
- **Extremes & Outliers** — identifying the single largest financial loss and highest gain in a transaction dataset using `MIN`/`MAX` paired with `INDEX`/`MATCH`, then investigating discount level as a likely driver.
- **Central Tendency (Beyond the Average)** — calculating the **median** Sales value to reveal how a small number of large B2B orders skew the mean, giving a more honest picture of "typical" transaction size.
- **Most Common Value (Mode)** — determining the most frequently ordered quantity to inform warehouse packaging decisions.
- **Volatility / Spread** — measuring standard deviation and coefficient of variation on Gross revenue figures to quantify how unpredictable a revenue stream is.
- **Ranking Queries** — pulling the Nth-highest/lowest value from a dataset (e.g., 3rd-highest grossing title, 5th-shortest runtime) using `LARGE`/`SMALL`.
- **Conditional Tagging** — converting numeric ratings into text-based tiers (e.g., "Masterpiece", "Excellent", "Good", "Average") using nested `IF`/`IFS` logic.
- **Sampling Logic** — flagging every Nth row (e.g., every 4th record) for QA audit sampling using `MOD`.

## Tools & Functions Used

`SUM` · `SUMIF` · `AVERAGE` · `MEDIAN` · `MODE.SNGL` · `STDEV.P` · `MIN` · `MAX` · `LARGE` · `SMALL` · `INDEX` / `MATCH` · `VLOOKUP` / `XLOOKUP` · `MOD` · `COUNTA` / `COUNTIF` · nested `IF` / `IFS` · Text-to-Columns · Go To Special (Blanks) · Number/Currency formatting

## Key Insights

- Revenue and profit figures were highly skewed by a small number of outlier transactions — the **median** told a very different story from the **mean**, exposing how misleading a simple average can be for business decisions.
- A significant data quality issue (product-category mismatches) was identified and corrected using a standardized mapping approach rather than manual row-by-row fixes.
- Discount levels appeared to correlate strongly with the most extreme profit outcomes (both the biggest loss and biggest gain came from the same product category, with vastly different discount rates).

## How to Use

1. Open the relevant `.xlsx` file in Excel.
2. Formulas referenced above can be adapted to any similarly structured dataset by adjusting the cell ranges.
3. See inline comments/notes in each sheet for formula explanations.

## License

This project is intended for educational and portfolio purposes.
