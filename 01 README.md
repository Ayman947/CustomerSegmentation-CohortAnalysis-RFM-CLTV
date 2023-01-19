# RFM & CLTV Customer Segmentation


## **Background** 

  - XYZ is an Egyptian <u>online retail</u> start-up where the <u>marketing</u> team needs to run marketing more <u>effectively yet efficiently</u>. As a start-up, its performance is acceptable, however, it can perform rather better once the <u>problems</u> they face got solved.


## **Problems** 

1. <u>Fluctuations</u> in the number of orders made by customers.

2. Many customers <u>churned</u> from XYZ. 

3. Marketing campaigns' <u>impact</u> on business performance is not measurable.


## **Objectives** 

1. Launching <u>customized accurately targeted</u> marketing campaigns to maintain <u>high monthly orders</u>.

2. Planning for <u>feasible reactivation and retention</u> marketing campaigns.

3. Measuring <u>marketing activities' impact</u> on the business.


## **Questions** 

1. What are the <u>customer groups</u> based on their ordering behaviors? <u>(i.e *recency, frequency and monetary value*)</u>

2. What are the customers' future <u>worth/value</u> based on their ordering behaviors?


3. What are the <u>crucial KPIs</u> of the business?


## **Analytics Solutions / Methodologies**

1. Using ML Clustering models to conduct <u>RFM Customer Segmentation</u>.

2. Using BG/NBD & Gamma-Gamma Models to <u>predicting Customer lifetime value</u>.

3. Building a <u>business intelligence (BI) dashboard</u> to keep track of XYZ's business performance.



## **Data Sources**

- **About:** This is the ordering transactional data set that contains all of the last 12 months’ transactions.
- **Date:** 30th September 2021 to 31st October, 2022
- **Rows:** 1,276,436 rows
- **Columns:** 5 columns
- **Data Dictionary:**

| Column Name | Description | Sample Value  |
|-------------|-------------|---------------|
| Order Id    | The order's unique Id  | 211216115328MQGI |
| Order DateTime | The date/time when the order made | 2021-12-16 08:53:00 |	
| Order Price | The order's value  | 48.00 |
| User Id     | The user's id who made the order  | 2745796d-645c	|
| Quantity    | The ordered quantity  | 1 |



 ## **Environment** & **Packages**

  | Package Name | Functionality                 |
  |--------------|-------------------------------|
  | datetime     | Date/Time manipulations |
  | hdbscan      | HDBSCAN Clustering Model |
  | lifetimes    | CLTV Predictions |  
  | matplotlib   | Data Visualizatiom            |  
  | missingno    | Visualizing Null Values |
  | mpl_toolkits | 3d Plotting |  
  | numpy        | Numerical Calculations & Array Manipulations   |
  | Pandas       | Data Manipulation             |
  | pandasql     | Writing SQL in Python |
  | seaborn      | Data Visualizatiom            |
  | sklearn      | Machine Learning Algorithms   |
  | yellowbrick  | Clustering Models Visualization |



## **Data Cleansning & Preprocessing**

  - Renaming the columns to be in lowercase separated by '_' instead of spaces (i.e following the same naming convention).
  - Modifying columns data types.
  - Checking for duplicates.
  - Checking for nulls.
  - Sorting our dataframe by order_datetime
  - Extracting RFM data from the transactions data.
  - Extracting Cohorts data from the transactions data.
  - Extracting Monthly KPIs data from the transactions data.
  - Scaling (normalizing) the data.


  ## **Modeling**

  - We've built **KMeans** with **4 clusters** model to group **customers** using **RFM** behaviors. The models showed **0.521 Silhouette** score.
  - We've used **BG/NBD** & **Gamma-Gamma** models to predict 6-month customers' **orders & CLTVs**.
  - We've built a BI **KPIs dashboard** using **Tableau**.



  ## **Final Results**

  - KMeans model grouped the customers into 4 groups based on their RFM data.

  | Cluster | Name | %_users | avg_tenure | avg_recency | avg_frequency | avg_monetary | #_users |
  | ------- | ---- | ------- | ---------- | ----------- | ------------- | ------------ | ------- |
  | 1 | Low-Spending About to Churned | 61% | 126 | 76 | 2 | 127 | 256383 |
  | 2 | Low-Spending Churned | 32% | 276 | 264 | 2 | 91 | 135992 |
  | 3 | Champions | 1% | 313 | 19 | 52 | 3425 | 2290 |
  | 4 | Potential Loyalists | 6% | 263 | 42 | 14 | 943 | 25846 |
  
  - ![3d RFM Clusters](https://github.com/Ayman947/Marketing-RFM-CLTV-Segmentation/blob/main/clusters-3d-rfm.PNG)
  - ![Clusters Features Relative Importance]([link](https://github.com/Ayman947/Marketing-RFM-CLTV-Segmentation/blob/main/clusters-relative-importance.PNG))
  
  - [Dashboard Name](link)



  ## **Recommendations**

  - csd
  - vdf



  ## **Conclusion**

  - ###
  - ###


  ## **Appendix**

  - (Code-Dashboard-Paper)
  - Presentation Storytelling

GRAMMERLY
