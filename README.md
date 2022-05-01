# Amazon_Vine_Analysis

## Overview

Big Market is a marketing company that uses Big Data to help clients to optimize their business. One of their main client Sellby is about to release a large catalog that require data analytics. They want to compare the reviews of their similar products vs competitors to make marketing decisions. 

The project analyzed the Music Dataset from Amazon Vine program (paid reviews) and non-Vine (unpaid reviews).

Two deliverables where performed:

1)	Using knowledge in cloud ETL process, created an AWS RDS database with tables in pgAdmin. The dataset was extracted and was transformed to four separate DataFrames. And finally, data was uploaded to the appropriate tables and did queries in pgAdmin confirming data were uploaded.

2)	 Using knowledge of PySpark, determined total number of reviews, number of 5-star reviews and percentage of reviews for the two types of review – Amazon Vine program (paid) and unpaid.   


## Results

### Deliverable 1: Perform ETL on Amazon Product Reviews

The Amazon_Reviews_ETL.ipynb file does the following:

- An Amazon Review dataset is extracted as a DataFrame 

![deliv_1-df.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv_1-df.png)


- The extracted dataset is transformed into four DataFrames with the correct columns 

![deliv_1-customers_df.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv_1-customers_df.png)

![deli_1-products_df.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deli_1-products_df.png)

![deliv_1-review_id_df.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv_1-review_id_df.png)

![deliv_1-vine_df.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv_1-vine_df.png)


- All four DataFrames are loaded into their respective tables in pgAdmin 

![deliv_1-customers_table.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv_1-customers_table.png)

![deliv1-products_table.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv1-products_table.png)

![deliv_1-review_id_table.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv_1-review_id_table.png)

![deliv_1-vine_table.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv_1-vine_table.png)



### Deliverable 2: Determine Bias of Vine Reviews

The Vine_Review_Analysis does the following:

- There is a DataFrame for the vine_table data 

![deliv_2-vine_df.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/deliv_2-vine_df.png)


- The data is filtered to create a DataFrame where there are 20 or more total votes

![delive_2-filtered_df_20_or_more_votes.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/delive_2-filtered_df_20_or_more_votes.png)


- The data is filtered to create a DataFrame where the percentage of helpful_votes is equal to or greater than 50%

![delive_2-filtered_df_helpful_votes_greater_50.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/delive_2-filtered_df_helpful_votes_greater_50.png)


- The data is filtered to create a DataFrame or where there is a Vine review

![delive_2-filtered_df_Vine_review_paid.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/delive_2-filtered_df_Vine_review_paid.png)


- The data is filtered to create a DataFrame where there isn’t a Vine review

![delive_2-filtered_df_without_Vine_unpaid.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/delive_2-filtered_df_without_Vine_unpaid.png)


- The total number of reviews, the number of 5-star reviews, and the percentage 5-star reviews are calculated for all Vine and non-Vine reviews

![delive_2-total.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/delive_2-total.png)



## Summary

In summary for Music Dataset, the positivity bias is to the non-Vine reviews (unpaid service) than Vine reviews (paid service) with the following data:

-	With total reviews of 105,986, only 7 are Vine reviews and 105,979 are non-Vine reviews. 
-	Percentage of 5-star reviews, 0% for Vine and 63.76 % for non-Vine  

For additional analysis, since bias to non-Vine we can add the filter to unpaid reviews if it is a verified purchase. 

![delive_3-addtl_analysis.png](https://github.com/OPahunang/Amazon_Vine_Analysis/blob/main/resources/delive_3-addtl_analysis.png)
