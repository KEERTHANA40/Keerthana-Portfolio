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

