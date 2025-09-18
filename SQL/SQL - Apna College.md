- Relational: tables
- Non relational : no tables ( NoSql )
- CRUD- Create , Read , Update, Delete
- schema- design of table
- field- column
- record- row. 
- NULL value is different than a zero value or a field that contains spaces, NULL is black space
- Creating database
```sql
CREATE DATABASE db_name;
DROP DATABASE db_name;
USE db_name;

SHOW DATABASES;
SHOW TABLES;

--to not show but only warning
CREATE DATABASE IF NOT EXISTS bd_name;
DROP DATABASE IF EXISTS db_name;
```
- Tables
```SQL
CREATE TABLE table_name(
 column_name1  data_type  constraint,
 column_name2  data_type  constraint,
 column_name3  data_type  constraint,
);

--To define schema of table
CREATE TABLE student(
id INT PRIMARY KEY,
name VARCHAR(50),
age INT NOT NULL
);

--  deleting a table
DROP TABLE table_name;

-- insert in table
INSERT INTO table_name VALUES ( 1, 'ARUN' , 19);
--OR, timewaste version
INSERT INTO table_name
(column1, column2)
VALUES
(C1V1, C2V1),
(C1V1, C2V1),
(C1V1, C2V1);

-- select all colimns from table
SELECT * FROM table_name;
```
- primary key should always be unique
- Datatypes
	![[Pasted image 20240822114259.png]]
- TINYINT UNSIGNED (0 to 255)
- TINTYINT (-128 to 127)
## Alias
- alternate name
```sql
SELECT * FROM student3 as s
INNER JOIN course as c
WHERE s.ID= c.ID;
```
## Keys
- Primary Key: uniquely identify the row
	- a single or multiple columns
	- should be only only one pk and should NOT be null.
	- multiple fields are used as a primary key, they are called a composite key.
- Foreign Key: pk for other table
	- can be multiple foreign keys
	- fk can have duplicate or null values
## Constraints
- NOT NULL 
- UNIQUE
- PRIMARY KEY
- FOREIGN KEY
- DEFAULT
- CHECK
```SQL
id INT NOT NULL

id INT UNIQUE

--TWO WAYS TO WRITE PK
id INT PRIMARY KEY;
--OR
id INT,
PRIMARY KEY(id)

id INT,
name VARCHAR(50)
PRIMARY KEY(id, name)

CREATE TABLE marks (
rollno INT,
percentage INT,
FOREIGN KEY rollno REFERENCES student(rollno)
);

salary INT DEFAULT 5000;
--ex
CREATE TABLE emp (
id INT ,
salary INT DEFAULT 5000
);
INSERT INTO emp(id) VALUES (1), (2);         --SPECIFY THE COLUMN ID

CREATE TABLE new(
age INT CHECK (age >=18)
);

CREATE TABLE new(
age INT,
city VARCHAR(50),
id INT PRIMARY KEY,  
CONSTRAINT age_check CHECK (age>=18 AND city='Pune')
);

```
## Clauses
#### Select
```SQL
 SELECT * FROM table_name;
 SELECT col1, col2 FROM tab_name;
 SELECT DISTINCT col FROM tab_name;
```
#### Where
```SQL
SELECT col1, col2 FROM table_name
WHERE condns;

SELECT * FROM emp WHERE age>=18;
SELECT * FROM emp WHERE city='Mumbai' AND marks>80;
```
	![[Pasted image 20240822133833.png]]
	-  Between (selects for a given range)
	- between operator is inclusive , below 80 and 90 r also considered
	- In (matches any value in the list)
	- NOT (to negate the given condition)
``` SQL
SELECT * FROM student WHERE marks>80 AND city='Mumbai';
SELECT * FROM student WHERE marks >90 OR city ='Mumbai' ;
SELECT * FROM student WHERE marks BETWEEN 80 AND 90;
SELECT FROM student WHERE city IN ("Delhi", "Mumbai");
SELECT FROM student WHERE city NOT IN ("Delhi", "Mumba 
```

#### Limit 
- sets limit on no of rows to be displayed
```SQL
SELECT * FROM table_name LIMIT no;
SELECT * FROM students LIMIT 5;
SELECT * FROM student WHERE marks > 75 LIMIT 5 ;
-- limit should come after where , and it displayes 5 rows, not first 5 but any 5 that follow the condition in asceinding order
```
#### Order By
```SQL
SELECT * FROM student ORDER BY city ;
SELECT * FROM student ORDER BY city ASC;
SELECT * FROM student ORDER BY city DESC;
```
- TOP 3 students by marks
```sql
SELECT * FROM student ORDER BY marks DESC LIMIT 3;
```
#### Group By
- group the result by columns 
```SQL
-- count no of students in each city
SELECT city , count(name) FROM student GROUP BY city;
SELECT city, avg(marks) FROM student GROUP BY city;

--gives error cuz name is not inside group by
SELECT city, count(rollno), name FROM student GROUP BY city;
--no error
SELECT city, count(rollno), name FROM student GROUP BY city,name;
```
	![[Pasted image 20240822152951.png]]
#### Having
- conditional like WHERE clause but is used where WHERE cna't be used
- WHERE - rows
- HAVING- groups
```SQL
-- Q . below one give error, why?
SELECT count(rollno),city FROM student GROUP BY city HAVING marks >90;
```
## General Order

```sql
SELECT 
FROM 
WHERE
GROUP BY
HAVING
ORDER BY
```
## Aggregate Functions

