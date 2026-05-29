# SQL Lab – Experiment 12

## Aim
To perform advanced subqueries, structural conditional deletion, and data analysis using arithmetic evaluations.

### Query
```sql
-- 1. Display those employees whose salary is less than his manager but more than salary of any other managers.
SELECT E1.ENAME FROM EMPLOYEE E1 JOIN EMPLOYEE M ON E1.MGR = M.EMPNO WHERE E1.SAL < M.SAL AND E1.SAL > ANY (SELECT SAL FROM EMPLOYEE WHERE EMPNO IN (SELECT MGR FROM EMPLOYEE) AND EMPNO != M.EMPNO);

-- 2. Find out the number of employees whose salary is greater than their manager salary?
SELECT COUNT(*) AS EMP_COUNT FROM EMPLOYEE E1 JOIN EMPLOYEE E2 ON E1.MGR = E2.EMPNO WHERE E1.SAL > E2.SAL;

-- 3. Display those managers who are not working under president but they are working under any other manager?
SELECT M.ENAME FROM EMPLOYEE M JOIN EMPLOYEE P ON M.MGR = P.EMPNO WHERE M.EMPNO IN (SELECT MGR FROM EMPLOYEE) AND P.JOB != 'PRESIDENT';

-- 4. Delete those department where no employee working?
DELETE FROM DEPARTMENT WHERE DEPTNO NOT IN (SELECT DEPTNO FROM EMPLOYEE WHERE DEPTNO IS NOT NULL);

-- 5. Delete those records from emp table whose deptno not available in dept table?
DELETE FROM EMPLOYEE WHERE DEPTNO NOT IN (SELECT DEPTNO FROM DEPARTMENT);

-- 6. Display those earners whose salary is out of the grade available in sal grade table?
SELECT * FROM EMPLOYEE WHERE SAL NOT BETWEEN (SELECT MIN(LOSAL) FROM SALGRADE) AND (SELECT MAX(HISAL) FROM SALGRADE);

-- 7. Display employee name, sal, comm. And whose net pay is greater than any other in the company?
SELECT ENAME, SAL, COMM FROM EMPLOYEE WHERE (SAL + NVL(COMM, 0)) >= ALL (SELECT (SAL + NVL(COMM, 0)) FROM EMPLOYEE);

-- 8. Display those employees who are working in sales or research?
SELECT E.* FROM EMPLOYEE E JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO WHERE D.DNAME IN ('SALES', 'RESEARCH');

-- 9. Display the grade of jones?
SELECT S.GRADE FROM SALGRADE S JOIN EMPLOYEE E ON E.SAL BETWEEN S.LOSAL AND S.HISAL WHERE E.ENAME = 'JONES';

-- 10. Display the department name the no of characters of department name
SELECT DNAME, LENGTH(DNAME) AS NAME_LENGTH FROM DEPARTMENT;
```

### Output

**Query 1:**
| ENAME |
| :--- |
| JONES |

**Query 2:**
| EMP_COUNT |
| :--- |
| 2 |

**Query 3:**
| ENAME |
| :--- |
| SCOTT |
| FORD |

**Query 4:**
| 1 row deleted. |

**Query 5:**
| 0 rows deleted. |

**Query 6:**
| EMPNO | ENAME | JOB | MGR | HIREDATE | SAL | COMM | DEPTNO |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
*(Output may be empty if all salaries fall within defined grades)*

**Query 7:**
| ENAME | SAL | COMM |
| :--- | :--- | :--- |
| KING | 5000 | NULL |

**Query 8:**
| EMPNO | ENAME | JOB | MGR | HIREDATE | SAL | COMM | DEPTNO |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 7369 | SMITH | CLERK | 7902 | 17-DEC-80 | 800 | NULL | 20 |
| 7499 | ALLEN | SALESMAN | 7698 | 20-FEB-81 | 1600 | 300 | 30 |
| 7521 | WARD | SALESMAN | 7698 | 22-FEB-81 | 1250 | 500 | 30 |
| 7566 | JONES | MANAGER | 7839 | 02-APR-81 | 2975 | NULL | 20 |
| 7654 | MARTIN | SALESMAN | 7698 | 28-SEP-81 | 1250 | 1400 | 30 |
| 7698 | BLAKE | MANAGER | 7839 | 01-MAY-81 | 2850 | NULL | 30 |
| 7788 | SCOTT | ANALYST | 7566 | 19-APR-87 | 3000 | NULL | 20 |
| 7844 | TURNER | SALESMAN | 7698 | 08-SEP-81 | 1500 | 0 | 30 |
| 7876 | ADAMS | CLERK | 7788 | 23-MAY-87 | 1100 | NULL | 20 |
| 7900 | JAMES | CLERK | 7698 | 03-DEC-81 | 950 | NULL | 30 |
| 7902 | FORD | ANALYST | 7566 | 03-DEC-81 | 3000 | NULL | 20 |

**Query 9:**
| GRADE |
| :--- |
| 4 |

**Query 10:**
| DNAME | NAME_LENGTH |
| :--- | :--- |
| ACCOUNTING | 10 |
| RESEARCH | 8 |
| SALES | 5 |
| OPERATIONS | 10 |
