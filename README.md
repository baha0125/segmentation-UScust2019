# segmentation-UScust2019

**1.The dataset and main objective**

The dataset was retrieved from US Federal Reserve ([data reference](https://www.federalreserve.gov/econres/scfindex.htm)) that contain Survey of Customer Finances (SCF). SCF itself include information on families’ balance sheets, pensions, income, and demographic characteristics. For information, the dataset contains 351 columns and 28,885 rows.

The main objective of this project is to segment household that have hard time getting credit with net worth less than 3 million. The segmentation process will be carried out using KMeans unsupervised learning.

**2.Exploratory Data Analysis**
The exploratory data analysis will be held for investigate data. Because there are so many feature in this dataset, Lets choose some features as below :
- Age

According to the image below, the distribution of age follows exponential distribution with the people who are most concerned seem to be between 30 and 50. 

<img src='https://raw.githubusercontent.com/bahategar/segmentation-UScust2019/main/images/Screenshot%202022-09-28%20190743.png'>

- Background

According to the image below, people with background bachelor above seems doesn't fear or hasn't been turned down for their credit. 

<img src='https://raw.githubusercontent.com/bahategar/segmentation-UScust2019/main/images/Screenshot%202022-09-28%20191818.png'>

- Assets and Debt

According to the image below, the 'DEBT' and 'HOUSES' has positive relationship with the number of coefficient is 0.79. It seems that the main source of debt is their primary residence.

<img src='https://raw.githubusercontent.com/bahategar/segmentation-UScust2019/main/images/Screenshot%202022-09-28%20191833.png'>

**3.Building Model**

- Determine Features

In this model the features that I used is top 5 features that have high variance. The features and the variance values can be seen in the image below.

<img src='https://raw.githubusercontent.com/bahategar/segmentation-UScust2019/main/images/Screenshot%202022-09-28%20191908.png'>

According to the images below, the features that I've chosen are ASSET, NFIN, HOUSES, DEBT, and NETWORTH. The meaning of these features is described below:

 (i) ASSET: Total value of assets held by household, 2019 dollars
 
 (ii) NFIN:	Total value of nonfinancial assets held by household, 2019 dollars
 
 (iii) HOUSES: Total value of primary residence of household, 2019 dollars
 
 (iv) DEBT:	Total value of debt held by household, 2019 dollars
 
 (v) NETWORTH: Total net worth of household, 2019 dollars
- Parameter Tunning

Parameter tunning is done to determine the number of clusters in our model. The number of cluster in our model is determined by plotting inertia measurement vs number of clusters and silhouette score vs number of clusters. The right number is choosing by look for the "bend in the elbow" of graphics. According to the images below, the number of clusters that I've chosen is 3.

<img src='https://raw.githubusercontent.com/bahategar/segmentation-UScust2019/main/images/Screenshot%202022-09-28%20191929.png'>

<img src='https://raw.githubusercontent.com/bahategar/segmentation-UScust2019/main/images/Screenshot%202022-09-28%20191945.png'>

**4.Results**

According to the image below, the households in the cluster 1 have the highest net worth and the lowest is cluster 2. If we see the DEBT feature, it does not scale as net worth increases. People in the cluster 1 might not need to worry about carrying debt because their net worth is so high but for the others they might have enough money to pay down their debts, but not quite enough money to leverage what they have into additional debts.

<img src='https://raw.githubusercontent.com/bahategar/segmentation-UScust2019/main/images/Screenshot%202022-09-28%20192001.png'>

In addition, I visualize it the result of clustering on the 2-D scatter plot below.

<img src='https://raw.githubusercontent.com/bahategar/segmentation-UScust2019/main/images/Screenshot%202022-09-28%20192022.png'>