- COUNT()  - how many r present
- MAX()
- MIN()
- SUM()
- AVG()
```SQL
SELECT COUNT(name) FROM student; 
SELECT MAX(marks) FROM student; 
SELECT MIN(marks) FROM student; 
SELECT SUM(marks) FROM student; 
SELECT AVG(marks) FROM student; 
```
## Table Related Queries
#### Update
```sql
UPDATE student SET marks= marks+1;
UPDATE student SET grade='B' WHERE grade='A';
UPDATE student SET grade= 'A' WHERE marks> 90;
```
#### Delete
```sql
DELETE tab_name WHERE condn;
DELETE student WHERE marks< 33;
DELETE FROM student;     -- entire table gets deleted
```
#### Alter
```sql
ALTER TABLE table_name ADD COLUMN colum_name data_type constain;
ALTER TABLE table_name DROP COLUMN  colname dataatype ;
ALTER TABLE tab_name RENAME newtabname;

-- change
ALTER TABLE tabname CHANGE oldname newname newdatatype newconstrain;
-- just wanna rename the column
ALTER TABLE tabname CHANGE oldname newname olddatype;

--- modify
ALTER TABLE tabname MODIFY newdatatype newconstrain;
```

```sql
--ADD Column
ALTER TABLE student ADD COLUMN age INT NOT NULL DEFAULT 19;
--MODIFY Column
ALTER TABLE student MODIFY age VARCHAR(2);
--CHANGE Column (rename)
ALTER TABLE student CHANGE age stu_age INT;
--DROP Column
ALTER TABLE student DROP COLUMN stu_age;
--RENAME Table
ALTER TABLE student RENAME TO stu;
```
#### Truncate
- deletes the data in the table , keep the table
- DROP- deletes the table along with dat
```sql
TRUNCATE TABLE student;
```
## Foreign keys
- ![[Pasted image 20240822184713.png]]
- remember the direction of arrow
-  like parent n child table
#### Cascading for FK
- if fk is updated/ deleted, then the change will happen in both tables
```sql
CREATE TABLE teacher(
id INT PRIMARY KEY,
name VARCHAR(50),
dept_id INT,
FOREIGN KEY (dept_id) REFERENCES dept(id)
ON DELETE CASCADE
ON UPDATE CASCADE
);

UPDATE dept SET id=3 WHERE id=2; -- the id in teacher table gets updated too
```
## JOINS
- used to combine rows from two or more tables , based on a related column between them
- mostly used where there is fk
	![[Pasted image 20240822203841.png]]
### Inner Join
```sql
SELECT colum1
FROM tab1
INNER JOIN tab2
ON tab1.column= tab2.column;
```
### Left Join
```sql
SELECT columNs
FROM tab1
LEFT JOIN tab2
ON tab1.column= tab2.column;
```
### Right Join
```sql
SELECT columNs
FROM tab1
RIGHT JOIN tab2
ON tab1.column= tab2.column;
```
### Full Join/ Full Outer Join
- doen't exist in mysql we just do
	- LEFT JOIN UNION RIGHT UNION
- oracle and other has this
```sql
SELECT * FROM student3 as s
LEFT JOIN course as c
ON s.ID= c.ID
UNION
SELECT *
FROM student3 as s
RIGHT JOIN course as c
ON s.id= c.id;
```
#### Exclusive Join
![[Pasted image 20240822222725.png]]
![[Pasted image 20240822222753.png]]
```sql
-- left exclusive
SELECT * FROM student3 as a
LEFT JOIN course as b
ON a.ID= b.ID
WHERE b.id IS NULL;
--rigth exclusive
SELECT * FROM student3 as a
RIGTH JOIN course as b
ON a.ID= b.ID
WHERE a.id IS NULL;
-- left and right part without the intersection part
select * from student3 as a
left join course as b
on a.id = b.id
where b.id is null
union
select * from student3 as a
right join course as b
on a.id = b.id
where a.id is null;
```
### Self Join
- used when there is heirarcial relation within the table
	![[Pasted image 20240822224201.png]]
```sql
SELECT * 
FROM tablename as a 
JOIN tablename as b 
ON a.col1= a.col1;

select a.name as manager, b.name 
from employee as a
join employee as b on a.id= b.manager_id;
```
## Union
- gives unique values from two or more tables(duplicates r deleted)
- don't have to keep ; at the end of sentence
- To use unio
	- every SELECT should have same no of columns
	- columns should have same datatype
	- columns in every SELECT should be in same order
```sql
SELECT col FROM tableA
UNION
SELECT col FROM tableB
```
- UNION ALL  gives duplicates
```sql
select name from  employee
union all
select name from  employee
```
## Sub Queries
- subquery / inner query / nested query within another sql query
- can be written inside
	- SELECT
	- FROM
	- WHERE- most used
```sql
SELECT col
FROM tabname
WHERE colname operator
(subquery);
```
- Q find even numbers from roll numbers
```sql
SELECT name, rollno FROM student WHERE rollno IN 
(SELECT rollno FROM student WHERE rollno%2=0);
```
- Q find student who have marks greater than avg marks
```sql
SELECT name, marks
FROM student
WHERE marks> (SELECT  AVG(marks) FROM student);
```
- Q  find max marks from the students of Delhi
```sql
SELECT MAX(marks) FROM (SELECT * FROM student WHERE city='Delhi') AS temp;
--or
SELECT MAX(marks) FROM student WHERE city='Delhi';
```
- Q length of a string
```sql
SELECT tweet_id FROM Tweets WHERE length(content)>15;
```
## MySql Views
- a virtual table , a fake one
- doesn't affect the actual database
```sql
CREATE VIEW view1 AS
SELECT rollno, name, marks FROM student;

SELECT * FROM view1;
DROP VIEW  view1;
```

## Leetcode
- to not get duplicate elements DISTINCT in SELECT
- decimals-  salary DECIMAL (18, 2) , like salary INT
- To drop a DEFAULT constraint, use the following SQL:
	ALTER TABLE CUSTOMERS
	ALTER COLUMN SALARY DROP DEFAULT;