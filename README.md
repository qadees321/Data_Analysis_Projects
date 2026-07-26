# From Messy Rows to a Real Dashboard 📊

I started this project with something every analyst dreads: a raw sales sheet full of blanks, duplicate helper columns, and inconsistent entries. No fancy dataset, no pre-cleaned CSV from Kaggle — just a year's worth of transactional sales data from across Pakistan that needed real work before it could say anything useful.

This repo walks through that whole journey: **raw data → cleaning → pivot analysis → dashboard.**

## What's actually in the file

The workbook is split into four sheets, each one a step in the process rather than a random tab:

- **`Raw_Data`** – the untouched export. Sale dates, customers, cities, states, regions, product categories, quantities, pricing, cost, profit, and tax — over a thousand rows of it.
- **`Data_Table`** – the cleaned version. Blank rows, broken entries, and stray duplicate columns got stripped out here so the numbers could actually be trusted.
- **`Pivot Table`** – where the real digging happened. Sales and profit broken down by product category, city, state, region, month, and customer.
- **`Dashboard`** – the final, visual summary built on top of all of that.

## What the data actually says

Once the pivots were built, a few things stood out that weren't obvious from the raw rows:

- Total sales landed around **PKR 27.3 million**, with roughly **10% flowing through as gross profit**.
- The **South region carries the business** — it alone accounts for well over a third of total sales, with **Sindh** as the top-performing state and **Karachi** as the single biggest city by revenue.
- **Furniture and Clothing** are neck-and-neck at the top of the product category list, each pulling in more than PKR 5.6 million, just ahead of Stationery and Electronics.
- Monthly sales stay fairly steady through the year, with **January and March** running slightly ahead of the rest — nothing seasonal blows the trend out of the water, which itself is worth knowing.
- A handful of repeat customers (Hafey, Areeba, Ahmed) show up again and again near the top of the revenue list, hinting at where loyalty or account-based selling might already be working.

## Why I built it this way

Anyone can drop numbers into a chart. The part that actually takes effort — and the part I wanted this repo to show — is everything *before* the chart: figuring out what counts as a valid row, deciding how to handle inconsistent city/state naming, and only then asking what story the pivot tables are trying to tell.

## Tools used

- Microsoft Excel — data cleaning, PivotTables, and dashboard visuals (no external BI tool, deliberately — wanted to show what's possible natively in Excel)

## Take a look

Open `Dashboard.xlsx` and start with the **Dashboard** tab for the summary view, or dig into the **Pivot Table** tab if you want to see how each number was built.

Feedback and suggestions on the cleaning approach are always welcome — always looking for a smarter way to handle messy real-world data.
