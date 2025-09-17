Research Question
Can we build an accurate and scalable movie recommendation system that suggests movies to users based on their preferences, past ratings, and movie features, while comparing different classification approaches for improved prediction accuracy?

Expected Data Sources
The MovieLens dataset Links to an external site. maintained by the University of Minnesota’s GroupLens research lab. Larger versions of MovieLens (e.g., 1M, 10M ratings) may also be explored for scalability testing.

Techniques Expected to Use

Exploratory Data Analysis (EDA): Clean and merge multiple files (users, movies, ratings, metadata), analyze distributions (ratings by genre, ratings by age group), identify missing values, and visualize patterns in movie preferences. This will include identifying correlations, handling missing ratings, and exploring relationships between features.
Baseline Model: Use linear regression to produce an initial predictive output for recommendation scores.
Two-Step Classification Approach:

Predict whether a user will like/dislike a movie (binary classification).
Rank liked movies for final recommendations.
Models: Logistic Regression, Decision Trees, and Support Vector Machines (SVM), with performance comparisons for both steps.
Module 19 (Recommendation Systems) will cover techniques that I expect to use such as using the SURPRISE library to build and analyze recommender systems on real datasets and explore hybrid recommendation systems. Module 21/22  (Deep Neural Networks) will also help in maximizing model generalizability so I expect to include these techniques to progressively improve the recommendation system. 

Expected Results
A recommendation system capable of suggesting relevant movies for each user. The system will provide comparative performance metrics for different classification models, insights from collaborative vs. content-based filtering, and potentially improved accuracy from neural network integration.

Why This Question Is Important
With thousands of titles competing for attention, streaming platforms risk overwhelming users without effective recommendations. A strong recommendation engine keeps viewers engaged, reduces decision fatigue, and increases watch time. If this question is left unanswered, platforms could lose users to competitors with better personalization. By turning raw viewing data into easy-to-use recommendations, this project demonstrates how data can create a better viewer experience and drive business value.