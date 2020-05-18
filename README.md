## Background

Many of Amazon's shoppers depend on product reviews to make a purchase. Amazon makes these datasets publicly available. However, they are quite large and can exceed the capacity of local machines to handle. One dataset alone contains over 1.5 million rows; with over 40 datasets, this can be quite taxing on the average local computer. The first goal for this project will be to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance. The second goal will be to use PySpark or SQL to perform a statistical analysis of selected data.

- - -

## Project outline:

### level-1: 
* use the furnished schemata (sql/video_game_vine_schema.sql and sql/software_vine_schema.sql)to create two tables (video_vine_reviews and software_vine_reviews) in my RDS database.

* create two notebooks (level-1/aws_video_games_review_to_rds.ipynb and level-1/aws_software_reviews_to_rds.ipynb) to extract two datasets (video games reviews and software reviews) from s3.amazonaws,com (https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz and https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Software_v1_00.tsv.gz).

* drop duplicates and incomplete records, select vine reviews data, create dataframes for the vine reviews and write the dataframes into RDS database.

##### (the number of records (reviews) for video games dataset: 1,785,886)
##### (the number of records (reviews) for software dataset: 341,913)


### level-2: 
* Analyze whether the vine reviews from Amazon's Vine program are trustworthy.

- - -

## Outcome:

The total vine reviews of video games is 4,290 and the total vine reviews of software is 10,415. Although the number of records for video game (1,785,886 reviews) is higher than the number of records for software (341,913 reviews), the vine reviews of video games is lower than the vine reviews of software. 53.94 % of vine reivews for video game have no helpful vote and 48.53% of vine reviews for software have no helpful vote. This may indicate that there is a low confidence value from customers to trust the vine reviews. Moreover, around 70% of vines reviews (video game: 77%, software: 68%) have 4 or 5 star rating. There may be a tendency for vine reviews to give products high star rating. Therefore, the vine reviews may not be trustworthy.
