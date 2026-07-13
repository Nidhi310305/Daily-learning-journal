# 2026-06-28 — Cricket Player Segmentation using K-Means Clustering

**Domain:** Machine Learning

**Algorithm:** K-Means Clustering

**Dataset:** Cricket Player Statistics

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

**Type:** Hands-on Unsupervised Learning Implementation

---

## Learning Objectives

- Understand the fundamentals of unsupervised learning using K-Means clustering.
- Learn how feature scaling influences distance-based algorithms.
- Determine the optimal number of clusters using the Elbow Method and Silhouette Score.
- Analyze and interpret clusters using real-world cricket player statistics.

---

## Topics Studied

- Unsupervised Learning
- K-Means Clustering
- Data Cleaning
- Feature Engineering
- Standardization
- Euclidean Distance
- Elbow Method
- WCSS (Within-Cluster Sum of Squares)
- Silhouette Score
- Cluster Visualization
- Cluster Interpretation

---

## Key Concepts

### K-Means Clustering

K-Means is an unsupervised machine learning algorithm that partitions observations into **K distinct clusters** based on feature similarity. Unlike supervised learning, no target labels are provided—the algorithm discovers patterns directly from the data.

### Feature Engineering

Before clustering, the dataset was prepared by:

- Converting the `Span` column into an `Experience` feature.
- Cleaning the `HS` (Highest Score) column by removing non-numeric characters.
- Removing unnecessary features such as player names from the clustering dataset.

### Standardization

Since K-Means relies on Euclidean distance, numerical features were standardized using **StandardScaler** to ensure that variables with larger ranges did not dominate the clustering process.

### Choosing the Optimal Number of Clusters

Two evaluation techniques were explored:

- **Elbow Method** using WCSS
- **Silhouette Score** for measuring cluster quality

The Silhouette Score helped identify the most suitable number of clusters for this dataset.

---

## Practical Work Completed

- Loaded and explored the Cricket Player dataset.
- Handled dataset encoding using `latin1`.
- Created an `Experience` feature from career span.
- Cleaned and converted numeric columns.
- Removed unnecessary features.
- Applied feature standardization.
- Built a K-Means clustering model.
- Evaluated different values of **K** using the Elbow Method.
- Compared clustering quality using the Silhouette Score.
- Generated player clusters.
- Visualized clusters using 2D and 3D scatter plots.
- Analyzed statistical characteristics of each cluster.

---

## Challenges Faced

- Understanding why K-Means requires standardized features.
- Determining the optimal number of clusters.
- Interpreting the meaning of different player groups after clustering.
- Cleaning mixed-format numerical columns before model training.

---

## Quick Revision Notes

- K-Means is an **unsupervised** learning algorithm.
- Similar observations are grouped into clusters.
- Standardization is essential because K-Means uses Euclidean distance.
- WCSS measures within-cluster variation.
- The Elbow Method provides an initial estimate for selecting K.
- Silhouette Score evaluates cluster quality (-1 to +1).
- Higher Silhouette Scores indicate better-separated clusters.

---

## Resources

### Notebook

- [K-Means Clustering Hands-on](../notebooks/K_Means_HANDSON.ipynb)

### Related Learning Entries

- Linear Regression on Insurance Dataset
- Housing Price Prediction using Linear Regression
- Bank Marketing Classification using Logistic Regression
- Decision Tree Classification

### Key Libraries Used

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

## Next Steps

- Hierarchical Clustering
- DBSCAN
- Principal Component Analysis (PCA)
- Cluster Evaluation Techniques
- Dimensionality Reduction for Visualization

---

## Reflection

This notebook introduced my first unsupervised learning algorithm and demonstrated how clustering can uncover meaningful patterns without labeled data. Beyond implementing K-Means, the exercise emphasized the importance of preprocessing, feature scaling, and objective methods such as the Elbow Method and Silhouette Score for selecting an appropriate number of clusters. Visualizing and interpreting the resulting player groups strengthened my understanding of exploratory machine learning and segmentation techniques.

---
