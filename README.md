# Sentipick 
A café recommendation system that combines sentiment analysis of user reviews with item-based collaborative filtering. It evaluates review sentiment to understand user preferences and uses similarity between cafés to suggest relevant options based on past user interactions.
## Data
The dataset consists of about 2000 reviews of 20 different
cafés scraped from Google Maps
- Columns: user_id, cafe_id, cafe_name, review, polarity_score
- Rows: each review
- Excluded: ratings without any textual feedback or any that
contained less than 5 words
## Sentiment Analysis
- Create a sentiment analysis classifier with NLTK's VADER and Hugging Face RoBERTa Transformers which both are pre-trained models
- Generate polarity score (positive, negative, neutral, compound) for each review.
- Compound score: the
weighted average of the scores for
positive, negative, and neutral
sentiment of each text (ranges
from -1 to +1)
## Recommender System
- Split the dataset into
training set and
testing set.
- Transform the data into user-item
rating matrix, each cafe representing the item, 
the compound score representing the rating.
- For Item-based
Collaborative Filtering
compute similarity
scores between each
item vector pair using
cosine similarity
- Generate recommendations for a
target user by predicting unknown
ratings.
1. compute item similarity matrix
2. looping over the testing matrix,
get predictions based on similar
items and pick top 2 nearest
neighbors
3. compute weighted average
prediction
## Evaluation
Evaluate predictions
by Mean Absolute
Error and Root Mean
Square Error

