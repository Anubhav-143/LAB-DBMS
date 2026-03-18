# Experiment 4 – Date Queries, Salary Calculations, and Updates

**CO No.: 1, 2**

---

## Queries

### 1. Display the list of employees who joined before 30th June 1980 or after 31st Dec 1981

```sql
SELECT * FROM EMPLOYEE
WHERE HIREDATE < TO_DATE('30-JUN-80','DD-MON-YY')
   OR HIREDATE > TO_DATE('31-DEC-81','DD-MON-YY');
```

### 2. Display the names of employees whose names have the second alphabet A

```sql
SELECT ENAME FROM EMPLOYEE WHERE ENAME LIKE '_A%';
```

### 3. Display the names of employees whose name is exactly five characters in length

```sql
SELECT ENAME FROM EMPLOYEE WHERE LENGTH(ENAME) = 5;
```

### 4. Display the names of employees whose names have the second alphabet A in their names (same as query 2)

```sql
SELECT ENAME FROM EMPLOYEE WHERE ENAME LIKE '_A%';
```

### 5. Display the names of employees who are not working as salesman, clerk or analyst

```sql
SELECT ENAME FROM EMPLOYEE WHERE JOB NOT IN ('SALESMAN', 'CLERK', 'ANALYST');
```

### 6. Display the name of the employee along with their annual salary (SAL*12); the highest earner should appear first

```sql
SELECT ENAME, SAL * 12 AS ANNUAL_SALARY FROM EMPLOYEE ORDER BY ANNUAL_SALARY DESC;
```

### 7. Display name, sal, hra, pf, da, totalsal for each employee (HRA = 15% of SAL, DA = 10% of SAL, PF = 5% of SAL, TOTAL = (SAL + HRA + DA) - PF)

```sql
SELECT ENAME,
       SAL,
       SAL * 0.15                               AS HRA,
       SAL * 0.05                               AS PF,
       SAL * 0.10                               AS DA,
       (SAL + SAL * 0.15 + SAL * 0.10) - SAL * 0.05 AS TOTAL_SAL
FROM EMPLOYEE
ORDER BY TOTAL_SAL;
```

### 8. Update the salary of each employee by 10% increment who are not eligible for commission

```sql
UPDATE EMPLOYEE SET SAL = SAL * 1.10 WHERE COMM IS NULL OR COMM = 0;
```

### 9. Display those employees whose salary is more than 3000 after a 20% increment

```sql
SELECT * FROM EMPLOYEE WHERE SAL * 1.20 > 3000;
```

### 10. Display those employees whose salary contains at least 3 digits

```sql
SELECT * FROM EMPLOYEE WHERE SAL >= 100;
```
