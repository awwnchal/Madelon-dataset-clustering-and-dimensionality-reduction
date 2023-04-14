# Madelon-dataset-clustering-and-dimensionality-reduction

This repository contains code for exploring the Madelon dataset using k-means clustering and PCA. The Madelon dataset is a synthetic dataset generated for a machine learning competition, with 500 features and 2,600 data points. The dataset has a highly non-linear structure, making it an interesting problem for clustering and dimensionality reduction.

Getting started

To get started, you can download the Madelon dataset from the link provided in the problem statement. The dataset is in a .txt format, and you can read it in using your preferred programming language. In this repository, we provide a Jupyter notebook that walks through the steps for clustering and dimensionality reduction.

# K-means clustering
Before performing any dimensionality reduction, we first apply k-means clustering on the Madelon dataset. We try the following k values: 4, 8, 16, 32, 64. We preprocess the data by standardizing it (subtract the mean and divide by the standard deviation) before applying k-means clustering. We also initialize the cluster centers randomly.

We plot the number of clusters k (x-axis) versus the sum of squared distance (SSE) between data points and their assigned centroids (y-axis). We observe that the SSE decreases as k increases, but the rate of decrease slows down as k gets larger. We use the elbow method to select the optimal k, which is the value of k where the rate of decrease slows down significantly. In this case, we find that k=16 is the optimal value.

We also rerun k-means with k=8, but this time ensuring that the centroids are all different. We observe that the final clusters created are different from the clusters created when the centroids are initialized randomly. This highlights the importance of the initialization step in k-means clustering.

Evaluation metrics that can be used to assess the quality of clusters produced include the silhouette coefficient, Davies-Bouldin index, and Calinski-Harabasz index.

# PCA
We fit the standardized data with PCA to reduce the dimensionality of the dataset. We create a cumulative variance plot, which shows the number of components included (x-axis) versus the amount of variance captured (y-axis). We aim to retain at least 75% of the variance, and we find that we need to keep around 60 principal components.

We then perform PCA with the selected principal components and plot the transformed data on a graph with the first two principal components as the axes. We also plot the original data on a graph with the two original variables that have the highest absolute combined loading for PC 1 and PC 2. We examine the scatter plot of PC 1 (x-axis) versus PC 2 (y-axis) for all data points and qualitatively analyze if there are visible clusters.

# K-means clustering with PCA
We then run k-means clustering on the transformed data from the previous problem. We use the same k values as before and generate an elbow plot. We find that the optimal k is different from the one we found in the first problem - k=32 is the optimal value.

We compare the SSE values plotted in this exercise to the previous plot generated before performing PCA and observe that the SSE values are significantly lower after dimensionality reduction.

We create a scatter plot of PC 1 (x-axis) versus PC 2 (y-axis) for all of the transformed data points and label the cluster centers and color-code by cluster assignment for the first 5 iterations of k=32. We observe that the algorithm begins to converge to optimal assignments. This highlights the advantage of using dimensionality reduction techniques such as PCA before clustering high-dimensional datasets.
