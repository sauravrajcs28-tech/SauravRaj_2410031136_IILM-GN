# SQL Lab – Experiment 9

## Aim
To use subqueries and nested queries to retrieve data based on dynamic conditions and filtering criteria.

### Query
```sql
-- 1. Find the name of all employees who earn more than the average salary
SELECT ENAME, SAL FROM EMPLOYEE WHERE SAL > (SELECT AVG(SAL) FROM EMPLOYEE);

-- 2. Find the name of all employees who earn the highest salary in their department
SELECT ENAME, DEPTNO, SAL FROM EMPLOYEE WHERE (DEPTNO, SAL) IN (SELECT DEPTNO, MAX(SAL) FROM EMPLOYEE GROUP BY DEPTNO);

-- 3. Find the name of all employees who are managers (their EMPNO is listed in the MGR column)
SELECT ENAME FROM EMPLOYEE WHERE EMPNO IN (SELECT DISTINCT MGR FROM EMPLOYEE WHERE MGR IS NOT NULL);

-- 4. Find the name of all employees who work in 'ACCOUNTING' (Using subquery)
SELECT ENAME FROM EMPLOYEE WHERE DEPTNO = (SELECT DEPTNO FROM DEPARTMENT WHERE DNAME = 'ACCOUNTING');

-- 5. Find the name of all employees whose salary is greater than the average salary of their department
SELECT ENAME, DEPTNO, SAL FROM EMPLOYEE E WHERE SAL > (SELECT AVG(SAL) FROM EMPLOYEE WHERE DEPTNO = E.DEPTNO);
```

### Output
**Query 1 (More than Avg):**
| ENAME | SAL |
| :--- | :--- |
| JONES | 2975 |
| BLAKE | 2850 |
| CLARK | 2450 |
| SCOTT | 3000 |
| KING | 5000 |
| FORD | 3000 |

**Query 2 (Highest in Dept):**
| ENAME | DEPTNO | SAL |
| :--- | :--- | :--- |
| KING | 10 | 5000 |
| SCOTT | 20 | 3000 |
| FORD | 20 | 3000 |
| BLAKE | 30 | 2850 |

**Query 3 (All Managers):**
| ENAME |
| :--- |
| JONES |
| BLAKE |
| CLARK |
| SCOTT |
| KING |
| FORD |
