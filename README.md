# Airbnb Market Analysis – Power BI Dashboard

An interactive Power BI dashboard that explores Airbnb listings across 10 European cities: **what drives the nightly price**, **how prices differ between cities, room types and weekdays/weekends**, and **what influences guest satisfaction**.

## Dashboard Preview

| Overview | Price Influencers | Satisfaction |
|---|---|---|
| ![Overview](images/overview.png) | ![Price Influencers](images/influencers.png) | ![Satisfaction](images/satisfaction.png) |

## Pages

### 1. Overview
- **KPI cards:** average price per night, average guest satisfaction, and total number of listings.
- **Average price per night by city** (bar chart) and by city and day type (column chart).
- **Listings by room type** (donut chart): Entire home/apt, Private room, Shared room.
- **Slicers:** city, day type (weekdays / weekends) and room type.
- **Sidebar navigation buttons** to move between pages.

### 2. Price Influencers
A **Key Influencers** visual with `price_per_night` as the target. It shows which factors push the price up or down.

Explained by: city, room type, day type, person capacity, bedrooms, distance to city center, distance to metro, attraction index, restaurant index, cleanliness rating, superhost status, multi-listing host and business listing.

### 3. Satisfaction
A **Key Influencers** visual with `guest_satisfaction_overall` as the target. It uses the same factors as above, plus the nightly price.

## Data Model

The report uses a **star schema**:

```
dim_city ──────┐
dim_day_type ──┼──► fact_listings
dim_room_type ─┘
```

| Table | Description |
|---|---|
| `fact_listings` | One row per listing: price, satisfaction, cleanliness, bedrooms, capacity, distances, indexes, host flags |
| `dim_city` | City dimension |
| `dim_day_type` | Weekdays / weekends |
| `dim_room_type` | Entire home/apt, Private room, Shared room |

## Key Findings (from the Overview page)
- **Amsterdam** has the highest average nightly price, followed by **Paris** and **London**. **Athens** has the lowest among the 10 cities (weekdays view).
- Average price per night is about **134**, and average guest satisfaction is about **92.6**.
- **Entire homes/apartments (~62.7%)** and **private rooms (~36.6%)** make up almost all listings. Shared rooms are under 1%.

## Customization
- Custom Power BI theme with the Airbnb color palette: [`airbnb_theme.json`](airbnb_theme.json)
- Custom page background with the Airbnb logo: [`airbnb_background_logo.png`](airbnb_background_logo.png)

## Tools
- Power BI Desktop (data modeling, visuals, Key Influencers, page navigation buttons)
- Custom JSON theme

## How to Use
1. Download `Airbnb_Dashboard.pbix`.
2. Open it with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
3. Use the sidebar buttons or the page tabs to navigate. Use the slicers to filter by city, day type and room type.

## Data Source
Add the dataset name and link here (for example, the Kaggle page you downloaded it from).

## Author
Your name · [LinkedIn](https://www.linkedin.com/) · [GitHub](https://github.com/)
