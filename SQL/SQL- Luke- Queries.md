- <mark style="background: #FFF3A3A6;">keywords r not case sensitive but db names are</mark>

- SELECT - identifies the columns (or data) from a db
- FROM - Identifies the table we are connecting to
- `*` - Special command to select all the columns
- LIMIT- query only a certain amount of rows
- DISTINCT - get unique rows (categories)
	- resource intense (performs calculation on every dp)
- perform more than one sql query by ending each query with '`;`' at the end
- WHERE - filter out using a condition
- COMMENTS 
	- single line ->`--comments`  -> two dashes before text
	- multi line  -> `/* multi line */`
- ORDER BY - sort the rows 
	- NULL is smallest  
	- ASC or DESC
# <mark style="background: #FFF3A3A6;">Order to Write Commands</mark>
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition
GROUP BY column
HAVING condition
ORDER BY column1 [ASC |DESC] ...
LIMIT number;
```
### Some ways to select
- `SELECT * FROM bd_name`
- `SELECT column_name1, column_name2 FROM db_name`
- `SELECT  db_name.column_name FROM db_name` -> while combining diff tables- 
- `SELECT column_name FROM db_name LIMIT 5`
- `SELECT column_name1 FROM db_name;  SELECT column_name2 FROM db_name ;`
- `SELECT column_name FROM db_name WHERE column_name='5' `
- `SELECT column_name FROM db_name WHERE column_name='5' ORDER BY column_name ACS/ DESC `

- `-- query for relavent data`   -> comment
- `/* multi line comment */`
# Comparison
- Used within the **WHERE** or **HAVING** clause
- Used in conjunction with comparison operators:
    - `=`, `<>`(NOT), `>`, `<`, `>=`, and `<=`
- Used in conjunction with logical operators:
    - `AND`, `OR`, `BETWEEN`,`NOT` and `IN` 
```sql
WHERE
    job_title = 'Data Analyst'
-- NOT
WHERE NOT
    job_title = 'Data Analyst'
-- or
WHERE
    job_title <> 'Data Analyst'
-- AND and OR
WHERE
    job_title = 'Data Analyst' AND/OR  salary_avg > 90000
-- BETWEEN
WHERE
    salary BETWEEN 60000 AND 90000

-- IN
WHERE
    job_title = 'Data Analyst' OR job_title = 'Data Scientist' OR 
    job_title = 'Data Engineer'   -- instead of all this just do
WHERE
    job_title IN ('Data Analyst','Data Engineer','Data Scientist')
    
```
## Wild cards
- used to substitute one or more characters in a string
- used with `LIKE` operator
	- `LIKE`
	- `%`  -> `%Analyst%`  , `%Business%Analyst%`
	- `_`   -> single character  `%Business_Analyst%`
	- <mark style="background: #FFF3A3A6;"> used in WHERE clause</mark>
```sql
WHERE
	column_name LIKE '%DATA%'
```
# Alias 
- use `AS` 
	![[Pasted image 20250915135849.png]]
- or just leave space between name and alias
	![[Pasted image 20250915140005.png]]
# Arithmetic Operations
1. **Addition (`+`)**  
    Adds two numbers together.
```sql
SELECT 10 + 5 AS result;  -- Output: 15
```
- Or with columns:
```sql
SELECT salary + bonus AS total_salary
FROM employees;
    ```
2. **Subtraction (`-`)**  
    Subtracts the second number from the first.
```sql
    SELECT 10 - 5 AS result;  -- Output: 5
    SELECT salary - deductions AS net_salary
    FROM employees;
```
3. **Multiplication (`*`)**  
    Multiplies two numbers.
```sql
SELECT 10 * 5 AS result;  -- Output: 50
SELECT quantity * price AS total_cost
FROM orders;
```
4. **Division (`/`)**  
    Divides the first number by the second.
```sql
    SELECT 10 / 2 AS result;  -- Output: 5
    SELECT total_amount / months AS avg_per_month
    FROM subscriptions;
```
5. **Modulus (`%`)**  
    Returns the remainder of a division.
```sql
    SELECT 10 % 3 AS result;  -- Output: 1
    SELECT employee_id % 2 AS is_even
    FROM employees;
```
- make new columns too
	![[Pasted image 20250915141049.png]]
```sql
SELECT salary, salary * 0.1 AS bonus FROM employees;

SELECT * FROM orders WHERE (quantity * unit_price) > 100;

SELECT name, age, (current_date - birth_date) / 365 AS age_years 
FROM people 
ORDER BY (current_date - birth_date) / 365;

