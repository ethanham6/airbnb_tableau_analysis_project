# airbnb_tableau_analysis_project

# Seattle Airbnb Analysis: Interactive Tableau Dashboard

An interactive Tableau dashboard that explores how Airbnb listing prices, unit sizes, and calendar prices vary across Seattle, WA.

**[View the live dashboard on Tableau Public](https://public.tableau.com/app/profile/ethan.ham7063/viz/AirBnBAnalysisProject_17928014209490/Dashboard1)**

![Dashboard preview]((https://github.com/ethanham6/airbnb_tableau_analysis_project/blob/main/Dashboard%201.png))

## The questions

- How does average price change with the number of bedrooms, and how many listings exist at each size?
- Which Seattle zipcodes have the highest and lowest average prices?
- How did total calendar prices change week to week across 2016?

## Dataset

- **Source:** [Seattle Airbnb Open Data on Kaggle](https://www.kaggle.com/datasets/airbnb/seattle)
- **Location:** Seattle, Washington, US
- **Listings table:** 3,818 listings with 92 attributes each (location, property type, bedrooms, price, host details, review scores, availability, and more)
- **Calendar table:** listing ID, date, availability, and price per night, covering 2016
- **Workbook file:** `Tableau Full Project.xlsx`, with the Listings and Calendar sheets

## Tools

Tableau Public and Excel

## What the dashboard shows

| View | What it shows |
|---|---|
| Avg Price Per Bedroom | Average price for listings with 1 to 6 bedrooms |
| Distinct Count of Bedroom Listings | How many listings exist at each bedroom count |
| Price by Zipcode | Average price for each zipcode (bar chart, sorted high to low) |
| Price Per Zipcode | The same price data on a Seattle map, so geographic patterns are visible |
| Revenue for Year | Weekly total of calendar prices across 2016 |

## Data preparation

1. Connected the **Listings** and **Calendar** sheets and joined them on `Listings.id = Calendar.listing_id` (inner join), so each calendar price is tied to its listing.
2. Excluded listings with a missing **zipcode**, so the location views only compare listings with a known location.
3. Excluded listings with **0 or missing bedrooms** (the dashboard keeps 6 of 8 bedroom values), which would otherwise distort the average-price-per-bedroom view.
4. Limited the weekly view to the 2016 calendar year.

## Key findings

- **Price rises steadily with unit size.** Average price climbs from **$96.20** for 1-bedroom listings to **$175.40** (2), **$249.70** (3), **$315.40** (4), **$450.00** (5), and **$584.80** for 6-bedroom listings. A 6-bedroom listing averages about six times the price of a 1-bedroom.
- **Supply drops sharply as units get larger.** There are **483** two-bedroom listings, **206** three-bedroom, **55** four-bedroom, and just **20** five-bedroom listings, so the largest homes are both the most expensive and the scarcest.
- **Location matters a lot.** Average price across zipcodes ranges from roughly $60 to roughly $205. Zipcode **98119** averages **$171.10**, about double the **$84.20** in **98177**. Other high-priced zipcodes on the map include **98136** ($144.10) and **98112** ($143.40).
- **Weekly totals climb early in the year, then level off.** The total starts near $1.0 million in early January, rises to about $2.0 million by late spring, stays roughly flat between $2.0 and $2.1 million through the fall, and reaches its highest point, about $2.1 million, in late December.

## Limitations

- **"Revenue" is a weekly total of calendar prices, not confirmed earnings.** In this dataset's calendar, prices are typically recorded only for nights marked available, so the line reflects listed prices for open nights, not bookings. Filtering on the `available` field would show exactly what the line includes.
- **The inner join keeps only listings found in both sheets,** so the dashboard may cover fewer than all 3,818 listings.
- **Excluding null zipcodes and 0-bedroom listings** removes some listings from the analysis.
- **Prices are averages across listings and days,** so a few expensive listings in a small zipcode can pull its average up.

## What I learned

- Joining two sheets in Tableau and checking how the join changes record counts and sums
- Choosing the right chart for each question: a map for geography, a line for time, bars for comparisons
- Handling null and zero values so averages are not misleading
- Reading a metric carefully, such as what "price" and "revenue" actually represent in a calendar table

## Next steps

- Filter the calendar by availability to separate open nights from booked ones, and rename the weekly view to match what it measures
- Add filters for property type and room type
- Run the same analysis in SQL to cross-check the Tableau results
- Test whether review scores and host status relate to price


    └── AirBnB_Analysis_Project.twbx
