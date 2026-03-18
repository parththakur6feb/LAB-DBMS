# Experiment 5

## Aim
To perform SQL queries using aggregate functions and string functions on the EMPLOYEE table.

---

## Theory
Aggregate functions in SQL are used to perform calculations on a set of values and return a single value. Common aggregate functions include COUNT, SUM, AVG, MAX, and MIN. String functions are used to manipulate text data.

In this experiment:
- Aggregate functions are used to perform calculations.
- Group operations are applied on employee data.
- String functions are used for formatting text.

---

## Experiment Questions
1. Display total number of employees.
2. Display total salary of all employees.
3. Display maximum salary.
4. Display minimum salary.
5. Display average salary.
6. Display maximum salary of clerks.
7. Display maximum salary in department 20.
8. Display minimum salary of salesman.
9. Display average salary of managers.
10. Display total salary of analysts in department 40.
11. Display employee names in uppercase.
12. Display employee names in lowercase.
13. Display employee names in proper case.
14. Display length of your name.
15. Display length of all employee names.

---

## Queries

### 1. Total number of employees
```sql
SELECT COUNT(*) AS TOTAL_EMPLOYEES
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 183454.png>)

---

### 2. Total salary of all employees
```sql
SELECT SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 183522.png>)

---

### 3. Maximum salary
```sql
SELECT MAX(SAL) AS MAX_SALARY
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 183548.png>)

---

### 4. Minimum salary
```sql
SELECT MIN(SAL) AS MIN_SALARY
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 183619.png>)

---

### 5. Average salary
```sql
SELECT AVG(SAL) AS AVG_SALARY
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 183642.png>)

---

### 6. Maximum salary of clerks
```sql
SELECT MAX(SAL) AS MAX_CLERK_SALARY
FROM EMPLOYEE
WHERE JOB = 'CLERK';
```
![alt text](<Screenshot 2026-02-11 183734.png>)

---

### 7. Maximum salary in department 20
```sql
SELECT MAX(SAL) AS MAX_SAL_DEPT20
FROM EMPLOYEE
WHERE DEPTNO = 20;
```
![alt text](<Screenshot 2026-02-11 183812.png>)

---

### 8. Minimum salary of salesman
```sql
SELECT MIN(SAL) AS MIN_SALESMAN_SALARY
FROM EMPLOYEE
WHERE JOB = 'SALESMAN';
```
![alt text](<Screenshot 2026-02-11 183849.png>)

---

### 9. Average salary of managers
```sql
SELECT AVG(SAL) AS AVG_MANAGER_SALARY
FROM EMPLOYEE
WHERE JOB = 'MANAGER';
```
![alt text](<Screenshot 2026-02-11 183916.png>)

---

### 10. Total salary of analysts in department 40
```sql
SELECT SUM(SAL) AS TOTAL_ANALYST_SALARY
FROM EMPLOYEE
WHERE JOB = 'ANALYST' AND DEPTNO = 40;
```
![alt text](<Screenshot 2026-02-11 183948.png>)

---

### 11. Employee names in uppercase
```sql
SELECT UPPER(ENAME) AS UPPER_NAME
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 184021.png>)

---

### 12. Employee names in lowercase
```sql
SELECT LOWER(ENAME) AS LOWER_NAME
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 184049.png>)

---

### 13. Employee names in proper case
```sql
SELECT INITCAP(ENAME) AS PROPER_NAME
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 184157.png>)

---

### 14. Length of your name
```sql
SELECT LENGTH('YOUR_NAME') AS NAME_LENGTH
FROM DUAL;
```
![alt text](<Screenshot 2026-02-11 184505.png>)

---

### 15. Length of all employee names
```sql
SELECT ENAME, LENGTH(ENAME) AS NAME_LENGTH
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-11 184122.png>)

---

## Output
- Successfully used aggregate functions like COUNT, SUM, AVG, MAX, and MIN.
- Performed conditional aggregation.
- Applied string functions for formatting text.

---

## Result
Successfully executed SQL queries using aggregate functions and string functions.