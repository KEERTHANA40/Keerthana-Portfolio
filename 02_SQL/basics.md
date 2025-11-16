SQL - Structured Query language - RDB - ORDER MATTERS
# tables
1. SHOW TABLES;
2. SHOW COLUMNS from tablename OR DESC tablename - description of the table
4. DROP TABLES;
5. -- OR >> comments
# Working on table
1. CREATE TABLE <tablename>(
   col1 type1 PRIMARY KEY,
   col2 type2
   )
2. INSERT INTO tablename (col1, col2) VALUES(v1,v2); = no need to specify column names
3. INSERT INTO name1
   SELECT * from name2
4. CREATE TABLE name1 **as**
   SELECT * from name2
5. Rules for col1 - PRIMARY KEY, AUTO INCREMENT, NOT NULL. DEFAULT (giving value if passed NULL), KEY, 

# Operations on table
CRUD
C - create
R - read
U - Update
D - Delete

# Select - to get certain things
1. SELECT * FROM tablename
2. SELECT col1 FROM tablename
3. SELECT col1 FROM tablename WHERE condition

# Update -
1. Rule of thumb - always use SELECT before UPDATE
2. UPDATE tablename SET col1 = value WHERE condition **first tablename then operation**
3. **if where condition not given, then updates the whole column**

# DISTINCT
1. SELECT DISTINCT col1 from tablename

# ORDER BY
SELECT * FROM tablename ORDER BY col1/the index of col
SELECT * FROM tablename ORDER BY col1/the index of col **DESC**

<img width="828" height="418" alt="image" src="https://github.com/user-attachments/assets/c537f34c-386d-419a-a7a9-4bb760a74f1d" />

<img width="740" height="935" alt="image" src="https://github.com/user-attachments/assets/6fd81acc-25b0-4799-b2d3-20f2fe732623" />

# LIMIT - end output count

# LIKE - considering with conditions
% = any number 
_ = 1 character only

# Delete From- 
1. Same rules as UPDATE
2. DELETE FROM tablename WHERE condition
   
## String manipulation
# CONCAT
SELECT CONCAT(col1,col2) AS newcol1 FROM tablename

# Substring - SUBSTR
SELECT SUBSTR(col1,1,20) AS newcol1 FROM tablename

# Replace
SELECT REPLACE(Str,s1,s2) FROM tablename

# TRIM - remove whitespaces

## Aggregate functions
# COUNT 
SELECT COUNT (*) FROM tablename = null not considered
SELECT COUNT (DISTINCT col1) FROM tablename

# GROUP BY
SELECT COUNT(*) FROM tablename GROUP BY col1

# MIN MAX SUM AVG

SELECT, WHERE, GROUP BY examples.

# HackerRank
Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
<img width="300" height="290" alt="image" src="https://github.com/user-attachments/assets/272b70a8-fad7-42e1-bba1-705ba6d98c50" />

SELECT count(city) - count(distinct city) from STATION;

# SQL Basics — Sept 20

## SELECT & WHERE
```sql
-- Select specific columns
SELECT name, age FROM employees;

-- Filter rows
SELECT * FROM employees WHERE age > 30;

-- Order by column
SELECT name, salary FROM employees ORDER BY salary DESC LIMIT 5;

-- Count rows
SELECT COUNT(*) FROM employees;

-- Average salary
SELECT AVG(salary) FROM employees WHERE department = 'IT';

-- Inner join example
SELECT e.name, d.dept_name
FROM employees e
JOIN departments d ON e.dept_id = d.id;

# SQL Basics — SELECT / WHERE / ORDER BY (Sept 23)

## 1) SELECT
Example:
```sql
SELECT customer_id, order_date, total_amount
FROM orders;

SELECT customer_id, order_date, total_amount
FROM orders
WHERE total_amount > 1000;

SELECT customer_id, order_date, total_amount
FROM orders
WHERE total_amount > 1000
ORDER BY order_date DESC;

# SQL Basics — SELECT / WHERE / ORDER BY / JOIN (Sept 25)

## 1) Review (from Sept 23)
- SELECT columns
- WHERE filters rows
- ORDER BY sorts

## 2) Simple INNER JOIN

Example:

```sql
SELECT c.customer_id, c.customer_name, o.order_date, o.total_amount
FROM customers c
INNER JOIN orders o
  ON c.customer_id = o.customer_id
WHERE o.total_amount > 1000
ORDER BY o.order_date DESC;
```

**Notes:**
- `INNER JOIN` combines rows where the join condition matches (customer_id in both tables).
- Always alias tables (`c`, `o`) for clarity.
- Common interview Q: difference between INNER vs LEFT JOIN.

- Understanding joins:

## JOINs quick notes (Sept 29)
- INNER JOIN: returns rows with matching keys in both tables.
- LEFT JOIN: all rows from left table + matching from right (NULL if no match).
- RIGHT JOIN: all rows from right table + matching from left.
- FULL OUTER JOIN: all rows from both tables, NULL where no match.

# SQL Basics — GROUP BY & Aggregation (Oct 7)

-- 1. Total amount per customer
SELECT customer, SUM(amount) AS total_amount, COUNT(*) AS orders
FROM orders
GROUP BY customer
ORDER BY total_amount DESC;

-- 2. Daily avg order amount
SELECT order_date, AVG(amount) AS avg_amount
FROM orders
GROUP BY order_date
ORDER BY order_date;

-- 3. Group + HAVING (filter groups)
SELECT customer, SUM(amount) AS total_amount
FROM orders
GROUP BY customer
HAVING SUM(amount) > 100;

## 4) JOIN Examples (Oct 9)

-- INNER JOIN example
SELECT c.customer_name, o.order_date, o.amount
FROM customers c
INNER JOIN orders o ON c.customer_id = o.customer_id;

-- LEFT JOIN example
SELECT c.customer_name, o.amount
FROM customers c
LEFT JOIN orders o ON c.customer_id = o.customer_id;

-- Note:
INNER JOIN → only matching records.
LEFT JOIN → all records from left table + matched rows from right.

# INNER JOIN — Practical Example (Oct 10)

SELECT c.customer_id, c.name, o.order_date, o.total_amount  
FROM customers c  
INNER JOIN orders o ON c.customer_id = o.customer_id;

-- INNER JOIN returns only matching records between tables.
