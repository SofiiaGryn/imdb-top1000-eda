# IMDb Top 1000 Movies — Exploratory Data Analysis

Exploratory data analysis of the IMDb Top 1000 Movies dataset, answering 24 analytical questions through data cleaning, feature engineering, and visualization.

---

## Overview

This project is part of Sprint 3 at Turing College. It explores the IMDb Top 1000 Movies dataset from Kaggle, covering a wide range of genres, directors, actors, ratings, revenues, and release years.

The notebook focuses on practicing data cleaning best practices, defining reusable helper functions, and conducting a thorough exploratory analysis.

---

## Dataset

**Source:** [Kaggle — IMDb Dataset of Top 1000 Movies and TV Shows](https://www.kaggle.com/datasets/harshitshankhdhar/imdb-dataset-of-top-1000-movies-and-tv-shows)

**Size:** 1,000 rows covering films across multiple decades and genres.

**Key columns:** Title, Genre, Director, Main Star, Released Year, Runtime, IMDb Rating, Meta Score, Revenue (millions), Votes (millions), Certificate.

---

## Project Structure

```
project/
│
├── Sprint_3_project.ipynb   # Main analysis notebook
└── README.md                # Project documentation
```

---

## Notebook Structure

### 1. Data Loading
- Downloads the dataset directly from Kaggle using `opendatasets`

### 2. Helper Functions
- `fill()` — fills NaN values with mean or median depending on outlier presence
- `hist_plot()` — plots a histogram with annotated mean and median lines

### 3. Data Cleaning
- Dropped unnecessary columns (`Star2`, `Star3`, `Star4`) and duplicate rows
- Renamed columns for clarity (`Star1` → `Main Star`, `Gross` → `Revenue(millions)`)
- Handled missing values in `Certificate`, `Meta_score`, and `Revenue` using outlier-aware strategies (median where outliers were detected)
- Fixed a data entry error in `Released_Year` (manually corrected *Apollo 13* from `"PG"` to `1995`)
- Converted `Runtime` and `Released_Year` to integers
- Normalized `Revenue` and `Votes` to millions
- Simplified `Genre` to retain only the primary genre per film

### 4. Exploratory Data Analysis — 24 Questions

Examples of questions explored:

- What is the highest-rated movie in the dataset?
- Which directors have the most movies in the top 1000?
- Which genre has the highest average gross revenue?
- Are movies with longer runtimes generally rated higher?
- What is the relationship between number of votes and gross revenue?
- How many movies have an IMDb rating ≥ 8.5 and a Metascore > 85?

The analysis also includes an **off-program section** where the correlation formula is manually verified using covariance and variance decomposition.

---

## Key Findings

- Most films have an IMDb rating between **7.7 and 8.1**, with a near-symmetrical distribution.
- **Drama** is the most represented genre in the top 1000.
- **Family** genre has the highest average gross revenue, but this is misleading due to a very small sample size and one major outlier (E.T.).
- There is a **moderate positive correlation (0.58)** between number of votes and gross revenue.
- There is **no meaningful correlation** between runtime and ratings (verified both automatically and manually).

---

## Installation

```bash
pip install pandas numpy matplotlib seaborn opendatasets
```

Then open the notebook:

```bash
jupyter lab
```

You will need your **Kaggle credentials** (username and API key) to download the dataset.

---

## Notes

- This is an exploratory analysis, not a causal study.
- Results depend on IMDb's selection of the top 1000 films, which introduces selection bias.
- Some genres are underrepresented, which can skew averages.

---

## Author

Sofiia Gryn — Turing College, Sprint 3
