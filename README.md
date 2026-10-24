Auspify Data Science Internship

Projects completed for the Auspify Technologies Data Science Internship Program, using the Netflix titles dataset. Each task is in its own folder, with a notebook, a short README and screenshots of the outputs.

Tasks
#	Task	Level	What it does	Folder
1	Data Cleaning & Preprocessing	Easy	Cleans and transforms the raw dataset (8,790 rows to 8,787 rows, 10 to 19 columns). Finds hidden "Not Given" missing values and removes duplicate titles.	Task1_Data_Cleaning
2	Exploratory Data Analysis	Easy	Explores the cleaned data: movies vs TV shows, top countries and genres, content added per year, movie length and audience ratings.	Task2_EDA
3	Recommendation System Analysis	Medium	Content-based recommender using TF-IDF and cosine similarity on genre, director, country and type. Matches the audience group 50% of the time vs 32% for random picks.	Task3_Recommendation
4	Trend Prediction Analysis	Medium	Analyzes titles by release year and compares forecasting models on 2017–2020. Forecasts 2021–2025.	Task4_Trend_Prediction
Tools used

Python, Pandas, NumPy, Matplotlib, Seaborn, scikit-learn, statsmodels, Jupyter Notebook

Data flow
Dataset.csv  →  Task 1 (cleaning)  →  Netflix_Cleaned.csv  →  Tasks 2, 3 and 4

Tasks 2, 3 and 4 read Netflix_Cleaned.csv, which is stored in the Task1_Data_Cleaning folder. To run those notebooks, place a copy of the file next to them.

How to run
1.Install the libraries: pip install pandas numpy matplotlib seaborn scikit-learn statsmodels jupyter.

2.Open a notebook in Jupyter.

3.Make sure Netflix_Cleaned.csv is in the same folder as the notebook, then run the cells from top to bottom.

Kaushika Dewmini Data Science Intern, Auspify Technologies

#Auspify #AuspifyTechnologies #AuspifyInternship #AuspifyProjects
