# Data Analytics Project 01 📊

Three datasets, one spreadsheet, zero patience for messy data.

## What's actually in here

I got tired of doing "analysis" that only ever touched one clean, pre-packaged dataset — so I picked three completely different ones on purpose: a curated movie list, a deliberately messy sales export, and a well-known retail dataset. Different problems, different muscles.

### 🎬 IMDB Top 1000
Started with the classic IMDB Top 1000 movies list and pushed past the obvious "what's the highest rated movie" question. Instead I went after things like:
- Total gross revenue across the entire list, and how wildly it swings between titles (built out a volatility/fluctuation check to quantify it)
- The 3rd highest-grossing film and the shortest movie sitting in the bottom 5 by runtime — the kind of oddly specific lookups a stakeholder actually asks for
- Converted the raw `IMDB_Rating` numbers into readable tiers (Masterpiece / Excellent / Good / Average) and counted how many movies land in each, turning a column of decimals into something a non-analyst can skim in five seconds

### 🛒 Sales Data (50,000 rows)
This one's the messy one, and it's messy on purpose. The raw export has products mislabeled into the wrong category — a "Notebook" tagged as Furniture, a "Laptop" tagged as Furniture (it's not, obviously) — so before any real analysis could happen, I had to:
- Build out an `Incorrect Category` vs `Correct Category` comparison to catch and fix the mislabeling
- Deduplicate the record count and confirm the real number of clean entries
- Break down category performance once the categories were actually trustworthy, including isolating Electronics-only products and totaling their revenue

Basically: don't trust the category column just because it exists.

### 🏬 Superstore Dataset
The deepest one. Took the well-known Superstore orders dataset and layered in the kind of logic a Finance or Ops team would actually request, one requirement at a time:
- **Profit Tier** — flags every order as Profitable / Loss / Break-even off the Profit column
- **Audit Flag & Region Codes** — a lightweight validation layer plus shorthand region codes for filtering
- **Sales Ranking** — every single order ranked against the entire dataset, highest sale to lowest
- **B2B Promotion Flag** — an XOR-style rule (qualifies if Corporate segment *or* over $1,000 in sales, but disqualified if it's *both*) — the kind of "sounds simple, isn't" logic that trips up a plain AND/OR
- **Dynamic, filter-aware totals** — a running Sales total that recalculates when you filter by City or Region, wrapped in error handling so a deleted column shows a clean message instead of Excel's `#REF!`
- Quartile and percentile thresholds to define sales tiers (bottom 25%, top 25%, top 5% VIP) for a Finance-style segmentation

## Why I built it this way

Anyone can filter a spreadsheet and screenshot a pivot table. What I wanted to practice was the stuff that actually shows up in a real analyst's inbox: "can you exclude X but not Y," "flag this but not if it's also that," "make sure this doesn't break when someone deletes a column." Those requests sound small until you're the one writing the formula.

## Tools
Excel formulas (COUNTIFS, SUMIFS, AVERAGEIFS, SUBTOTAL, QUARTILE, PERCENTILE, RANK, nested IF/OR/AND logic), no macros, no external BI tool — just spreadsheet fundamentals pushed as far as they'll go.

---
*Feedback, questions, or "why didn't you just use Python for this" — all welcome. Open an issue.*
