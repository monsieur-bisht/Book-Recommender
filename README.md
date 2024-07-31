# Movie Recommendation App

Welcome to the **Movie Recommendation App**! This is a Streamlit application that provides personalized movie recommendations based on user-selected preferences using the MovieLens dataset.

# Usage
Launch the app:

1.Run the application by executing streamlit run app.py in your terminal.

2,Open a web browser and navigate to http://localhost:8501.

3.Select your favorite movies:
        Use the dropdown menu to choose movies that you like from the available list.

Adjust the slider:
        Choose how many movie recommendations you would like to receive. The slider allows you to select between 1 and 20 recommendations.

Click the "Give me recommendations" button:
        After selecting your favorite movies and setting the desired number of recommendations, click the button to generate personalized suggestions.

View your recommendations:
        The app will display a list of recommended movies along with their similarity scores, showing how closely they align with your selected preferences.

# Dataset
The application utilizes the MovieLens Dataset (ml-latest-small.zip), which contains the following components:

Ratings: Includes user ratings for various movies, providing a rich source of user preferences and trends.

Format: userId, movieId, rating, timestamp

Movies: Contains metadata about movies, including titles and genres.

Format: movieId, title, genres

The dataset is sourced from GroupLens Research, which offers a collection of research datasets on movie ratings.

# Methodology
The Movie Recommendation App employs user-based collaborative filtering to provide recommendations. Here's a step-by-step breakdown of the methodology:

Data Loading:
The application downloads the MovieLens dataset, extracts the necessary CSV files, and loads them into pandas DataFrames for processing.

Matrix Construction:
A user-item matrix is built where each row represents a user, each column represents a movie, and the values represent the user's rating for that movie. Missing ratings are filled with zeros.

Cosine Similarity Calculation:
The app calculates the cosine similarity between users based on their movie ratings. This metric measures the angle between two vectors, determining how similar users are in terms of their preferences.

Recommendation Generation:

Users select their favorite movies, and the app calculates the average rating for these movies across all users.

It identifies similar users based on the cosine similarity scores and aggregates their ratings to compute weighted ratings for all movies.

The app then sorts these weighted ratings and provides the top N recommended movies that have not been rated by the user, ensuring personalized suggestions.
