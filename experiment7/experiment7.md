# Experiment 7

## Aim
To perform advanced SQL queries using aggregate functions, grouping, and analytical calculations.

---

## Theory
SQL allows advanced data analysis using aggregate functions along with GROUP BY and HAVING clauses. These help in summarizing data and performing calculations across groups.

In this experiment:
- Aggregate functions are used for calculations.
- GROUP BY is used to group records.
- HAVING clause is used to filter grouped data.
- Date and numeric calculations are performed.

---

## Experiment Questions
1. Compute number of days remaining in the current year.
2. Find highest and lowest salary and their difference.
3. List employees whose commission is greater than 25% of salary.
4. Display salary in formatted form.
5. Display job-wise salary based on department (matrix query).
6. Display total employees and count based on year of joining.
7. Find last Sunday of any month.
8. Display department-wise number of employees.
9. Display job-wise number of employees.
10. Display department-wise total salary.

---

## Queries

### 1. Days remaining in current year
```sql
SELECT (TO_DATE('31-DEC-' || TO_CHAR(SYSDATE,'YYYY'),'DD-MON-YYYY') - SYSDATE) AS DAYS_LEFT
FROM DUAL;
```
![alt text](<Screenshot 2026-02-18 121717.png>)

---

### 2. Highest, lowest salary and difference
```sql
SELECT MAX(SAL) AS MAX_SAL,
       MIN(SAL) AS MIN_SAL,
       (MAX(SAL) - MIN(SAL)) AS DIFFERENCE
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-18 122631.png>)

---

### 3. Employees with commission > 25% of salary
```sql
SELECT ENAME, SAL, COMM
FROM EMPLOYEE
WHERE COMM > (0.25 * SAL);
```
![alt text](<Screenshot 2026-02-18 122854.png>)

---

### 4. Salary in formatted form
```sql
SELECT ENAME, TO_CHAR(SAL, '$9999') AS FORMATTED_SALARY
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-18 124314.png>)

---

### 5. Matrix query (job-wise salary by department)
```sql
SELECT JOB,
       SUM(CASE WHEN DEPTNO = 10 THEN SAL ELSE 0 END) AS DEPT10,
       SUM(CASE WHEN DEPTNO = 20 THEN SAL ELSE 0 END) AS DEPT20,
       SUM(CASE WHEN DEPTNO = 30 THEN SAL ELSE 0 END) AS DEPT30,
       SUM(SAL) AS TOTAL
FROM EMPLOYEE
GROUP BY JOB;
```
![alt text](<Screenshot 2026-02-18 125839.png>)

---

### 6. Total employees and count by joining year
```sql
SELECT COUNT(*) AS TOTAL_EMPLOYEES,
       SUM(CASE WHEN EXTRACT(YEAR FROM HIREDATE) = 1980 THEN 1 ELSE 0 END) AS Y1980,
       SUM(CASE WHEN EXTRACT(YEAR FROM HIREDATE) = 1981 THEN 1 ELSE 0 END) AS Y1981,
       SUM(CASE WHEN EXTRACT(YEAR FROM HIREDATE) = 1982 THEN 1 ELSE 0 END) AS Y1982,
       SUM(CASE WHEN EXTRACT(YEAR FROM HIREDATE) = 1983 THEN 1 ELSE 0 END) AS Y1983
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-21 185205.png>)

---

### 7. Last Sunday of current month
```sql
SELECT NEXT_DAY(LAST_DAY(SYSDATE) - 7, 'SUNDAY') AS LAST_SUNDAY
FROM DUAL;
```
![alt text](<Screenshot 2026-02-18 132032.png>)

---

### 8. Department-wise employee count
```sql
SELECT DEPTNO, COUNT(*) AS EMP_COUNT
FROM EMPLOYEE
GROUP BY DEPTNO;
```
![alt text](<Screenshot 2026-02-21 185558.png>)

---

### 9. Job-wise employee count
```sql
SELECT JOB, COUNT(*) AS EMP_COUNT
FROM EMPLOYEE
GROUP BY JOB;
```
![alt text](<Screenshot 2026-02-21 185657.png>)

---

### 10. Department-wise total salary
```sql
SELECT DEPTNO, SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE
GROUP BY DEPTNO;
```
![alt text](<Screenshot 2026-02-21 185921.png>)

---

## Output
- Successfully applied aggregate functions with grouping.
- Performed analytical and conditional queries.
- Generated summarized reports using SQL.

---

## Result
Successfully executed advanced SQL queries using GROUP BY, aggregate functions, and analytical operations.