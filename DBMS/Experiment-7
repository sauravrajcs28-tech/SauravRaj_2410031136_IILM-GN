# Experiment-7

##  Aim

To perform aggregate functions, grouping, matrix queries, and date queries on EMPLOYEE table.


------------------------------------------------------------------------

## Question 1

Compute the number of days remaining in this year.


``` sql
SELECT DATEDIFF(
CONCAT(YEAR(CURDATE()),'-12-31'),
CURDATE()
) AS DAYS_LEFT;
```

### Output
+-----------+
| DAYS_LEFT |
+-----------+
|       309 |
+-----------+
1 row in set (0.000 sec)

------------------------------------------------------------------------
## Question 2

Find highest salary, lowest salary, and their difference.

``` sql
SELECT 
MAX(SAL) AS HIGHEST_SALARY,
MIN(SAL) AS LOWEST_SALARY,
MAX(SAL)-MIN(SAL) AS DIFFERENCE
FROM EMPLOYEE;
```

### Output
+----------------+---------------+------------+
| HIGHEST_SALARY | LOWEST_SALARY | DIFFERENCE |
+----------------+---------------+------------+
|           6050 |           968 |       5082 |
+----------------+---------------+------------+
1 row in set (0.002 sec)

------------------------------------------------------------------------
## Question 3

Employees whose commission > 25% of salary.

``` sql
SELECT *
FROM EMPLOYEE
WHERE COMM > SAL*0.25;
```

### Output
+-------+--------+----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+----------+------+------------+------+------+--------+
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250 | 1400 |     30 |
+-------+--------+----------+------+------------+------+------+--------+
1 row in set (0.000 sec)

------------------------------------------------------------------------
## Question 4

Display salary in dollar format.

``` sql
SELECT ENAME,
CONCAT('$',FORMAT(SAL,2)) AS SALARY_DOLLAR
FROM EMPLOYEE;
```

### Output
+--------+---------------+
| ENAME  | SALARY_DOLLAR |
+--------+---------------+
| SMITH  | $968.00       |
| ALLEN  | $1,600.00     |
| WARD   | $1,250.00     |
| JONES  | $3,600.00     |
| MARTIN | $1,250.00     |
| BLAKE  | $3,449.00     |
| CLARK  | $2,965.00     |
| SCOTT  | $3,630.00     |
| KING   | $6,050.00     |
| TURNER | $1,500.00     |
| ADAMS  | $1,331.00     |
| JAMES  | $1,150.00     |
| FORD   | $3,630.00     |
| MILLER | $1,573.00     |
+--------+---------------+
14 rows in set (0.003 sec)

------------------------------------------------------------------------
## Question 5

Matrix query showing job wise salary per department.

``` sql
SELECT JOB,
SUM(CASE WHEN DEPTNO=10 THEN SAL ELSE 0 END) AS DEPT10,
SUM(CASE WHEN DEPTNO=20 THEN SAL ELSE 0 END) AS DEPT20,
SUM(CASE WHEN DEPTNO=30 THEN SAL ELSE 0 END) AS DEPT30,
SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE
GROUP BY JOB;
```

### Output
+-----------+--------+--------+--------+--------------+
| JOB       | DEPT10 | DEPT20 | DEPT30 | TOTAL_SALARY |
+-----------+--------+--------+--------+--------------+
| ANALYST   |      0 |   3630 |      0 |         7260 |
| CLERK     |   1573 |   2299 |   1150 |         5022 |
| MANAGER   |      0 |   6565 |   3449 |        10014 |
| PRESIDENT |      0 |   6050 |      0 |         6050 |
| SALESMAN  |      0 |      0 |   5600 |         5600 |
+-----------+--------+--------+--------+--------------+
5 rows in set (0.002 sec)

------------------------------------------------------------------------
...
## Question 6

Total employees and hired in 1980-1983.

``` sql
SELECT
COUNT(*) AS TOTAL_EMP,
SUM(YEAR(HIREDATE)=1980) AS HIRED_1980,
SUM(YEAR(HIREDATE)=1981) AS HIRED_1981,
SUM(YEAR(HIREDATE)=1982) AS HIRED_1982,
SUM(YEAR(HIREDATE)=1983) AS HIRED_1983
FROM EMPLOYEE;
```

### Output
+-----------+------------+------------+------------+------------+
| TOTAL_EMP | HIRED_1980 | HIRED_1981 | HIRED_1982 | HIRED_1983 |
+-----------+------------+------------+------------+------------+
|        14 |          1 |         10 |          2 |          1 |
+-----------+------------+------------+------------+------------+
1 row in set (0.002 sec)


------------------------------------------------------------------------
## Question 7

Last Sunday of any month.

``` sql
SELECT LAST_DAY(CURDATE())
- INTERVAL (DAYOFWEEK(LAST_DAY(CURDATE()))-1) DAY
AS LAST_SUNDAY;
```

### Output
+-------------+
| LAST_SUNDAY |
+-------------+
| 2026-02-22  |
+-------------+
1 row in set (0.005 sec)

------------------------------------------------------------------------
## Question 8

Department numbers and total employees.

``` sql
SELECT DEPTNO,
COUNT(*) AS TOTAL_EMPLOYEES
FROM EMPLOYEE
GROUP BY DEPTNO;
```

### Output
+--------+-----------------+
| DEPTNO | TOTAL_EMPLOYEES |
+--------+-----------------+
|     10 |               1 |
|     20 |               6 |
|     30 |               6 |
|     40 |               1 |
+--------+-----------------+
4 rows in set (0.001 sec)

------------------------------------------------------------------------
## Question 9

Jobs and total employees in each job.

``` sql
SELECT JOB,
COUNT(*) AS TOTAL_EMP
FROM EMPLOYEE
GROUP BY JOB;
```

### Output
+-----------+-----------+
| JOB       | TOTAL_EMP |
+-----------+-----------+
| ANALYST   |         2 |
| CLERK     |         4 |
| MANAGER   |         3 |
| PRESIDENT |         1 |
| SALESMAN  |         4 |
+-----------+-----------+
5 rows in set (0.006 sec)

------------------------------------------------------------------------
## Question 10

Department numbers and total salary.

``` sql
SELECT DEPTNO,
SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE
GROUP BY DEPTNO;
```

### Output
+--------+--------------+
| DEPTNO | TOTAL_SALARY |
+--------+--------------+
|     10 |         1573 |
|     20 |        18544 |
|     30 |        10199 |
|     40 |         3630 |
+--------+--------------+
4 rows in set (0.006 sec)

------------------------------------------------------------------------
