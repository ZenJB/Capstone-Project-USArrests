# Capstone-Project-USArrests
This has an analysis of USArrests dataset utilizing PCA, Hierarchical Clustering and K-Means Clustering techniques

# Desciption of Data: 
This data set contains statistics, in arrests per 100,000 residents,
for assault, murder, and rape in each of the 50 US states in 1973. Also given is the
percent of the population living in urban areas

# Key steps taken on the analysis
### Imported required libraries
### Preprocessing: Check and address any missing values, inconsistent datatypes, scaling using Minmaxscaler
### Visualization: Utilized seaborn correlation heatmaps, boxplots, biplot, k-means cluster plot, dendograms
### PCA (Principal Component Analysis): Fitted PCA model from SKLearn, visualized required PCA dimensions using sns lineplots and the PCA itself using biplot. Reduced dimensions by 50% (from 4 to 2)
### Hierarchical Clustering: Fitted AgglomerativeClustering model across all linkage methods to zero-in on "Complete" linkage method using dendogram. Identified that the data clusters neatly into 2 categories
### K-Means Clustering: Fitted K-Means Clustering model, visualized using K-Means cluster plot to show the cities with higher or lower number of arrests per capita

# Intrepretations and Conclusion: 

## Interpretation 1: From the correlation heat map, the following observations can be made:
1) Rate of arrests for assault has very strong positive correlation with the rate of arrests for murder.
2) Rate of arrests for assault has strong positive correlation with the rate of arrests for rape.
3) Rate of arrests for murder has moderate positive correlation with the rate of arrests for rape.
4) Urbanpopulation percentage has moderate positive correlation with the rate of arrests for rape.
5) Urbanpopulation percentage has weak positive correlation with the rate of arrests for assault.
6) Urbanpopulation percentage has almost no correlation with the rate of arrests for murder.This analysis concludes that the USArrests dataset can be meaningfully split into two dimensions/clusters showing the cities with higher and lower number of arrests per capita

## Interpretation 2: From pca explained variance rations, we can deduce that two components explain over 85% of variance (0.62 + 0.24 = 0.86). And the other two components have relatively lower contribution to the variance within our data. However, lets use a graph to visually identify the number of components required

## Interpretation 3: From the biplot - 
Each point on a biplot is the projected observation, transformed from the original data. The importance of each feature is indicated by the length of the arrows on the biplot. This corresponds to the magnitude of the values in the eigenvectors. From this biplot, we see that Assault and UrbanPop are the most important features as the arrows to each of these dominate the biplot.

## Interpretation 4: PCA components - 
From the table showing PCA components, it seems that the Assault has by far the highest importance in the first principle component, while UrbanPop has the highest important in the second component. These observations agree with those deduced from the biplot. 
Further these PCA component vectors indicate that:
Prinicipal Component 1 is calculated predominantly from the sum of all arrest parameters (coefficients 0.54, 0.64 and 0.48 aligning to the arrests columns in the data frame), hence PC1 is an indicator of the total arrests per capita
Principal Component 2 is calculated predominantly from the population (coefficient 0.88 aligning with the urban population column in the dataframe) and therefore PC2 is an indicator of the urban population

## Interpretation 5: From the dendogram, combined with the K-means cluster scatter plot - 
These two graphs show that the Arrests per capita can be divided into two clusters, one where all the states with higher number of arrests per capita (green color dendogram) vs the other cluster where the arrests per capita is lower (orange color dendogram)


## Interpretation 6: The K-means scatter plot shows that the clustering splits well the dataset along Principal Component 1 (total arrests per capita) and that the urban population (Prinicipal Component 2) is similar along the top level clusters.

## CONCLUSION:

##### The analysis splits the dataset into two clusters:
##### Cluster 1 (Aqua color) - lower total arrests per capita and can be regarded as High-risk States.
##### Cluster 2 (violet color) - higher total arrests per capita  and can be regarded as High-risk States.
