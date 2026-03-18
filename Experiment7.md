# Experiment 7 – Advanced Queries (Grouping, Formatting, and Matrix Queries)

**CO No.: 1, 2**

---

## Queries

### 1. Compute the number of days remaining in this year

```sql
SELECT TO_DATE('31-DEC-' || TO_CHAR(SYSDATE, 'YYYY'), 'DD-MON-YYYY') - TRUNC(SYSDATE)
    AS DAYS_REMAINING_IN_YEAR
FROM DUAL;
```

### 2. Find the highest and lowest salaries and the difference between them

```sql
SELECT MAX(SAL) AS HIGHEST_SAL,
       MIN(SAL) AS LOWEST_SAL,
       MAX(SAL) - MIN(SAL) AS DIFFERENCE
FROM EMPLOYEE;
```

### 3. List employees whose commission is greater than 25% of their salary

```sql
SELECT * FROM EMPLOYEE WHERE COMM > SAL * 0.25;
```

### 4. Make a query that displays salary in dollar format

```sql
SELECT ENAME, TO_CHAR(SAL, '$99,999.00') AS SALARY_IN_DOLLARS FROM EMPLOYEE;
```

### 5. Create a matrix query to display the job, salary for that job based on department number, and the total salary for that job across all departments

```sql
SELECT JOB,
       SUM(CASE WHEN DEPTNO = 10 THEN SAL ELSE 0 END) AS "DEPT 10",
       SUM(CASE WHEN DEPTNO = 20 THEN SAL ELSE 0 END) AS "DEPT 20",
       SUM(CASE WHEN DEPTNO = 30 THEN SAL ELSE 0 END) AS "DEPT 30",
       SUM(CASE WHEN DEPTNO = 40 THEN SAL ELSE 0 END) AS "DEPT 40",
       SUM(SAL)                                        AS "TOTAL"
FROM EMPLOYEE
GROUP BY JOB
ORDER BY JOB;
```

### 6. Query to display total number of employees and number hired in 1980, 1981, 1982, and 1983

```sql
SELECT COUNT(*)                                                    AS TOTAL,
       SUM(CASE WHEN TO_CHAR(HIREDATE,'YYYY') = '1980' THEN 1 ELSE 0 END) AS "1980",
       SUM(CASE WHEN TO_CHAR(HIREDATE,'YYYY') = '1981' THEN 1 ELSE 0 END) AS "1981",
       SUM(CASE WHEN TO_CHAR(HIREDATE,'YYYY') = '1982' THEN 1 ELSE 0 END) AS "1982",
       SUM(CASE WHEN TO_CHAR(HIREDATE,'YYYY') = '1983' THEN 1 ELSE 0 END) AS "1983"
FROM EMPLOYEE;
```

### 7. Query to get the last Sunday of any month

```sql
SELECT NEXT_DAY(LAST_DAY(SYSDATE) - 7, 'SUNDAY') AS LAST_SUNDAY_OF_MONTH FROM DUAL;
```

### 8. Display department numbers and total number of employees working in each department

```sql
SELECT DEPTNO, COUNT(*) AS TOTAL_EMPLOYEES
FROM EMPLOYEE
GROUP BY DEPTNO
ORDER BY DEPTNO;
```

### 9. Display the various jobs and total number of employees within each job group

```sql
SELECT JOB, COUNT(*) AS TOTAL_EMPLOYEES
FROM EMPLOYEE
GROUP BY JOB
ORDER BY JOB;
```

### 10. Display department numbers and total salary for each department

```sql
SELECT DEPTNO, SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE
GROUP BY DEPTNO
ORDER BY DEPTNO;
```
