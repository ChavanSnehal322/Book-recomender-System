# Book-recomender-System


A web application that suggests books based on user preferences using **Collaborative Filtering** and **Content-Based Recommender** techniques. The system uses various algorithms and data processing methods to offer personalized book recommendations.

The system is built using Python, Flask, Apache Spark, and machine learning techniques to provide book recommendations based on user ratings and book features. 

The two primary techniques used in this project are Collaborative Filtering and Content-Based Filtering.


**__Overview__**

This Book Recommender System makes use of different recommendation algorithms to suggest books:

Collaborative Filtering: The system predicts which books a user might like based on the preferences of other similar users.

Content-Based Filtering: The system suggests books similar to those that the user has already liked, based on book features such as title, author, and genre.

The backend is powered by Apache Spark for handling large datasets and Flask for the web interface. The recommendation engine is trained using the books' metadata and user ratings.


**__Technologies used__**

  - Python 3.x
  
  - Flask (Web Framework)
  
  - Pandas (Data Manipulation)
  
  - Scikit-learn (Machine Learning)
  
  - Apache Spark (Big Data Processing)
  
  - PySpark (Spark's Python API)
  
  - TfidfVectorizer & CountVectorizer (Text Vectorization)
  
  - cosine_similarity (Similarity Measurement)
  
  - Pickle (Saving and Loading Data)


_Prerequisites:_
  
  Python 3.x (Check your version by running python --version)

  Apache Spark (Spark is required for Collaborative Filtering)
  

**__Steps to run the project:__**

1. Check if python is installed
     > python --version

2. Clone the repo
    > git clone https://github.com/yourusername/book-recommender.git

3. Traverse to the location of folder
     > cd book-recommender
     
4. Create and activate a virtual environment
     > python -m venv venv
     > source venv/bin/activate  # On Windows: venv\Scripts\activate
     
5. Download or provide your dataset:
  - Download the book dataset from Kaggle or use your custom dataset.
  - Make sure the dataset files (Goodread_books.csv, ratings.csv) are placed in the correct directory or update the paths in the code accordingly.

6. Run the cells one by one
   - Execute the cells in order as the output is used for processing in the next cell
   
7. Open your browser and navigate to http://127.0.0.1:5000/ to access the Book Recommender System.


**__Outcomes__**

  Once the application is running:
  
  You will see a simple homepage with a search bar to enter book titles.
  
  After entering a search query, the system will display a list of books that match your input.
  
  The Collaborative Filtering technique will suggest books based on the preferences of similar users.
  
  The Content-Based Filtering technique will recommend books based on the book features (such as genre, description, etc.).
  
  You can interact with the system and receive new suggestions each time.


__Approaches used:__

1. Collaborative Filtering:
Collaborative Filtering recommends books based on the behavior of other users with similar preferences. It works by creating a **user-item matrix** where rows represent users and columns represent books. Ratings of books by users are placed in the matrix.

The system then calculates similarities between users using cosine similarity to recommend books that similar users liked.

_Steps:_

  - Data Preprocessing: Read the ratings.csv file to get user ratings and process them.
  
  - Train a Model: Use Apache Spark's ALS (Alternating Least Squares) algorithm to train the recommendation model.
  
  - Make Predictions: Generate predictions using the trained model and recommend books to users.
  
  - RMSE Calculation: Evaluate the model's performance using Root Mean Squared Error (RMSE).


2. Content-Based Filtering

      Content-Based Filtering recommends books based on their features such as title, genre, author, etc. It uses **TfidfVectorizer** and **CountVectorizer** to process the book titles and compute similarities.

_Steps:_

  - Feature Extraction: Extract key features (such as bigrams) from the book titles using CountVectorizer or TfidfVectorizer.
  
  - Calculate Similarity: Calculate the cosine similarity between books based on their features.
  
  - Recommendation: Use the calculated similarities to recommend books based on the input title.
  
The Content-Based approach allows the system to suggest books based on title similarity and other features, even without user ratings.


