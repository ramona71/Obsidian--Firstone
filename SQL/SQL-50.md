# 4. [1148. Article Views I](https://leetcode.com/problems/article-views-i/)
- my ans = optimal
```sql
# Write your MySQL query statement below

SELECT DISTINCT author_id AS id FRoM Views WHERE author_id = viewer_id ORDER BY id ASC
```
# 5. [620. Not Boring Movies](https://leetcode.com/problems/not-boring-movies/)
- my ans = optimal
```sql
# Write your MySQL query statement below

SELECT * FROM Cinema 
WHERE id%2<>0 AND description<>'boring' ORDER BY rating DESC
```
- not optimal but another way
```sql
SELECT * FROM Cinema
WHERE id % 2 = 1 AND description <> 'boring'ORDER BY rating DESC;
```

> 'id%2<>0' is better than' id % 2 = 1' as it works for both +ve n -ve no.s

# [1683. Invalid Tweets](https://leetcode.com/problems/invalid-tweets/)
- my ans  - wrong
```sql
SELECT tweet_id FROM Tweets HAVING LENGTH(content)>15
```
- correct & optimal
```sql
SELECT tweet_id FROM Tweets WHERE LENGTH(content) > 15; 
```
- The issue:
	- `HAVING` is used **after aggregation (GROUP BY)** to filter groups.
	- You don’t have `GROUP BY` here.
	- You just want to filter **rows**, not groups.
# [1251. Average Selling Price](https://leetcode.com/problems/average-selling-price/)
- my ans
```sql
```
- optimal
```sql
```
# [1075. Project Employees I](https://leetcode.com/problems/project-employees-i/)
- my ans
```sql
```
- optimal
```sql
```
# JOINS
# [1378. Replace Employee ID With The Unique Identifier](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier/)
- my ans = optimal
```sql
SELECT EmployeeUNI.unique_id, Employees.name FROM Employees
LEFT JOIN EmployeeUNI ON Employees.id=EmployeeUNI.id
```
# [1068. Product Sales Analysis I](https://leetcode.com/problems/product-sales-analysis-i/)
- my ans
```sql
SELECT p.product_name, s.year , s.price FROM Sales as s
LEFT JOIN Product as p ON s.product_id= p.product_id
```
# [2356. Number of Unique Subjects Taught by Each Teacher](https://leetcode.com/problems/number-of-unique-subjects-taught-by-each-teacher/)
- my ans
```sql
SELECT teacher_id , COUNT(DISTINCT subject_id) AS cnt FROM Teacher GROUP BY teacher_id
```
#
- my ans
```sql
```
- optimal
```sql
```
#
- my ans
```sql
```
- optimal
```sql
```
#
- my ans
```sql
```
- optimal
```sql
```
#
- my ans
```sql
```
- optimal
```sql
```