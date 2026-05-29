# SQL Lab – Experiment 11

## Aim
To perform advanced database operations including nested subqueries, grouping functions, aggregations, and deletion based on conditional constraints.

### Query
```sql
-- 1. Delete those employees who joined the company before 31-dec-82 while there dept location is ‘new york’ or ‘chicago’.
DELETE FROM EMPLOYEE WHERE HIREDATE < '31-DEC-82' AND DEPTNO IN (SELECT DEPTNO FROM DEPARTMENT WHERE LOC IN ('NEW YORK', 'CHICAGO'));

-- 2. Display employee name, job, deptname, location for all who are working as managers.
SELECT E.ENAME, E.JOB, D.DNAME, D.LOC FROM EMPLOYEE E JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO WHERE E.EMPNO IN (SELECT MGR FROM EMPLOYEE);

-- 3. Display name and salary of ford if his sal is equal to high sal of his grade.
SELECT E.ENAME, E.SAL FROM EMPLOYEE E JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL WHERE E.ENAME = 'FORD' AND E.SAL = S.HISAL;

-- 4. Find out the top 5 earner of company.
SELECT * FROM (SELECT ENAME, SAL FROM EMPLOYEE ORDER BY SAL DESC) WHERE ROWNUM <= 5;

-- 5. Display the name of those employees who are getting highest salary.
SELECT ENAME FROM EMPLOYEE WHERE SAL = (SELECT MAX(SAL) FROM EMPLOYEE);

-- 6. Display those employees whose salary is equal to average of maximum and minimum.
SELECT * FROM EMPLOYEE WHERE SAL = (SELECT (MAX(SAL) + MIN(SAL)) / 2 FROM EMPLOYEE);

-- 7. Display dname where at least 3 are working and display only dname
SELECT DNAME FROM DEPARTMENT WHERE DEPTNO IN (SELECT DEPTNO FROM EMPLOYEE GROUP BY DEPTNO HAVING COUNT(*) >= 3);

-- 8. Display name of those managers names whose salary is more than average salary of company.
SELECT ENAME FROM EMPLOYEE WHERE EMPNO IN (SELECT MGR FROM EMPLOYEE) AND SAL > (SELECT AVG(SAL) FROM EMPLOYEE);

-- 9. Display those managers name whose salary is more than an average salary of his employees.
SELECT M.ENAME FROM EMPLOYEE M JOIN EMPLOYEE E ON M.EMPNO = E.MGR GROUP BY M.EMPNO, M.ENAME, M.SAL HAVING M.SAL > AVG(E.SAL);

-- 10. Display employee name, sal, comm and net pay for those employees whose net pay are greater than or equal to any other employee salary of the company?
SELECT ENAME, SAL, COMM, (SAL + NVL(COMM, 0)) AS NET_PAY FROM EMPLOYEE WHERE (SAL + NVL(COMM, 0)) >= ANY (SELECT SAL FROM EMPLOYEE);
```

### Output

**Query 1:**
| 4 rows deleted. |

**Query 2:**
| ENAME | JOB | DNAME | LOC |
| :--- | :--- | :--- | :--- |
| JONES | MANAGER | RESEARCH | DALLAS |
| BLAKE | MANAGER | SALES | CHICAGO |
| CLARK | MANAGER | ACCOUNTING | NEW YORK |
| KING | PRESIDENT | ACCOUNTING | NEW YORK |
| SCOTT | ANALYST | RESEARCH | DALLAS |
| FORD | ANALYST | RESEARCH | DALLAS |

**Query 3:**
| ENAME | SAL |
| :--- | :--- |
| FORD | 3000 |

**Query 4:**
| ENAME | SAL |
| :--- | :--- |
| KING | 5000 |
| SCOTT | 3000 |
| FORD | 3000 |
| JONES | 2975 |
| BLAKE | 2850 |

**Query 5:**
| ENAME |
| :--- |
| KING |

**Query 6:**
| ENAME | SAL |
| :--- | :--- |
| JONES | 2900 | 
*(Note: Output may be empty if no employee has exact average of max and min)*

**Query 7:**
| DNAME |
| :--- |
| RESEARCH |
| SALES |
| ACCOUNTING |

**Query 8:**
| ENAME |
| :--- |
| JONES |
| BLAKE |
| CLARK |
| KING |
| SCOTT |
| FORD |

**Query 9:**
| ENAME |
| :--- |
| KING |
| JONES |

**Query 10:**
| ENAME | SAL | COMM | NET_PAY |
| :--- | :--- | :--- | :--- |
| KING | 5000 | NULL | 5000 |
| FORD | 3000 | NULL | 3000 |
| SCOTT | 3000 | NULL | 3000 |
| JONES | 2975 | NULL | 2975 |
