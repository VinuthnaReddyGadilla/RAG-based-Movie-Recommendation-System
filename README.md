## RAG-Based Movie Recommendation Engine
An interactive recommendation engine that suggests movies based on user mood or watch history using Retrieval-Augmented Generation (RAG). The application uses Streamlit for the interface, SentenceTransformer for embeddings, and GPT-2 for generating recommendation explanations.

### Project Overview
This project builds a movie recommendation engine that allows users to get movie suggestions based on either their current mood or favorite movies. The app combines retrieval and generation techniques, leveraging pre-trained models to provide tailored movie recommendations with contextual explanations.

### Features
**Mood-Based Recommendations**: Users can input a description of their current mood or preferences, and the app will suggest movies that align with their state.<br>
**Watch History-Based Recommendations**: Users can list their favorite movies, and the app will recommend similar movies, justifying each choice based on mood, genre, and themes.<br>
Contextual Explanations: For each recommendation, the app generates a short explanation detailing why the movie is a good fit.<br>
Token Efficiency Metrics: Tracks and displays the token count for each recommendation to optimize computational efficiency.<br>
### Dataset
**The dataset used in this project is sourced directly from the Hugging Face Datasets library**:

from datasets import load_dataset<br>
dataset = load_dataset("Pablinho/movies-dataset")["train"]<br>
It contains detailed information on movies, including titles, overviews, genres, popularity scores, and more. No manual data download is required.<br>

Preprocessing
The dataset is filtered to include movies with non-empty titles, overviews, and genres. The overviews are converted to lowercase and stripped of extra spaces for consistency.

### Preprocessing
The dataset is filtered to include movies with non-empty titles, overviews, and genres. The overviews are converted to lowercase and stripped of extra spaces for consistency.<br>

### Installation
**Clone this repository**:
git clone https://github.com/yourusername/movie-recommendation-engine.git
cd movie-recommendation-engine
### Install dependencies:
pip install -r requirements.txt
### Download the dataset from Kaggle, and place it in the data/ folder:
The Movies Dataset on Kaggle
### Run the app:
streamlit run app.py
### Usage
**Choose a Recommendation Type**: Select either "Suggest Movies Based on Current Mood" or "Recommend Movies Based on Watch History".

### Provide Input:
If using mood-based recommendations, enter a brief description of your mood.
If using watch history-based recommendations, list up to 5 of your favorite movies.
**View Recommendations**: The app will display a list of recommended movies, with overviews, genres, and explanations for each suggestion.

### Project Structure
**main.py**: Main application file with Streamlit interface.
data/: Folder to store the Kaggle movies dataset and pre-computed embeddings.

### Model and Techniques<br>
**SentenceTransformer**: Generates embeddings for movie overviews to enable similarity-based retrieval.<br>
**GPT-2 (via Hugging Face)**: Generates contextual explanations for each recommendation based on user input.<br>
**Cosine Similarity**: Used to calculate similarity between user input (mood or movie embeddings) and movie embeddings from the dataset.<br>

### Future Improvements<br>
**Additional Mood Adjustments**: Enhance mood-based adjustments to better match genres.<br>
**Model Optimization**: Experiment with more compact models for token and cost efficiency.<br>
**Enhanced Explanations**: Use additional models or prompt-engineering techniques to generate even more engaging explanations.<br>

### Acknowledgments
Special thanks to Kaggle for providing the movie dataset used in this project.
