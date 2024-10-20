# Netflix Movie Recommendation System

This project is a **Content-Based Movie Recommendation System** that suggests similar movies based on the description and genre. Built using **Streamlit** for the front-end and leveraging **CountVectorizer** and **Cosine Similarity** from **scikit-learn**, this system helps users find movies similar to the ones they like.

## Features

- Recommends 5 movies similar to the selected movie.
- Uses **cosine similarity** to compute similarity based on the genre and description (overview).
- Provides a **Streamlit** web interface for user interaction with dropdown selection for movies.
- Simple and efficient design with easy setup for personal use.

## Table of Contents

- [Installation](#installation)
- [How It Works](#how-it-works)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

## Installation

To get this project up and running, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/Netflix-Movie-Recommendation-System-with-simple-GUI.git
    ```

2. Navigate into the project directory:

    ```bash
    cd netflix-movie-recommendation-system
    ```

3. Create and activate a virtual environment:

    ```bash
    python -m venv .venv
    source .venv/bin/activate     # For MacOS/Linux
    .venv\Scripts\activate        # For Windows
    ```

4. Install the required dependencies:

    ```bash
    pip install pandas streamlit
    ```

5. Run the Streamlit app:

    ```bash
    streamlit run app.py
    ```

6. Open your browser and go to `http://localhost:8501/` to interact with the app.

## How It Works

### Backend (Movie Recommendation Algorithm)

1. **Data Preprocessing:**
   - The dataset is loaded from a CSV file, and columns like `title`, `overview`, and `genre` are processed.
   - A new feature `tags` is created by combining the `overview` and `genre` columns to form a textual representation of the movie.

2. **Text Vectorization:**
   - A **CountVectorizer** is used to convert the `tags` column into a matrix of token counts. This transforms the text into numerical features.

3. **Cosine Similarity:**
   - Cosine similarity is computed between all movie vectors to identify movies that are most similar to the selected one.

4. **Recommendation Function:**
   - The recommendation function retrieves the index of the selected movie and calculates the similarity scores for all other movies. The top 5 most similar movies are returned as recommendations.

### Frontend (Streamlit App)

1. A **Streamlit** app provides the user interface.
2. Users can select a movie from a dropdown list.
3. Upon clicking "Show Recommendation," 5 similar movies are displayed in columns.

## Usage

1. After running the app using Streamlit, a webpage will open where you can:
   - Select a movie from the dropdown list.
   - Click the "Show Recommendation" button.
   - The app will display 5 movies similar to the selected movie.

## Project Structure
├── .venv                               # Virtual environment folder
├── app.py                              # Streamlit application
├── movies_list.pkl                     # Pickle file containing processed movie data
├── similarity.pkl                      # Precomputed similarity matrix for recommendations
├── netflix-movie-recommendation-system.ipynb   # Jupyter Notebook for system development


## Future Work

- **Enhance Data Features:** Add more features like cast, director, and movie ratings to improve recommendation accuracy.
- **Collaborative Filtering:** Integrate user-based or item-based collaborative filtering for better personalization.
- **UI Improvements:** Enhance the front-end with better styling and visual improvements.
- **Deployment:** Deploy the Streamlit app to a cloud service like Heroku or Streamlit Cloud for broader access.

## Contributing

Feel free to fork the repository, create a branch, make improvements, and submit a pull request. Contributions are welcome and appreciated!

