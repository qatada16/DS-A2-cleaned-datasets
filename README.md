# DS Assignment 2 - Cleaned Datasets (23L-0998)

Cleaned versions of the two datasets used in Data Science (CS4048) Assignment 2 (EDA). These exact files are used again in Assignment 3.

**Version:** v1.0  
**Date:** 17 October 2026

## Files

| File | Rows x Cols | Original source |
|---|---|---|
| `23L_0998_A2_netflix_cleaned.csv` | 8803 x 22 | Kaggle: Netflix Movies and TV Shows by Shivam Bansal, https://www.kaggle.com/datasets/shivamb/netflix-shows (`netflix_titles.csv`, 8807 x 12, CC0) |
| `23L_0998_A2_supermarket_cleaned.csv` | 1000 x 25 | `supermarket_Sales.csv` provided by the course instructor (1000 x 17) |

## What was changed

### Netflix
- Moved 3 runtimes ("74 min", "84 min", "66 min") that were in `rating` back into `duration`.
- Merged `UR` into `NR` and filled the 4 missing ratings (and the 3 above) with `NR`.
- Filled missing `director`, `cast` and `country` with `Unknown`.
- Removed empty country names caused by stray commas, trimmed spaces.
- Stripped and converted `date_added` to a date (YYYY-MM-DD). 10 rows have no date and were kept with an empty date.
- Removed 4 duplicate listings (same title, type, director and year, only casing or a trailing space differs). Kept the latest listing.
- Outliers (very short/long movies, old titles, long series) were kept.
- Added columns: `year_added`, `month_added`, `lag_years`, `movie_minutes`, `seasons`, `n_countries`, `n_genres`, `n_cast`, `main_country`, `rating_group`.

### Supermarket Sales
- No missing values, duplicates or label problems were found, so no rows were changed.
- `Date` converted to YYYY-MM-DD, and a combined `datetime` column was added.
- Added columns: `month`, `month_name`, `weekday`, `weekday_num`, `hour`, `day_part`, `is_weekend`.
- All original columns are kept. Note that `Tax 5%`, `Total`, `Cost of goods sold` and `Gross income` are exact functions of `Unit price x Quantity`, `Gross margin percentage` is constant, and `City` is the same as `Branch`.

## Versioning
Any later change to the cleaning will be published as a new version (v1.1, v2.0 ...). v1.0 will not be overwritten.
