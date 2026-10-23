# 🎬 Item-Based Collaborative Filtering Recommender System

---

## 📌 Project Overview

This project implements an **Item-Based Collaborative Filtering** recommendation engine utilizing the MovieLens benchmark dataset. Instead of profiling individual user preferences, the algorithm evaluates global rating co-occurrence patterns across films to compute cosine similarity scores and recommend top affinity titles.

---

## 📊 Dataset Structure

Built on the official **MovieLens Latest Small Dataset** from GroupLens Research:

* **Ratings Schema (`ratings.csv`):** 100,836 ratings across 9,742 movies by 610 users (`userId`, `movieId`, `rating`, `timestamp`).
* **Movies Schema (`movies.csv`):** Movie titles and genre designations (`movieId`, `title`, `genres`).

---

## 🔬 Mathematical Methodology

### 1. User-Item Interaction Matrix
The merged rating stream is reshaped into a high-dimensional pivot matrix $R \in \mathbb{R}^{M 	imes U}$ where rows represent movies ($M$), columns represent users ($U$), and entries $r_{m,u}$ denote user ratings. Unrated pairings are zero-filled.

### 2. Cosine Similarity Metric
Item-item similarity is computed via the Cosine Similarity operator across rating vectors $ec{u}$ and $ec{v}$:

$$	ext{Similarity}(ec{u}, ec{v}) = rac{ec{u} \cdot ec{v}}{\|ec{u}\|_2 \|ec{v}\|_2}$$

The resulting symmetric similarity matrix $S \in \mathbb{R}^{M 	imes M}$ enables sub-second nearest-neighbor retrieval for any selected movie title.

---

## 💡 Recommendation Examples

### Query: `Toy Story (1995)`
```text
Top-10 Recommended Movies:
1. Toy Story 2 (1999)                                    [Similarity: 0.5726]
2. Jurassic Park (1993)                                  [Similarity: 0.5656]
3. Independence Day (1996)                               [Similarity: 0.5643]
4. Star Wars: Episode IV - A New Hope (1977)             [Similarity: 0.5574]
5. Forrest Gump (1994)                                   [Similarity: 0.5471]
6. The Lion King (1994)                                  [Similarity: 0.5411]
7. Star Wars: Episode VI - Return of the Jedi (1983)     [Similarity: 0.5411]
8. Mission: Impossible (1996)                            [Similarity: 0.5389]
9. Groundhog Day (1993)                                  [Similarity: 0.5342]
10. Back to the Future (1985)                            [Similarity: 0.5304]
```

### Query: `Finding Nemo (2003)`
```text
Top-10 Recommended Movies:
1. The Incredibles (2004)                                [Similarity: 0.7264]
2. Shrek (2001)                                          [Similarity: 0.7014]
3. Monsters, Inc. (2001)                                 [Similarity: 0.6973]
4. Pirates of the Caribbean: Curse of Black Pearl (2003) [Similarity: 0.6523]
5. Shrek 2 (2004)                                        [Similarity: 0.6251]
6. Catch Me If You Can (2002)                            [Similarity: 0.5942]
7. The Lord of the Rings: Return of the King (2003)      [Similarity: 0.5873]
8. The Lord of the Rings: The Two Towers (2002)          [Similarity: 0.5681]
9. Harry Potter and Prisoner of Azkaban (2004)           [Similarity: 0.5603]
10. Ocean's Eleven (2001)                                [Similarity: 0.5568]
```

---

## 🚀 Execution & Setup Instructions

1. **Repository Cloning:**
   ```bash
   git clone https://github.com/pranataa-labs/Item-Based-Collaborative-Filtering.git
   cd Item-Based-Collaborative-Filtering
   ```
2. **Download MovieLens Dataset:**
   Extract `ratings.csv` and `movies.csv` from [GroupLens](https://grouplens.org/datasets/movielens/latest/).
3. **Run Notebook:**
   Open `Simple_Recommendation_System.ipynb` in Google Colab or JupyterLab and execute all cells.

---

## 🛠️ Technology Stack

* **Python 3.10+**
* **Pandas & NumPy** (Matrix operations & pivot reshaping)
* **Scikit-Learn** (`cosine_similarity`)
* **Google Colab & JupyterLab**
