# Movie Recommendation System – Capstone Project

## Project Overview

This project builds an end-to-end **movie recommendation system** using the [MovieLens 1M dataset](https://grouplens.org/datasets/movielens/1m/). Our goal was to predict user preferences for movies based on historical interactions and provide **personalized recommendations** that improve content discovery and engagement.

The project combines **collaborative filtering**, **content-based features**, and **classification models** to deliver recommendations. It explores the entire machine learning lifecycle — from data exploration and preprocessing to model building, evaluation, and recommendation generation.


## Non-Technical Summary (Business Perspective)

### Problem Statement

With thousands of movies available, users often experience choice overload, leading to poor engagement and churn. A recommendation system addresses this by **understanding user preferences** and **surfacing relevant titles** automatically.

Our goal:

* Predict whether a user will **like** a movie based on their historical ratings and content attributes.
* Rank movies to show the most relevant recommendations first.


### Key Insights and Findings

* **User preferences follow distinct patterns** based on genre and past interactions. For example, users who rate "Comedy" movies highly are significantly more likely to enjoy similar titles, even if they haven’t watched them before.
* Adding **content-based metadata** (like genres and tags) to collaborative signals improved predictive accuracy, especially for the cold-start problem (new users or new movies).
* Logistic Regression and Support Vector Machines performed consistently well, achieving **~72% accuracy** in predicting whether a user will like a movie.
* Feature importance analysis revealed that:

  * **User average rating** and **movie popularity** were the strongest predictors of preference.
  * Certain genres (e.g., Comedy, Drama, Action) had strong positive weights, while others were more neutral.


### Business Value

* **Improved Engagement:** Personalized recommendations increase user satisfaction and watch time.
* **Content Discovery:** Helps surface lesser-known titles to the right audience.
* **Strategic Insights:** Feature analysis informs marketing and acquisition strategies based on genre or user segments.


### Next Steps & Recommendations

* **Incorporate Deep Learning:** Neural collaborative filtering or hybrid neural models can capture more complex user-movie relationships.
* **Leverage Time Series Analysis:** Include timestamps to model how user preferences evolve over time.
* **Add Explainations:** Surface “Why recommended?” explanations to improve user trust and interaction.


# Technical Report

## Data Acquisition

**Dataset**
Source: MovieLens 1M
Size: ~1 million ratings from 6,040 users on 3,900 movies
Schema:
- movies.csv
- ratings.csv
- users.csv


## Data Preprocessing / Preparation
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
- Split 1: test_size=0.2; random_state=42

## Modeling
We implemented multiple predictive models:
| Model                   | Description                                      |
| ----------------------- | ------------------------------------------------ |
| **Logistic Regression** | Baseline binary classifier (like/dislike)        |
| **Decision Tree**       | Non-linear model capturing feature interactions  |
| **SVM**                 | High-dimensional classifier for robust accuracy  |
| **Linear Regression**   | Used for rating prediction (regression approach) |
Additionally:
- GridSearchCV was applied to tune hyperparameters.
- Cross-validation ensured model robustness.

## Results
| Model               | Accuracy | Macro F1 | Weighted F1 |
| ------------------- | -------- | -------- | ----------- |
| Logistic Regression | 0.7199   | 0.71     | 0.72        |
| Decision Tree       | 0.7178   | 0.70     | 0.71        |
| SVM                 | 0.7198   | 0.70     | 0.71        |

Logistic Regression provided the best trade-off between interpretability and performance.
All models performed consistently, confirming the predictive signal in the feature set.

## Feature Importance (Logistic Regression)
User average rating: Most influential predictor
Movie mean rating: Strongly correlated with “like” probability
Genre features: Comedy, Action, Drama contributed significantly
TF-IDF tags: Added marginal improvement but increased interpretability

## Visualizations
Our exploratory data analysis (EDA) included:
- Distribution of ratings and genres
- Ratings per user and per movie
- Correlation heatmaps
- Feature importance plots

These visualizations highlighted strong user–movie interaction trends and guided feature engineering decisions.

## Repository Structure
```plaintext
Capstone_Recommender/
│
├── Capstone_recommender.ipynb    # Main analysis & modeling notebook
├── README.md                     # This file – project summary & findings
├── data/                         # Raw and preprocessed datasets
│   ├── movies.csv
│   ├── ratings.csv
│   └── users.csv
```


## Conclusion
This project demonstrates how to build a complete recommendation system from data exploration to predictive modeling and how to interpret the results to drive product decisions. The models achieved solid predictive performance (~72% accuracy) and revealed actionable insights about user preferences.
With further enhancements like deep learning models, time-aware recommendations, and deployment pipelines, this system could power real-world personalization engines in streaming platforms or content discovery apps.