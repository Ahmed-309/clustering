# Clustering

Jupyter notebooks practicing unsupervised clustering with scikit-learn: K-Means and hierarchical clustering on mall customer data, and a fuller K-Means walkthrough on the wine dataset with scaling, cluster selection, and PCA visualisation.

## Notebooks

| Notebook | Method | Dataset | What it does |
|---|---|---|---|
| `Kmeans.ipynb` | K-Means | `Mall_Customers.csv` | Uses the elbow method over k = 1–10, fits 5 clusters on annual income and spending score, and plots them |
| `Hc.ipynb` | Agglomerative (Ward linkage) | `Mall_Customers.csv` | Plots a dendrogram to choose k, then fits 5 clusters on the same two features and plots them |
| `wine_cluster.ipynb` | K-Means | `wine-clustering.csv` | Scales all 13 chemical features, compares elbow and silhouette scores to pick k = 3, then projects the clusters onto two principal components and profiles each cluster in original units |

`wine_cluster.ipynb` is the most complete of the three. Its saved outputs come from a full run: 178 wines, no missing values, three clusters of 65, 51, and 62 wines, with a silhouette score of 0.285.

## Installation

```bash
git clone https://github.com/Ahmed-309/clustering.git
cd clustering
python -m venv .venv
.venv\Scripts\activate        # Windows
# source .venv/bin/activate   # macOS/Linux
pip install -r requirements.txt
```

## Usage

```bash
jupyter notebook
```

Open a notebook and run its cells from top to bottom.

**Before running:** all three notebooks load their CSV from an absolute Windows path, for example `pd.read_csv('D:\\python\\Clustering\\wine-clustering.csv')`. Both CSVs are in this repo, so change each path to the plain filename, for example `pd.read_csv('wine-clustering.csv')`.

`Kmeans.ipynb` and `Hc.ipynb` point at `D:\python\Mall_Customers.csv`, one directory above; the file is included here as `Mall_Customers.csv`.

## Known issues

- The saved output of the last cell in `Hc.ipynb` records a Jupyter kernel crash rather than the cluster plot. Re-running the notebook should regenerate it.

## Data

- `Mall_Customers.csv` — 200 customers, with customer ID, genre (gender), age, annual income (k$), and spending score (1–100). Both mall notebooks cluster on the last two columns only.
- `wine-clustering.csv` — 178 wines with 13 chemical measurements (alcohol, malic acid, magnesium, flavanoids, proline, and others) and no class label.

## Requirements

- Python 3.10+ (these notebooks were run on Python 3.14)
- pandas, numpy, matplotlib, scipy, scikit-learn (see `requirements.txt`)
