# **EXPERIMENT – 1**





##### **🎯 Aim**



To create tables (EMPLOYEE, DEPARTMENT), insert records, and perform basic SQL operations like insert, update, and delete in MariaDB.





##### **📘 Theory**



In MariaDB, data is stored in tables consisting of rows and columns.



###### Key Concepts:

###### **1️⃣ CREATE TABLE**



Used to create a new table.



CREATE TABLE table\_name (...);

###### **2️⃣ INSERT INTO**



Used to insert records.



INSERT INTO table\_name VALUES (...);

###### **3️⃣ UPDATE**



Used to modify data.



UPDATE table\_name SET column=value;

###### **4️⃣ DELETE**



Used to delete records.





##### **💻 SQL Queries**



**MariaDB \[(none)]> SHOW DATABASES;**

**+--------------------+**

**| Database           |**

**+--------------------+**

**| 2cse15g2\_0896      |**

**| companay           |**

**| information\_schema |**

**| mysql              |**

**| performance\_schema |**

**| phpmyadmin         |**

**| test               |**

**+--------------------+**

**7 rows in set (0.058 sec)**



**MariaDB \[(none)]> USE 2CSE15G2\_0896;**

**Database changed**



###### **1. Create Employee Table**

**MariaDB \[2CSE15G2\_0896]> CREATE TABLE EMPLOYEE(EMPNO INT(4) PRIMARY KEY,ENAME VARCHAR(20) NOT NULL, JOB VARCHAR(20), MGR INT(4), HIREDATE DATE,SAL INT(10),COMM INT(7),DEPTNO INT(2),FOREIGN KEY(DEPTNO) REFERENCES DEPARTMENT(DEPTNO));**

**Query OK, 0 rows affected (0.020 sec)**



**MariaDB \[2CSE15G2\_0896]> DESC EMPLOYEE;**

**+----------+-------------+------+-----+---------+-------+**

**| Field    | Type        | Null | Key | Default | Extra |**

**+----------+-------------+------+-----+---------+-------+**

**| EMPNO    | int(4)      | NO   | PRI | NULL    |       |**

**| ENAME    | varchar(20) | NO   |     | NULL    |       |**

**| JOB      | varchar(20) | YES  |     | NULL    |       |**

**| MGR      | int(4)      | YES  |     | NULL    |       |**

**| HIREDATE | date        | YES  |     | NULL    |       |**

**| SAL      | int(10)     | YES  |     | NULL    |       |**

**| COMM     | int(7)      | YES  |     | NULL    |       |**

**| DEPTNO   | int(2)      | YES  | MUL | NULL    |       |**

**+----------+-------------+------+-----+---------+-------+**

**8 rows in set (0.020 sec)**





###### **2. Create Department Table**



**MariaDB \[2CSE15G2\_0896]> DESC DEPARTMENT;**

**+--------+-------------+------+-----+---------+-------+**

**| Field  | Type        | Null | Key | Default | Extra |**

**+--------+-------------+------+-----+---------+-------+**

**| DEPTNO | int(2)      | NO   | PRI | NULL    |       |**

**| DNAME  | varchar(15) | NO   |     | NULL    |       |**

**+--------+-------------+------+-----+---------+-------+**

**2 rows in set (0.024 sec)**





###### **3. Insert Values into Department**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO DEPARTMENT VALUES (10, 'RESEARCH');**

**Query OK, 1 row affected (0.002 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO DEPARTMENT VALUES (20, 'ACCOUNTING');**

**Query OK, 1 row affected (0.001 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO DEPARTMENT VALUES (30, 'SALES');**

**Query OK, 1 row affected (0.002 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO DEPARTMENT VALUES (40, 'OPERATIONS');**

**Query OK, 1 row affected (0.001 sec)**



**MariaDB \[2CSE15G2\_0896]> SELECT\*FROM DEPARTMENT;**

**+--------+------------+**

**| DEPTNO | DNAME      |**

**+--------+------------+**

**|     10 | RESEARCH   |**

**|     20 | ACCOUNTING |**

**|     30 | SALES      |**

**|     40 | OPERATIONS |**

**+--------+------------+**

**4 rows in set (0.000 sec)**







###### **4. Insert Sample Employee Records**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7499,'ALLEN','SALESMAN',7698,'1981-02-20',1600,300,30);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7521,'WARD','SALESMAN',7698,'1981-02-22',1250,300,30);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7566,'JONES','MANAGER',7839,'1981-04-02',2975,NULL,20);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7654,'MARTIN','SALESMAN',7698,'1981-09-28',1250,1400,30);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7698,'BLAKE','MANAGER',7839,'1981-05-01',2850,NULL,30);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7782,'CLARK','MANAGER',7839,'1981-06-09',2450,NULL,20);**

**Query OK, 1 row affected (0.002 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7788,'SCOTT','ANALYST',7566,'1982-12-09',3000,NULL,40);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7839,'KING','PRESIDENT',NULL,'1981-11-17',5000,NULL,20);**

**Query OK, 1 row affected (0.004 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7844,'TURNER','SALESMAN',7698,'1981-09-08',1500,0,30);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7876,'ADAMS','CLERK',7788,'1983-01-12',1100,NULL,20);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7900,'JAMES','CLERK',7698,'1981-12-03',950,NULL,30);**

