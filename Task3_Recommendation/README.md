# Task 3 – Recommendation System Analysis

**Auspify Technologies – Data Science Internship Program**

## Objective

Build a basic content-based recommendation model that suggests Netflix titles similar to a title the user picks.

## Dataset

- **Input:** `Netflix_Cleaned.csv` – the output of Task 1 (8,787 titles, 19 columns).
- The file is stored in the [`Task1_Data_Cleaning`](../Task1_Data_Cleaning/Netflix_Cleaned.csv) folder. To run the notebook, place a copy next to it.

## What I did

### 1. Extracted relevant content features
The dataset has no plot description or cast column, so I described each title using four fields:
genres (`listed_in`), director, country and type. I left out "Unknown" values so that thousands of titles would not look similar just because information was missing.

### 2. Performed text preprocessing
I made all text lowercase and removed spaces inside names, so "Independent Movies" stays one token. I then joined each title's features into one text string. Genres are repeated twice, so they have the most influence.

### 3. Calculated content similarity
I converted the text to numbers with TF-IDF (8,787 titles × 5,114 features) and compared titles using cosine similarity. Similarity is calculated for one title at a time, which avoids storing a full 8,787 × 8,787 matrix.

### 4. Generated recommendations for selected titles
A `recommend(title)` function returns the 5 most similar titles. Examples:

| Watched | Top recommendations |
|---|---|
| *Midnight Mass* | *The Haunting of Hill House*, *The Haunting of Bly Manor*, *Ratched* (similarity 0.901) |
| *Ganglands* | *Lupin*, *Crime Time* (0.863) |
| *Sankofa* | *Shanghai*, *LSD: Love, Sex Aur Dhokha* (0.519) |

### 5. Evaluated recommendation quality
I picked 300 random titles and checked how often their top 5 recommendations had the same audience group (Kids, Older Kids, Teens, Adults, Not Rated). Audience was not used to build the features, so the test is not circular.

| | Same-audience rate |
|---|---|
| My model | **0.50** |
| Random picks | 0.32 |

## Key takeaways

- The recommender clearly does better than random picks and gives sensible suggestions.
- It is limited. It only sees genre, director, country and type, with no plot text.
- Many titles tie at the same score because they share the same genres and an unknown director.
- To improve it, I would add plot descriptions or cast data and handle ties between titles with identical features.

## Files in this folder

| File | Description |
|---|---|
| `Task3_Recommendation.ipynb` | Notebook with all steps, outputs and explanations |
| `Screenshots/` | Output screenshots for each step |
