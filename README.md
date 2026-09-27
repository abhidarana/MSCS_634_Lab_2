# MSCS 634 - Lab 2: KNN and RNN Classification on Wine Dataset

## Purpose
The purpose of this lab is to explore and compare the performance of K-Nearest Neighbors (KNN) and Radius Neighbors (RNN) classifiers on the sklearn Wine Dataset. The lab evaluates how hyperparameter choices (neighbor count $k$ for KNN and search radius $r$ for RNN) impact model accuracy.

## Key Insights
1. **Feature Scaling Importance:** Distance-based algorithms require feature normalization/standardization (`StandardScaler`) to prevent features with large numeric scales (e.g., Proline) from dominating the distance calculations.
2. **KNN Trends:** KNN yields stable, high accuracy across moderate values of $k$. Very small $k$ values risk fitting to noise, while larger $k$ values provide smooth class boundaries.
3. **RNN Trends:** RNN performance depends directly on setting an appropriate search radius matched to feature space density. 

## Challenges and Decisions Made
* **Data Scaling & Radius Adjustment:** The original prompt suggested large radius values (350–600) designed for unscaled data. Because feature standardization was applied, search radii were adjusted to standard deviation metrics ($2.0 - 4.5$) to properly capture spatial neighborhoods.
* **Handling Isolated Radius Points:** Added `outlier_label='most_frequent'` to the `RadiusNeighborsClassifier` to prevent execution errors when test points contain zero neighbors within smaller radii.

## Submission Files
* `Wine_KNN_RNN_Lab.ipynb` - Jupyter Notebook containing data loading, training, evaluation, and visualizations.
* `README.md` - Lab project overview and insights summary.