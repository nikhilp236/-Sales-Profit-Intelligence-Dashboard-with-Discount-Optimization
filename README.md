# Sales & Profit Intelligence Dashboard

A Power BI + SQL + Python project that digs into 500K+ retail transactions to answer a question that should worry any business: *why are we selling more but keeping less?*

The short version — nearly a third of all transactions were losing money, and the culprit was discounting with no strategy behind it. This project traces that leak back to specific products and time periods, then lays out a pricing fix that could cut losses from ~33% to under 15%.

## Why I built this

Most "sales dashboard" projects stop at showing numbers go up or down. I wanted to build something closer to what an actual analyst gets asked to do: take a messy 500K-row dataset, find out *why* profit wasn't matching revenue, and hand back a recommendation someone could actually act on — not just a chart.

## The problem

The business looked healthy on the surface — strong revenue, steady sales volume. But profit margins were sitting at around 5%, and roughly a third of transactions were actually losing money. Digging in, the pattern wasn't random: it traced back to discounts that weren't tied to demand at all. High-selling products were getting discounted just as heavily as slow-moving ones, which meant the company was giving away margin on items that would have sold anyway.

## How I approached it

1. **Extracted and queried the raw data in SQL** — joins, CTEs, and window functions to pull sales, discount, and product-level detail out of 500K+ transaction records.
2. **Cleaned and engineered features in Python** (Pandas, NumPy) — handling inconsistent product categories, calculating per-transaction margin, and flagging loss-making rows.
3. **Built the dashboard in Power BI** — two pages, one for the overall sales/profit picture and one purpose-built for loss analysis, with drill-down by product and time period.
4. **Turned the patterns into pricing recommendations** rather than just leaving the findings as charts.

## What the data showed

- Sales peak from September to November, but profit doesn't scale with that peak — discounting eats the seasonal gain.
- Profit margin holds around 5% overall, well below what the revenue numbers would suggest.
- Beyond a certain discount threshold, deeper discounts stopped driving more volume — the company was just giving away margin for free.
- A handful of high-sales products were consistently low- or negative-margin — these accounted for a disproportionate share of the total loss.

## Dashboard

**Sales & Profit Overview**
![Sales and profit overview page](https://github.com/nikhilp236/-Sales-Profit-Intelligence-Dashboard-with-Discount-Optimization/blob/main/sales%20and%20discount(1).png)

**Loss Analysis & Recommendations**
![Loss analysis and recommendations page](https://github.com/nikhilp236/-Sales-Profit-Intelligence-Dashboard-with-Discount-Optimization/blob/main/sales%20and%20discount(2).png)

Both pages support filtering and drill-down by product and time period, so the numbers aren't just a snapshot — you can trace a loss back to the transactions causing it.

## Recommendations

- Cap discounts at 10–15% on products where they're currently uncontrolled
- Stop discounting high-demand, high-sales products entirely — they don't need the push
- Reserve deeper discounts (15–30%) for genuinely low-performing products, where they can actually move volume
- Raise prices 5–8% on products that sell well but carry thin margins
- Re-price or retire products that are consistently loss-making regardless of discount
- Introduce bundling on mid-performing products to lift average order value without relying on blanket discounts
- Shift to a seasonal pricing model that matches the Sep–Nov demand spike instead of discounting through it

## Why this matters for the business

If applied, this pricing strategy could take the loss rate from ~33% down to under 15%, and lift overall margins from ~5% into the 10–15% range — without needing to change what's being sold, just how it's priced. It also gives the business a repeatable way to catch loss-making products early instead of finding out at quarter-end.

## Tools

Power BI · SQL · Python (Pandas, NumPy)

## Repo structure

```
├── data/
├── dashboard/
├── images/
├── notebooks/
└── README.md
```

## What I'd do differently

Given more time, I'd pull in cost-of-goods data to calculate true margin rather than approximating it from price and discount alone, and I'd want at least a full year of data to confirm the Sep–Nov pattern holds rather than being a one-off. This was a solid first pass at connecting discount behavior to profit, but a production version would need to survive that kind of scrutiny.

---
If this was useful or you spot something I should've done differently, I'd genuinely like to hear it — feel free to open an issue.
