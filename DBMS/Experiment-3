# Experiment 3

## Aim

To perform sorting, pattern matching, logical operators, and
salary-based queries on EMPLOYEE table.

------------------------------------------------------------------------

## Question 1

List all employees and jobs in Department 30 in descending order by
salary.

``` sql
SELECT ENAME, JOB, SAL
FROM EMPLOYEE
WHERE DEPTNO = 30
ORDER BY SAL DESC;
```

### Output
+--------+----------+------+
| ENAME  | JOB      | SAL  |
+--------+----------+------+
| BLAKE  | MANAGER  | 3449 |
| ALLEN  | SALESMAN | 1600 |
| TURNER | SALESMAN | 1500 |
| WARD   | SALESMAN | 1250 |
| MARTIN | SALESMAN | 1250 |
| JAMES  | CLERK    | 1150 |
+--------+----------+------+
6 rows in set (0.001 sec)

------------------------------------------------------------------------

## Question 2

List job and Department Number of employees whose name are five letters
long begin with "A" and end with "N".

``` sql
SELECT JOB, DEPTNO
FROM EMPLOYEE
WHERE ENAME LIKE 'A___N';
```

### Output
+----------+--------+
| JOB      | DEPTNO |
+----------+--------+
| SALESMAN |     30 |
+----------+--------+
1 row in set (0.002 sec)
------------------------------------------------------------------------

## Question 3

Display the name of employees whose name start with alphabet S.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE 'S%';
```

### Output
+-------+
| ENAME |
+-------+
| SMITH |
| SCOTT |
+-------+
2 rows in set (0.001 sec)

------------------------------------------------------------------------

## Question 4

Display the names of employees whose name ends with alphabet S.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE '%S';
```

### Output
+-------+
| ENAME |
+-------+
| JONES |
| ADAMS |
| JAMES |
+-------+
3 rows in set (0.001 sec)

------------------------------------------------------------------------

## Question 5

Display names of employees working in department 10, 20, 40 or working
as clerks, salesman or analyst.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE DEPTNO IN (10,20,40)
   OR JOB IN ('CLERK','SALESMAN','ANALYST');
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
| CLARK  |
| SCOTT  |
| KING   |
| TURNER |
| ADAMS  |
| JAMES  |
| FORD   |
| MILLER |
+--------+
13 rows in set (0.001 sec)

------------------------------------------------------------------------

## Question 6

Display employee number and names for employees who earn commission.

``` sql
SELECT EMPNO, ENAME
FROM EMPLOYEE
WHERE COMM IS NOT NULL;
```

### Output
+-------+--------+
| EMPNO | ENAME  |
+-------+--------+
|  7499 | ALLEN  |
|  7521 | WARD   |
|  7654 | MARTIN |
|  7844 | TURNER |
+-------+--------+
4 rows in set (0.001 sec)

------------------------------------------------------------------------

## Question 7

Display employee number and total salary for each employee.

``` sql
SELECT EMPNO, SAL + IFNULL(COMM,0) AS TOTAL_SALARY
FROM EMPLOYEE;
```

### Output
+-------+--------------+
| EMPNO | TOTAL_SALARY |
+-------+--------------+
|  7369 |          968 |
|  7499 |         1900 |
|  7521 |         1550 |
|  7566 |         3600 |
|  7654 |         2650 |
|  7698 |         3449 |
|  7782 |         2965 |
|  7788 |         3630 |
|  7839 |         6050 |
|  7844 |         1500 |
|  7876 |         1331 |
|  7900 |         1150 |
|  7902 |         3630 |
|  7934 |         1573 |
+-------+--------------+
14 rows in set (0.001 sec)
------------------------------------------------------------------------

## Question 8

Display employee number and annual salary for each employee.

``` sql
SELECT EMPNO, SAL*12 AS ANNUAL_SALARY
FROM EMPLOYEE;
```

### Output
+-------+---------------+
| EMPNO | ANNUAL_SALARY |
+-------+---------------+
|  7369 |         11616 |
|  7499 |         19200 |
|  7521 |         15000 |
|  7566 |         43200 |
|  7654 |         15000 |
|  7698 |         41388 |
|  7782 |         35580 |
|  7788 |         43560 |
|  7839 |         72600 |
|  7844 |         18000 |
|  7876 |         15972 |
|  7900 |         13800 |
|  7902 |         43560 |
|  7934 |         18876 |
+-------+---------------+
14 rows in set (0.001 sec)

------------------------------------------------------------------------

## Question 9

Display names of all employees working as clerks and drawing salary more
than 3000.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB='CLERK'
AND SAL > 3000;
```

### Output
Empty set (0.001 sec)

------------------------------------------------------------------------

## Question 10

Display names of employees working as clerk, salesman or analyst and
drawing salary more than 3000.

``` sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB IN ('CLERK','SALESMAN','ANALYST')
AND SAL > 3000;
```

### Output
+-------+
| ENAME |
+-------+
| SCOTT |
| FORD  |
+-------+
2 rows in set (0.002 sec)
------------------------------------------------------------------------
