# Task 1 – Data Cleaning & Preprocessing

**Auspify Technologies – Data Science Internship Program**

## Objective

Prepare the raw Netflix dataset for analysis by cleaning, transforming, and organizing it into a reliable dataset for later tasks (EDA, recommendation system, trend prediction).

## Dataset

- **Input:** `Dataset.csv` – 8,790 rows, 10 columns (raw Netflix titles data)
- **Output:** `Netflix_Cleaned.csv` – 8,787 rows, 19 columns (cleaned and feature-engineered)

## What I did

### 1. Imported the dataset
Loaded `Dataset.csv` with Pandas and did an initial inspection with `df.head()` and `df.info()`.

### 2. Identified missing and duplicate records
- `df.isnull().sum()` reported **zero nulls** in every column, but this turned out to be misleading.
- `value_counts()` on `director` and `country` revealed the placeholder text **"Not Given"** standing in for missing data — 2,588 rows (≈29%) in `director` and 287 rows (≈3%) in `country`.
- A full-row duplicate check (`df.duplicated()`) returned 0, but checking on `title` + `type` found **3 duplicate pairs** (same show, same director, same year, same duration — just a different `show_id`).

### 3. Handled null values and inconsistent formats
- Removed the 3 duplicate rows (`8790 → 8787` rows).
- Converted the `"Not Given"` placeholders to real `NaN` values, then filled them with `"Unknown"` rather than dropping the rows (dropping would have discarded ~29% of the data).
- Merged the rare `NR` and `UR` rating labels into a single `"Not Rated"` category.
- Stripped stray whitespace from text columns.

### 4. Transformed categorical and date-related columns
- Converted `date_added` to a proper `datetime` type and extracted `year_added`, `month_added`, `month_name`, and `day_of_week`.
- Split `duration` into a numeric `duration_value` and a `duration_unit` (`min` or `Season`).
- Extracted `primary_country` and `primary_genre` from the comma-separated `country` and `listed_in` columns.
- Grouped `rating` into a simpler `audience` category (Kids / Older Kids / Teens / Adults / Not Rated).
- Converted repeated-value columns (`type`, `rating`, `duration_unit`, `audience`) to the `category` dtype for efficiency.

### 5. Produced the clean dataset
Final checks confirmed:
- **0** missing values
- **0** duplicate rows
- **8,787 rows × 19 columns**

Saved as `Netflix_Cleaned.csv`.

## Key takeaway

Pandas' default null check can miss "hidden" missing data recorded as placeholder text. Checking `value_counts()` on key columns — not just `isnull().sum()` — was what actually surfaced the real data quality issues in this dataset.

## Files in this folder

| File | Description |
|---|---|
| `Task1_Data_Cleaning.ipynb` | Notebook with all cleaning steps and outputs |
| `Dataset.csv` | Original raw dataset |
| `Netflix_Cleaned.csv` | Cleaned dataset used in later tasks |
| `screenshots/` | Evidence of each step (before/after checks) |
