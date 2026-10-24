# airbnb_tableau_analysis_project

# Airbnb Listings Analysis: Interactive Tableau Dashboard

An interactive Tableau dashboard that explores how Airbnb prices, supply, and revenue vary by location and unit size.

**[View the live dashboard on Tableau Public](https://public.tableau.com/app/profile/ethan.ham7063/viz/AirBnBAnalysisProject_17928014209490/Dashboard1)**

![Dashboard preview](images/dashboard.png)

## The questions

- Which zipcodes have the highest and lowest average listing prices?
- How does average price change with the number of bedrooms, and how many listings exist at each size?
- How did revenue from bookings change week to week across 2016?

## Dataset

- **Source:** [add the link where you downloaded the data]
- **Listings sheet:** 3,818 listings with 92 attributes each (location, property type, bedrooms, price, host details, review scores, availability, and more)
- **Calendar sheet:** listing ID, date, availability, and price. The version used here has 10,000 rows.
- **File:** `Tableau Full Project.xlsx`, combining both sheets

## Tools

Tableau Public and Excel

## What the dashboard shows

The dashboard combines five views:

| View | What it shows |
|---|---|
| Price by Zipcode | Average price for each zipcode (bar chart) |
| Price Per Zipcode | The same price data on a map, so geographic patterns are visible |
| Revenue for Year | Weekly total of calendar prices from January through December 2016 |
| Avg Price Per Bedroom | Average price by number of bedrooms |
| Distinct Count of Bedroom Listings | How many listings exist at each bedroom count |

## Data preparation

1. Connected the **Listings** and **Calendar** sheets and joined them on `Listings.id = Calendar.listing_id` (inner join), so each calendar price is tied to its listing.
2. Excluded listings with a missing **zipcode** so the location views only compare listings with a known location.
3. Excluded listings with **0 or missing bedrooms**, which would otherwise distort the average-price-per-bedroom view.
4. Limited the revenue view to the 2016 calendar year.

## Key findings

*Add 3 to 4 findings with numbers from your dashboard. Examples of what to look for:*

- The zipcode with the highest average price was **[zipcode]** at about **$[amount]**, compared with **$[amount]** for the lowest.
- Average price rose from **$[amount]** for [N]-bedroom listings to **$[amount]** for [N]-bedroom listings.
- Most listings are **[N]-bedroom** units, which means **[what that suggests]**.
- Weekly revenue peaked in **[month or week]** at **$[amount]** and was lowest in **[month]**.

## Limitations

- The Calendar sheet contains 10,000 rows, so the revenue view reflects that sample rather than every listing-night.
- Prices are listed prices, not confirmed bookings, so "revenue" here means the sum of calendar prices rather than money actually earned.
- Excluding null zipcodes and 0-bedroom listings removes some listings from the analysis.

## What I learned

- Joining two sheets in Tableau and checking how the join affects counts and sums
- Choosing the right chart for each question (a map for geography, a line for time, bars for comparisons)
- Handling null and zero values so averages are not misleading
- Writing findings for a non-technical audience

## Next steps

- Add a filter for property type and room type
- Run the same analysis in SQL to cross-check the Tableau results
- Test whether review scores and host status relate to price

## Repository structure

```
airbnb-tableau-dashboard/
├── README.md
├── images/
│   └── dashboard.png
├── data/
│   └── Tableau Full Project.xlsx
└── tableau/
    └── AirBnB_Analysis_Project.twbx
```
