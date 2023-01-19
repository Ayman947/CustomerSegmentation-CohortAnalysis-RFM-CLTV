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

  - KMeans model grouped the customers into **4 groups** based on their **RFM data**.

  | Cluster | Name | %_users | avg_tenure | avg_recency | avg_frequency | avg_monetary | #_users |
  | ------- | ---- | ------- | ---------- | ----------- | ------------- | ------------ | ------- |
  | 1 | Low-Spending About to Churned | 61% | 126 | 76 | 2 | 127 | 256383 |
  | 2 | Low-Spending Churned | 32% | 276 | 264 | 2 | 91 | 135992 |
  | 3 | Champions | 1% | 313 | 19 | 52 | 3425 | 2290 |
  | 4 | Potential Loyalists | 6% | 263 | 42 | 14 | 943 | 25846 |

  ![3d RFM Clusters](https://github.com/Ayman947/Marketing-RFM-CLTV-Segmentation/blob/main/clusters-3d-rfm.PNG)

  ![Clusters Features Relative Importance](https://github.com/Ayman947/Marketing-RFM-CLTV-Segmentation/blob/main/clusters-relative-importance.PNG)
  
  
  
  - Customers are grouped into **4 segments** according to their **CLTVs**.
  
  | Segment | Recency | Tenure | Frequency | Monetary | 6_monhths_clv |
  | ------- | ------- | ------ | --------- | -------- | ------------- |
  | Hibernating | 113 | 250 | 7 | 403 |  8 |
  | Need Attention | 188 | 207 | 1 | 67 | 47 |
  | Loyal Customers | 136 | 159 | 2 | 100 |  119 |
  | Champions | 97 | 120 | 3 | 193 | 639 |
  
  ![Segment CLTVS](https://github.com/Ayman947/Marketing-RFM-CLTV-Segmentation/blob/main/users-segment-CLV.PNG)
  
  
  - A BI KPIs dashboard was built to monitor active users, orders and revenues.

![KPIs Dashboard](https://github.com/Ayman947/Marketing-RFM-CLTV-Segmentation/blob/main/KPIs-Dashboard.PNG)
  


  ## **Recommendations**

> RFM-based Recommendations

> **Based on the insights above, marketing activities can be strategized and  customized to fit the different customers profiles:**
 

- **Champions ≈ 1%:**

   - These customers may be <u>rewarded</u> to stay <u>loyal</u> to our company. 
   - <u>Communication</u> with this group should make them feel <u>valued and appreciated</u>
   - Also, They can become early adopters of new products and will help promote the brand.


- **Potential Loyalists ≈ 6%:**

  - These customers may be offered <u>membership, loyalty programs or recommend related products</u> to upsell them and help to make them Champions.


- **Low-Spending Churned & About to Churned Customers ≈ 93%**
  
  - <u>Retention & reactivation</u> campaigns may be launched to make them order again, but it's also important to take their <u>CLVs</u> into consideration to be still <u>profitable customers</u>. 



> CLTV-based Recommendations

> **Having known the CLTVs, budgets for retention & activation campaigns will be set in a more feasible way**.

- Below is the **CLTV corresponding to every segment**:

    - Champions  ≈ 640
    - Loyal Customers ≈ 120
    - Need Attention ≈ 45
    - Hibernating ≈ 10

- **CLTV improvement tips:**

  - **Automating customized marketing** actions using softwares.
  - Increasing **customer satisfaction** to prolong their customer lifespan
  - Encouraging additional purchases without increasing the marketing budget, which can be done by **selling complementary services**.



  ## **Conclusion**

  - ###
  - ###


  ## **Appendix**

  - (Code-Dashboard-Paper)
  - Presentation Storytelling

GRAMMERLY
