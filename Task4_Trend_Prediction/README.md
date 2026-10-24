# Task 4 – Trend Prediction Analysis

**Auspify Technologies – Data Science Internship Program**

## Objective

Analyze historical Netflix content trends by release year and forecast future content growth.

## Dataset

- **Input:** `Netflix_Cleaned.csv` – the output of Task 1 (8,787 titles, 19 columns).
- The file is stored in the [`Task1_Data_Cleaning`](../Task1_Data_Cleaning/Netflix_Cleaned.csv) folder. To run the notebook, place a copy next to it.

## What I did

### 1. Prepared release-year data
I counted the number of titles for each `release_year` from 2000 to 2020. I left out 2021 because the data stops in September 2021, so that year is incomplete and would look like a false drop.

### 2. Analyzed yearly content trends
I plotted titles per release year and calculated the year-on-year growth rate.

- Titles grew from 286 in 2013 to a peak of **1,144 in 2018**.
- After the peak, the count fell to 1,029 in 2019 (-10.1%) and 953 in 2020 (-7.4%).

### 3. Built forecasting models
I split the data by time, not randomly: **training on 2000–2016 and testing on 2017–2020**. I compared five models using MAE and RMSE:

| Model | MAE | RMSE |
|---|---|---|
| Naive (repeat last year) | 138.0 | 153.9 |
| Polynomial (degree 2) | 183.7 | 203.5 |
| Linear regression | 454.4 | 464.7 |
| ARIMA(1,1,1) | 699.8 | 802.5 |
| Holt (damped trend) | 718.4 | 833.9 |

### 4. Visualized future predictions
I refitted Holt and ARIMA on all the data and forecast 2021–2025.

| Year | Holt | ARIMA |
|---|---|---|
| 2021 | 888 | 907 |
| 2022 | 835 | 879 |
| 2023 | 794 | 862 |
| 2024 | 760 | 852 |
| 2025 | 734 | 846 |

### 5. Interpreted results
- The simple "repeat last year" baseline had the lowest error on the test years.
- The more complex models were trained during fast growth (2000–2016) and kept projecting it, but the trend changed direction after 2018.
- Both final forecasts expect the yearly count to level off or decline slightly, not return to rapid growth.

## Limitations

- The drop in 2019–2020 may partly be caused by COVID slowing production.
- The dataset only holds titles that were on Netflix in 2021, so recent years are not a full count of what was produced.
- With about 20 yearly data points, forecasts five years ahead are rough estimates, not exact predictions.

## Files in this folder

| File | Description |
|---|---|
| `Task4_Trend_Prediction.ipynb` | Notebook with all steps, outputs and explanations |
| `Screenshots/` | Output screenshots for each step |
