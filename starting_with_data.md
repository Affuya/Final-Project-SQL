Question 1: 

SQL Queries:
SELECT 
  COALESCE(city, 'Other') AS city, 
  COALESCE(country, 'Other') AS country, 
  CAST(totaltransactionrevenue AS NUMERIC) AS total_revenue_numeric
FROM all_sessions
WHERE 
  totaltransactionrevenue IS NOT NULL
  AND city IS NOT NULL
  AND city <> ''
  AND country IS NOT NULL
  AND country <> ''
ORDER BY total_revenue_numeric DESC
LIMIT 1;

Answer:
CITY IS NOT AVAILABLE IN DATASET
COUNTRY IS UNITED STATES
TOTALTRANSACTIONREVENUE 1015480000


Question 2: 

SQL Queries:
SELECT 
  city, 
  country, 
  ROUND(AVG(productquantity)::numeric, 2) AS average_products_ordered
FROM all_sessions
WHERE productquantity IS NOT NULL
GROUP BY city, country
ORDER BY average_products_ordered DESC;

Answer:


Question 3: 

SQL Queries:
SELECT 
  COALESCE(NULLIF(city, ''), 'Other') AS city, 
  COALESCE(NULLIF(country, ''), 'Other') AS country, 
  v2productcategory, 
  COUNT(*) AS order_count
FROM all_sessions
WHERE v2productcategory IS NOT NULL
  AND (city IS NOT NULL AND city != '(not set)')
  AND (country IS NOT NULL AND country != '(not set)')
  AND (city IS NOT NULL AND city != 'not available in demo dataset')
  AND (country IS NOT NULL AND country != 'not available in demo dataset')
GROUP BY city, country, v2productcategory
HAVING COUNT(*) > 10
ORDER BY country, city, order_count DESC;

Answer:



Question 4: 

SQL Queries:

Answer:



Question 5: 

SQL Queries:

Answer:
