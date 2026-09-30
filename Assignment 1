-- 1. Female customers
SELECT customer_id, cust_first_name, cust_last_name,
       gender, cust_marital_status
FROM sh.customers
WHERE gender = 'F';


-- 2. Last name starts with S and birth year > 1970
SELECT customer_id, cust_first_name, cust_last_name,
       cust_year_of_birth
FROM sh.customers
WHERE cust_last_name LIKE 'S%'
  AND cust_year_of_birth > 1970;


-- 3. Products with list price between 100 and 500
SELECT product_id, product_name, product_category, list_price
FROM sh.products
WHERE list_price BETWEEN 100 AND 500;


-- 4. Minimum price < 50 and status available
SELECT product_id, product_name, min_price, product_status
FROM sh.products
WHERE min_price < 50
  AND product_status = 'available';


-- 5. Transactions with amount sold > 1000
SELECT product_id, customer_id, quantity_sold, amount_sold
FROM sh.sales
WHERE amount_sold > 1000;


-- 6. Quantity sold > 2 and channel ID = 3
SELECT product_id, customer_id, quantity_sold, channel_id
FROM sh.sales
WHERE quantity_sold > 2
  AND channel_id = 3;


-- 7. Channels containing "Direct"
SELECT channel_id, channel_desc
FROM sh.channels
WHERE channel_desc LIKE '%Direct%';


-- 8. Promotions with cost > 1000
SELECT promo_id, promo_name, promo_cost, promo_category
FROM sh.promotions
WHERE promo_cost > 1000;


-- 9. End date > begin date and cost > 500
SELECT promo_id, promo_name, promo_begin_date,
       promo_end_date, promo_cost
FROM sh.promotions
WHERE promo_end_date > promo_begin_date
  AND promo_cost > 500;


-- 10. Countries belonging to region 52790
SELECT country_id, country_name, region_id
FROM sh.countries
WHERE region_id = 52790;


-- 11. Dates belonging to year 2000
SELECT time_id, day_name, calendar_month_name, calendar_year
FROM sh.times
WHERE calendar_year = 2000;


-- 12. December 2001
SELECT time_id, day_name, calendar_month_name, calendar_year
FROM sh.times
WHERE calendar_month_name = 'December'
  AND calendar_year = 2001;


-- 13. Unit price greater than unit cost
SELECT product_id, time_id, unit_cost, unit_price
FROM sh.costs
WHERE unit_price > unit_cost;


-- 14. Unit cost > 100 and unit price < 1000
SELECT product_id, time_id, unit_cost, unit_price
FROM sh.costs
WHERE unit_cost > 100
  AND unit_price < 1000;


-- 15. Household size > 3
SELECT customer_id, education, occupation, household_size
FROM sh.supplementary_demographics
WHERE household_size > 3;

-- 16. Number of customers by marital status
SELECT cust_marital_status,
       COUNT(*) AS customer_count
FROM sh.customers
GROUP BY cust_marital_status;


-- 17. Average year of birth by gender
SELECT gender,
       AVG(cust_year_of_birth) AS avg_birth_year
FROM sh.customers
GROUP BY gender;


-- 18. Average list price by product category
SELECT product_category,
       AVG(list_price) AS avg_list_price
FROM sh.products
GROUP BY product_category;


-- 19. Highest minimum price by product subcategory
SELECT product_subcategory,
       MAX(min_price) AS highest_min_price
FROM sh.products
GROUP BY product_subcategory;


-- 20. Total sales amount by channel
SELECT channel_id,
       SUM(amount_sold) AS total_sales
FROM sh.sales
GROUP BY channel_id;


-- 21. Total quantity sold by product
SELECT product_id,
       SUM(quantity_sold) AS total_quantity
FROM sh.sales
GROUP BY product_id;


-- 22. Average sales amount by promotion
SELECT promo_id,
       AVG(amount_sold) AS avg_sales_amount
FROM sh.sales
GROUP BY promo_id;


-- 23. Total promotion cost by category
SELECT promo_category,
       SUM(promo_cost) AS total_promo_cost
FROM sh.promotions
GROUP BY promo_category;


-- 24. Number of countries by region
SELECT region_id,
       COUNT(*) AS country_count
FROM sh.countries
GROUP BY region_id;


-- 25. Average unit cost by product
SELECT product_id,
       AVG(unit_cost) AS avg_unit_cost
FROM sh.costs
GROUP BY product_id;

-- 26. Customers by gender and marital status
SELECT gender,
       cust_marital_status,
       COUNT(*) AS customer_count
FROM sh.customers
GROUP BY gender, cust_marital_status;


-- 27. Products by category and subcategory
SELECT product_category,
       product_subcategory,
       COUNT(*) AS product_count
FROM sh.products
GROUP BY product_category, product_subcategory;


-- 28. Total sales by product and channel
SELECT product_id,
       channel_id,
       SUM(amount_sold) AS total_sales
FROM sh.sales
GROUP BY product_id, channel_id;


-- 29. Total quantity by channel and promotion
SELECT channel_id,
       promo_id,
       SUM(quantity_sold) AS total_quantity
FROM sh.sales
GROUP BY channel_id, promo_id;


-- 30. Average unit cost by product and promotion
SELECT product_id,
       promo_id,
       AVG(unit_cost) AS avg_unit_cost
FROM sh.costs
GROUP BY product_id, promo_id;  


-- 31. Total sales by channel where amount sold > 500
SELECT channel_id,
       SUM(amount_sold) AS total_sales
FROM sh.sales
WHERE amount_sold > 500
GROUP BY channel_id;


-- 32. Average list price by category where list price > 100
SELECT product_category,
       AVG(list_price) AS avg_list_price
FROM sh.products
WHERE list_price > 100
GROUP BY product_category;


-- 33. Count customers born after 1970 by marital status
SELECT cust_marital_status,
       COUNT(*) AS customer_count
FROM sh.customers
WHERE cust_year_of_birth > 1970
GROUP BY cust_marital_status;


-- 34. Average promotion cost by category where cost > 500
SELECT promo_category,
       AVG(promo_cost) AS avg_promo_cost
FROM sh.promotions
WHERE promo_cost > 500
GROUP BY promo_category;


-- 35. Maximum unit price by product where unit cost > 50
SELECT product_id,
       MAX(unit_price) AS max_unit_price
FROM sh.costs
WHERE unit_cost > 50
GROUP BY product_id;

-- 36. Marital statuses having more than 100 customers
SELECT cust_marital_status,
       COUNT(*) AS customer_count
FROM sh.customers
GROUP BY cust_marital_status
HAVING COUNT(*) > 100;


-- 37. Product categories with average list price > 500
SELECT product_category,
       AVG(list_price) AS avg_list_price
FROM sh.products
GROUP BY product_category
HAVING AVG(list_price) > 500;


-- 38. Channels with total sales > 100000
SELECT channel_id,
       SUM(amount_sold) AS total_sales
FROM sh.sales
GROUP BY channel_id
HAVING SUM(amount_sold) > 100000;


-- 39. Promotion categories with average cost > 1000
SELECT promo_category,
       AVG(promo_cost) AS avg_promo_cost
FROM sh.promotions
GROUP BY promo_category
HAVING AVG(promo_cost) > 1000;


-- 40. Products with average unit price > 500
SELECT product_id,
       AVG(unit_price) AS avg_unit_price
FROM sh.costs
GROUP BY product_id
HAVING AVG(unit_price) > 500;
