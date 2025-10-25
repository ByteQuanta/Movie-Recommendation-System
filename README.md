# 🎬 Hybrid Movie Recommendation System (ALS + Content-Based)

A hybrid movie recommendation engine combining **collaborative filtering (ALS)** with **content-based similarity**.  
It uses implicit matrix factorization for user–item interactions and integrates movie genres as content features.  
Additionally, the model is optimized using **Optuna** for hyperparameter tuning.

---

## Important Note
The source of the dataset used in this project is [Kaggle](https://www.kaggle.com/datasets/mohamedelmallah1/movielens-1m-with-posters-and-metadata?select=users.csv)


---

## 🚀 Features

✅ **Collaborative Filtering (ALS)** — Learns latent user–item factors from ratings  
✅ **Content-Based Hybridization** — Merges genre embeddings with ALS factors  
✅ **Cold-Start Handling** — Uses content similarity for unseen items  
✅ **Optuna Optimization** — Automatically tunes `factors`, `regularization`, and `iterations`  
✅ **Evaluation Metrics** — Calculates RMSE on a test split  
✅ **Mini CLI Interface** — Search for a movie and get user-based recommendations  

---

## 🧠 Tech Stack

| Category | Libraries / Tools |
|-----------|------------------|
| Data Processing | `pandas`, `numpy`, `scipy.sparse` |
| Modeling | `implicit` (ALS), `sklearn` |
| Optimization | `optuna` |
| Visualization | `matplotlib`, `seaborn` |
| Evaluation | RMSE, Cosine Similarity |

---

## ⚙️ How It Works

### 1️⃣ Data Loading & Cleaning
- Loads movie and rating data from CSV files.  
- Filters active users (with more than 20 ratings).  
- Creates internal mappings (`user_id` → `user_idx`, `movie_id` → `movie_idx`).

### 2️⃣ ALS Collaborative Filtering
- Uses **Alternating Least Squares (ALS)** from the `implicit` library.  
- Builds a sparse user–item matrix.  
- Learns latent embeddings for users and movies.

### 3️⃣ Hybrid Content Integration
- Converts genres into multi-hot vectors using `MultiLabelBinarizer`.  
- Combines normalized ALS item vectors with normalized genre vectors.

### 4️⃣ Model Evaluation
- Splits data into training and testing sets.  
- Computes RMSE between predicted and actual ratings.

### 5️⃣ Optuna Hyperparameter Optimization
- Tunes:
  - `factors` (latent dimension size)
  - `regularization`
  - `iterations`
- Minimizes RMSE on validation data.

### 6️⃣ Cold-Start Recommendation
- For new or unseen movies, uses **cosine similarity** between genre embeddings.

### 7️⃣ User Interface
- Command-line prompts for:
  - Searching a movie title
  - Entering a user ID
  - Displaying watch history and recommended movies

---



