# Experiment -- Retrieving Data from Employee Table

------------------------------------------------------------------------

## 1. List all distinct jobs in Employee

``` sql
SELECT DISTINCT Job FROM Employee;
```

### Output
+-----------+
| Job       |
+-----------+
| CLERK     |
| SALESMAN  |
| MANAGER   |
| ANALYST   |
| PRESIDENT |
+-----------+
5 rows in set (0.003 sec)

------------------------------------------------------------------------

## 2. List all information about employee in Department 30

``` sql
SELECT * FROM Employee
WHERE DeptNo = 30;
```

### Output (Sample)
+-------+--------+----------+------+------------+------+------+--------+
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+--------+----------+------+------------+------+------+--------+
|  7499 | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600 |  300 |     30 |
|  7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250 |  300 |     30 |
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250 | 1400 |     30 |
|  7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 3449 | NULL |     30 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500 |    0 |     30 |
|  7900 | JAMES  | CLERK    | 7698 | 1981-12-03 | 1150 | NULL |     30 |
+-------+--------+----------+------+------------+------+------+--------+
6 rows in set (0.002 sec)

------------------------------------------------------------------------

## 3. Find department numbers greater than 20

``` sql
SELECT DeptNo FROM Employee
WHERE DeptNo > 20;
```

### Output
+--------+
| DeptNo |
+--------+
|     30 |
|     30 |
|     30 |
|     30 |
|     30 |
|     30 |
|     40 |
+--------+
7 rows in set (0.002 sec)

------------------------------------------------------------------------

## 4. Managers and Clerks in Department 30

``` sql
SELECT * FROM Employee
WHERE DeptNo = 30
AND Job IN ('MANAGER','CLERK');
```

### Output
+-------+-------+---------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+---------+------+------------+------+------+--------+
|  7698 | BLAKE | MANAGER | 7839 | 1981-05-01 | 3449 | NULL |     30 |
|  7900 | JAMES | CLERK   | 7698 | 1981-12-03 | 1150 | NULL |     30 |
+-------+-------+---------+------+------------+------+------+--------+
2 rows in set (0.001 sec)

------------------------------------------------------------------------

## 5. Employee name, number and department of all clerks

``` sql
SELECT EmpNo, EName, DeptNo
FROM Employee
WHERE Job = 'CLERK';
```

### Output
+-------+--------+--------+
| EmpNo | EName  | DeptNo |
+-------+--------+--------+
|  7369 | SMITH  |     20 |
|  7876 | ADAMS  |     20 |
|  7900 | JAMES  |     30 |
|  7934 | MILLER |     10 |
+-------+--------+--------+
4 rows in set (0.001 sec)

------------------------------------------------------------------------

## 6. Managers not in Department 30

``` sql
SELECT * FROM Employee
WHERE Job = 'MANAGER'
AND DeptNo <> 30;
```

### Output
+-------+-------+---------+------+------------+------+------+--------+
| EMPNO | ENAME | JOB     | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |
+-------+-------+---------+------+------------+------+------+--------+
|  7566 | JONES | MANAGER | 7839 | 1981-04-02 | 3600 | NULL |     20 |
|  7782 | CLARK | MANAGER | 7839 | 1981-06-09 | 2965 | NULL |     20 |
+-------+-------+---------+------+------------+------+------+--------+
2 rows in set (0.001 sec)

------------------------------------------------------------------------

## 7. Employees in Dept 10 who are not Manager or Clerk

``` sql
SELECT * FROM Employee
WHERE DeptNo = 10
AND Job NOT IN ('MANAGER','CLERK');
```

### Output
Empty set (0.001 sec)

------------------------------------------------------------------------

## 8. Employees and jobs earning between 1200 and 1400

``` sql
SELECT EName, Job
FROM Employee
WHERE Sal BETWEEN 1200 AND 1400;
```

### Output
+--------+----------+
| EName  | Job      |
+--------+----------+
| WARD   | SALESMAN |
| MARTIN | SALESMAN |
| ADAMS  | CLERK    |
+--------+----------+
3 rows in set (0.001 sec)

------------------------------------------------------------------------

## 9. Name and DeptNo of Clerks, Analysts or Salesman

``` sql
SELECT EName, DeptNo
FROM Employee
WHERE Job IN ('CLERK','ANALYST','SALESMAN');
```

### Output (Sample)
+--------+--------+
| EName  | DeptNo |
+--------+--------+
| SMITH  |     20 |
| ALLEN  |     30 |
| WARD   |     30 |
| MARTIN |     30 |
| SCOTT  |     40 |
| TURNER |     30 |
| ADAMS  |     20 |
| JAMES  |     30 |
| FORD   |     20 |
| MILLER |     10 |
+--------+--------+
10 rows in set (0.001 sec)

------------------------------------------------------------------------

## 10. Name and DeptNo of employees whose names begin with M

``` sql
SELECT EName, DeptNo
FROM Employee
WHERE EName LIKE 'M%';
```
### Output
+--------+--------+
| EName  | DeptNo |
+--------+--------+
| MARTIN |     30 |
| MILLER |     10 |
+--------+--------+
2 rows in set (0.001 sec)

------------------------------------------------------------------------

# End of Retrieval Queries
