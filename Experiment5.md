# Experiment 5 – Aggregate Functions and String Functions

**CO No.: 1, 2**

---

## Queries

### 1. Display the total number of employees working in the company

```sql
SELECT COUNT(*) AS TOTAL_EMPLOYEES FROM EMPLOYEE;
```

### 2. Display the total salary being paid to all employees

```sql
SELECT SUM(SAL) AS TOTAL_SALARY FROM EMPLOYEE;
```

### 3. Display the maximum salary from the employee table

```sql
SELECT MAX(SAL) AS MAX_SALARY FROM EMPLOYEE;
```

### 4. Display the minimum salary from the employee table

```sql
SELECT MIN(SAL) AS MIN_SALARY FROM EMPLOYEE;
```

### 5. Display the average salary from the employee table

```sql
SELECT AVG(SAL) AS AVG_SALARY FROM EMPLOYEE;
```

### 6. Display the maximum salary being paid to a clerk

```sql
SELECT MAX(SAL) AS MAX_CLERK_SALARY FROM EMPLOYEE WHERE JOB = 'CLERK';
```

### 7. Display the maximum salary being paid in department number 20

```sql
SELECT MAX(SAL) AS MAX_SAL_DEPT20 FROM EMPLOYEE WHERE DEPTNO = 20;
```

### 8. Display the minimum salary paid to any salesman

```sql
SELECT MIN(SAL) AS MIN_SALESMAN_SALARY FROM EMPLOYEE WHERE JOB = 'SALESMAN';
```

### 9. Display the average salary drawn by managers

```sql
SELECT AVG(SAL) AS AVG_MANAGER_SALARY FROM EMPLOYEE WHERE JOB = 'MANAGER';
```

### 10. Display the total salary drawn by analysts working in department number 40

```sql
SELECT SUM(SAL) AS TOTAL_ANALYST_SAL_DEPT40 FROM EMPLOYEE WHERE JOB = 'ANALYST' AND DEPTNO = 40;
```

### 11. Display the names of employees in uppercase

```sql
SELECT UPPER(ENAME) AS ENAME_UPPER FROM EMPLOYEE;
```

### 12. Display the names of employees in lowercase

```sql
SELECT LOWER(ENAME) AS ENAME_LOWER FROM EMPLOYEE;
```

### 13. Display the names of employees in proper case (initcap)

```sql
SELECT INITCAP(ENAME) AS ENAME_PROPER FROM EMPLOYEE;
```

### 14. Display the length of your name using an appropriate function

```sql
SELECT LENGTH('YourName') AS NAME_LENGTH FROM DUAL;
```

### 15. Display the length of all employee names

```sql
SELECT ENAME, LENGTH(ENAME) AS NAME_LENGTH FROM EMPLOYEE;
```
