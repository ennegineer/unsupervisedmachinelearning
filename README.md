# Unsupervised Machine Learning

## Data preparation

The dataset used in this project is from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist). 

First, we dropped all cryptocurrencies not currently traded, dropped all rows with NaN values, and dropped the `IsTrading`, `CoinName`, and original index column, `Unnamed: 0`.

Next, we converted categorical features `Algorithm` and `ProofType` into numerical data using the Pandas get_dummies() function.

Lastly, we standardized the dataset using StandardScaler to ensure that larger values did not skew the outcome.

## Dimensionality reduction

Now that we had cleaned, scaled, numeric data, we needed to perform dimensionality reduction with PCA. We opted for an explained variance of 90%. This dropped some of our features (columns), but not enough - so we further reduced the dataset features with t-SNE.

We created a scatter plot on the t-SNE output to look for distinct clusters, but the results were not clear.

## Cluster analysis with k-means

We created an elbow plot to look for the best number of clusters. From the visual, we chose 5 clusters as the elbow of the curve seemed most fitted at k = 5. When running the cluster analysis and graphing the results, we also tried 4 and 9 clusters, but 5 appeared to have the best outcome.

## Recommendation

Of the cryptocurrencies on the trading market, we can put them into approximately 5 categories with a classification system. 

After preprocessing the data, we ran it through dimensionality reduction (PCA) and t-SNE to lower the number of features down to two. Using an elbow curve to find the number of clusters to use, we ran a k-means cluster analysis and graphed it to visually see the clusters.
