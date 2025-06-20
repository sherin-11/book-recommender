# 📚 Book Recommendation System

This project is a hybrid **Book Recommender System** built using Python and pandas, designed to provide book suggestions using both **popularity-based** and **collaborative filtering** techniques. The model is trained on the [Book-Crossing Dataset](https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset) from Kaggle.

---

## 🔍 Features

- Popularity-based recommendations: Top-rated books with high user engagement
- Collaborative filtering using cosine similarity: Personalized recommendations based on user behavior
- Cleaned and merged datasets (Books, Ratings, Users)
- Supports storing preprocessed data and model results using `pickle`

---

## 📁 Dataset Used

The dataset is fetched using `kagglehub`:

- **Books** — book metadata including title, author, and image URLs  
- **Users** — user metadata including age and location  
- **Ratings** — ratings given by users to books (0–10 scale)

---

## 🧠 Models

### 1. Popularity-Based Recommendation

- Recommends books that have:
  - More than 250 ratings
  - High average rating
- Outputs top 50 popular books along with metadata and cover images

### 2. Collaborative Filtering (Memory-Based)

- Uses **pivot table** of users and book ratings
- Filters:
  - Users with > 200 ratings
  - Books with > 50 ratings
- Computes **cosine similarity** between books
- Provides recommendations based on similar books to a given title

---



## 🛠️ Requirements

* Python 3.x
* pandas
* numpy
* scikit-learn
* kagglehub
* pickle

Install requirements using:

```bash
pip install pandas numpy scikit-learn kagglehub
```

---

## 📦 Setup

```python
import kagglehub
path = kagglehub.dataset_download("arashnic/book-recommendation-dataset")
```

Then load and preprocess the datasets:

```python
books = pd.read_csv(f"{path}/books.csv")
users = pd.read_csv(f"{path}/users.csv")
ratings = pd.read_csv(f"{path}/ratings.csv")
```

---



