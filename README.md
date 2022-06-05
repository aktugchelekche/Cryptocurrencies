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

<p align="center"><img width="300" alt="Screen Shot 2022-06-05 at 2 53 14 PM" src="https://user-images.githubusercontent.com/98676400/172068083-7f636305-d0a8-4263-879c-99fcea7c019d.png"></p>
<p align="center">Figure-2</p>


### Clustering Cryptocurrencies Using K-means

In this part, by utilizing <code> Elbow Curve </code> we find out how many clusters will be best fit for this data set that is the value of <code> K-Means</code>. The sharp turn at <code> k=4 </code> in <code> Figure-3</code> indicates that <strong> 4 </strong> will be the number of clusters that our algorithm will use. 

<p align="center"><img width="697" alt="Screen Shot 2022-06-05 at 3 05 11 PM" src="https://user-images.githubusercontent.com/98676400/172068530-a01e53ae-477d-48fa-80d9-b08c0f43c255.png"></p>
<p align="center">Figure-3</p>








Resources
Data Source: crypto_data.csv
Software: Jupyter Notebook
Languages: Python
Libraries: Scikit-learn, Pandas, Plotly
Environment: Python 3.7
