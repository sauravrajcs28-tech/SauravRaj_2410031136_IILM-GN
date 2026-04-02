# Employee & Department Table Creation with Constraints (With Output)

------------------------------------------------------------------------

## Create DEPARTMENT Table

``` sql
CREATE TABLE Department (
    DeptNo NUMBER(2) PRIMARY KEY,
    DName VARCHAR2(15) NOT NULL
);
```

### Output

Table created.

------------------------------------------------------------------------

## Create EMPLOYEE Table

``` sql
CREATE TABLE Employee (
    EmpNo NUMBER(4) PRIMARY KEY,
    EName VARCHAR2(20) NOT NULL,
    Job VARCHAR2(20),
    Mgr NUMBER(4),
    HireDate DATE,
    Sal NUMBER(10),
    Comm NUMBER(7,2),
    DeptNo NUMBER(2),
    CONSTRAINT fk_dept
    FOREIGN KEY (DeptNo)
    REFERENCES Department(DeptNo)
);
```

### Output

Table created.

------------------------------------------------------------------------

# Experiment -- DDL & DML Operations

## 1. Create Employee_Master table with data

``` sql
CREATE TABLE Employee_Master AS
SELECT * FROM Employee;
```

### Output

Table created. 14 rows inserted.

------------------------------------------------------------------------

## 2. Delete records where DeptNo = 10

``` sql
DELETE FROM Employee_Master
WHERE DeptNo = 10;
```

### Output

3 rows deleted.

------------------------------------------------------------------------

## 3. Update 10% increment in salary of DeptNo 20

``` sql
UPDATE Employee_Master
SET Sal = Sal + (Sal * 0.10)
WHERE DeptNo = 20;
```

### Output

5 rows updated.

------------------------------------------------------------------------

## 4. Modify SAL datatype to NUMBER(10,2)

``` sql
ALTER TABLE Employee_Master
MODIFY Sal NUMBER(10,2);
```

### Output

Table altered.

------------------------------------------------------------------------

## 5. Drop Employee_Master Table

``` sql
DROP TABLE Employee_Master;
```

### Output

Table dropped.

------------------------------------------------------------------------

# End of Experiment
