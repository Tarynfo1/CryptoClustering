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


    <img width="366" alt="dataframe" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/crypto_dataframe.png">

    __Plotted DataFrame__

    
    <img width="366" alt="dataframe2" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/plotted_dataframe.png">

 2. Use the elbow method to find the best value for k.<br><br>
  __What is the value for k?__ The best value for k is 4.
    
    <img width="366" alt="elbow data" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/elbow_curve.png">

 3. Cluster Cryptocurrencies with K-means Using the Original Scaled Data
    
    <img width="913" alt="predictions scatter chart" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/predictions_scatter.png">

  4. Optimise Clusters with Principal Component Analysis
        Use the elbow method on the PCA data to find the best value for k.
  <img width="129" alt="pca kmeans elbow plot" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/pca_kmeans_elbow.png">

  5. Cluster Cryptocurrencies with K-means Using the PCA Data.
  
  <img width="129" alt="demographic_info" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/pca_predictions_scatter.png">


  __Analysis Results__
    * Adapt the Gauge Chart from [https://plot.ly/javascript/gauge-charts/](https://plotly.com/javascript/gauge-charts/) to plot the weekly washing frequency of the individual.
    * You will need to modify the example gauge code to account for values ranging from 0 through 9.
    * Update the chart whenever a new sample is selected.
 
Cryptocurrency by segment - KMeans <br>
    <img width="321" alt="gauge_chart" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/scatter_by_crypto_kmeans.png"><br>

Crypto Currency by segment - primary <br> <br>
    <img width="321" alt="gauge_chart" src="https://github.com/Tarynfo1/CryptoClustering/blob/main/Resources/Images/scatter_by_crypto_primary_c.png"><br>
 

***
## Acknowledgements
- https://plotly.com/python/reference/indicator/#indicator-gauge-axis-dtick assisted in the following code snippet
```
          gauge: {
              axis: {range: [0,10], tickmode: "linear", tick0: 2, dtick: 2}, 
              bar: {color: "rgba(14, 127, 0, .5)"},
```

- Reference from https://www.d3indepth.com/requests/ assisted in the following code snippet
```
// // Fetch the JSON data and console log it
d3.json(url).then(function(data){
    console.log(data);
});
```  

- Reference https://plotly.com/python/v3/gauge-charts/ assisted in the following code snippet
```
// Assign the first object to obj variable
      let obj = filteredData[0]
      console.log(obj)
      // Trace for the data for the gauge chart
      let trace = [{
          domain: { x: [0, 1], y: [0, 1] },
          value: obj.wfreq,
          title: { text: "<b>Belly Button Washing Frequency</b><br>Scrubs per Week", font: {size: 24}},
          type: "indicator", 
          mode: "gauge+number",
          gauge: {
              axis: {range: [0,10], tickmode: "linear", tick0: 2, dtick: 2}, 
              bar: {color: "rgba(14, 127, 0, .5)"},
              steps: [
```

- Reference from AskBCS Learning assistant Mohamed Metwali assisted with the following code snippet
```
' // Filter data where id = selected value after converting their types 
' // (bc meta.id is in integer format and selectValue from is in string format)
' let filteredData = metadata.filter((meta) => meta.id == selectedId.id);
```
