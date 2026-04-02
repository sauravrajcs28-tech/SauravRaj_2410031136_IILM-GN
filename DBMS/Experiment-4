# Experiment 4

## Aim

To perform date conditions, string matching, salary calculations, and
update queries on EMPLOYEE table.

------------------------------------------------------------------------

## Question 1

Display employees who joined before 30-June-1980 or after 31-Dec-1981.

``` sql
SELECT * 
FROM EMPLOYEE
WHERE HIREDATE < '1980-06-30'
   OR HIREDATE > '1981-12-31';
```

### Output
+-------+--------+---------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+---------+------+------------+------+------+--------+
|  7788 | SCOTT  | ANALYST | 7566 | 1982-12-09 | 3630 | NULL |     40 |
|  7876 | ADAMS  | CLERK   | 7788 | 1983-01-12 | 1331 | NULL |     20 |
|  7934 | MILLER | CLERK   | 7782 | 1982-01-23 | 1573 | NULL |     10 |
+-------+--------+---------+------+------------+------+------+--------+
3 rows in set (0.002 sec)

------------------------------------------------------------------------

## Question 2

Display names of employees whose second alphabet is A.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE '_A%';
```

### Output
+--------+
| ENAME  |
+--------+
| WARD   |
| MARTIN |
| JAMES  |
+--------+
3 rows in set (0.003 sec)

------------------------------------------------------------------------

## Question 3

Display names of employees whose name is exactly five characters.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE LENGTH(ENAME) = 5;
```

### Output
+-------+
| ENAME |
+-------+
| SMITH |
| ALLEN |
| JONES |
| BLAKE |
| CLARK |
| SCOTT |
| ADAMS |
| JAMES |
+-------+
8 rows in set (0.001 sec)
------------------------------------------------------------------------

## Question 4

Display names of employees whose second alphabet is A.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE '_A%';
```

### Output
+--------+
| ENAME  |
+--------+
| WARD   |
| MARTIN |
| JAMES  |
+--------+
3 rows in set (0.001 sec)
------------------------------------------------------------------------

## Question 5

Display names of employees who are NOT salesman, clerk, or analyst.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB NOT IN ('SALESMAN','CLERK','ANALYST');
```

### Output
+-------+
| ENAME |
+-------+
| JONES |
| BLAKE |
| CLARK |
| KING  |
+-------+
4 rows in set (0.001 sec)

------------------------------------------------------------------------

## Question 6

Display employee name and annual salary. Highest salary first.

``` sql
SELECT ENAME, SAL*12 AS ANNUAL_SALARY
FROM EMPLOYEE
ORDER BY SAL DESC;
```

### Output
+--------+---------------+
| ENAME  | ANNUAL_SALARY |
+--------+---------------+
| KING   |         72600 |
| SCOTT  |         43560 |
| FORD   |         43560 |
| JONES  |         43200 |
| BLAKE  |         41388 |
| CLARK  |         35580 |
| ALLEN  |         19200 |
| MILLER |         18876 |
| TURNER |         18000 |
| ADAMS  |         15972 |
| MARTIN |         15000 |
| WARD   |         15000 |
| JAMES  |         13800 |
| SMITH  |         11616 |
+--------+---------------+
14 rows in set (0.002 sec)

------------------------------------------------------------------------

## Question 7

Display ENAME, SAL, HRA (15%), DA (10%), PF (5%), TOTALSAL.

``` sql
SELECT ENAME,
       SAL,
       SAL*0.15 AS HRA,
       SAL*0.10 AS DA,
       SAL*0.05 AS PF,
       (SAL + SAL*0.15 + SAL*0.10 - SAL*0.05) AS TOTALSAL
FROM EMPLOYEE
ORDER BY TOTALSAL;
```

### Output
+--------+------+--------+--------+--------+----------+
| ENAME  | SAL  | HRA    | DA     | PF     | TOTALSAL |
+--------+------+--------+--------+--------+----------+
| SMITH  |  968 | 145.20 |  96.80 |  48.40 |  1161.60 |
| JAMES  | 1150 | 172.50 | 115.00 |  57.50 |  1380.00 |
| WARD   | 1250 | 187.50 | 125.00 |  62.50 |  1500.00 |
| MARTIN | 1250 | 187.50 | 125.00 |  62.50 |  1500.00 |
| ADAMS  | 1331 | 199.65 | 133.10 |  66.55 |  1597.20 |
| TURNER | 1500 | 225.00 | 150.00 |  75.00 |  1800.00 |
| MILLER | 1573 | 235.95 | 157.30 |  78.65 |  1887.60 |
| ALLEN  | 1600 | 240.00 | 160.00 |  80.00 |  1920.00 |
| CLARK  | 2965 | 444.75 | 296.50 | 148.25 |  3558.00 |
| BLAKE  | 3449 | 517.35 | 344.90 | 172.45 |  4138.80 |
| JONES  | 3600 | 540.00 | 360.00 | 180.00 |  4320.00 |
| FORD   | 3630 | 544.50 | 363.00 | 181.50 |  4356.00 |
| SCOTT  | 3630 | 544.50 | 363.00 | 181.50 |  4356.00 |
| KING   | 6050 | 907.50 | 605.00 | 302.50 |  7260.00 |
+--------+------+--------+--------+--------+----------+
14 rows in set (0.003 sec)

------------------------------------------------------------------------

## Question 8

Increase salary by 10% for employees with NO commission.

``` sql
UPDATE EMPLOYEE
SET SAL = SAL + SAL*0.10
WHERE COMM IS NULL;
```

### Output
Query OK, 10 rows affected (0.007 sec)
Rows matched: 10  Changed: 10  Warnings: 0

------------------------------------------------------------------------

## Question 9

Display employees whose salary is more than 3000 after 20% increment.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE SAL*1.20 > 3000;
```

### Output
+-------+
| ENAME |
+-------+
| JONES |
| BLAKE |
| CLARK |
| SCOTT |
| KING  |
| FORD  |
+-------+
6 rows in set (0.002 sec)

------------------------------------------------------------------------

## Question 10

Display employees whose salary has at least 3 digits.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE LENGTH(SAL) >= 3;
```

### Output
+--------+
| ENAME  |
+--------+
| SMITH  |
| ALLEN  |
| WARD   |
| JONES  |
| MARTIN |
| BLAKE  |
| CLARK  |
| SCOTT  |
| KING   |
| TURNER |
| ADAMS  |
| JAMES  |
| FORD   |
| MILLER |
+--------+
14 rows in set (0.003 sec)

------------------------------------------------------------------------
