# Big-Data-Challenge: Amazon-Shoppers-Product-Reviews

## Background

In this assignment I will put my ETL skills to the test. Many of Amazon's shoppers depend on product reviews to make a purchase. Amazon makes these datasets publicly available. However, they are quite large and can exceed the capacity of local machines to handle. One dataset alone contains over 1.5 million rows; with over 40 datasets, this can be quite taxing on the average local computer. My first goal for this project will be to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance. The second goal will be to use PySpark or SQL to perform a statistical analysis of selected data.

There are two levels to this project. The second level is optional.

1. Create DataFrames to match production-ready tables from two big Amazon customer review datasets.
2. Analyze whether reviews from Amazon's Vine program are trustworthy.
- - -

## Instructions
![image](https://user-images.githubusercontent.com/94668201/172257114-7a82628d-d2f3-4488-b9b6-2af5385b1ade.png) 

### Level 1

* Used the furnished schema to create tables in my RDS database.

* Created two separate Google Colab notebooks and **Extracted** any two datasets from the list at [review dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt), one into each notebook.

![image](https://user-images.githubusercontent.com/94668201/172257609-bedd1b75-aaa3-41d1-b39d-67e80a3291c0.png)

  **Note:** It is possible to ETL both data sources in a single notebook, but due to the large data sizes, it will be easier to work with these S3 data sources in two separate Colab notebooks.

* Made sure to handle the header correctly. If I read the file without the header parameter, I may have found that the column headers are included in the table rows.

* For each notebook (one dataset per notebook), completed the following:

  * Counted the number of records (rows) in the dataset.

  * **Transformed** the dataset to fit the tables in the [schema file](../Resources/schema.sql). Made sure the DataFrames matched in data type and in column name.

  * **Loaded** the DataFrames that correspond to tables into an RDS instance. **Note:** This process can take up to 10 minutes for each. Made sure that everything is correct before uploading.

![image](https://user-images.githubusercontent.com/94668201/172257308-dd30d285-8cad-4cf4-a8ad-b7b422f57810.png)


### Level 2

In Amazon's Vine program, reviewers receive free products in exchange for reviews.

  <img width="573" alt="vine01" src="https://user-images.githubusercontent.com/94668201/172256574-e6956988-0385-476d-9a69-d4607442cea7.png">

Amazon has several policies to reduce the bias of its Vine reviews: [https://www.amazon.com/gp/vine/help?ie=UTF8](https://www.amazon.com/gp/vine/help?ie=UTF8).

But are the Vine reviews truly trustworthy? I was tasked to investigate whether Vine reviews are free of bias. I used either PySpark or SQL to analyze the data.

* If I choose to use SQL, first used Spark on Colab to extract and transform the data and loaded it into a SQL table on my RDS account. Performed my analysis with SQL queries on RDS.

* While there are no hard requirements for the analysis, I considered the steps to take to reduce noisy data, e.g., filtering for reviews that met a certain number of helpful votes, total votes, or both.

* Submited a summary of my findings and analysis.


## References

Amazon customer Reviews Dataset. (n.d.). Retrieved April 08, 2021, from: [https://s3.amazonaws.com/amazon-reviews-pds/readme.html](https://s3.amazonaws.com/amazon-reviews-pds/readme.html)

- - -
