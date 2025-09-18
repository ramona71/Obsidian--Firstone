# PostGreSQL
- manipulate tables (create, drop, insert, alter, update)
- gotta launch pgAdmin to connect to server and run the database
- To create a db
	- `add a new connection`
	- test and save the connection
- to run click on ![[Pasted image 20250915184743.png]] above the code
# Data Types
- https://www.postgresql.org/docs/current/datatype.html
- `INT`
	- whole no.
	- 4 bytes 
- `NUMERIC` 
	- precise no. with fixed decimal points
	- `precision` - no of digits
	- `scale` - no of digits to right of decimal
	- `NUMERIC(6,3)`
- `VARCHAR (n)`
	- n - max length of string 
	- `VARCHAR (10)`
- `TEXT`
	- unlimited length 
- `BOOLEAN`
	- `true, false, NULL`
- `DATE`
	- `YY-MM-DD`
- `TIMESTAMP`
	-  `YY-MM-DD HH:MI:SS`
- `TIMESTAMP WITH TIME ZONE`
	-   `YY-MM-DD HH:MI:SS+ 00:00`
# Manipulate tables (CAID)
<mark style="background: #FFF3A3A6;">All these changes are permanent</mark>
- CREATE TABLE: create tables
- INSERT INTO : add columns (data) to your tables
- ALTER TABLE: alter tables
	- ADD: add columns
	- RENAME COLUMN: rename columns
	- ALTER COLUMN: change the datatype of a column
	- DROP COLUMN: delete a column
- DROP TABLE: delete tables
## Syntax
### **1. CREATE TABLE** 
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);
```
**Notes:**
- Define each column with a name and data type.
- Can also add constraints like `PRIMARY KEY`, `NOT NULL`.
### **2. INSERT INTO** 
- Adds rows (data) into a table.
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES ( (value1, value2...),
		 (value1, value2...),
		...
	    );
```
**Notes:**
- Column list is optional if inserting into all columns.
- Data must match the column’s data type.
### **3. ALTER TABLE** 
- Changes the structure of an existing table.
```sql
ALTER TABLE table_name
	ADD column_name datatype;
	RENAME COLUMN column_name TO new_name;
	ALTER COLUMN column_name TYPE datatype;
	DROP COLUMN column_name;
```
 a) **ADD** – Add new columns
- don't forget to UPDATE the values when u add a new column
```sql
ALTER TABLE table_name
ADD column_name datatype;
```
 b) **RENAME COLUMN** – Rename existing column
```sql
ALTER TABLE table_name
RENAME COLUMN old_name TO new_name;
```
 c) **ALTER COLUMN** – Change datatype of a column
 - sometimes u can't change a datatype to another (pizza to int) so better assign correctly in the first time
```sql
ALTER TABLE table_name
ALTER COLUMN column_name TYPE new_datatype;
```
 d) **DROP COLUMN** 
-  Delete a column
```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```
**Notes:**
- Use carefully, `DROP COLUMN` permanently deletes data in that column.
- Not all databases support every option in the same way.
### **4. DROP TABLE**
- Deletes an entire table.
```sql
DROP TABLE table_name;
```
**Notes:**
- Removes the table and all its data permanently.
- Often used with `IF EXISTS` to avoid errors:
```sql
DROP TABLE IF EXISTS table_name;
```
## UPDATE
- modify existing data in table / add new values when a new column is added
- SET- specifies the column to be updated
- WHERE - filters rows on condition
```sql
UPDATE table_name
SET column_name ='new value'
WHERE condn;
```
- if multiple rows r there, repeat this statement for all those rows INDIVIDUALLY
### <mark style="background: #FFF3A3A6;">All these changes are permanent</mark>

# Handling Dates
- Date Functions in SQL: used to perform operations on date and time values
	- `::DATE`:<mark style="background: #ABF7F7A6;"> converts to a date format</mark> by removing the time portion
	- `AT TIME ZONE`: converts a timestamp (UTC) to a specified time zone
		- can be used on timestamps with or without time zone info
	- `EXTRACT`: gets specific date parts (e.g., year, month, day)
### TIMESTAMP WITH TIME ZONE vs TIMESTAMP WITHOUT TIME ZONE
- **`TIMESTAMP WITH TIME ZONE` (aka `timestamptz`)**
    - Stores both the date/time **and** the time zone info.
    - Automatically adjusts when you convert to another time zone.
    - Example: `"2025-09-16 10:00:00+00"` means 10 AM in **UTC**.
- **`TIMESTAMP WITHOUT TIME ZONE`**
    - Stores only the **date and time**, with **no time zone info**.
    - Treated as a “local time,” so you must explicitly tell SQL what zone it’s in if you want conversion.
    - Example: `"2025-09-16 10:00:00"` → Could be 10 AM anywhere.
```sql
-- ways to select
SELECT '2024-05-07':: DATE,   -- convert string to DATE datatype
        '123':: INTEGER;

SELECT job_title_short AS title,
    job_posted_date::DATE as job_date;   -- way to convert to DATE datatype
    
-- timestamp with time zone
SELECT column_name AT TIME ZONE 'EST' FROM table_name;
--timestamp without timezone (converting from utc to est)
SELECT column_name AT TIME ZONE 'UTC' AT TIME ZONE 'EST' FROM table_name;

-- extract
SELECT (MONTH FROM column_name) AS column_month FROM table_name
SELECT * FROM job_table WHERE (MONTH FROM job_posted_date)='1' ;
```
# Create table from filtered data
- create a table where only january job postings are stored
```sql
CREATE TABLE january_jobs AS
	SELECT * FROM job_table WHERE (MONTH FROM job_posted_date)='1' ;
```
# Case expression
- if else statement 
```sql
SELECT
  CASE
    WHEN column_name = 'Value1' THEN 'Description for Value1'
    WHEN column_name = 'Value2' THEN 'Description for Value2'
    ELSE 'Other'
  END AS column_description
FROM table_name;
-- ex
SELECT
  CASE
    WHEN column_name = 'Value1' THEN 'Description for Value1'
    WHEN column_name = 'Value2' THEN 'Description for Value2'
    ELSE 'Other'
  END AS column_description
FROM table_name;

```

1. **CASE** → Starts the conditional block (like saying “IF”).
2. **WHEN condition THEN result** → If the condition is true, return this result.    
    - If `column_name = 'Value1'`, return `'Description for Value1'`.
    - If `column_name = 'Value2'`, return `'Description for Value2'`.
3. **ELSE** → If none of the above conditions are true, return `'Other'`.
4. **END** → Marks the end of the CASE expression.
5. **AS column_description** → Gives a name to the output column.