SELECT department, SUM(salary) 
FROM employees 
GROUP BY department 
HAVING SUM(salary) > 100000;
```
# Group by and Having
- GROUP BY- Group rows that share a property so that aggregate functions can be applied
	- groups rows that have same values into summary rows
	- eg: total no of sales by each item
- HAVING - Filter groups based on the result of an aggregate function (unlike WHERE, which filters rows)
	- <mark style="background: #FFF3A3A6;">used cuz u can't aggregate fxns in WHERE</mark>
# Aggregation Fxns
- used with SELECT or GROUP BY or HAVING
- SUM()
- COUNT()
- AVG()
- MAX()
- MIN()
```sql
SELECT SUM(salary) AS salary_sum
SELECT COUNT(*)  -- count of all
SELECT COUNT(DISTINCT column) AS column_count   --distinct values count 
--
SELECT SUM(salary) AS department_salary , employees
FROM department,
GROUP BY departments;
--
SELECT department,
COUNT(employee_id)
FROM employees
GROUP BY department
HAVING COUNT (employee_id) > 10;
--
SELECT job_title_short AS jobs, AVG(salary_year_avg) AS salary_avg, COUNT(job_title_short) as job_count
FROM job_postings_fact
GROUP BY job_title_short
HAVING job_count>100    -- no 'WHERE' cuz can't aggregate in it
ORDER BY salary_avg           -- can use alias created above
```
![[Pasted image 20250915151430.png]]
# Null
- no value
- different form 0 and " "
- used in WHERE or HAVING
```SQL
WHERE salary_avg IS NOT NULL
```
# JOINS
- ![[Pasted image 20250915151723.png]]
- LEFT JOIN- most popular
- <mark style="background: #FFF3A3A6;">make sure to put table name before the column names</mark>
```sql
-- LEFT JOIN
SELECT job_post.job_id,
	 job_post.job_title_short as title,
	 company.name as company
FROM job_postings_fact AS job_post
LEFT JOIN company_dim as company
	 ON job_post.company_id= company.company_id
	 
-- RIGHT JOIN
SELECT job_post.job_id,
	 job_post.job_title_short as title,
	 company.name as company
FROM job_postings_fact AS job_post
RIGHT JOIN company_dim as company
	 ON job_post.company_id= company.company_id
	
-- INNER JOIN
SELECT job_post.job_id,
	 job_post.job_title_short as title,
	 company.name as company
FROM job_postings_fact AS job_post
INNER JOIN company_dim as company
	 ON job_post.company_id= company.company_id
INNER JOIN skill_dim as skills
	 ON job_post.skill_id= skills.skill_id
-- FULL OUTER JOIN  (nobody uses it)
```
# Full Order of Execution
1. FROM/JOIN
	-  Specifies the tables to retrieve data from and how to join them.
2. WHERE
	-  Filters rows based on conditions.
3. GROUP BY
	• Group rows share a property so aggregate functions can be applied. 4. HAVING
	• Filters groups based on aggregate conditions (used after GROUP BY). 5. SELECT
	• Select specific columns to display in the final result.
4. DISTINCT
	• Removes duplicate rows from the result set (applied after SELECT). 7. ORDER BY
	• Sorts the result set based on specified columns/values.
5. LIMIT/OFFSET
	• Limits the number of rows returned, often used for pagination.
# Strings
- string fxns in sql
1. LENGTH / LEN  
```sql
SELECT LENGTH('Hello');   -- MySQL, PostgreSQL, Oracle
SELECT LEN('Hello');      -- SQL Server
````
2. UPPER / LOWER
```sql
SELECT UPPER('sql fun');
SELECT LOWER('SQL FUN');
```
3. TRIM / LTRIM / RTRIM
```sql
SELECT TRIM('   hello   ');
SELECT LTRIM('   hello');
SELECT RTRIM('hello   ');
```
4. SUBSTRING / SUBSTR
```sql
SELECT SUBSTRING('Database', 1, 4);  -- SQL Server, PostgreSQL
SELECT SUBSTR('Database', 1, 4);     -- Oracle, MySQL
```
5. CONCAT / ||
```sql
SELECT CONCAT('Hello', ' ', 'World');
SELECT 'Hello' || ' World';          -- Postgres, Oracle
```
6. REPLACE
```sql
SELECT REPLACE('I like SQL', 'SQL', 'Databases');
```
7. POSITION / CHARINDEX / INSTR
```sql
SELECT POSITION('a' IN 'Database');   -- Postgres
SELECT CHARINDEX('a', 'Database');    -- SQL Server
SELECT INSTR('Database', 'a');        -- MySQL, Oracle
```
8. LEFT / RIGHT
```sql
SELECT LEFT('Database', 4);
SELECT RIGHT('Database', 4);
```