# 👾 Steam Horror Game Clustering Engine

> Full Big Data ML pipeline across **4,600+ Steam horror games**. Scraped two APIs + web, engineered a 459-dimension feature matrix, applied K-Means clustering with PCA and t-SNE visualization, and built a recommender system on top.

**Copenhagen Business School — Big Data Course, 2025**

---

## Results — Cluster Visualizations

### 10 Clusters — PCA
![10 Cluster PCA](cluster_10_PCA.png)

### 10 Clusters — t-SNE
![10 Cluster t-SNE](cluster_10_t-SNE.png)

### 20 Clusters — PCA
![20 Cluster PCA](cluster_20_PCA.png)

### 20 Clusters — t-SNE
![20 Cluster t-SNE](cluster_20_t-SNE.png)

### Elbow Method — Optimal K
![Elbow Method](k_means_elbow%20300.png)

---

## Key Findings

- **Strategy, Platformer, Abstract Horror, and Roguelike** games form distinct natural clusters
- Playtime and review score are **positively correlated** within clusters
- The recommender surfaces context-aware suggestions beyond simple genre matching — input a game, get back titles with shared gameplay tags, genre, and market features

---

## Pipeline

```
Steam Store API ──┐
SteamSpy API ─────┼──► Feature Matrix (459 dims) ──► K-Means ──► PCA / t-SNE ──► Recommender
BeautifulSoup ────┘         4,600+ games
```

| Step | Script | Output |
|---|---|---|
| Get all Steam games | `all_games.py` | `steam_apps.csv` |
| Filter to horror | `filter_horror_games.py` | `horror_games.csv` |
| Scrape tags & reviews | `tag_games.py` | enriched dataset |
| Build feature matrix | `feature_matrix.py` | 459-dim matrix |
| K-Means clustering | `K_means_clustering.py` | cluster labels |
| Analyze clusters | `clustered_games_analysis.py` | cluster profiles |
| Visualize | `visualization_cluster.py` | PCA + t-SNE plots |
| Recommend | `recommender.py` | similar game suggestions |

---

## How to Run

```bash
pip install pandas scikit-learn beautifulsoup4 matplotlib requests

python all_games.py
python filter_horror_games.py
python tag_games.py
python feature_matrix.py
python K_means_clustering.py
python clustered_games_analysis.py
python visualization_cluster.py  # optional
python recommender.py            # optional
```

---

## Tech Stack
`Python` `pandas` `numpy` `scikit-learn` `matplotlib` `BeautifulSoup4` `Steam Store API` `SteamSpy API`
