

# Customer Segmentation Pipeline
In today’s competitive market, understanding customer behavior is crucial for business success.
## Overview
- Segment credit-card customers using unsupervised clustering followed by supervised modeling.

## Data
- 8,950 customers, 17 numerical features (financial behavior) + `CUST_ID`.

## Preprocessing
- Imputed missing values in `MINIMUM_PAYMENTS` and `CREDIT_LIMIT`.
- Standardized features for uniform scaling.

## Clustering
- PCA to reduce to 2 dimensions (for visualization).
- Elbow method to determine optimal clusters (**k = 4**).
- K-Means clustering and cluster profiles.

## Classification
- Use cluster labels as target variable.
- Train multiple models:
  - Decision Tree (~93.4% accuracy)
  - Gaussian Naive Bayes (~91.2%)
  - Random Forest (~95.8%)
  - Logistic Regression (~82.0%)

## Visualizations
- Feature distributions (KDE/histograms), correlation heatmap, elbow curve, PCA scatter plot, cluster sizes, per-cluster histograms.

## Persistence
- Saved trained K-Means model as `kmeans_model.pkl`.

## Usage
- Load model and new customer features → scale → PCA transform → predict cluster → profile segment.

## Future Work
- Explore other clustering methods (DBSCAN, GMM, Spectral, Agglomerative).
- Hyperparameter tuning, deeper segmentation criteria, and integration into production.
