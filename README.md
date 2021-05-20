# FacebookNetworkAnalysis
Analyzing and visualizing a user's Facebook network using NetworkX and community detection methods

# Introduction
In this project, I built a network analysis platform using NetworkX to analyze and visualize the Facebook network of an individual. For a given network, the platform returns local and global summaries, visualizations of the distributions of several features, and a graph of the network color-coded by the identified communities.  

![alt text](https://github.com/amtan20/FacebookNetworkAnalysis/blob/main/GN_Community_Detection.png)

# Data
The edgelists used to build this network come from: https://snap.stanford.edu/data/ego-Facebook.html

# Summary of methods
1. NetworkX for calculating summary statistics and visualizing the graphs 
2. Community detection using 2 different algorithms: Girvan-Newman and node2vec with Kmeans clustering 
3. Adjusted rand score to compare the results of the two community detection algorithms 

# Findings
There is a accuracy/efficiency tradeoff when using the two community detection algorithms. Girvan-Newman more accurately identifed communities in the Facebook network, but it was computationally very expensive, taking nearly 5 hours to process Node 107! On the other hand, node2vec processed Node 107 in seconds, but had a lower rand score. The table summarizes the rand score of each community detection method when compared with the ground truth labels of the social circles. 

| Node     | Girvan-Newman Community Detection | node2vec + Kmeans |
|----------|---------------------|--------|
|0         | 0.335               | 0.206 |
|107       | 0.596               | 0.508 | 
