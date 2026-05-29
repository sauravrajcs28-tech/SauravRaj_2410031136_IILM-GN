# SQL Lab – Experiment 10

## Aim
To execute complex queries involving aggregate functions, subqueries (`ANY`, `ALL`), and multi-table joins.

### Query
```sql
-- 1. Display the names of employees from department number 10 with salary greater than that of any employee working in other departments.
SELECT ENAME FROM EMPLOYEE WHERE DEPTNO = 10 AND SAL > ANY (SELECT SAL FROM EMPLOYEE WHERE DEPTNO != 10);

-- 2. Display the names of employee from department number 10 with salary greater than that of all employee working in other departments.
SELECT ENAME FROM EMPLOYEE WHERE DEPTNO = 10 AND SAL > ALL (SELECT SAL FROM EMPLOYEE WHERE DEPTNO != 10);

-- 3. Display the details of employees who are in sales dept and grade is 3.
SELECT E.* FROM EMPLOYEE E JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL WHERE D.DNAME = 'SALES' AND S.GRADE = 3;

-- 4. Display those who are not managers and who are managers anyone.
SELECT * FROM EMPLOYEE WHERE JOB != 'MANAGER' AND EMPNO IN (SELECT MGR FROM EMPLOYEE);

-- 5. Display those employees whose manager name is jones.
SELECT * FROM EMPLOYEE WHERE MGR = (SELECT EMPNO FROM EMPLOYEE WHERE ENAME = 'JONES');

-- 6. Display ename who are working in sales dept.
SELECT ENAME FROM EMPLOYEE WHERE DEPTNO = (SELECT DEPTNO FROM DEPARTMENT WHERE DNAME = 'SALES');

-- 7. Display employee name, deptname, salary and comm. For those sal in between 2000 to 5000 while location is chicago.
SELECT E.ENAME, D.DNAME, E.SAL, E.COMM FROM EMPLOYEE E JOIN DEPARTMENT D ON E.DEPTNO = D.DEPTNO WHERE E.SAL BETWEEN 2000 AND 5000 AND D.LOC = 'CHICAGO';

-- 8. Display those employees whose salary greater than his manager salary.
SELECT E1.ENAME FROM EMPLOYEE E1 JOIN EMPLOYEE E2 ON E1.MGR = E2.EMPNO WHERE E1.SAL > E2.SAL;

-- 9. Display those employees who are working in the same dept where his manager is working.
SELECT E1.ENAME FROM EMPLOYEE E1 JOIN EMPLOYEE E2 ON E1.MGR = E2.EMPNO WHERE E1.DEPTNO = E2.DEPTNO;

-- 10. Display grade and employees name for the dept no 10 or 30 but grade is not 4, while joined the company before 31-dec-82.
SELECT S.GRADE, E.ENAME FROM EMPLOYEE E JOIN SALGRADE S ON E.SAL BETWEEN S.LOSAL AND S.HISAL WHERE E.DEPTNO IN (10, 30) AND S.GRADE != 4 AND E.HIREDATE < '31-DEC-82';
```

### Output

**Query 1:**
| ENAME |
| :--- |
| CLARK |
| KING |

**Query 2:**
| ENAME |
| :--- |
| KING |

**Query 3:**
| EMPNO | ENAME | JOB | MGR | HIREDATE | SAL | COMM | DEPTNO |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 7499 | ALLEN | SALESMAN | 7698 | 20-FEB-81 | 1600 | 300 | 30 |
| 7844 | TURNER | SALESMAN | 7698 | 08-SEP-81 | 1500 | 0 | 30 |

**Query 4:**
| EMPNO | ENAME | JOB | MGR | HIREDATE | SAL | COMM | DEPTNO |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 7788 | SCOTT | ANALYST | 7566 | 19-APR-87 | 3000 | NULL | 20 |
| 7902 | FORD | ANALYST | 7566 | 03-DEC-81 | 3000 | NULL | 20 |
| 7839 | KING | PRESIDENT | NULL | 17-NOV-81 | 5000 | NULL | 10 |

**Query 5:**
| EMPNO | ENAME | JOB | MGR | HIREDATE | SAL | COMM | DEPTNO |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 7788 | SCOTT | ANALYST | 7566 | 19-APR-87 | 3000 | NULL | 20 |
| 7902 | FORD | ANALYST | 7566 | 03-DEC-81 | 3000 | NULL | 20 |

**Query 6:**
| ENAME |
| :--- |
| ALLEN |
| WARD |
| MARTIN |
| BLAKE |
| TURNER |
| JAMES |

**Query 7:**
| ENAME | DNAME | SAL | COMM |
| :--- | :--- | :--- | :--- |
| BLAKE | SALES | 2850 | NULL |

**Query 8:**
| ENAME |
| :--- |
| SCOTT |
| FORD |

**Query 9:**
| ENAME |
| :--- |
| SMITH |
| ALLEN |
| WARD |
| MARTIN |
| TURNER |
| JAMES |
| ADAMS |
| MILLER |

**Query 10:**
| GRADE | ENAME |
| :--- | :--- |
| 5 | KING |
| 3 | TURNER |
| 2 | JAMES |
