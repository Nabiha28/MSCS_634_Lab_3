# MSCS_634_Lab_3
# Lab 3: Clustering Analysis Using K-Means and K-Medoids Algorithms

## Purpose
The purpose of this lab is to explore and evaluate partitioned clustering techniques using the benchmark **Wine Dataset** from the `sklearn` library. The project applies both **K-Means** and **K-Medoids** algorithms ($k=3$) to partition the dataset based on chemical features. The analysis evaluates and compares the geometric structures of the generated clusters using foundational data mining metrics, specifically the **Silhouette Score** (measuring cluster cohesion and separation) and the **Adjusted Rand Index (ARI)** (measuring agreement against the true ground-truth class labels).

---

## Key Insights & Observations
* **Normalization Impact:** Standardizing the dataset using Z-score normalization was essential due to the highly varying scales of the 13 continuous chemical properties (e.g., Magnesium vs. Proline). Without this step, features with larger magnitudes would have disproportionately dominated the Euclidean distance calculations.
* **Metric Performance Comparison:** 
  * **K-Means** achieved a slightly higher **Silhouette Score** compared to K-Medoids. This is expected because the normalized Wine dataset contains dense, continuous features where calculating the mathematical mean (centroid) minimizes the overall inertia more effectively than choosing a discrete data sample.
  * Both algorithms demonstrated strong classification alignment with the actual Wine categories, as reflected by high **Adjusted Rand Index (ARI)** scores.
* **Cluster Centers & Geometry:** 
  * **K-Means** creates a centroid calculated as the average coordinate space of a cluster, which may represent an idealized, synthetic data point.
  * **K-Medoids** strictly chose actual existing rows from the dataset as center anchors (medoids). This makes the K-Medoids interpretation highly valuable when real-world representative exemplars are needed.
  * In terms of positioning, K-Means showed cleaner boundaries in continuous 2D PCA space, while K-Medoids demonstrated robust resistance to potential boundary noise.

---

## When to Use Each Algorithm
* **K-Means:** Preferable when dealing with strictly continuous, normalized datasets where minimizing the sum of squared errors within spherical clusters is the primary goal, and computational efficiency on large data sizes is required.
* **K-Medoids:** Preferable when the dataset contains significant outliers or noise (since medoids are far less sensitive to extreme values than means), or when the cluster center *must* map directly to a real, interpretable data observation.

---

## Project Structure
* `MSCS_634_Lab_3.ipynb`: The complete Jupyter Notebook containing data preprocessing, model implementations, calculations, and side-by-side PCA visualizations.
* `README.md`: This file, documenting project purpose and analytical findings.
