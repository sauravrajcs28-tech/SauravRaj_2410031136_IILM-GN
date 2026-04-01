# Experiment-6

## Aim

To perform date functions, DECODE function, and advanced queries on
EMPLOYEE table.

------------------------------------------------------------------------

## Question 1

Display empno, ename, dept name using DECODE.

``` sql
SELECT EMPNO, ENAME,
DECODE(DEPTNO,
10,'ACCOUNTING',
20,'RESEARCH',
30,'SALES',
40,'OPERATIONS') AS DEPARTMENT
FROM EMPLOYEE;
```

### Output
+-------+--------+------------+
| EMPNO | ENAME  | DEPARTMENT |
+-------+--------+------------+
|  7369 | SMITH  | RESEARCH   |
|  7499 | ALLEN  | SALES      |
|  7521 | WARD   | SALES      |
|  7566 | JONES  | RESEARCH   |
|  7654 | MARTIN | SALES      |
|  7698 | BLAKE  | SALES      |
|  7782 | CLARK  | RESEARCH   |
|  7788 | SCOTT  | OPERATIONS |
|  7839 | KING   | RESEARCH   |
|  7844 | TURNER | SALES      |
|  7876 | ADAMS  | RESEARCH   |
|  7900 | JAMES  | SALES      |
|  7902 | FORD   | RESEARCH   |
|  7934 | MILLER | ACCOUNTING |
+-------+--------+------------+
14 rows in set (0.003 sec)

------------------------------------------------------------------------

## Question 2

Display your age in days.

``` sql
SELECT DATEDIFF(CURDATE(),'2006-01-18') AS AGE_DAYS;
```

### Output
+----------+
| AGE_DAYS |
+----------+
|     7343 |
+----------+
1 row in set (0.000 sec)

------------------------------------------------------------------------

## Question 3

Display your age in months.

``` sql
SELECT TIMESTAMPDIFF(MONTH,'2006-01-18',CURDATE()) AS AGE_MONTHS;
```

### Output
+------------+
| AGE_MONTHS |
+------------+
|        241 |
+------------+
1 row in set (0.000 sec)
------------------------------------------------------------------------

## Question 4

Display formatted current date.

``` sql
SELECT DATE_FORMAT(NOW(),'%D %M %W %Y');
```

### Output

24th February Tuesday 2026

------------------------------------------------------------------------

## Question 5

Display hire message for each employee.

``` sql
SELECT CONCAT(ENAME,' has joined on ',HIREDATE)
FROM EMPLOYEE;
```
### Output
+------------------------------------------+
| CONCAT(ENAME,' has joined on ',HIREDATE) |
+------------------------------------------+
| SMITH has joined on 1980-12-17           |
| ALLEN has joined on 1981-02-20           |
| WARD has joined on 1981-02-22            |
| JONES has joined on 1981-04-02           |
| MARTIN has joined on 1981-09-28          |
| BLAKE has joined on 1981-05-01           |
| CLARK has joined on 1981-06-09           |
| SCOTT has joined on 1982-12-09           |
| KING has joined on 1981-11-17            |
| TURNER has joined on 1981-09-08          |
| ADAMS has joined on 1983-01-12           |
| JAMES has joined on 1981-12-03           |
| FORD has joined on 1981-12-03            |
| MILLER has joined on 1982-01-23          |
+------------------------------------------+
14 rows in set (0.002 sec)

------------------------------------------------------------------------

## Question 6

Scott joined message.

``` sql
SELECT CONCAT('Scott has joined on ',HIREDATE)
FROM EMPLOYEE
WHERE ENAME='SCOTT';
```
### Output
+-----------------------------------------+
| CONCAT('Scott has joined on ',HIREDATE) |
+-----------------------------------------+
| Scott has joined on 1982-12-09          |
+-----------------------------------------+
------------------------------------------------------------------------

## Question 7

Nearest Saturday after current date.

``` sql
SELECT NEXT_DAY(CURDATE(),'SATURDAY');
```

### Output
28-02-2026
------------------------------------------------------------------------

## Question 8

Display current time.

``` sql
SELECT CURTIME();
```
### Output
14:42:15

------------------------------------------------------------------------

## Question 9

Date three months before today.

``` sql
SELECT DATE_SUB(CURDATE(),INTERVAL 3 MONTH);
```
### Output
25-Nov-2025

------------------------------------------------------------------------

## Question 10

Employees joined in December.

