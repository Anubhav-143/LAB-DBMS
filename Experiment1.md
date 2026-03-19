# Experiment 1 – Table Creation, Data Insertion, and DDL Operations

**CO No.: 1, 2**

---

## Table Structures

### EMPLOYEE Table

| Column Name | Data Type | Size | Attributes       |
|-------------|-----------|------|------------------|
| EMPNO       | Number    | 4    | Primary Key      |
| ENAME       | Varchar2  | 20   | Not Null         |
| JOB         | Varchar2  | 20   |                  |
| MGR         | Number    | 4    |                  |
| HIREDATE    | Date      |      |                  |
| SAL         | Number    | 10   |                  |
| COMM        | Number    | 7    |                  |
| DEPTNO      | Number    | 2    | Foreign Key      |

### DEPARTMENT Table

| Column Name | Data Type | Size | Attributes  |
|-------------|-----------|------|-------------|
| DEPTNO      | Number    | 2    | Primary Key |
| DNAME       | Varchar2  | 15   | Not Null    |

---

## Create Tables

```sql
CREATE TABLE DEPARTMENT (
    DEPTNO NUMBER(2)    PRIMARY KEY,
    DNAME  VARCHAR2(15) NOT NULL
);

CREATE TABLE EMPLOYEE (
    EMPNO    NUMBER(4)    PRIMARY KEY,
    ENAME    VARCHAR2(20) NOT NULL,
    JOB      VARCHAR2(20),
    MGR      NUMBER(4),
    HIREDATE DATE,
    SAL      NUMBER(10),
    COMM     NUMBER(7),
    DEPTNO   NUMBER(2)    REFERENCES DEPARTMENT(DEPTNO)
);
```

---

## Insert Data

### DEPARTMENT

```sql
INSERT INTO DEPARTMENT VALUES (10, 'RESEARCH');
INSERT INTO DEPARTMENT VALUES (20, 'ACCOUNTING');
INSERT INTO DEPARTMENT VALUES (30, 'SALES');
INSERT INTO DEPARTMENT VALUES (40, 'OPERATIONS');
```

### EMPLOYEE

```sql
INSERT INTO EMPLOYEE VALUES (7369, 'SMITH',  'CLERK',     7902, TO_DATE('17-DEC-80','DD-MON-YY'),  800,  NULL, 20);
INSERT INTO EMPLOYEE VALUES (7499, 'ALLEN',  'SALESMAN',  7698, TO_DATE('20-FEB-81','DD-MON-YY'), 1600,  300, 30);
INSERT INTO EMPLOYEE VALUES (7521, 'WARD',   'SALESMAN',  7698, TO_DATE('22-FEB-81','DD-MON-YY'), 1250,  300, 30);
INSERT INTO EMPLOYEE VALUES (7566, 'JONES',  'MANAGER',   7839, TO_DATE('02-APR-81','DD-MON-YY'), 2975, NULL, 20);
INSERT INTO EMPLOYEE VALUES (7654, 'MARTIN', 'SALESMAN',  7698, TO_DATE('28-SEP-81','DD-MON-YY'), 1250, 1400, 30);
INSERT INTO EMPLOYEE VALUES (7698, 'BLAKE',  'MANAGER',   7839, TO_DATE('01-MAY-81','DD-MON-YY'), 2850, NULL, 30);
INSERT INTO EMPLOYEE VALUES (7782, 'CLARK',  'MANAGER',   7839, TO_DATE('09-JUN-81','DD-MON-YY'), 2450, NULL, 20);
INSERT INTO EMPLOYEE VALUES (7788, 'SCOTT',  'ANALYST',   7566, TO_DATE('09-DEC-82','DD-MON-YY'), 3000, NULL, 40);
INSERT INTO EMPLOYEE VALUES (7839, 'KING',   'PRESIDENT', NULL, TO_DATE('17-NOV-81','DD-MON-YY'), 5000, NULL, 20);
INSERT INTO EMPLOYEE VALUES (7844, 'TURNER', 'SALESMAN',  7698, TO_DATE('08-SEP-81','DD-MON-YY'), 1500,    0, 30);
INSERT INTO EMPLOYEE VALUES (7876, 'ADAMS',  'CLERK',     7788, TO_DATE('12-JAN-83','DD-MON-YY'), 1100, NULL, 20);
INSERT INTO EMPLOYEE VALUES (7900, 'JAMES',  'CLERK',     7698, TO_DATE('03-DEC-81','DD-MON-YY'),  950, NULL, 30);
INSERT INTO EMPLOYEE VALUES (7902, 'FORD',   'ANALYST',   7566, TO_DATE('03-DEC-81','DD-MON-YY'), 3000, NULL, 20);
INSERT INTO EMPLOYEE VALUES (7934, 'MILLER', 'CLERK',     7782, TO_DATE('23-JAN-82','DD-MON-YY'), 1300, NULL, 10);
```

---

## Queries

### 1. Create Employee_master table with data using Employee table

```sql
CREATE TABLE EMPLOYEE_MASTER AS SELECT * FROM EMPLOYEE;
```

### 2. Delete all records in Employee_master whose DEPTNO is 10

```sql
DELETE FROM EMPLOYEE_MASTER WHERE DEPTNO = 10;
```

### 3. Update salary by 10% for employees in DEPTNO 20 in Employee_master

```sql
UPDATE EMPLOYEE_MASTER SET SAL = SAL * 1.10 WHERE DEPTNO = 20;
```

### 4. Alter SAL column size to NUMBER(10,2) in Employee_master

```sql
ALTER TABLE EMPLOYEE_MASTER MODIFY SAL NUMBER(10,2);
```

### 5. Drop Employee_master table

```sql
DROP TABLE EMPLOYEE_MASTER;
```