**Query OK, 1 row affected (0.002 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7902,'FORD','ANALYST',7566,'1981-12-03',3000,NULL,20);**

**Query OK, 1 row affected (0.004 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7934,'MILLER','CLERK',7782,'1982-01-23',1300,NULL,10);**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> INSERT INTO EMPLOYEE VALUES (7369,'SMITH','CLERK',7902,'1980-12-17',800,NULL,20);**

**Query OK, 1 row affected (0.002 sec)**



**MariaDB \[2CSE15G2\_0896]> SELECT\*FROM EMPLOYEE;**

**+-------+--------+-----------+------+------------+------+------+--------+**

**| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |**

**+-------+--------+-----------+------+------------+------+------+--------+**

**|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  800 | NULL |     20 |**

**|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 |  300 |     30 |**

**|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 |  300 |     30 |**

**|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 2975 | NULL |     20 |**

**|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 |     30 |**

**|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL |     30 |**

**|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2450 | NULL |     20 |**

**|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL |     40 |**

**|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL |     20 |**

**|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 |    0 |     30 |**

**|  7876 | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1100 | NULL |     20 |**

**|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |  950 | NULL |     30 |**

**|  7902 | FORD   | ANALYST   | 7566 | 1981-12-03 | 3000 | NULL |     20 |**

**|  7934 | MILLER | CLERK     | 7782 | 1982-01-23 | 1300 | NULL |     10 |**

**+-------+--------+-----------+------+------------+------+------+--------+**

**14 rows in set (0.001 sec)**





###### **5. Create Employee\_Master Table**



**MariaDB \[2CSE15G2\_0896]> CREATE TABLE EMPLOYEE\_MASTER AS SELECT\*FROM EMPLOYEE;**

**Query OK, 14 rows affected (0.011 sec)**

**Records: 14  Duplicates: 0  Warnings: 0**



**MariaDB \[2CSE15G2\_0896]> SELECT\*FROM EMPLOYEE\_MASTER;**

**+-------+--------+-----------+------+------------+------+------+--------+**

**| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |**

**+-------+--------+-----------+------+------------+------+------+--------+**

**|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  800 | NULL |     20 |**

**|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 |  300 |     30 |**

**|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 |  300 |     30 |**

**|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 2975 | NULL |     20 |**

**|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 |     30 |**

**|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL |     30 |**

**|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2450 | NULL |     20 |**

**|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL |     40 |**

**|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL |     20 |**

**|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 |    0 |     30 |**

**|  7876 | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1100 | NULL |     20 |**

**|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |  950 | NULL |     30 |**

**|  7902 | FORD   | ANALYST   | 7566 | 1981-12-03 | 3000 | NULL |     20 |**

**|  7934 | MILLER | CLERK     | 7782 | 1982-01-23 | 1300 | NULL |     10 |**

**+-------+--------+-----------+------+------------+------+------+--------+**

**14 rows in set (0.000 sec)**





###### **6. Delete Records where deptno = 10**



**MariaDB \[2CSE15G2\_0896]> DELETE FROM EMPLOYEE\_MASTER WHERE DEPTNO = 10;**

**Query OK, 1 row affected (0.003 sec)**



**MariaDB \[2CSE15G2\_0896]> SELECT\*FROM EMPLOYEE\_MASTER;**

**+-------+--------+-----------+------+------------+------+------+--------+**

**| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |**

**+-------+--------+-----------+------+------------+------+------+--------+**

**|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  800 | NULL |     20 |**

**|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 |  300 |     30 |**

**|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 |  300 |     30 |**

**|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 2975 | NULL |     20 |**

**|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 |     30 |**

**|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL |     30 |**

**|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2450 | NULL |     20 |**

**|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL |     40 |**

**|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5000 | NULL |     20 |**

**|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 |    0 |     30 |**

