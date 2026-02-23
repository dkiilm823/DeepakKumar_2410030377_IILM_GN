# SQL Lab – Experiment 4

# Aim
To execute SQL queries for retrieving,updating and analyzing employee data using conditions, attern matching and calculations.

## Question 1
Display the list of employees who have joined the company before 30th June 80 or after 31st Dec 81. 
 ## Query
```sql
SELECT *FROM Employee
WHERE hiredate < '1980-06-30'
OR hiredate > '1981-12-31';
```
## Question 2
Display the names of employees whose names have second alphabet A in their names. 
 ## Query
```sql
SELECT ename FROM Employee
WHERE ename LIKE '_A%';
```
## Question 3
Display the names of employees whose name is exactly five characters in length 
 ## Query
```sql
SELECT ename FROM Employee
WHERE ename LIKE '_____';
```
## Question 4
Display the names of employees whose names have second alphabet A in their names. 
 ## Query
```sql
SELECT ename FROM Employee
WHERE ename LIKE '_A%';
```
## Question 5
Display the names of employees who are not working as salesman or clerk or analyst. 
 ## Query
```sql
SELECT ename FROM Employee
WHERE job NOT IN ('SALESMAN', 'CLERK', 'ANALYST');
```
## Question 6
Display the name of the employee along with their annual salary (sal*12). The name of the employee earning highest 
salary should appear first. 
 ## Query
```sql
SELECT ename, (sal * 12) AS annual_salary FROM Employee
ORDER BY sal DESC;
```
## Question 7
Display name, sal, hra, pf, da, totalsal for each employee. The output should be in the order of total sal, hra 15% of sal, da 
10% of sal, pf 5% of sal. Total salary will be (sal*hra*da)-pf. 
 ## Query
```sql
SELECT ename,sal,
(sal * 0.15) AS hra,
(sal * 0.10) AS da,
(sal * 0.05) AS pf,
((sal + (sal * 0.15) + (sal * 0.10)) - (sal * 0.05)) AS totalsal
FROM Employee ORDER BY totalsal DESC;
```
## Question 8
Update the salary of each employee by 10% increment who are not eligible for commission. 

 ## Query
```sql
UPDATE Employee SET sal = sal * 1.10
WHERE comm IS NULL;
```
## Question 9
Display those employees whose salary is more than 3000 after giving 20% increment. 
 ## Query
```sql
SELECT ename, (sal * 1.20) AS increased_salary FROM Employee
WHERE (sal * 1.20) > 3000;
```
## Question 10
Display those employees whose salary contains atleast 3 digits.
 ## Query
```sql
SELECT ename, sal FROM Employee
WHERE sal >= 100;
```