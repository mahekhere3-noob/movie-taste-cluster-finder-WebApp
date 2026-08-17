# Movie Taste Cluster Finder Web App 🎬

A **K-Means clustering** model that groups users by their movie genre preferences — no labels, no "correct answer," just patterns the model finds on its own. Built with `pandas` and `scikit-learn`, with an interactive **Streamlit web interface**.

---

## 📊 Problem Statement

Can a model group people by movie taste, and tell you who else shares yours?

This project uses K-Means to cluster 50 users based on how they rate six genres (Action, Comedy, Drama, Horror, Romance, Sci-Fi), then lets a new user rate the same genres to find out which taste cluster they'd belong to.

---

## 📁 Dataset

- **50** users
- **Features:** ratings (1-5) across 6 genres — Action, Comedy, Drama, Horror, Romance, Sci-Fi
- **No target column** — this is unsupervised learning

---

## ⚙️ Approach

1. Load user genre ratings into a pandas DataFrame
2. Standardize the ratings with `StandardScaler` (so no single genre dominates the distance calculation)
3. Fit `KMeans` with 3 clusters
4. Label each cluster by its two highest-rated genres
5. For a new user, scale their ratings the same way and predict which cluster they land in
6. Show a comparison chart and a list of similar users from that cluster

---

## 🧠 Tech Stack

**Model:**
- Python 3
- pandas
- scikit-learn (`KMeans`, `StandardScaler`)
- Matplotlib

**Web Interface:**
- Streamlit

---

## 🚀 How to Run

```bash
git clone <your-repo-url>
cd movie-taste-cluster-finder
pip install streamlit pandas scikit-learn matplotlib
streamlit run app.py
```

Rate all six genres from 1-5, click "Find My Cluster," and see your taste group, how you compare to the cluster average, and a few users who rate movies like you do.

---

## 📈 Result

The model finds **3 natural taste groups** in the data:
- **Action / Sci-Fi Fans**
- **Intense Genre Fans** (high Action, Horror, and Sci-Fi)
- **Drama / Romance Lovers**

A test profile (Action=5, Comedy=2, Drama=1, Horror=1, Romance=2, SciFi=5) correctly lands in the Action/Sci-Fi cluster.

---

## 🔍 A Note on Unsupervised Learning

This is fundamentally different from every classification/regression project in this series — there's no accuracy score, because there's no "right answer" to check against. The model just finds structure in the data, and it's on us to interpret what that structure means.

---

## 🔍 Limitations & Next Steps

- Trained on a small, synthetically generated dataset (50 users), not real streaming platform data.
- The number of clusters (3) was fixed rather than determined algorithmically (e.g. via the Elbow Method).
- Cluster labels are auto-generated from top genres and may occasionally read awkwardly.

**Planned improvements:**
- Use the Elbow Method to justify the choice of K
- Test on a larger, real-world ratings dataset (e.g. MovieLens)
- Add actual movie title recommendations per cluster, not just genre profiles

---

## 📝 Note

This project was built as a learning exercise in unsupervised clustering using scikit-learn.
