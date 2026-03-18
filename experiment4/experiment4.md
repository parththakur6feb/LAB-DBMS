# Experiment 4

## Aim
To perform SQL queries using string functions, arithmetic operations, date conditions, and update statements.

---

## Theory
SQL supports various functions and operations to manipulate and retrieve data effectively. String functions help in pattern matching, arithmetic expressions help in calculations, and date functions help in filtering records based on time.

In this experiment:
- String operations are performed using LIKE.
- Arithmetic calculations are applied on salary.
- Date conditions are used for filtering.
- UPDATE statements are used to modify records.

---

## Experiment Questions
1. Display employees who joined before 30-June-1980 or after 31-Dec-1981.
2. Display employees whose second letter is 'A'.
3. Display employees whose names are exactly five characters long.
4. Display employees who are not salesman, clerk, or analyst.
5. Display employee name and annual salary in descending order of salary.
6. Display name, salary, HRA, DA, PF, and total salary.
7. Update salary by 10% for employees not eligible for commission.
8. Display employees whose salary is more than 3000 after 20% increment.
9. Display employees whose salary has at least 3 digits.

---

## Queries

### 1. Employees based on joining date
```sql
SELECT *
FROM EMPLOYEE
WHERE HIREDATE < TO_DATE('30-JUN-1980','DD-MON-YYYY')
   OR HIREDATE > TO_DATE('31-DEC-1981','DD-MON-YYYY');
```


---

### 2. Second letter is 'A'
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE ENAME LIKE '_A%';
```

---

### 3. Names with exactly 5 characters
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE LENGTH(ENAME) = 5;
```

---

### 4. Not salesman, clerk, or analyst
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE JOB NOT IN ('SALESMAN', 'CLERK', 'ANALYST');
```

---

### 5. Annual salary in descending order
```sql
SELECT ENAME, (SAL * 12) AS ANNUAL_SALARY
FROM EMPLOYEE
ORDER BY ANNUAL_SALARY DESC;
```

---

### 6. Salary breakdown
```sql
SELECT ENAME, SAL,
       (SAL * 0.15) AS HRA,
       (SAL * 0.10) AS DA,
       (SAL * 0.05) AS PF,
       (SAL + (SAL * 0.15) + (SAL * 0.10) - (SAL * 0.05)) AS TOTAL_SAL
FROM EMPLOYEE;
```

---

### 7. Update salary by 10% (no commission)
```sql
UPDATE EMPLOYEE
SET SAL = SAL + (SAL * 0.10)
WHERE COMM IS NULL;
```

---

### 8. Salary more than 3000 after 20% increment
```sql
SELECT ENAME, SAL
FROM EMPLOYEE
WHERE (SAL * 1.20) > 3000;
```

---

### 9. Salary with at least 3 digits
```sql
SELECT ENAME, SAL
FROM EMPLOYEE
WHERE SAL >= 100;
```

---

## Output
- Successfully applied string and date conditions.
- Performed arithmetic operations on salary.
- Updated records using UPDATE statement.

---

## Result
Successfully executed SQL queries using string functions, arithmetic operations, date conditions, and update statements.