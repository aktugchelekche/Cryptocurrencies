# Cryptocurrencies
Unsupervised Machine Learning. 

## Overview of the Analysis

The purpose of this project is to perform Unsupervised Machine Learning models to discover any groupings, trends, or other information that could help us pitch cryptocurrencies to investors. A report that includes trending cryptocurrencies in the market as well as a classtification plots will be provided at the end of the analysis. 


## Analysis

### Preprocessing the Data for PCA

The dataset will be preprocessed by follwing steps in order to perform PCA : 

* Keep all the cryptocurrencies that are being traded.
* Drop the IsTrading column.
* Remove rows that have at least one null value.
* Filter the crypto_df DataFrame so it only has rows where coins have been mined.
* Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
* Remove the CoinName column from the crypto_df DataFrame since it's not going to be used on the clustering algorithm.
* Use the get_dummies() method to create variables for the two text features, Algorithm and ProofType, and store the resulting data in a new DataFrame named X.
* Use the StandardScaler fit_transform() function to standardize the features from the X DataFrame.

After completing Data Processing and Transforming steps above, an array of standardize the features will be as in <code>Figure-1</code>


<p align="center"><img width="560" alt="Screen Shot 2022-06-05 at 2 47 39 PM" src="https://user-images.githubusercontent.com/98676400/172067883-0b47461d-8f78-49ba-8de6-154fac172359.png"></p>
<p align="center">Figure-1</p>

### Reducing Data Dimensions Using PCA

PCA algorithm was applied to array in <code> Figure 1 </code> with three principal components then converted to a dataframe as in <code>Figure-2 </code>

<p align="center"><img width="250" alt="Screen Shot 2022-06-05 at 2 53 14 PM" src="https://user-images.githubusercontent.com/98676400/172068083-7f636305-d0a8-4263-879c-99fcea7c019d.png"></p>
<p align="center">Figure-2</p>


### Clustering Cryptocurrencies Using K-means

In this part, by utilizing <code> Elbow Curve </code> we find out how many clusters will be best fit for this data set that is the value of <code> K-Means</code>. The sharp turn at <code> k=4 </code> in <code> Figure-3</code> indicates that <strong> 4 </strong> will be the number of clusters that our algorithm will use. 

<p align="center"><img width="500" alt="Screen Shot 2022-06-05 at 3 05 11 PM" src="https://user-images.githubusercontent.com/98676400/172068530-a01e53ae-477d-48fa-80d9-b08c0f43c255.png"></p>
<p align="center">Figure-3</p>

# Results 

#### Created a new DataFrame including predicted clusters and cryptocurrencies features.

After using <code> k=4 </code> for <code>K-Means model</code>,a new data frame was created by joining PCA and Crypto dataframes and a column names <code>Class</code> added as showing in <code>Figure-4</code>

<p align="center"><img width="667" alt="Screen Shot 2022-06-05 at 3 15 38 PM" src="https://user-images.githubusercontent.com/98676400/172068871-2a46f843-ec03-455a-95a1-774139a86c91.png"></p>
<p align="center">Figure-4</p>

#### 3D-Scatter with Clusters

This 3D-Scatter in <code>Figure-5</code> plot help us to see how classes was populated and distrubuted within 3 Principal Components. 

<p align="center"><img width="565" alt="Screen Shot 2022-06-05 at 3 18 21 PM" src="https://user-images.githubusercontent.com/98676400/172068963-fd08adb8-93f3-4a24-8b6e-de7a0a521249.png"></p>
<p align="center">Figure-5</p>


#### Tradable cryptocurrencies.

The table in <code> Figure-6</code> contains coins that currently tradable which is a subset of dataframe in <code>Figure-4</code> 


<p align="center"><img width="650" alt="Screen Shot 2022-06-05 at 3 26 19 PM" src="https://user-images.githubusercontent.com/98676400/172069430-4214e963-a0e3-4a82-930b-a5409c0106ec.png"></p>
<p align="center">Figure-6</p>


#### Scatter Plot for Tradable cryptocurrencies.

Finally, the plot in <code>Figure-7</code> is demostrading the distrubution of each cluster in 2D. 

<p align="center"><img width="651" alt="Screen Shot 2022-06-05 at 3 34 10 PM" src="https://user-images.githubusercontent.com/98676400/172069509-9d3c1d1a-f082-476a-845e-a9ae301db317.png"></p>
<p align="center">Figure-7</p>

In conclution, a ML algorithm can help us to have an idea whether there is similarities among different cryptocurrencies and  they show similar behoviors in the market. Thus, we can provide with visuals to help investors to make better decision on this trending market. 




# Resources
* Data Source: [crypto_data.csv](https://github.com/aktugchelekche/Cryptocurrencies/tree/main/Resources)
* Software/Languages: Jupyter Notebook- Google Colab, Python.
* Libraries: Scikit-learn, Pandas, Plotly. HvPlot.

