# AMAZON_VINE_ANALYSIS

***RESOURCES:*** 

SOFTWARE: Amazon Web Services (AWS) RDS, Google Colaboratory Notebook, Jupyter Notebook, Python, PySpark, pgAdmin, Pandas, SQL, VSC
DATA SOURCES: Amazon s3 bucket resources, SQL table schema, Amazon ETL starter code
_________________________________

***OVERVIEW:***

The purpose of this Challenge was to assist Jennifer with a big data analysis and perform ETL on 'Amazon's Healthcare Products' review in CSV format. Such were written by members of the paid Amazon Vine program, where companies such as Sellby pay a nominal fee to Amazon for reviews on their respective products. PySpark was utilized to extract, transform and load the data into pgAdmin. Connections between AWS, pgAdmion and Google colab were completed to address the analysis, due to the nature of the large data size, which could be  stored in Amazon's S3: simple storage service . This was done to avoid the constraints of a single computer storage system. (Deliverable 1). The second step was to determine the posssible incidence of bias between paid and unpaid vine reviews using PySpark, Pandas and SQL (Deliverable 2).



<img width="1423" alt="s3buckets_healthcare_table" src="https://user-images.githubusercontent.com/90135381/155857287-19bec0aa-3635-49f2-b6c4-830c8df470dd.png">

                                        FIGURE 1: Access to Amazon Healthcare Table-Colab
                                        
In Deliverable 1, the Healthcare table was extracted for scrutiny (ETL) from Amazon's website. The RDS connection was established and the tables were then created (FIGURES 1 and 2).


<img width="1428" alt="aws_connection-colab" src="https://user-images.githubusercontent.com/90135381/155857277-da2fb602-49e6-45b9-8646-57d7fd896151.png">

                                        FIGURE 2: Access RDS

___________________________________

***RESULTS:***

***DELIVERABLE 1: Perform ETL (extract, transform, load) on Amazon Products Review***

A dataset was chosen from the Amazon Review datsets for Healthcare and a new database was created in Amazon RDS server. The dataset was extracted and cleaned/transformed into 4 Data Frames, which were then matched to schema and loaded into pgAdmin for query check to examine (FIGURES 3 through 10):
1. customers_table_df: using groupby(), agg(), count(customer_id), withColumnRenamed() to customers table
2. products_table_df: with select() product_id, product_title, drop_duplicates(), product_ids to products_table
3. review_id_table_df: with select(), review date to review_id_table
4. vine_table_df: with select() to vine_table


<img width="1428" alt="customers_id_table-colab" src="https://user-images.githubusercontent.com/90135381/155857324-c7fa348e-cd9b-4843-ab88-e5547f7762ec.png">

                                        FIGURE 3: Customer DF Table-Colab


<img width="1440" alt="pgadmin-customers_table" src="https://user-images.githubusercontent.com/90135381/155857556-49d96109-0c96-4490-a9d3-2370ee1d87e9.png">


                                         FIGURE 4: Customer Table-pgAdmin
                                         
<img width="1409" alt="products_df_table-colab" src="https://user-images.githubusercontent.com/90135381/155857526-bb2dc601-7296-4c9e-b543-a716fb64e979.png">

                                         FIGURE 5: Products DF Table


<img width="1440" alt="pgadmin-products_table" src="https://user-images.githubusercontent.com/90135381/155857558-adff21ef-ec67-4b88-8170-d77b8f44a08c.png">

                                          FIGURE 6: Products Table-pgAdmin


<img width="1398" alt="review_id_df_table-colab" src="https://user-images.githubusercontent.com/90135381/155857373-538db384-09a3-495a-aa66-cf28ddaa7dc8.png">

                                          FIGURE 7: Review ID DF Table-Colab


<img width="1440" alt="pgadmin-review_id_table" src="https://user-images.githubusercontent.com/90135381/155857559-a617cc71-b880-4f45-b386-663393c5ca96.png">

                                           FIGURE 8: Review ID Table-pgAmin


<img width="1428" alt="vine_df_table-colab" src="https://user-images.githubusercontent.com/90135381/155857386-71628208-b842-4a3f-99c7-4360713aded5.png">

                                            FIGURE 9: Vine DF Table-colab


<img width="1440" alt="pgadmin-vine_table" src="https://user-images.githubusercontent.com/90135381/155857561-2d3a216e-8557-4b1a-b9d6-6b2ed1fca787.png">


                                            Figure 10: Vine DF Table-pgAdmin
                                            
***DELIVERABLE 2: Determine Bias of Vine Reviews***

For Deliverable 2, PySpark, Pandas and SQL were utilized to determine if there was a bias of the product reviews written under the Vine Program. A comparison was performed for total and percentage of 5 star reviews for both paid and unpaid vine submissions (FIGURES 12 through 15). The data was filtered and a new dataframe was created for total_votes whhich had a count greater than 20. Further filtering was performed and the helpful_votes were divided by total_votes equal to orgreater than 50% and seperated into paid and unpaid dataframes. Finally, the total number of reviews, the number of 5 star reviews and the percentage of 5 star reviews were calculated for both. 

<img width="1422" alt="vine_review_analysis_output" src="https://user-images.githubusercontent.com/90135381/155857285-a91e26eb-208f-448f-98be-53711e49f89d.png">

                                            FIGURE 11: Vine Review Analysis


<img width="1433" alt="helpful_votes_table-colab" src="https://user-images.githubusercontent.com/90135381/155857570-8d8b4801-6118-487e-a874-798b7250b625.png">

                                            FIGURE 12: Helpful Votes Table

<img width="1424" alt="total_votes_table-colab" src="https://user-images.githubusercontent.com/90135381/155857574-4cc7e820-fe81-419b-8721-f5bff9e2b421.png">

                                            FIGURE 13: Total Votes Table

<img width="1432" alt="vine_paid_df_table-colab" src="https://user-images.githubusercontent.com/90135381/155857576-53689c8a-e75a-4759-b005-11360d73a264.png">

                                            FIGURE 14: Vine Paid DF Table



<img width="1438" alt="vine_unpaid_table" src="https://user-images.githubusercontent.com/90135381/155857580-d577e7c8-456e-4e96-8d9f-bca9184d28ed.png">

                                            FIGURE 15: Vine Unpaid DF Table
                                            
As illustrated above, the following data was extrapolated:


 PAID VINE REVIEWS: total=497                      UNPAID VINE REVIEWS: total=120,863
                    total 5star reviews=220                             total 5star reviews=120,863
                    % 5star reviews=44.26%                              % 5star reviews=61.61%


_______________________________________________

***SUMMARY:***


_________________________________________________
***REFERENCES:*** BCS, GOOGLE, GitHub, StackOverflow
