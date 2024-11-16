# Movie Recommendation System Project

## Overview
This project focuses on building a content-based movie recommendation system using the **TMDB 5000 Movies Dataset**. The system provides recommendations for movies that are similar to a selected movie based on the text descriptions of their overviews. The implementation employs natural language processing (NLP) techniques and cosine similarity to identify related content.

## Objective
The primary goal of this project is to create an application that suggests movies similar to a user’s input. By leveraging the content (i.e., movie overviews), the recommendation engine helps users discover films that match their interests.

## Dataset
The project utilizes the **TMDB 5000 Movies** and **TMDB 5000 Credits** datasets, which contain information about movie titles, overviews, casts, crews, and other metadata. These datasets were merged on the 'id' column to form a comprehensive dataset for analysis.

## Methodology
### 1. Data Preparation
- Loaded the data using Pandas and merged the `movies_data` and `credits_data` on the `id` column.
- Cleaned the data by handling missing values, replacing NaNs in the 'overview' column with empty strings.

### 2. Model Implementation
- Used **TF-IDF Vectorization** to transform movie overviews into numerical representations:
  - Employed the `TfidfVectorizer` from `scikit-learn` with English stop words removed.
- Constructed a **cosine similarity matrix** using `linear_kernel()` to measure similarity between all pairs of movie overviews.
- Created a reverse mapping of movie titles to DataFrame indices to facilitate quick lookups.

### 3. Recommendation Function
Defined a function, `get_recommendations(title, cosine_sim=cosine_sim)`, that:
- Takes a movie title as input.
- Finds the corresponding index from the movie indices map.
- Retrieves and sorts the cosine similarity scores.
- Returns the titles of the top 10 most similar movies.

### Example Output
Given an input movie title such as **"The Avengers"**, the system returns:
- Iron Man 3
- Iron Man 2
- Captain America: The Winter Soldier
- Thor: The Dark World
- Guardians of the Galaxy

## Deployment Plan
The project can be deployed as a web application using frameworks such as **Streamlit**. This would allow users to input movie titles and receive a list of similar movie recommendations through an interactive interface.

## Future Enhancements
- Incorporate additional metadata like genres, cast, and crew details for a hybrid recommendation model.
- Integrate with a movie database API for real-time data updates.
- Deploy the application to platforms such as **Heroku** or **Render** for public access.

This project demonstrates the effectiveness of content-based filtering in building a simple yet powerful movie recommendation system. By analyzing movie overviews and using cosine similarity, users are provided with personalized movie suggestions that align with their preferences.


