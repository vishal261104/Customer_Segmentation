# Customer Segmentation with Clustering (Marketing Campaign)

A concise, practical notebook for unsupervised customer segmentation on a marketing campaign dataset. It walks through data exploration, preprocessing, dimensionality reduction (PCA), and clustering with K-Means, including the Elbow Method to choose `k`. Visualizations make the clusters easy to interpret for marketing insights.

See the notebook: [Ai_Project.ipynb](Ai_Project.ipynb)

## Overview
- **Goal:** Segment customers into meaningful groups to support targeting and personalization.
- **Dataset:** `marketing_campaign_final.csv` (29 columns; examples include `Education`, `Marital_Status`, `Income`, etc.).
- **Approach:**
  - Exploratory data analysis with charts and distributions.
  - Preprocessing: drop identifiers, handle missing values, encode categories, scale features.
  - PCA to reduce dimensionality for visualization and stability.
  - K-Means clustering; Elbow Method guides the choice of `k`.

## Key Features
- **EDA:** Pie charts and boxplots for categorical and numerical distributions.
- **Preprocessing:**
  - Drop `ID`.
  - Impute `Income` with the mean.
  - Encode categorical features (via `ColumnTransformer` + encoder) and combine with numeric.
  - Standardize features using `StandardScaler`.
- **Dimensionality Reduction:** 3-component PCA (`random_state=0`) for cluster visualization.
- **Clustering:** K-Means and **Elbow Method** to select the optimal number of clusters.
- **Visualization:** 2D/3D scatter plots of PCA components colored by cluster labels.

## Project Structure
- [Ai_Project.ipynb](Ai_Project.ipynb): End-to-end workflow (EDA → preprocessing → PCA → K-Means → plots).
- `marketing_campaign_final.csv`: Place alongside the notebook or update the path in the import cell.

## Setup (Windows)
Install a clean Python environment and required libraries.

```powershell
python -m venv .venv
.\.venv\Scripts\activate
pip install -U pip
pip install pandas numpy matplotlib seaborn scikit-learn
```

If you use Anaconda, create and activate a conda env, then install the same packages.

## How to Run
1. Ensure `marketing_campaign_final.csv` is in the same folder as the notebook (or update the `pd.read_csv` path).
2. Open the notebook: [Ai_Project.ipynb](Ai_Project.ipynb).
3. Run cells top-to-bottom.
   - Importing the dataset: confirms 29 columns and types.
   - EDA: visualize distributions (`Education`, `Marital_Status`, etc.).
   - Preprocessing: drop `ID`, impute `Income`, encode + scale.
   - PCA: reduce to 3 components and create visualization features (`col1`, `col2`, `col3`).
   - Elbow: plot SSE vs `k` to select cluster count.
   - K-Means: fit and visualize final clusters.

## Results
- **Optimal `k`:** Determined via the Elbow Method.
- **Clusters:** Visualized with PCA; separations reflect differences in demographics and spending behavior.
- **Insights:** Use cluster profiles to tailor offers, messaging, and campaign allocation.

## Reproducibility Notes
- PCA uses `random_state=0`. If you want fully deterministic runs, set seeds for all stochastic steps (e.g., `KMeans(random_state=...)`).

## Extending the Project
- **Algorithms:** Try Agglomerative Clustering or DBSCAN for non-spherical clusters.
- **Metrics:** Add Silhouette Score or Calinski–Harabasz for cluster quality.
- **Features:** Engineer new behavioral features (e.g., recency/frequency/monetary).
- **Model Ops:** Save scalers, encoders, and cluster models for reuse.

## Troubleshooting
- **File not found:** Verify `marketing_campaign_final.csv` resides next to [Ai_Project.ipynb](Ai_Project.ipynb) or fix the path in the import cell.
- **Plot rendering issues:** Ensure VS Code’s Jupyter extension is enabled; rerun affected cells.
- **Packages missing:** Re-run the install commands in your active environment.

## License
This repository contains educational materials created for learning and experimentation. Please ensure any dataset usage complies with its original terms.