**|  7876 | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1100 | NULL |     20 |**

**|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |  950 | NULL |     30 |**

**|  7902 | FORD   | ANALYST   | 7566 | 1981-12-03 | 3000 | NULL |     20 |**

**+-------+--------+-----------+------+------------+------+------+--------+**

**13 rows in set (0.000 sec)**



###### **7. Update Salary by 10% for Dept 20**



**MariaDB \[2CSE15G2\_0896]> UPDATE EMPLOYEE\_MASTER SET SAL=SAL\*1.10 WHERE DEPTNO=20;**

**Query OK, 6 rows affected (0.003 sec)**

**Rows matched: 6  Changed: 6  Warnings: 0**



**MariaDB \[2CSE15G2\_0896]> SELECT\*FROM EMPLOYEE\_MASTER;**

**+-------+--------+-----------+------+------------+------+------+--------+**

**| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL  | COMM | DEPTNO |**

**+-------+--------+-----------+------+------------+------+------+--------+**

**|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  880 | NULL |     20 |**

**|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600 |  300 |     30 |**

**|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250 |  300 |     30 |**

**|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 3273 | NULL |     20 |**

**|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250 | 1400 |     30 |**

**|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850 | NULL |     30 |**

**|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2695 | NULL |     20 |**

**|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000 | NULL |     40 |**

**|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5500 | NULL |     20 |**

**|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500 |    0 |     30 |**

**|  7876 | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1210 | NULL |     20 |**

**|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |  950 | NULL |     30 |**

**|  7902 | FORD   | ANALYST   | 7566 | 1981-12-03 | 3300 | NULL |     20 |**

**+-------+--------+-----------+------+------------+------+------+--------+**

**13 rows in set (0.000 sec)**





###### **8. Alter Table (increase salary size)**



**MariaDB \[2CSE15G2\_0896]> ALTER TABLE EMPLOYEE\_MASTER MODIFY SAL DECIMAL(10,2);**

**Query OK, 13 rows affected (0.028 sec)**

**Records: 13  Duplicates: 0  Warnings: 0**



**MariaDB \[2CSE15G2\_0896]> SELECT\*FROM EMPLOYEE\_MASTER;**

**+-------+--------+-----------+------+------------+---------+------+--------+**

**| EMPNO | ENAME  | JOB       | MGR  | HIREDATE   | SAL     | COMM | DEPTNO |**

**+-------+--------+-----------+------+------------+---------+------+--------+**

**|  7369 | SMITH  | CLERK     | 7902 | 1980-12-17 |  880.00 | NULL |     20 |**

**|  7499 | ALLEN  | SALESMAN  | 7698 | 1981-02-20 | 1600.00 |  300 |     30 |**

**|  7521 | WARD   | SALESMAN  | 7698 | 1981-02-22 | 1250.00 |  300 |     30 |**

**|  7566 | JONES  | MANAGER   | 7839 | 1981-04-02 | 3273.00 | NULL |     20 |**

**|  7654 | MARTIN | SALESMAN  | 7698 | 1981-09-28 | 1250.00 | 1400 |     30 |**

**|  7698 | BLAKE  | MANAGER   | 7839 | 1981-05-01 | 2850.00 | NULL |     30 |**

**|  7782 | CLARK  | MANAGER   | 7839 | 1981-06-09 | 2695.00 | NULL |     20 |**

**|  7788 | SCOTT  | ANALYST   | 7566 | 1982-12-09 | 3000.00 | NULL |     40 |**

**|  7839 | KING   | PRESIDENT | NULL | 1981-11-17 | 5500.00 | NULL |     20 |**

**|  7844 | TURNER | SALESMAN  | 7698 | 1981-09-08 | 1500.00 |    0 |     30 |**

**|  7876 | ADAMS  | CLERK     | 7788 | 1983-01-12 | 1210.00 | NULL |     20 |**

**|  7900 | JAMES  | CLERK     | 7698 | 1981-12-03 |  950.00 | NULL |     30 |**

**|  7902 | FORD   | ANALYST   | 7566 | 1981-12-03 | 3300.00 | NULL |     20 |**

**+-------+--------+-----------+------+------------+---------+------+--------+**

**13 rows in set (0.001 sec)**



###### **9. Drop Table employee\_master**



**MariaDB \[2CSE15G2\_0896]> DROP TABLE EMPLOYEE\_MASTER;**

**Query OK, 0 rows affected (0.004 sec)**





##### **🧾 Conclusion**



Thus, tables were created, data inserted, updated, and deleted successfully in MariaDB.































