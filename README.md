# Clustering Analysis for WSL Players

This script performs clustering analysis on Women’s Super League (WSL) players based on their performance features. It includes data preprocessing, dimensionality reduction using PCA and t-SNE, clustering with KMeans, and evaluation of the clustering results using silhouette scores. The results are visualized using scatter plots.
Requirements

Ensure you have the following Python libraries installed:

    pandas
    scikit-learn
    matplotlib

You can install these libraries using pip if they are not already installed:

bash

    pip install pandas scikit-learn matplotlib

Script Overview

    Data Preprocessing: Scales the features of the DataFrame using StandardScaler and returns the scaled data and indices of the original data.
    PCA (Principal Component Analysis): Reduces dimensionality of the data to 2 components for visualization and returns the explained variance ratio.
    t-SNE (t-Distributed Stochastic Neighbor Embedding): Further reduces dimensionality to 2 components for visualization using t-SNE.
    Clustering and Evaluation: Performs KMeans clustering on the data and calculates the silhouette score to evaluate the clustering quality.
    Visualization: Plots the clusters in 2D space for both PCA and t-SNE results.

Usage

    Prepare Your Data:
    Ensure you have a DataFrame df with relevant features for clustering. Update the features_by_pos dictionary with the correct feature names for each player position.

    Define Features:
    Update the features_by_pos dictionary with the specific features for each position:

    python

    features_by_pos = {
        'GK': [...],  # Features for Goalkeepers
        'DF': [...],  # Features for Defenders
        'MF': [...],  # Features for Midfielders
        'FW': [...]   # Features for Forwards
    }

    Run the Script:
    Execute the script. It will process data for each player position (GK, DF, MF, FW), apply PCA and t-SNE, perform KMeans clustering, and visualize the results.

Functions

    preprocess_data(df, features):
        Description: Scales the data and returns the scaled features and original indices.
        Parameters:
            df: The input DataFrame.
            features: List of feature names to be used for clustering.
        Returns: Scaled data and indices.

    apply_pca(X_scaled, n_components=2):
        Description: Applies PCA to reduce dimensionality to 2 components.
        Parameters:
            X_scaled: Scaled data.
            n_components: Number of PCA components (default is 2).
        Returns: PCA transformed data and explained variance ratio.

    apply_tsne(X_scaled, perplexity=30, learning_rate=200, n_iter=1000):
        Description: Applies t-SNE to reduce dimensionality to 2 components.
        Parameters:
            X_scaled: Scaled data.
            perplexity: Perplexity parameter for t-SNE (default is 30).
            learning_rate: Learning rate parameter for t-SNE (default is 200).
            n_iter: Number of iterations for t-SNE (default is 1000).
        Returns: t-SNE transformed data.

    clustering_and_evaluation(X, num_clusters=3):
        Description: Performs KMeans clustering and computes the silhouette score.
        Parameters:
            X: Data to be clustered.
            num_clusters: Number of clusters for KMeans (default is 3).
        Returns: Cluster labels and silhouette score.

    visualize_clusters(X, labels, title):
        Description: Visualizes clusters in a 2D scatter plot.
        Parameters:
            X: Data to be visualized.
            labels: Cluster labels.
            title: Title of the plot.

Results

The script will output the explained variance ratio for PCA components and silhouette scores for both PCA and t-SNE clustering. Visualizations for each player position will be shown, illustrating the clustering results.
