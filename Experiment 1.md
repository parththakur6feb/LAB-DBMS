# Experiment 1

## Aim
To create tables with given constraints, insert data, and perform basic SQL operations like create, delete, update, alter, and drop.

---

## Theory
A Database Management System (DBMS) allows users to define, create, maintain, and control access to databases. SQL (Structured Query Language) is used to perform operations on databases.

In this experiment:
- Tables are created using constraints like PRIMARY KEY, FOREIGN KEY, and NOT NULL.
- Data is inserted into tables.
- Various SQL commands such as CREATE, DELETE, UPDATE, ALTER, and DROP are used.

---

## Experiment Questions
1. Create EMPLOYEE and DEPARTMENT tables with given constraints.
2. Insert given values into both tables.
3. Create EMPLOYEE_MASTER table from EMPLOYEE.
4. Delete records from EMPLOYEE_MASTER where DEPTNO = 10.
5. Update salary by 10% for employees in DEPTNO = 20.
6. Alter SAL column datatype.
7. Drop EMPLOYEE_MASTER table.

---

## Queries

### 1. Create DEPARTMENT Table
```sql
CREATE TABLE DEPARTMENT (
    DEPTNO NUMBER(2) PRIMARY KEY,
    DNAME VARCHAR2(15) NOT NULL
);
```

### 2. Create EMPLOYEE Table
```sql
CREATE TABLE EMPLOYEE (
    EMPNO NUMBER(4) PRIMARY KEY,
    ENAME VARCHAR2(20) NOT NULL,
    JOB VARCHAR2(20),
    MGR NUMBER(4),
    HIREDATE DATE,
    SAL NUMBER(10),
    COMM NUMBER(7),
    DEPTNO NUMBER(2),
    FOREIGN KEY (DEPTNO) REFERENCES DEPARTMENT(DEPTNO)
);
```

### 3. Insert Values into DEPARTMENT
```sql
INSERT INTO DEPARTMENT VALUES (10, 'RESEARCH');
INSERT INTO DEPARTMENT VALUES (20, 'ACCOUNTING');
INSERT INTO DEPARTMENT VALUES (30, 'SALES');
INSERT INTO DEPARTMENT VALUES (40, 'OPERATIONS');
```

### 4. Create EMPLOYEE_MASTER Table
```sql
CREATE TABLE EMPLOYEE_MASTER AS
SELECT * FROM EMPLOYEE;
```

### 5. Delete Records
```sql
DELETE FROM EMPLOYEE_MASTER
WHERE DEPTNO = 10;
```

### 6. Update Salary
```sql
UPDATE EMPLOYEE_MASTER
SET SAL = SAL + (SAL * 0.10)
WHERE DEPTNO = 20;
```

### 7. Alter Table
```sql
ALTER TABLE EMPLOYEE_MASTER
MODIFY SAL NUMBER(10,2);
```

### 8. Drop Table
```sql
DROP TABLE EMPLOYEE_MASTER;
```

---

## Output

### Table Creation
Tables created successfully.

### Data Insertion
Records inserted successfully.

### Delete Operation
Rows with DEPTNO = 10 deleted.

### Update Operation
Salary updated by 10% for DEPTNO = 20.

### Alter Table
Column SAL modified to NUMBER(10,2).

### Drop Table
EMPLOYEE_MASTER table deleted successfully.

---

## Result
Successfully created tables, inserted data, and performed SQL operations including DELETE, UPDATE, ALTER, and DROP.