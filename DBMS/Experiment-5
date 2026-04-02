# Experiment 5

## Aim

To perform aggregate functions and string functions on EMPLOYEE table.

------------------------------------------------------------------------

## Question 1

Display total number of employees.

``` sql
SELECT COUNT(*) AS TOTAL_EMPLOYEES
FROM EMPLOYEE;
```

### Output
+-----------------+
| TOTAL_EMPLOYEES |
+-----------------+
|              14 |
+-----------------+
1 row in set (0.003 sec)

------------------------------------------------------------------------

## Question 2

Display total salary paid.

``` sql
SELECT SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE;
```

### Output
+--------------+
| TOTAL_SALARY |
+--------------+
|        31368 |
+--------------+
1 row in set (0.001 sec)

------------------------------------------------------------------------

## Question 3

Display maximum salary.

``` sql
SELECT MAX(SAL) AS MAX_SALARY
FROM EMPLOYEE;
```

### Output
+------------+
| MAX_SALARY |
+------------+
|       5500 |
+------------+
1 row in set (0.002 sec)

------------------------------------------------------------------------

## Question 4

Display minimum salary.

``` sql
SELECT MIN(SAL) AS MIN_SALARY
FROM EMPLOYEE;
```

### Output
+------------+
| MIN_SALARY |
+------------+
|        880 |
+------------+
1 row in set (0.002 sec)

------------------------------------------------------------------------

## Question 5

Display average salary.

``` sql
SELECT AVG(SAL) AS AVG_SALARY
FROM EMPLOYEE;
```

### Output
+------------+
| AVG_SALARY |
+------------+
|  2240.5714 |
+------------+
1 row in set (0.001 sec)
------------------------------------------------------------------------

## Question 6

Display maximum salary of clerk.

``` sql
SELECT MAX(SAL)
FROM EMPLOYEE
WHERE JOB='CLERK';
```

### Output
+----------+
| MAX(SAL) |
+----------+
|     1430 |
+----------+
1 row in set (0.002 sec)
------------------------------------------------------------------------

## Question 7

Display maximum salary in dept 20.

``` sql
SELECT MAX(SAL)
FROM EMPLOYEE
WHERE DEPTNO=20;
```

### Output
+----------+
| MAX(SAL) |
+----------+
|     5500 |
+----------+
1 row in set (0.003 sec)
------------------------------------------------------------------------

## Question 8

Display minimum salary of salesman.

``` sql
SELECT MIN(SAL)
FROM EMPLOYEE
WHERE JOB='SALESMAN';
```

### Output
+----------+
| MIN(SAL) |
+----------+
|     1250 |
+----------+
1 row in set (0.002 sec)

------------------------------------------------------------------------

## Question 9

Display average salary of managers.

``` sql
SELECT AVG(SAL)
FROM EMPLOYEE
WHERE JOB='MANAGER';
```

### Output
+-----------+
| AVG(SAL)  |
+-----------+
| 3034.3333 |
+-----------+
1 row in set (0.002 sec)
------------------------------------------------------------------------

## Question 10

Display total salary of analyst in dept 40.

``` sql
SELECT SUM(SAL)
FROM EMPLOYEE
WHERE JOB='ANALYST' AND DEPTNO=40;
```

### Output
+----------+
| SUM(SAL) |
+----------+
|     3300 |
+----------+
1 row in set (0.003 sec)

------------------------------------------------------------------------

## Question 11

Names in uppercase.

``` sql
SELECT UPPER(ENAME) FROM EMPLOYEE;
```

### Output
+--------------+
| UPPER(ENAME) |
+--------------+
| SMITH        |
| ALLEN        |
| WARD         |
| JONES        |
| MARTIN       |
| BLAKE        |
| CLARK        |
| SCOTT        |
| KING         |
| TURNER       |
| ADAMS        |
| JAMES        |
| FORD         |
| MILLER       |
+--------------+
14 rows in set (0.001 sec)
------------------------------------------------------------------------

## Question 12

Names in lowercase.

``` sql
SELECT LOWER(ENAME) FROM EMPLOYEE;
```

### Output
+--------------+
| LOWER(ENAME) |
+--------------+
| smith        |
| allen        |
| ward         |
| jones        |
| martin       |
| blake        |
| clark        |
| scott        |
| king         |
| turner       |
| adams        |
| james        |
| ford         |
| miller       |
+--------------+
14 rows in set (0.001 sec)
------------------------------------------------------------------------

## Question 13

Names in proper case.

``` sql
SELECT CONCAT(UPPER(LEFT(ENAME,1)), LOWER(SUBSTRING(ENAME,2))) AS NAME_FORMATTED
FROM EMPLOYEE;
```

### Output
+----------------+
| NAME_FORMATTED |
+----------------+
| Smith          |
| Allen          |
| Ward           |
| Jones          |
| Martin         |
| Blake          |
| Clark          |
| Scott          |
| King           |
| Turner         |
| Adams          |
| James          |
| Ford           |
| Miller         |
+----------------+
14 rows in set (0.006 sec)
------------------------------------------------------------------------

## Question 14

Length of your name.

``` sql
SELECT LENGTH('TUSHAR SINGH');
```

### Output
+------------------------+
| LENGTH('TUSHAR SINGH') |
+------------------------+
|                     12 |
+------------------------+
1 row in set (0.000 sec)

------------------------------------------------------------------------

## Question 15

Length of all employee names.

``` sql
SELECT ENAME, LENGTH(ENAME)
FROM EMPLOYEE;
```

### Output
+--------+---------------+
| ENAME  | LENGTH(ENAME) |
+--------+---------------+
| SMITH  |             5 |
| ALLEN  |             5 |
| WARD   |             4 |
| JONES  |             5 |
| MARTIN |             6 |
| BLAKE  |             5 |
| CLARK  |             5 |
| SCOTT  |             5 |
| KING   |             4 |
| TURNER |             6 |
| ADAMS  |             5 |
| JAMES  |             5 |
| FORD   |             4 |
| MILLER |             6 |
+--------+---------------+
14 rows in set (0.001 sec)

------------------------------------------------------------------------
