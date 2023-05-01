# Cryptocurrency Clustering Project
This project aims to cluster cryptocurrencies according to their price changes using the K-means algorithm and Principal Component Analysis (PCA).

### Data
The data for this project consists of a CSV file that contains the following information for each cryptocurrency:

- Coin name
- Price change percentage in 24 hours
- Price change percentage in 7 days
- Price change percentage in 30 days
- Price change percentage in 60 days
- Price change percentage in 200 days
- Price change percentage in 1 Year
# Steps
The project consists of the following steps:

## 1. Find the Best Value for k by Using the Original Data
In this step, we use the elbow method to find the best value for k by using the original data. The elbow method is a technique that plots the inertia (the sum of squared distances of samples to their closest cluster center) against different values of k (the number of clusters) and identifies the optimal value of k where the inertia curve starts to bend or level off. To do this, we follow these steps:

- Create a list with the number of k-values to try. Use a range from 1 to 11.
- Create an empty list to store the inertia values.
- Create a for loop to compute the inertia with each possible value of k. Inside the loop:
  - Create a KMeans model using the loop counter for the n_clusters parameter.
  - Fit the model to the original data.
  - Append the model.inertia_ to the inertia list.
- Create a dictionary with the data to plot the elbow curve. The dictionary should have two keys: ‘k’ and ‘inertia’, and their corresponding values should be the lists created in the previous steps.
- Create a DataFrame with the data to plot the elbow curve.
- Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k. Use hvPlot to create the chart and set x=‘k’, y=‘inertia’, title=‘Elbow curve’, xlabel=‘Number of clusters (k)’, and ylabel=‘Inertia’.
## 2. Cluster the Cryptocurrencies with K-Means by Using the Original Data
In this step, we use the K-means algorithm along with the best value for k that we found in the previous step to cluster the cryptocurrencies according to their price changes. To do this, we follow these steps:

Initialize the K-means model with four clusters by using the best value for k.
Fit the K-means model by using the original data.
Predict the clusters for grouping the cryptocurrencies by using the original data. Review the resulting array of cluster values.
Create a copy of the original data, and then add a new column of the predicted clusters.
Using hvPlot, create a scatter plot by setting x=“PC1” and y=“PC2”. Color the graph points with the labels that you found by using K-means. Then add the crypto name to the hover_cols parameter to identify the cryptocurrency that each data point represents.
## 3. Optimize the Clusters with Principal Component Analysis
In this step, we perform PCA and reduce the features to three principal components. PCA is a technique that transforms a set of correlated features into a set of uncorrelated features called principal components that capture most of the variance in the data. To do this, we follow these steps:

- Create a PCA model instance, and set n_components=3.
- Use the PCA model to reduce the features to three principal components. Then review the first five rows of the DataFrame.
- Get the explained variance to determine how much information can be attributed to each principal component.
# Questions
The following questions are answered based on our analysis:

What’s the best value for k?
What are some advantages and disadvantages of using PCA for clustering?