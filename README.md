# walmart-hurricane-project
**DS2002 · Fall 2026 · Midterm Project**

## Team

**Water Duo**

| Name | GitHub | Main contribution |
|---|---|---|
| Jiaxian Wang | `jiaxian-wang` | Store-level sales and forecast-path analysis |
| Anya Chang | `enyachang1119-debug` | Board game sales and SQLite inventory analysis |

## Summary

We analyzed how sales changed across 12 Florida Walmart stores before Hurricane Helene. We cleaned the transaction data, grouped related SKUs, and joined Orlando sales with historical weather data. We also compared transaction records with SQLite sales and inventory data to investigate the reported increase in board game sales.

## Data

| File | Source | Contents |
|---|---|---|
| `walmart_transactions.csv` | DS2002 course data | September 2024 sales transactions |
| `store_locations.csv` | DS2002 course data | Store IDs, locations, and coordinates |
| `product_catalog.csv` | DS2002 course data | Product names, SKUs, categories, and package sizes |
| `distribution_centers.csv` | DS2002 course data | Distribution center locations and capacity |
| `inventory_and_sales.db` | DS2002 course data | Daily category sales and SKU-level inventory records |

The data files are in [`data/`](data/). We used the [Open-Meteo Historical Weather API](https://open-meteo.com/) to retrieve daily weather for Orlando. The API endpoint was `https://archive-api.open-meteo.com/v1/archive`. The forecast coordinates came from [NHC Hurricane Helene Forecast Advisory 10](https://www.nhc.noaa.gov/archive/2024/al09/al092024.fstadv.010.shtml).

## How to Run

1. Open the [final notebook](notebooks/walmart_hurricane_analytics.ipynb) in Google Colab.
2. Start a fresh runtime and select Runtime → Run all.
3. The first code cell clones the team repository if needed and loads the input files from `data/`. The weather cells request historical data from Open-Meteo.

## Key Findings

- In the seven days before landfall, average daily Breakfast sales rose 409.76% from baseline. Emergency products had the largest increase in daily units sold, from 356.57 to 1,006.43.
- Stores nearer the forecast path had a median sales increase of 144.26%, compared with 141.29% for farther stores. Both groups had a median surge onset of September 21.
- Recorded board game sales rose 156.58%. The SQLite sales summary reports the full Entertainment category, so it could not verify the reported 250% increase for board games.

## Recommendation

Walmart should prioritize emergency supplies and breakfast products before the next hurricane. Each store’s recent sales can help determine how much inventory to send and when to replenish it. For board games, Walmart should add a modest amount of stock at stores where recent sales indicate higher demand.

## Reflection

The five reflection responses are at the end of the final notebook under Reflection.
