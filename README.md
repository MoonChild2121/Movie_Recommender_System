# Movie Recommender System
The recommendation system uses a content-based approach, where movies are recommended based on their similarity in terms of tags. The website is developed using streamlit and deployed on Heroku. The user selects a movie and is recommended 5 movies which are most probable to the user's liking.


## Deployed on
https://moon-child-39ad11c95ef3.herokuapp.com/

## Datasets
The two datasets used are
https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata?select=tmdb_5000_movies.csv (4803, 20)
https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata?select=tmdb_5000_credits.csv (4803, 4)

## Data Preprocessing:
Merged the movies and credits datasets on the 'title' column.
Extracted relevant columns: 'movie_id', 'title', 'overview', 'genres', 'keywords', 'cast', 'crew'.
Handled missing values by dropping rows with null values.
Cleaned and processed the 'genres', 'keywords', 'cast', and 'crew' columns using ast.literal_eval.
Created a new column 'tags' by combining 'overview', 'genres', 'keywords', 'cast', and 'crew'.
Tokenized and stemmed the 'tags' column to prepare for vectorization.

## Text Vectorization:
Used CountVectorizer to convert the 'tags' into a numerical format.
Applied text vectorization with a maximum of 5000 features and English stop words.

## Cosine Similarity:
Calculated cosine similarity between movies based on their vectorized tags.
Created a similarity matrix to represent the similarity between movies.

## Recommendation Function:
Implemented a recommendation function (recommend) that takes a movie title as input and recommends similar movies.
The function prints the top 5 recommended movies based on similarity.

## Model Evaluation:
No explicit model evaluation is performed in this content-based recommendation system as it does not rely on user ratings or feedback.

## Save Model and Data:
Serialized the recommendation system by saving the 'movies_dict.pkl' and 'similarity.pkl' files using the pickle module.

## To Run
Make pkl files for new_df and similarity and put them in same directory as app.py to run the site locally, the rest of the files are for deployment

## Resources
Site used to get movie posters
https://www.themoviedb.org
Streamlit documentation
https://docs.streamlit.io/library/api-reference


