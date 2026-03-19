# Experiment 6 – DECODE Function and Date Functions

**CO No.: 1, 2**

---

## Queries

### 1. Display EMPNO, ENAME, DEPTNO; show department name instead of department number (using DECODE)

```sql
SELECT EMPNO, ENAME,
       DECODE(DEPTNO,
              10, 'RESEARCH',
              20, 'ACCOUNTING',
              30, 'SALES',
              40, 'OPERATIONS',
              'UNKNOWN') AS DEPARTMENT
FROM EMPLOYEE;
```

### 2. Display your age in days

```sql
SELECT TRUNC(SYSDATE - TO_DATE('15-AUG-2000', 'DD-MON-YYYY')) AS AGE_IN_DAYS FROM DUAL;
```

*Replace `'15-AUG-2000'` with your actual date of birth in `DD-MON-YYYY` format.*

### 3. Display your age in months

```sql
SELECT TRUNC(MONTHS_BETWEEN(SYSDATE, TO_DATE('15-AUG-2000','DD-MON-YYYY'))) AS AGE_IN_MONTHS FROM DUAL;
```

### 4. Display the current date as "15th August Friday Nineteen Ninety-Seven"

```sql
SELECT TO_CHAR(SYSDATE, 'DDth Month Day Year') AS FORMATTED_DATE FROM DUAL;
```

### 5. Display the following output for each row from the employee table: `<ENAME> earns <SAL> monthly but wants <SAL*3>`

```sql
SELECT ENAME || ' earns ' || SAL || ' monthly but wants ' || SAL * 3 AS DREAM_SALARY
FROM EMPLOYEE;
```

### 6. Scott has joined the company on Wednesday 13th August Nineteen Ninety (format hire date)

```sql
SELECT ENAME || ' has joined the company on ' ||
       TO_CHAR(HIREDATE, 'Day DDth Month Year') AS JOINING_DETAILS
FROM EMPLOYEE
WHERE ENAME = 'SCOTT';
```

### 7. Find the date of the nearest Saturday after the current date

```sql
SELECT NEXT_DAY(SYSDATE, 'SATURDAY') AS NEXT_SATURDAY FROM DUAL;
```

### 8. Display the current time

```sql
SELECT TO_CHAR(SYSDATE, 'HH:MI:SS AM') AS CURRENT_TIME FROM DUAL;
```

### 9. Display the date three months before the current date

```sql
SELECT ADD_MONTHS(SYSDATE, -3) AS THREE_MONTHS_BEFORE FROM DUAL;
```

### 10. Display those employees who joined the company in the month of December

```sql
SELECT * FROM EMPLOYEE WHERE TO_CHAR(HIREDATE, 'MON') = 'DEC';
```

### 11. Display those employees whose first 2 characters of hire date match the last 2 characters of their salary

```sql
SELECT * FROM EMPLOYEE
WHERE SUBSTR(TO_CHAR(HIREDATE, 'DD-MON-YY'), 1, 2) =
      SUBSTR(TO_CHAR(SAL), LENGTH(TO_CHAR(SAL)) - 1, 2);
```

### 12. Display those employees whose 10% of salary is equal to the year of joining

```sql
SELECT * FROM EMPLOYEE
WHERE SAL * 0.10 = TO_NUMBER(TO_CHAR(HIREDATE, 'YYYY'));
```

### 13. Display those employees who joined the company before the 15th of the month

```sql
SELECT * FROM EMPLOYEE WHERE TO_NUMBER(TO_CHAR(HIREDATE, 'DD')) < 15;
```

### 14. Display those employees who joined before the 15th of the month (same as query 13)

```sql
SELECT * FROM EMPLOYEE WHERE TO_NUMBER(TO_CHAR(HIREDATE, 'DD')) < 15;
```

### 15. Display those employees whose joining date is available in DEPTNO

```sql
SELECT * FROM EMPLOYEE
WHERE TO_NUMBER(TO_CHAR(HIREDATE, 'DD')) = DEPTNO;
```
