# Capstone Recommender: Technical Report

## 1) Problem Statement
**Problem Statement (inferred):** Build a movie recommendation system that predicts user preference for movies and ranks items to personalize recommendations. 
The system should leverage user–item interaction data (ratings) as well as item content (genres) to recommend relevant movies.
Key challenges include data sparsity, cold start for new users/movies, feature heterogeneity (numeric ratings, categorical genres, free‑text tags), and model selection.
Potential benefits: improved user engagement, faster content discovery, and data‑driven insights into audience tastes.

## 2) Model Outcomes / Predictions
- **Learning type(s):** Classification (e.g., like/dislike or ≥ threshold), Regression (e.g., predict rating; Surprise SVD)
- **Supervision:** Supervised learning for prediction; optional unsupervised components (e.g., SVD latent factors)
- **Expected outputs:**
  - For regression: a numeric rating prediction (e.g., 1–5 stars) and rank‑ordering of movies by predicted score.
  - For classification: a probability of 'like' (≥ threshold), enabling top‑N recommendations.

## 3) Data Acquisition
**Files referenced in notebook (if any):**

- movies.csv
- ratings.csv
- users.csv

**Rationale for multi‑source data:** Ratings capture user–item interactions; Movies metadata (genres/titles) provide content features; Tags add rich, high‑signal text features. Combining them supports both collaborative and content‑based signals.

We used the [MovieLens 1M dataset](https://grouplens.org/datasets/movielens/1m/). The dataset contain 1,000,209 anonymous ratings of approximately 3,900 movies made by 6,040 MovieLens users who joined MovieLens in 2000.

## 4) Data Preprocessing / Preparation
- Merging/joining tables
- Text vectorization (TF-IDF)
- Aggregation (groupby)
- Train/test split
- Type casting
- Missing-value imputation (fillna)
- Feature scaling (StandardScaler)
- Categorical encoding (OneHotEncoder)
- Pipeline construction
- Column-wise transformations
- Encoders: OneHotEncoder
- Vectorizers: TfidfVectorizer
- Scalers: StandardScaler

**Train/Test split(s):**
- Split 1: test_size=?; random_state=?
- Split 2: test_size=0.2; random_state=42
- Split 3: test_size=0.2; random_state=42

## 5) Modeling
- DecisionTreeClassifier
- LinearRegression
- LogisticRegression

## 6) Model Evaluation
### Overall metrics
| Model               | Accuracy | Macro Precision | Macro Recall | Macro F1 | Weighted Precision | Weighted Recall | Weighted F1 |
|---------------------|----------|-----------------|--------------|----------|--------------------|-----------------|-------------|
| Logistic Regression | 0.7199   | 0.72            | 0.70         | 0.71     | 0.72               | 0.72            | 0.72        |
| Decision Tree       | 0.7178   | 0.71            | 0.70         | 0.70     | 0.72               | 0.72            | 0.71        |
| SVM                 | 0.7198   | 0.72            | 0.70         | 0.70     | 0.72               | 0.72            | 0.71        |



