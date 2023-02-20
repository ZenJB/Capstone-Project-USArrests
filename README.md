# Capstone-Project-USArrests
This has an analysis of USArrests dataset utilizing PCA, Hierarchical Clustering and K-Means Clustering techniques

# Desciption of Data: 
This data set contains statistics, in arrests per 100,000 residents,
for assault, murder, and rape in each of the 50 US states in 1973. Also given is the
percent of the population living in urban areas

# Key steps taken on the analysis
### Importing required libraries
### Preprocessing: Checking and addressing any missing values, inconsistent datatypes, scaling using Minmaxscaler
### Initial Visualization: Utilized seaborn correlation heatmaps, boxplots
### PCA (Principal Component Analysis): Fitted PCA model from SKLearn, visualized required PCA dimensions using sns lineplots and the PCA itself using biplot. Reduced dimensions by 50%
### Hierarchical Clustering: Fitted AgglomerativeClustering model across all linkage methods to zero-in on "Complete" linkage method using dendogram. Identified that the data clusters neatly into 2 categories
### K-Means Clustering: Fitted K-Means Clustering model, visualized using K-Means cluster plot to show the cities with higher or lower number of arrests per capita
### Conclusion: This analysis concludes that the USArrests dataset can be meaningfully split into two clusters showing the cities with higher and lower number of arrests per capita
