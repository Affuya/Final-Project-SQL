Follow the instructions below to complete this project.

## Part 1: Loading csv Files into Database

Download the .csv files and create a new PostgreSQL database called `ecommerce`. Set up tables for each .csv file by following [these instructions](https://www.postgresqltutorial.com/postgresql-tutorial/import-csv-file-into-posgresql-table/](https://www.postgresqltutorial.com/postgresql-tutorial/import-csv-file-into-posgresql-table/) 

> #### Note
> We have gone over the ways that you can import a .csv file into the PostgreSQL database but [this resource](https://www.youtube.com/watch?v=6Jf7eTkIaR4) summarizes it, in case you need a refresher.

## Part 2: Data Cleaning

As always, once you have received any dataset, your first task is to orient yourself to the data contained within. While exploring the data, you should keep an eye out for any of potential data issues that need to be cleaned. 

**Cleaning hint**: The unit cost in the data needs to be divided by 1,000,000. 

Apart from this, did you see any other issue that requires cleaning? Be sure to take the time upfront to address them.

In your copy of the **CleaningData.txt** file, describe what issues you addressed by cleaning the data, and provide the queries you executed to clean the data.

## Part 3: Starting with Questions

This database provides data on revenue by product as well as data on how each visitor to the site interacted with the products (when they visited, where they were based, how many pages they viewed, how long they stayed on the site, and the number of transactions they entered).
 
In the **StartingWithQuestions.txt** file there are 5 questions you need to answer using the data. For each question, be sure to include:
The queries you used to answer the question
The answer to the question
 

## Part 4: Starting with Data

Consider the data you have available to you.  You can use the data to:
    - find all duplicate records
    - find total number of unique visitors (`fullVisitorID`)
    - find total number of unique visitors by referring sites
    - find each unique product viewed by each visitor
    - compute the percentage of visitors to the site that actually makes a purchase
    

In the **StartingWithData.txt** file, write 3 - 5 new questions that you could answer with this database. For each question, include
The queries you used to answer the question
The answer to the question

## Part 5: QA Your Data

In the **QA.txt** file, identify and describe your risk areas. Develop and execute a QA process to address them and validate the accuracy of your results. Provide the SQL queries used to execute the QA process.
