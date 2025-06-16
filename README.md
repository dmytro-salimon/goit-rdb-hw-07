#1
SELECT 
    id,
    date AS original_date,
    YEAR(date) AS year_value,
    MONTH(date) AS month_value,
    DAY(date) AS day_value
FROM orders
ORDER BY id;

#2
SELECT 
    id,
    date AS original_date,
    DATE_ADD(date, INTERVAL 1 DAY) AS date_plus_one_day
FROM orders
ORDER BY id;

#3
SELECT 
    id,
    date AS original_date,
    UNIX_TIMESTAMP(date) AS timestamp_seconds
FROM orders
ORDER BY id;

#4
SELECT COUNT(*) AS orders_count
FROM orders
WHERE date BETWEEN '1996-07-10 00:00:00' AND '1996-10-08 00:00:00';

#5
SELECT 
    id,
    date,
    JSON_OBJECT('id', id, 'date', date) AS json_data
FROM orders
ORDER BY id;
