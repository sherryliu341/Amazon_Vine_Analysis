# Amazon_Vine_Analysis
MODULE 16 Big Data - Challenge

## OVERVIEW OF THE ANALYSIS
### PURPOSE:  The purpose of the current analysis was to determine whether there is any bias toward favorable reviews from Amazon Vine members.  Specifically, we looked at reviews in the "US Pet Products" category.  Reviews were acquired from [Amazon AWS] (https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt).  Using PySpark, Amazon RDS and pgAdmin, the reviews were Extracted, Transformed and Loaded.  Then, again using PySpark, the data was analyzed to determine whether any bias is seen in the reviews.

## RESOURCES
  - Sources Files: [AmazonAWS US Pet Product Reviews] (https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Pet_Products_v1_00.tsv.gz) 
  - Software:  PySpark, pgAdmin/postgreSQL, Amazon AWS (RDS and S3)
 

## [RESULTS](Images/Data_Results.png)
#### After [extraction of the raw data](Images/Full_data.png), and transformation to a useful ["vine_table"](Images/Vine.png) containing only relevant columns, the data was further limited to reviews receiving at least 20 votes (total_votes >=20), and where there are at least 50% helpful votes.  There were a total of 38,010 reviews in this [reduced dataset](Images/20votes_50percent.png).

#### VINE reviews
  - There were a total of 170 reviews by Vine members.
  - Of those reviews, 65 reviews gave the product 5 stars.
  - The percentage of 5-star reviews given by Vine members was 38%.


#### NON-VINE reviews
  - There were a total of 37,840 reviews by non-Vine members.
  - Of those reviews, 20,612 reviews gave the product 5 stars.
  - The percentage of 5-star reviews given by NON-Vine reviewers was 54%.


## SUMMARY
### The results here suggest that there is no positivity bias for reviews received through the Vine program.  In fact, there is a strong indication, at least among US Pet Products, that the opposite may be true - that is, that there may be a tendency toward more 5 star reviews for unsolicited, uncompensated reviews.  There are many, many more non-Vine reviews overall than Vine reviews.  And 54% of those reviews gave 5 stars, versus the 38% of Vine reviewers that gave 5 stars.  This could be because unsolicited reviews are more likely to be submitted by purchasers who have a very strong response to a product (either positive or negative).  Vine reviewers are not rewarded for the numbers of stars given, but are required to give a review regardless of how strongly they feel about the product.  So, it would be very interesting to see if ratings are distributed more evenly between 1 and 5 stars for Vine reviewers, while non-Vine (unsolicited, uncompensated) reviewers might show a bias toward either very low (1 star) or very high (5 star) ratings.  It would be interesting as well to see if the trend is any different among different product categories.
