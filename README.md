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
## Dataset

Wine Dataset from the Scikit-learn library

Number of Samples: 178

Number of Features: 13

Number of Classes: 3

## Key Results

- The Wine dataset was standardized using Z-score normalization.
- K-Means clustering was performed using three clusters.
- K-Medoids clustering was also performed using three clusters.
- Silhouette Score was used to evaluate cluster separation.
- Adjusted Rand Index (ARI) was used to compare clustering results with the actual wine classes.
- Scatter plots were created to visualize and compare both clustering methods.

## Challenges

The primary challenge encountered during this lab was compatibility between the K-Medoids package and certain cloud notebook environments. Deepnote provided a compatible environment where the required package was successfully installed and executed.

## When to Use Each Algorithm
* **K-Means:** Preferable when dealing with strictly continuous, normalized datasets where minimizing the sum of squared errors within spherical clusters is the primary goal, and computational efficiency on large data sizes is required.
* **K-Medoids:** Preferable when the dataset contains significant outliers or noise (since medoids are far less sensitive to extreme values than means), or when the cluster center *must* map directly to a real, interpretable data observation.
* ## Analysis of Clustering Results

The K-Means and K-Medoids algorithms were applied to the standardized Wine dataset using three clusters.

The clustering quality was evaluated using the Silhouette Score and the Adjusted Rand Index (ARI).

The algorithm with the higher Silhouette Score produced more compact and well-separated clusters.

The algorithm with the higher ARI demonstrated better agreement between the predicted clusters and the actual wine classes.

K-Means is computationally efficient and performs well on datasets with spherical clusters.

K-Medoids is generally more robust to outliers because it selects actual data points as cluster centers instead of calculating the mean.

Based on the obtained results, both algorithms successfully identified meaningful clusters, while their performance differed slightly depending on the evaluation metric.

---

## Project Structure
* `MSCS_634_Lab_3.ipynb`: The complete Jupyter Notebook containing data preprocessing, model implementations, calculations, and side-by-side PCA visualizations.
* `README.md`: This file, documenting project purpose and analytical findings.
