# Cryptocurrencies

## Purpose

The purpose of this project is to delve into clustering algorithms in order to produce scatter plots for visualization of different cryptocurrency data. To do this, we preprocessed the data in order to be able to use it for PCA, reduced the data dimensions via PCA, clustered the cryptocurrencies using K-Means, and produced different methods of visualizing the cryptocurrencies.

## Process

### Preprocessing the Data

In order to get the data ready for use in PCA, it must first be cleaned and prepared to go through the PCA process. To do this, we single out cryptocurrencies that are still trading, remove all entries that are missing data, drop the column that designates a cryptocurrency as "still trading", and remove any cryptocurrencies that haven't had any mined coins since their inception. We then single out the name column for later, and then proceed to make dummies of the proof type and algorithm each crypto runs on before merging those to the TotalCoinsMined and TotalCoinSupply columns, and scaling the data using StandardScaler().

### Reducing Data Dimensions

For us to make use of any clustering methods, we need to lower the number of components that might go into the scatter plot and K-Means model. To do this, we used PCA to fit and transform the scaled data we got from the previous part into three principal components. Labeling each row with the index from the original data, we formed this data into a DataFrame so we might run it into K-Means to get inertia.

### K-Means and Predictions

In this part, we took the dataframe from the previous part and compiled inertia values via K-Means to determine an optimal number of clusters. By running through the numbers 1 and 10, we found 4 was an optimal number of clusters, and we went with it. We formed a prediction with 4 clusters, and added the prediction to the processed dataframe produced in deliverable 2.

### Visualizing Cryptocurrency Results

We ended up visualizing the data in three different ways:
- With the principal components serving as coordinates, we graphed each cryptocurrency in 3-D space, with their color and shape denoting the class they fell in when we added the prediction made in deliverable 3.
- We formed a dynamic table with the data that didn't correspond with the principal components, leaving a table whose entries can be sorted and grouped depending on the information desired.
- Using MinMaxScaler(), we took the TotalCoinSupply and TotalCoinsMined columns and turned them into principal components to be graphed in a 2-D space. Then we graphed them, with the color of each dot decided by the class column we had made to hold the cluster predictions.
