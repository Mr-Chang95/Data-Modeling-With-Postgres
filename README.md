# Sparkify ETL with Postgres and Python

## Project Description
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. They don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. The goal of this project is to create a SQL database for a music streaming startup called Sparkify. Sparkify's analytics team want to understand what songs users are listening on the company's music app. They want way to easily and effectively query their data. These data are stored in raw JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app on.

Here are the steps for this project:
- Data modeling with Postgres
- Creating star schema database
- ETL pipeline using Python

## Files Description
Here are the files:
- **`data folder`:** Folder where all needed jsons reside: log_data and song_data.
- **`create_tables.py`:** Python script recreates the database and tables used to store the data.
- **`etl.ipynb`:** Python Jupyter Notebook that was used to initially explore the data and test the ETL process.
- **`etl.py`:** Python script reads in the Log and Song data files, processes and inserts data into the database.
- **`sql_queries.py`:** Python script that defines all the SQL statements used in this project.
- **`test.ipynb`:** Python Jupyter Notebook that was used to test that data was loaded properly.

## Datasets
~~~~~
- **Song Dataset**: files are partitioned by the first three letters of each song's track ID
- **Log Dataset**: files in the dataset you'll be working with are partitioned by year and month
~~~~~ 

## Data Modeling
For this project, I will be using the star schema where we have 1 fact tables and 4 dimension table. The fact table will be called **`songplays`** while the 4 dimension tables will be called **`songs`, `artists`, `users` and `time`**. The latter consists of primaray keys which will be used to reference back to the fact table. 

Down below, you can see the entity relationship diagram(ERD) in the form of a star schema. 
![Sparkify_ERD drawio](https://user-images.githubusercontent.com/92649864/161654181-6b12794d-7c46-4600-91ea-10f3a6221890.png)

**Why use relational database for this project?**
~~~~~
- The data types are structured. 
- The amount of data we need to analyze is not large enough to require big data related solutions.
- This structure enables analysts to aggregate the data efficiently.
- Ability to use SQL that is more than enough for this kind of analysis.
- We need to use JOINS.
~~~~~

## How to Run Python Scripts
The first two steps can be run in terminal while the last step is best run in Jupyter notebook. To run in terminal, type in `python reate_tables.py`. <br> Please run the steps in this order. 
1. Run ***create_tables.py*** to create the database and tables.
2. Run ***etl.py*** to process for loading, extracting and inserting the data.
3. Run ***test.ipynb*** to confirm the creation of database and columns.