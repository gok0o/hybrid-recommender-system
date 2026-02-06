 Hybrid Recommender System (MovieLens)

This project implements a **Weighted Hybrid Recommender System** using the **MovieLens 1M dataset**.  
The system combines **content-based filtering** and **collaborative filtering** to generate more robust and personalized movie recommendations.

The project is structured to demonstrate how real-world recommender systems evolve from simple approaches to hybrid models.

---

 Project Overview

Recommender systems are widely used in platforms like Netflix, Spotify, and Amazon.  
Each recommendation approach has its own strengths and weaknesses:

- Content-based filtering works well for cold-start items but lacks personalization.
- Collaborative filtering captures user behavior but struggles with sparse data and cold-start users.
- Hybrid recommender systems combine both approaches to balance relevance, personalization, and robustness.

This project incrementally builds:
1. A **content-based recommender**
2. A **collaborative filtering recommender**
3. A **weighted hybrid recommender**

---

 Dataset

- **MovieLens 1M Dataset**
- Source: https://grouplens.org/datasets/movielens/1m/

### Files used:
- `movies.dat` → movie metadata (title, genres)
- `ratings.dat` → real user ratings

---

 Recommendation Approaches

### 1️⃣ Content-Based Filtering (Genre Similarity)
- Movies are represented using **multi-hot encoded genre vectors**
- Cosine similarity is used to measure similarity between movies
- Recommendations are based purely on item attributes
- Works well for cold-start items

📓 Notebook: `01_content_based_genres.ipynb`

---

### 2️⃣ Collaborative Filtering (Item-Based)
- Uses **real user ratings**
- Builds a user–item matrix
- Computes item–item similarity based on user rating patterns
- Captures collective user behavior

📓 Notebook: `02_collaborative_filtering.ipynb`

---

### 3️⃣ Weighted Hybrid Recommender
- Combines content-based and collaborative filtering similarity scores
- Final similarity is computed as:

\[
Hybrid\_Similarity = \alpha \cdot Content\_Similarity + (1-\alpha) \cdot CF\_Similarity
\]

- The parameter **α** controls the trade-off between content relevance and user behavior
- Provides more balanced and robust recommendations

📓 Notebook: `03_weighted_hybrid.ipynb`

---

## ⚖️ Role of α (Alpha)

- **High α** → More reliance on content-based similarity (stable, less personalized)
- **Low α** → More reliance on collaborative filtering (personalized, higher variance)
- α acts as a **bias–variance trade-off knob** in the recommender system

In this project, a fixed α is used for simplicity and interpretability.

---

## ⚠️ Limitations of the Hybrid Recommender

While the hybrid approach improves recommendation quality, it has several limitations:

1. **Manual Weight Selection**
   - The value of α is manually chosen
   - Different users or scenarios may require different α values

2. **Limited Content Features**
   - Content-based filtering relies only on movie genres
   - Does not capture finer details such as plot, cast, or director

3. **Residual Cold-Start Problem**
   - Cold-start is reduced but not eliminated
   - New users and new movies with no data still pose challenges

4. **Static Model**
   - The model does not learn from new interactions in real time
   - Requires recomputation when new data is added

---

## 🚀 Possible Improvements

- Learn α automatically using validation metrics
- Introduce richer content features (e.g., text embeddings)
- Use matrix factorization or deep learning–based recommenders
- Add user-aware hybrid logic
- Apply approximate nearest neighbor search for scalability

---

## 🛠️ Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- Jupyter Notebook

---

## ✅ Key Takeaways

- Hybrid recommenders balance stability and personalization
- Content-based and collaborative filtering complement each other
- Understanding trade-offs is more important than model complexity

---

## 📌 Author

Built as part of a hands-on machine learning learning journey, focusing on **understanding, explainability, and real-world design choices**.
