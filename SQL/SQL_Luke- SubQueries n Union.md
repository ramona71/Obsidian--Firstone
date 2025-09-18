# SubQueries n CTE (Common table Expressions)
## SubQueries
- creating temporary tables (result set) 
- A **subquery** is a query **inside another query**.  
- used when you need to calculate or filter something first, then use that result in the main query.
- <mark style="background: #FFF3A3A6;">used in SELECT, FROM , WHERE</mark>
- ex:
```sql
SELECT name, salary
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);

SELECT department, AVG(salary) AS avg_salary
FROM (SELECT * FROM employees WHERE active = TRUE) AS active_emps
GROUP BY department;

SELECT * 
FROM
 (SELECT * FROM job_posting WHERE EXTRACT(MONTH FROM job_posting='1'))
  AS january_jobs;


SELECT company_id,company_name AS name FROM company_dim
WHERE company_id IN (
	SELECT company_id FROM job_postings_fact 
	WHERE job_no_degree_mention = true
	ORDER BY company_id
)
```
## CTE (Common table Expressions)
giving a subquery a **temporary name** so you can use it more cleanly in your main query.
- Defined using `WITH`.
- <mark style="background: #FFF3A3A6;">used in SELECT, INSERT, UPDATE, DELETE </mark> defined using <mark style="background: #FFF3A3A6;">'WITH'</mark>
```sql
WITH cte_name AS (
    -- subquery here
    SELECT column1, column2
    FROM some_table
    WHERE condition
)
SELECT *
FROM cte_name
WHERE column1 > 100;

-- ex
WITH sales_cte AS (
    SELECT customer_id, SUM(amount) AS total_sales
    FROM sales
    GROUP BY customer_id
)
SELECT *
FROM sales_cte
WHERE total_sales > 10000;

-- example

WITH company_job_count AS (
	SELECT company_id, COUNT(*) AS total_jobs
	FROM job_postings_fact GROUP BY company_id
)
SELECT * FROM company_dim.name AS company_name, company_job_count.total_jobs
company_dim
LEFT JOIN company_job_count ON company_job_count.company_id = company_dim.company_id
```
