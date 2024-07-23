# cryptoclustering
Module 19 Challenge

## Overview

In this challenge, you'll leverage your Python and unsupervised learning skills to predict if cryptocurrencies are influenced by 24-hour or 7-day price changes.

## Steps

### 1. Initial Setup

1. Rename `Crypto_Clustering_starter_code.ipynb` to `Crypto_Clustering.ipynb`.
2. Load `crypto_market_data.csv` into a DataFrame.
3. Generate summary statistics and plot the data to understand its structure.

### 2. Prepare the Data

1. Use `StandardScaler()` from scikit-learn to normalize the data.
2. Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame.
3. Ensure the first five rows of the scaled DataFrame appear correctly.

### 3. Find the Best Value for k Using the Original Scaled DataFrame

1. Use the elbow method to find the best value for k:
    - Create a list of k values from 1 to 11.
    - Create an empty list to store inertia values.
    - Use a for loop to compute inertia for each k.
    - Plot the elbow curve using a line chart.
- We determined the optimal K value was 4

### 4. Cluster Cryptocurrencies with K-means Using the Original Scaled Data

1. Initialize the K-means model with the best k value.
2. Fit the model using the scaled DataFrame.
3. Predict clusters for the cryptocurrencies.
4. Add a column with predicted clusters to a copy of the original data.
5. Create a scatter plot using hvPlot:
    - x-axis: "price_change_percentage_24h"
    - y-axis: "price_change_percentage_7d"
    - Color points by K-means labels
    - Include "coin_id" in hover columns for identification.

### 5. Optimize Clusters with Principal Component Analysis

1. Perform PCA on the original scaled DataFrame to reduce features to three principal components.
2. Retrieve and document the explained variance for each principal component.
3. Create a new DataFrame with the PCA data, using "coin_id" as the index.
4. Ensure the first five rows of the PCA DataFrame appear correctly.

### 6. Find the Best Value for k Using the PCA Data

1. Use the elbow method on the PCA data:
    - Create a list of k values from 1 to 11.
    - Create an empty list for inertia values.
    - Use a for loop to compute inertia for each k.
    - Plot the elbow curve.
- We were able to determine that the best value for K when using the PCA data was 4.
- When comparing, we found out it did not differ from the best k value when using the original data.

### 7. Cluster Cryptocurrencies with K-means Using the PCA Data

1. Initialize the K-means model with the best k value.
2. Fit the model using the PCA data.
3. Predict clusters for the cryptocurrencies.
4. Add a column with predicted clusters to the PCA DataFrame.
5. Create a scatter plot using hvPlot:
    - x-axis: "PC1"
    - y-axis: "PC2"
    - Color points by K-means labels
    - Include "coin_id" in hover columns for identification.

## Conclusion

- The data transformed by PCA, with a reduced number of features, shows a clearer differentiation of clusters. This improved separation, highlights the distinct groups in a more effective manner and indicates that PCA has successfully captures the most important variations within the data.
