# Airbnb Seattle: Pricing and Availability Dashboard (Tableau)

Interactive Tableau dashboard analysing Airbnb listings in Seattle: price by area and bedroom count, listing structure, and how much of the calendar is unavailable.

Live dashboard: https://public.tableau.com/app/profile/.74781018/viz/airbnb-seattle_17932769878030/Dashboard1

## Data
Public Seattle Airbnb dataset (Kaggle), three tables:
- Listings: about 3,800 listings (price, bedrooms, zipcode, etc.)
- Calendar: nightly availability and price, snapshot taken on Jan 4, 2016
- Reviews: guest reviews with dates

## What the dashboard shows
- Average price by zipcode (bar chart and map): roughly 82 to 207 dollars per night depending on the area
- Average price by number of bedrooms: from about 96 dollars (1 bedroom) to 441 dollars (5 bedrooms)
- Number of listings by bedroom count: 1-bedroom listings dominate (2,417 of 3,440 in the 1 to 7 bedroom range)
- Share of nights unavailable by week: about 33% of nights are unavailable overall

## Data quality notes
- Joins vs relationships: the first version joined the three tables with inner joins, which produced 23.7 million rows from about 3,800 listings and distorted every average price. I replaced the joins with relationships, so each table is aggregated at its own level and listing counts are correct.
- Revenue chart replaced: the original "revenue" line summed prices of available nights only, so it did not show real revenue. I replaced it with the share of unavailable nights.
- Calendar is a snapshot, not history: it shows what was already booked or blocked on Jan 4, 2016 for the following year. A falling share of unavailable nights towards the end of the year reflects bookings not yet made, not falling demand.
- "Unavailable" is not the same as "booked": hosts can block dates themselves.
- 6 and 7 bedroom averages are based on very few listings (6 and 1) and are not reliable.

## Tools
Tableau Desktop, Tableau Public, Excel

## Author
Deniel Rahmatullin
