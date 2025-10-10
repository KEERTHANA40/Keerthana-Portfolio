SELECT, WHERE, GROUP BY examples.

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

