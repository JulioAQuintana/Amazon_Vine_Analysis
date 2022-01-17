# Amazon Vine Analysis

The following report shows an Analysis for big data module and represent the interaction between Google colab, AWS and Postgres.

   ![](https://github.com/JulioAQuintana/Amazon_Vine_Analysis/blob/main/Resources/logo.png)

## Project Overview

Since your work with Jennifer on the SellBy project was so successful, you’ve been tasked with another,
larger project: analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon
Vine program is a service that allows manufacturers and publishers to receive reviews for their
products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members,
who are then required to publish a review.

In this project, you’ll have access to approximately 50 datasets. Each one contains reviews of a
specific product, from clothing apparel to wireless products. You’ll need to pick one of these datasets
and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS
RDS instance, and load the transformed data into pgAdmin. Next, you’ll use PySpark, Pandas, or SQL to
determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, you’ll
write a summary of the analysis for Jennifer to submit to the SellBy stakeholders

The project purpose is to performe the analysis of AWS reviews by all members of paid Amazon Vine
Program and show the impact results, through this services the manufacturers recieve all data of they
products and compare the reviews between members and non members.

## Resources
For Analysis we require the following resources:

* Data Source: S3 Amazon review [at this link](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Electronics_v1_00.tsv.gz).
* Software: Google Colaboratory, PgAdmin, AWS, Postgres

## Results
Dataset has more than 3 million reviews stored, In order to focus on reviews that would be considered more likely to be helpful, we performed the dataset filter based in the next points:

* Count of Total votes equal or greater than 20.
* Percent of Helpful votes to Total Votes equal or greater than 50%.

   ![](https://github.com/JulioAQuintana/Amazon_Vine_Analysis/blob/main/Resources/helpfullvotes.png)
   
Using bulleted lists and images of DataFrames as support, address the following questions:

1. How many Vine reviews and non-Vine reviews were there?
  Vine members made up only 2.1% (1,080) of the reviews whereas the remaining 97.9% were Non-Vine members (49,659).
  ![](https://github.com/JulioAQuintana/Amazon_Vine_Analysis/blob/main/Resources/Total.png)  
  ![](https://github.com/JulioAQuintana/Amazon_Vine_Analysis/blob/main/Resources/programpaid.png)  

  ![](https://github.com/JulioAQuintana/Amazon_Vine_Analysis/blob/main/Resources/programunpaid.png)  
  

2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
* Vine members gave 454 out of 1,080 reviews a 5 star rating.
* Non-Vine members gave 23,034 out of 49,659 reviews a 5 star rating.

3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

* 42% of the reviews for Vine members were rated 5 stars.
* 46.4% of the reviews for Non-Vine members were rated 5 stars.

## Summary

Due the analysis we can say that the Vine members did not show bias when rating their products considering that the number of 5-star ratings was close to 10% less than Non-Vine members (42% vs. 46.4%). due that we are assuming that Vine customers use special critical mode to perfomr their reviews. However, this point is supported by the analysis including all of the data rather than filtering it to a percentage of helpful vs. total votes as we did for this analysis. the results are represented in the next analysis: 

  ![](https://github.com/JulioAQuintana/Amazon_Vine_Analysis/blob/main/Resources/Vine_dfAnalysis.png)  
  
finally, based on similar analysis using datasets from different product categories can provide us with the whole picture of whether reviews made by Vine members are bias.
