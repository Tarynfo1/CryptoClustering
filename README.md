# CryptoClustering challenge using unsupervised machine learning

<img width="1440" alt="crypto_image" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/cryptocluster.png">

## Description
* A project to create profitable crypto-portfolio recommendations, through the use of unsupervised machine learning and prediction throught the use of K-Means clustering.
 


*** 
## Analysis
 Determine through visual inspection of the cluster analysis results, what the impact is of using fewer features to cluster the data by, using K-means.

***
## File structure
- __Crypto_clustering.ipynb:__ code, dataframes, plots
- __README.md:__ Analysis of k-means data and cluster analysis results 
- __Resources:__ 
    -   __Images:__ Contains visual analysis results and images for readme file
    -   __crypto_market_data.csv__ csv file containing crypto data for analysis
***
## Dependencies
- pandas  
- Python
- NumPy
- scikit Learn
- hvPlot
***
## Instructions
1. Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file and create a DataFrame.<br>
    __Raw DataFrame:__


    <img width="913" alt="dataframe" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/crypto_dataframe.png">

    __Plotted DataFrame__

    
    <img width="913" alt="dataframe2" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/plotted_dataframe.png">

 2. Use the elbow method to find the best value for k.<br><br>
  __What is the value for k?__ The best value for k is 4.
    
    <img width="913" alt="elbow data" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/elbow_curve.png">

 3. Cluster Cryptocurrencies with K-means Using the Original Scaled Data
    
    <img width="913" alt="predictions scatter chart" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/predictions_scatter.png">

  4. Optimise Clusters with Principal Component Analysis
        Use the elbow method on the PCA data to find the best value for k.
  <img width="913" alt="pca kmeans elbow plot" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/pca_kmeans_elbow.png">

  5. Cluster Cryptocurrencies with K-means Using the PCA Data.
  
  <img width="913" alt="demographic_info" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/pca_predictions_scatter.png">


  __Analysis Results__
    **Question:** After visually analysing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?<br><br>As observed with the PCA features, the inertia of the clusters is significantly reduced when compared to that of the original features. The reduction in inertia indicates that the data points within each cluster exhibit much greater proximity to eachother, therby rendering them mroe easily distinguishable that those from the original data set. Furthermore, the PCA plot demonstrates a superior capacity to separate the two outliers, specifically 'theta token' and 'celsius-degree-token'.<br><br>
    In a broader context, it becomes apparent that the clusters predominantly retain the same cryptocurrencies, despite the notable proximity of coins like 'tezos' and 'iota' to the alternate cluster. This suggests that even with a 10% data loss, the models accuracy reains remarkably robust.
 
Cryptocurrency by segment - KMeans <br>
    <img width="913" alt="gauge_chart" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/scatter_by_crypto_kmeans.png"><br>

Crypto Currency by segment - primary <br> <br>
    <img width="913" alt="gauge_chart" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/scatter_by_crypto_primary_c.png"><br>
 

***
## Acknowledgements
- https://stackoverflow.com/questions/59678780/show-extra-columns-when-hovering-in-a-scatter-plot-with-hvplot assisted in the following code snippet
```
          # Create a scatter plot using hvPlot by setting 
# `x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`. 
# Colour the graph points with the labels found using K-Means and 
# add the crypto name in the `hover_cols` parameter to identify 
# the cryptocurrency represented by each data point.

predictions_scatter = market_data_predictions.hvplot.scatter(
title='Scatter Plot by Crypto Currency Segment - k=4',
x='price_change_percentage_24h',
y='price_change_percentage_7d',
by='CryptoCluster',
hover_cols=['coin_id'],
frame_width=700,
frame_height=500
)

predictions_scatter
```
 

- Reference https://vitalflux.com/pca-explained-variance-concept-python-example/ assisted in the following code snippet
```
# Retrieve the explained variance to determine how much information 
# can be attributed to each principal component.
variance = pca.explained_variance_ratio_

print(f'PC1 holds {variance[0]:.2f}%, PC2 holds {variance[1]:.2f}%, with PC3 holding {variance[2]: .2f}%. The primary components hold a total of {sum(variance) * 100: .2f}% of the original data')

```


