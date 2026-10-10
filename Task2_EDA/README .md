# Task 2 – Exploratory Data Analysis (EDA)

**Auspify Technologies – Data Science Internship Program**

## Objective

Explore the cleaned Netflix dataset to uncover trends, patterns, and insights across content type, country, genre, release timing, duration, and audience rating.

## Dataset

- **Input:** `Netflix_Cleaned.csv` — the output of Task 1 (8,787 rows, 19 columns)

## What I did

### 1. Analyzed dataset structure and statistics
Checked shape, dtypes, and summary statistics (`df.describe()`) for both numeric and text columns.

### 2. Studied content distribution by type
- **Movies:** 6,124 titles (69.7%)
- **TV Shows:** 2,663 titles (30.3%)

Netflix's catalog is weighted roughly 70/30 toward movies over TV shows.

### 3. Identified top countries and categories
**Top 3 countries by number of titles:**
1. United States — 3,240
2. India — 1,056
3. United Kingdom — 638

**Top genre:** Dramas (1,598 titles)

**Note:** `Unknown` (287 titles, from Task 1's cleaning of missing country data) appears at position #5 in the top-10 countries — a data quality artifact worth flagging rather than hiding.

### 4. Created visualizations for key metrics
- **Content added per year** — line chart showing growth over time, peaking in **2019** (2,014 titles added that year) before declining.
- **Release year distribution** — histogram showing most content was originally released in the last decade.
- **Movie duration distribution** — histogram centered around the average of **99.6 minutes** (median 98 minutes).
- **Audience breakdown** — pie chart showing **45.6%** of content is rated for Adults, the largest single group.

### 5. Summarized findings
See `Task2_EDA.ipynb` for the full write-up. Headline takeaways:
- Movies dominate the catalog roughly 2:1 over TV Shows.
- Content acquisition/production is concentrated in the US, India, and UK.
- Dramas is the single largest genre category.
- Content additions peaked in 2019, consistent with Netflix's major content expansion era before slowing down.
- The catalog leans toward mature audiences (Adults is the largest rating group), though all age groups are represented.

## Files in this folder

| File | Description |
|---|---|
| `Task2_EDA.ipynb` | Notebook with all analysis steps, outputs, and charts |
| `Netflix_Cleaned.csv` | Input dataset (carried over from Task 1) |
| `screenshots/` | The 7 generated charts |

## Charts included

1. `content_type_distribution.png` — Movies vs TV Shows
2. `top_countries.png` — Top 10 countries by title count
3. `top_genres.png` — Top 10 genres
4. `content_by_year.png` — Titles added per year
5. `release_year_distribution.png` — Histogram of release years
6. `movie_duration_distribution.png` — Histogram of movie lengths
7. `audience_breakdown.png` — Pie chart of audience/rating groups
