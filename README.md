# Movie Recommendation System/Content Based Approach
This repository contains code for a movie recommendation system based on content similarity. The system utilizes the TMDB 5000 Movies dataset to recommend movies to users based on the similarity of movie attributes such as genres, keywords, cast, crew, and overview.

# Problem Understanding
The goal of this project is to develop a movie recommendation system that suggests relevant movies to users. The problem involves leveraging the information available in the TMDB 5000 Movies dataset to calculate the similarity between movies and generate personalized recommendations.

# Approach
The code follows the following steps to achieve the movie recommendations:

1.Data Preprocessing: The dataset is read from two CSV files and merged to create a consolidated dataset. Relevant columns such as "id," "title," "genres," "keywords," "overview," "cast," and "crew" are selected for movie recommendation.

2.Handling Missing and Duplicate Values: Missing values are dropped from the dataset to ensure data integrity. Duplicate rows are removed to avoid bias and repetition in recommendations.

3.Data Transformation and Cleaning: String representations of lists are converted to actual lists using the ast.literal_eval() function. The selected columns are transformed and cleaned to extract relevant information.

4.Creating a New Column: A new column named "tags" is created by concatenating cleaned columns, representing a combination of relevant information for movie recommendation.

5.Preparing Text Data for Vectorization: Text data in the "tags" column is preprocessed for vectorization. Text is converted to lowercase, and stemming is applied using the PorterStemmer algorithm.

T6.ext Vectorization: The CountVectorizer from scikit-learn is used to convert the preprocessed text data into a matrix of token counts. Stop words are removed to focus on meaningful keywords.

7.Calculating Similarity: Cosine similarity is computed between all pairs of movie vectors using the cosine_similarity function from scikit-learn.

8.Movie Recommendation: The recommend(movie) function provides movie recommendations based on similarity scores. Given a movie title, the function retrieves the index of the movie in the dataset and calculates the similarity scores with other movies. The top 5 similar movies (excluding the input movie) are recommended.

# Usage
To use the movie recommendation system:

# Clone this repository.

Install the required dependencies by running pip install -r requirements.txt.

Run the movie_recommendation.py script.

Use the recommend(movie) function to get recommendations for a specific movie. Pass the movie title as the input to the function.

# Results
The movie recommendation system provides personalized movie recommendations based on content similarity. By analyzing movie attributes such as genres, keywords, cast, crew, and overview, the system suggests similar movies that match the user's interests. The effectiveness of the recommendations depends on the quality and relevance of the dataset used.

# Future Improvements
There are several ways to enhance the movie recommendation system:

Incorporate user feedback and ratings to improve the recommendation accuracy.

Explore collaborative filtering techniques to combine content-based and collaborative filtering approaches for better recommendations.

Incorporate additional movie attributes, such as release year, runtime, and user reviews, to capture more comprehensive movie information.

Implement a user interface to allow users to interact with the recommendation system and provide feedback.

# Conclusion
This movie recommendation system demonstrates the use of content-based filtering to generate movie recommendations. By leveraging the TMDB 5000 Movies dataset, the system calculates similarity between movies and provides personalized recommendations. The code provided can serve as a starting point for building more advanced recommendation systems or be used as a reference for understanding content-based filtering algorithms.
