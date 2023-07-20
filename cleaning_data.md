What issues will you address by cleaning the data?
-- Identify the specific data issues or inconsistencies that need to be addressed. 
-- Common issues include missing values, duplicates, incorrect data types, and formatting problems





Queries:
Below, provide the SQL queries you used to clean your data.
-- First checked a list of all the tables:
SELECT table_name
FROM information_schema.tables
WHERE table_schema = 'public';

-- Next I selected the columns that would be relevant to my present and also future analysis considering 
that some of the ones although had null values will be useful in future when the data required for the column is populated.

CREATE TABLE all_sessions_filtered AS
SELECT
	fullvisitorid,
	channelgrouping,
	time,
	country,
	city,
	totaltransactionrevenue,
	pageviews,
	timeonsite,
	date,
	pagetitle,
	searchkeyword,
	pagepathlevel1
FROM all_sessions;

I repeated the same process for all the other tables. Retaining only the relevant columns.
I retained the following columns for each table;
Analytics table -fullvisitorid, revenue, pageviews and time on site
Products table - stocklevel, name, sku
Sales_report_table- total_ordered, sentimentscore, sentimentmagnitude, stocklevel, name, productsku

I will use these columns to analyze revenue by product and visitor interaction patterns by exploring metrics such as 
revenue per visitor, revenue by country, revenue by product, visitor engagement metrics, sentiment analysis and stock levels.


-- Next step is to identify columns in the different tables to use as primary keys. I used the query below to check for columns with unique values
SELECT productsku, COUNT(*) 
	FROM sales_report
GROUP BY productsku
HAVING COUNT(*) >1;

I repeated the above query for all the tables and columns and discovered the underlisted columns with unique values;
productsku from the sales_report table and sales_by_sku tables
sku from the products table.

-- Next I will create a new column named "id" for the all_sessions_filtered and analytics table to represent my unique identifiers
and make those new columns my primary key.
The query below is what I used to create the new "id" column;
ALTER TABLE analytics
ADD COLUMN id SERIAL PRIMARY KEY;

--After adding new id columns to the analytics and all_sessions_filtered table, I assigned the earlier
identified columns for the other tables as primary keys using the query below;
ALTER TABLE sales_report
ADD PRIMARY KEY (productsku);