``` sql
SELECT *
FROM EMPLOYEE
WHERE MONTH(HIREDATE)=12;
```
### Output
+-------+-------+---------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+---------+------+------------+------+------+--------+
|  7369 | SMITH | CLERK   | 7902 | 1980-12-17 |  880 | NULL |     20 |
|  7788 | SCOTT | ANALYST | 7566 | 1982-12-09 | 3300 | NULL |     40 |
|  7900 | JAMES | CLERK   | 7698 | 1981-12-03 | 1045 | NULL |     30 |
|  7902 | FORD  | ANALYST | 7566 | 1981-12-03 | 3300 | NULL |     20 |
+-------+-------+---------+------+------------+------+------+--------+
4 rows in set (0.012 sec)
------------------------------------------------------------------------

## Question 11

First 2 chars hiredate - last 2 salary.

``` sql
SELECT *
FROM EMPLOYEE
WHERE LEFT(HIREDATE,2)=RIGHT(SAL,2);
```
### Output
Empty set (0.003 sec)
------------------------------------------------------------------------

## Question 12

10% salary equal joining year.

``` sql
SELECT *
FROM EMPLOYEE
WHERE SAL*0.10 = YEAR(HIREDATE);
```
### Output
Empty set (0.002 sec)

------------------------------------------------------------------------

## Question 13

Employees joined before 15th month.

``` sql
SELECT *
FROM EMPLOYEE
WHERE HIREDATE <= DATE_SUB(
    (SELECT MAX(HIREDATE) FROM EMPLOYEE),
    INTERVAL 15 MONTH
);
```
### Output
+-------+--------+----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+----------+------+------------+------+------+--------+
|  7369 | SMITH  | CLERK    | 7902 | 1980-12-17 |  880 | NULL |     20 |
|  7499 | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600 |  300 |     30 |
|  7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250 |  300 |     30 |
|  7566 | JONES  | MANAGER  | 7839 | 1981-04-02 | 3273 | NULL |     20 |
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250 | 1400 |     30 |
|  7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 3135 | NULL |     30 |
|  7782 | CLARK  | MANAGER  | 7839 | 1981-06-09 | 2695 | NULL |     20 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500 |    0 |     30 |
+-------+--------+----------+------+------------+------+------+--------+


------------------------------------------------------------------------

## Question 14

Employees joined before 15th of month.

``` sql
SELECT *
FROM EMPLOYEE
WHERE DAY(HIREDATE) < 15;
```
### Output
+-------+--------+----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+----------+------+------------+------+------+--------+
|  7566 | JONES  | MANAGER  | 7839 | 1981-04-02 | 3273 | NULL |     20 |
|  7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 3135 | NULL |     30 |
|  7782 | CLARK  | MANAGER  | 7839 | 1981-06-09 | 2695 | NULL |     20 |
|  7788 | SCOTT  | ANALYST  | 7566 | 1982-12-09 | 3300 | NULL |     40 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500 |    0 |     30 |
|  7876 | ADAMS  | CLERK    | 7788 | 1983-01-12 | 1210 | NULL |     20 |
|  7900 | JAMES  | CLERK    | 7698 | 1981-12-03 | 1045 | NULL |     30 |
|  7902 | FORD   | ANALYST  | 7566 | 1981-12-03 | 3300 | NULL |     20 |
+-------+--------+----------+------+------------+------+------+--------+
8 rows in set (0.002 sec)


------------------------------------------------------------------------

## Question 15

Employees whose joining date available in deptno.

``` sql
SELECT *
FROM EMPLOYEE
WHERE HIREDATE IS NOT NULL
AND DEPTNO IS NOT NULL;
```
### Output
+-------+--------+-----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+-----------+------+------------+------+------+--------+
|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  880 | NULL |     20 |
|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 |  300 |     30 |
|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 |  300 |     30 |
|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 3273 | NULL |     20 |
|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 |     30 |
|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 3135 | NULL |     30 |
|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2695 | NULL |     20 |
|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3300 | NULL |     40 |
|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5500 | NULL |     20 |
|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 |    0 |     30 |
|  7876 | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1210 | NULL |     20 |
|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 | 1045 | NULL |     30 |
|  7902 | FORD   | ANALYST   | 7566 | 1981-12-03 | 3300 | NULL |     20 |
|  7934 | MILLER | CLERK     | 7782 | 1982-01-23 | 1430 | NULL |     10 |
+-------+--------+-----------+------+------------+------+------+--------+
14 rows in set (0.003 sec)



------------------------------------------------------------------------
