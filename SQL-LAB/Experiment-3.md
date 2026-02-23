# SQL Lab – Experiment 3
# Aim
To perform SQL queries using SELECT,WHERE,ORDER BY and conditions to retrieve employee data from the database.


## Question 1
List all employees and jobs in Department 30 in descending 
order by salary. 
```sql
SELECT ename, job, sal FROM Employee
WHERE deptno = 30
ORDER BY sal DESC;
```
## Question 2
 List job and Department Number of employees whose name are five letters long begin with “A” and end with “N”. 
 ```sql
SELECT job, deptno FROM Employee
WHERE ename LIKE 'A___N';
```
## Question 3
 Display the name of employees whose name start with 
alphabet S. 
```sql
SELECT ename FROM Employee
WHERE ename LIKE 'S%';
```
## Question 4
 Display the names of employees whose name ends with 
alphabet S. 
```sql
SELECT ename FROM Employee
WHERE ename LIKE '%S';
```
## Question 5
 Display the names of employees working in department 
number 10 or 20 or 40 or employees working as clerks, 
salesman or analyst. 
```sql
SELECT ename FROM Employee
WHERE deptno IN (10, 20, 40)
OR job IN ('CLERK', 'SALESMAN', 'ANALYST');
```
## Question 6
 Display employee number and names for employees who earn 
commission. 
```sql
SELECT empno, ename FROM Employee
WHERE comm IS NOT NULL;
```
## Question 7
 Display employee number and total salary for each employee. 
```sql
SELECT empno, (sal + IFNULL(comm,0)) AS total_salary
FROM Employee;
```
## Question 8
 Display employee number and annual salary for each 
employee. 
```sql
SELECT empno, (sal * 12) AS annual_salary
FROM Employee;
```
## Question 9
 Display the names of all employees working as clerks and drawing a salary more than 3,000. 
 ```sql
SELECT ename FROM Employee
WHERE job = 'CLERK'
AND sal > 3000;
```
## Question 10
Display the names of employees who are working as clerk, salesman or analyst and drawing a salary more than 3,000.
```sql
SELECT ename FROM Employee
WHERE job IN ('CLERK', 'SALESMAN', 'ANALYST')
AND sal > 3000;
```
