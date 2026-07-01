# Movie Recommender System (Collaborative Filtering)
### By: Amartiya Kakodiya | IIT Kharagpur

## Overview
This project builds a user-based collaborative filtering 
recommender system from scratch using cosine similarity. 
Given a user-item rating matrix (200 users, 51 movies), 
the system identifies the most similar users and generates 
personalized movie recommendations using a similarity-weighted 
average of their ratings.

## Tools
Python | NumPy | Pandas | Scikit-learn | Matplotlib

## Methodology
1. Build MovieLens-style dataset (200 users, 51 movies, 5518 ratings)
2. Construct user-item rating matrix (pivot table, fill missing with 0)
3. Compute user-user cosine similarity matrix
4. For target user: find top-10 most similar users
5. Predict ratings using similarity-weighted average of neighbor ratings
6. Generate personalized top-N recommendations (excluding already rated)
7. Evaluate using Mean Absolute Error (MAE) on held-out ratings

## Key Results
- Total Users:          200
- Total Movies:         51
- Total Ratings:        5518
- Matrix Shape:         200 x 51
- Matrix Sparsity:      45.9%
- Neighbors Used (k):   10
- Mean Absolute Error:  0.60 (on 1-5 rating scale)

## Sample Recommendations (User 1)
| Movie                | Predicted Rating |
|----------------------|-----------------|
| Django Unchained     | 4.48            |
| Titanic              | 4.43            |
| Vertigo              | 4.34            |
| Rear Window          | 4.33            |
| The Lion King        | 4.32            |

## Key Insights
1. User-based collaborative filtering predicts ratings within 
   ~0.6 stars of actual ratings on a 1-5 scale
2. Cosine similarity effectively identifies users with similar 
   taste profiles for personalized recommendations
3. Real-world systems face much higher sparsity (95-99%) than 
   this demo dataset (45.9%) — production scale systems require 
   matrix factorization techniques (SVD, ALS)
4. This approach represents the foundation of recommendation 
   engines used by Netflix, Amazon and Spotify

## Visualisations
- recommender_evaluation.png — actual vs predicted ratings 
  scatter plot and user similarity heatmap (first 20 users)
