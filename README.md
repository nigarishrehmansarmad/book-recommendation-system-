# Book Recommendation System

This project implements a hybrid Book Recommendation System using the [Book-Crossing dataset](https://www.kaggle.com/datasets/somnambwl/bookcrossing-dataset). It suggests books to users based on their ratings and preferences by combining content-based and collaborative filtering techniques.

---

## Features

- **Content-Based Filtering** using book metadata (title, author, publisher)
- **User-Based Collaborative Filtering** based on similar users' preferences
- **Item-Based Collaborative Filtering** for users with only one rating
- **Global Top Picks** fallback for users with no ratings

---

## Dataset

- **Source**: [Book-Crossing Dataset on Kaggle](https://www.kaggle.com/datasets/somnambwl/bookcrossing-dataset)  
- **Files Used**:
  - `Books.csv`
  - `Ratings.csv`
  - `Users.csv`

---

## How It Works

1. **Data Loading**: Downloads and loads CSV files using `kagglehub` and `pandas`.
2. **Preprocessing**:
   - Fills missing values and removes zero ratings.
   - Merges `Books`, `Ratings`, and `Users` data.
3. **Feature Engineering**:
   - Combines `Title`, `Author`, and `Publisher`.
   - Applies `TfidfVectorizer` and normalizes vectors.
4. **Recommendation Logic** (`recommend_books(user_id, ...)`):
   - Chooses the appropriate method based on how many books the user has rated.

---

## Recommendation Methods

### 1. **Content-Based Filtering**
- Creates a metadata profile using `TF-IDF` and computes similarity using cosine distance.
- Recommends books similar to those rated highly by the user (≥ 8).

### 2. **User-Based Collaborative Filtering**
- Builds a user-item matrix and finds users with similar rating behavior.
- Suggests books liked by those similar users.

### 3. **Item-Based Collaborative Filtering**
- Triggered when the user has rated exactly one book.
- Finds other users who liked the same book and recommends books they also enjoyed.

### 4. **Global Top Picks**
- Used for new users with no prior ratings.
- Recommends the highest-rated books overall.

---

## Contributors

- [@Khoula Adil](https://github.com/KhoulaAdil)
- [@Uroosha Zehra Abidi](https://github.com/Uroosha4048)
- [@Nigarish Rehman Sarmad](https://github.com/nigarishrehmansarmad)
