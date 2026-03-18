# Experiment 6

## Aim
To perform SQL queries using date functions, conversion functions, and special functions like DECODE.

---

## Theory
SQL provides various built-in functions to work with dates, numbers, and conditional logic. Date functions help in manipulating and retrieving date values, while functions like DECODE allow conditional transformations similar to IF-ELSE logic.

In this experiment:
- Date functions like SYSDATE, ADD_MONTHS, NEXT_DAY are used.
- Conversion and formatting of date values are performed.
- Conditional logic is implemented using DECODE.

---

## Experiment Questions
1. Display empno, ename, and department name using DECODE.
2. Display your age in days.
3. Display your age in months.
4. Display the current date in a formatted style.
5. Find the nearest Saturday after current date.
6. Display current system time.
7. Display the date three months before current date.
8. Display employees who joined in December.
9. Display employees who joined before 15th of the month.

---

## Queries

### 1. Display empno, ename, dept name using DECODE
```sql
SELECT EMPNO, ENAME,
       DECODE(DEPTNO,
              10, 'RESEARCH',
              20, 'ACCOUNTING',
              30, 'SALES',
              40, 'OPERATIONS') AS DEPT_NAME
FROM EMPLOYEE;
```
![alt text](<Screenshot 2026-02-21 182744.png>)

---

### 2. Display your age in days
```sql
SELECT (SYSDATE - TO_DATE('01-JAN-2000','DD-MON-YYYY')) AS AGE_IN_DAYS
FROM DUAL;
```
![alt text](<Screenshot 2026-02-21 183019.png>)

---

### 3. Display your age in months
```sql
SELECT MONTHS_BETWEEN(SYSDATE, TO_DATE('01-JAN-2000','DD-MON-YYYY')) AS AGE_IN_MONTHS
FROM DUAL;
```
![alt text](<Screenshot 2026-02-21 183041.png>)

---

### 4. Display formatted current date
```sql
SELECT TO_CHAR(SYSDATE, 'DDth Month Day YYYY') AS FORMATTED_DATE
FROM DUAL;
```
![alt text](<Screenshot 2026-02-21 183108.png>)

---

### 5. Nearest Saturday after current date
```sql
SELECT NEXT_DAY(SYSDATE, 'SATURDAY') AS NEXT_SATURDAY
FROM DUAL;
```
![alt text](<Screenshot 2026-02-21 183221.png>)

---

### 6. Display current time
```sql
SELECT TO_CHAR(SYSDATE, 'HH24:MI:SS') AS CURRENT_TIME
FROM DUAL;
```
![alt text](<Screenshot 2026-02-21 190329.png>)

---

### 7. Date three months before current date
```sql
SELECT ADD_MONTHS(SYSDATE, -3) AS THREE_MONTHS_BEFORE
FROM DUAL;
```
![alt text](<Screenshot 2026-02-21 183324.png>)

---

### 9. Employees joined in December
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE TO_CHAR(HIREDATE, 'MON') = 'DEC';
```
![alt text](<Screenshot 2026-02-21 183444.png>)

---

### 10. Employees who joined before 15th of the month 
```sql
SELECT ENAME
FROM EMPLOYEE
WHERE DAY (HIREDATE) < 15;
```
![alt text](<Screenshot 2026-02-21 183406.png>)


---

## Output
- Successfully used date and time functions.
- Applied formatting using TO_CHAR.
- Implemented conditional logic using DECODE.

---

## Result
Successfully executed SQL queries using date functions, conversion functions, and conditional expressions.