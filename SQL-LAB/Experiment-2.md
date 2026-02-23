# SQL Lab – Experiment 2

# Aim
To retrieve data from the EMPLOYEE table using various SQL SELECT queries with conditions.

## Question 1
List all distinct job in Employee. 
 ## Query
```sql
SELECT DISTINCT Job
FROM Employee;
```
## Question 2
List all information about employee in Department Number 30. 
 ## Query
```sql
SELECT *FROM Employee
WHERE deptno = 30;
```
## Question 3
Find all department number with department names greater than 20.
 ## Query
```sql
SELECT deptno, Dname FROM Department
WHERE dname > 20;
``` 
## Question 4
Find all information about all the managers as well as the clerks in department 30.
 ## Query
```sql
SELECT *
FROM Employee
WHERE deptno = 30
AND job IN ('MANAGER','CLERK');
``` 
## Question 5
List the Employee name, Employee numbers and department of all clerks. 
 ## Query
```sql
SELECT Ename, EmpNo, deptno
FROM Employee
WHERE Job = 'CLERK';
```
## Question 6
Find all managers not in department 30.  
 ## Query
```sql
SELECT *
FROM Employee
WHERE Job = 'MANAGER'
AND deptno <> 30;
```
## Question 7
List information about all Employees in department 10 who are not manager or clerks. 
 ## Query
```sql
SELECT *
FROM Employee
WHERE deptno = 10
AND Job NOT IN ('MANAGER', 'CLERK');
```
## Question 8
Find Employees and jobs earning between 1200 and 1400. 
 ## Query
```sql
SELECT Ename, Job, Sal
FROM Employee
WHERE Sal BETWEEN 1200 AND 1400;
```
## Question 9
List Name and Department Number of employee who are clerks, analyst or salesman. 
 ## Query
```sql
SELECT Ename, deptno
FROM Employee
WHERE Job IN ('CLERK', 'ANALYST', 'SALESMAN');
```
## Question 10
List Name and Department Number of employee whose names began with M. 
 ## Query
```sql
SELECT Ename, deptno
FROM Employee
WHERE Ename LIKE 'M%';
```