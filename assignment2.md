

#Assignment 2 

```SQL

create table mydept_DBDA
(
deptid int primary key,
dname varchar(20) not null unique,
dloc varchar(20)
)


insert into mydept_DBDA values(30,'Purchase','Mumbai');




```


```SQL

create table myemployee
(
empno int primary key,
fname varchar(15) not null,
mname varchar(15),
lname varchar(15) not null,
sal float(9,2) check(sal >=1000),
doj date,
passportnum varchar(15) unique,
deptno int,
constraint fk_deptno foreign key(deptno) references mydept_DBDA(deptid) on
delete set null
on update cascade
)

```


```SQL
create table myemployee
(
empno int primary key,
ename varchar(15) not null,
mname varchar(15),
lname varchar(15) not null,
sal float(9,2) check(sal >=1000),
doj date,
passportnum varchar(15) unique,
deptno int,
constraint fk_deptno foreign key(deptno) references mydept_DBDA(deptid) on
delete set null
on update cascade
)

```


```sql

CREATE TABLE STUDENT (
    Sid int primary key,
    sname varchar(20)
)


insert into student values(1,"Rahul");
insert into student values(2,"Tushar");
insert into student values(3,"Ramu");


CREATE TABLE course (
    cid int primary key,
    cname varchar(20)
)

insert into course values(1,"JAVA");
insert into course values(2,"DATABASE");
insert into course values(3,"C++");

create table marks(
sid int,
cid int,
marks int,
constraint pk primary key(sid,cid),
constraint fk_sid foreign key (sid) references student(sid) on delete cascade,
constraint fk_cid foreign key (cid) references course(cid)
)


insert into marks values(1,1,99);
insert into marks values(1,3,98);
insert into marks values(2,1,95);
insert into marks values(2,2,97);

```


```sql
CREATE TABLE EMP
       (EMPNO INT(4) NOT NULL,
        ENAME varchar(10),
        JOB varchar(9),
        MGR INT(4),
        HIREDATE DATE,
        SAL DECIMAL(7, 2),
        COMM DECIMAL(7, 2),
        DEPTNO INT(2));

INSERT INTO EMP VALUES
        (101, 'RAHUL',  'CLERK',     106,
        STR_TO_DATE('12-JAN-2000', '%d-%b-%Y'),  1500, NULL, 20);
INSERT INTO EMP VALUES
        (7499, 'ALLEN',  'SALESMAN',  7698,
        STR_TO_DATE('20-FEB-1981', '%d-%b-%Y'), 1600,  300, 30);
INSERT INTO EMP VALUES
        (7521, 'WARD',   'SALESMAN',  7698,
        STR_TO_DATE('22-FEB-1981', '%d-%b-%Y'), 1250,  500, 30);
INSERT INTO EMP VALUES
        (7566, 'JONES',  'MANAGER',   7839,
        STR_TO_DATE('2-APR-1981', '%d-%b-%Y'),  2975, NULL, 20);
INSERT INTO EMP VALUES
        (7654, 'MARTIN', 'SALESMAN',  7698,
        STR_TO_DATE('28-SEP-1981', '%d-%b-%Y'), 1250, 1400, 30);
INSERT INTO EMP VALUES
        (7698, 'BLAKE',  'MANAGER',   7839,
        STR_TO_DATE('1-MAY-1981', '%d-%b-%Y'),  2850, NULL, 30);
INSERT INTO EMP VALUES
        (7782, 'CLARK',  'MANAGER',   7839,
        STR_TO_DATE('9-JUN-1981', '%d-%b-%Y'),  2450, NULL, 10);
INSERT INTO EMP VALUES
        (7788, 'SCOTT',  'ANALYST',   7566,
        STR_TO_DATE('09-DEC-1982', '%d-%b-%Y'), 3000, NULL, 20);
INSERT INTO EMP VALUES
        (7839, 'KING',   'PRESIDENT', NULL,
        STR_TO_DATE('17-NOV-1981', '%d-%b-%Y'), 5000, NULL, 10);
INSERT INTO EMP VALUES
        (7844, 'TURNER', 'SALESMAN',  7698,
        STR_TO_DATE('8-SEP-1981', '%d-%b-%Y'),  1500,    0, 30);

```


```SQL


create table emp10 as
(
select *
from emp
where 1=2
)


mysql> DESC EMP10;
+----------+--------------+------+-----+---------+-------+
| Field    | Type         | Null | Key | Default | Extra |
+----------+--------------+------+-----+---------+-------+
| EMPNO    | int          | NO   |     | NULL    |       |
| ENAME    | varchar(10)  | YES  |     | NULL    |       |
| JOB      | varchar(9)   | YES  |     | NULL    |       |
| MGR      | int          | YES  |     | NULL    |       |
| HIREDATE | date         | YES  |     | NULL    |       |
| SAL      | decimal(7,2) | YES  |     | NULL    |       |
| COMM     | decimal(7,2) | YES  |     | NULL    |       |
| DEPTNO   | int          | YES  |     | NULL    |       |
+----------+--------------+------+-----+---------+-------+
8 rows in set (0.00 sec)



ALTER TABLE EMP10
add primary key (EMPNO)
--------------------------------------------------------
mysql> desc emp10;
+----------+--------------+------+-----+---------+-------+
| Field    | Type         | Null | Key | Default | Extra |
+----------+--------------+------+-----+---------+-------+
| EMPNO    | int          | NO   | PRI | NULL    |       |
| ENAME    | varchar(10)  | YES  |     | NULL    |       |
| JOB      | varchar(9)   | YES  |     | NULL    |       |
| MGR      | int          | YES  |     | NULL    |       |
| HIREDATE | date         | YES  |     | NULL    |       |
| SAL      | decimal(7,2) | YES  |     | NULL    |       |
| COMM     | decimal(7,2) | YES  |     | NULL    |       |
| DEPTNO   | int          | YES  |     | NULL    |       |
+----------+--------------+------+-----+---------+-------+
8 rows in set (0.00 sec)

###########
ALTER TABLE dept
add primary key (deptno);

mysql> desc dept;
+--------+-------------+------+-----+---------+-------+
| Field  | Type        | Null | Key | Default | Extra |
+--------+-------------+------+-----+---------+-------+
| DEPTNO | int         | NO   | PRI | NULL    |       |
| DNAME  | varchar(14) | YES  |     | NULL    |       |
| LOC    | varchar(13) | YES  |     | NULL    |       |
+--------+-------------+------+-----+---------+-------+
3 rows in set (0.00 sec)



ALTER TABLE  salgrade
add primary key (grade);
mysql> desc salgrade;
+-------+------+------+-----+---------+-------+
| Field | Type | Null | Key | Default | Extra |
+-------+------+------+-----+---------+-------+
| GRADE | int  | NO   | PRI | NULL    |       |
| LOSAL | int  | YES  |     | NULL    |       |
| HISAL | int  | YES  |     | NULL    |       |
+-------+------+------+-----+---------+-------+
3 rows in set (0.00 sec)






```



```SQL



44. list all employees with salary > either Smith's salary or alan's sal


SELECT * FROM EMP 
WHERE SAL > (SELECT MAX(SAL)
FROM EMP
WHERE ENAME='ALLEN' OR ENAME='SMITH')  

mysql> SELECT * FROM EMP
    -> WHERE SAL > (SELECT MAX(SAL)
    -> FROM EMP
    -> WHERE ENAME='ALLEN' OR ENAME='SMITH') ;
+-------+-------+-----------+------+------------+---------+------+--------+
| empno | ename | job       | mgr  | hire       | sal     | comm | deptno |
+-------+-------+-----------+------+------------+---------+------+--------+
|  7566 | JONES | MANAGER   | 7839 | 1981-04-02 | 2975.00 | NULL |     20 |
|  7698 | BLAKE | MANAGER   | 7839 | 1981-05-01 | 2850.00 | NULL |     30 |
|  7782 | CLARK | MANAGER   | 7839 | 1981-06-09 | 2450.00 | NULL |     10 |
|  7788 | SCOTT | ANALYST   | 7566 | 1982-12-09 | 3000.00 | NULL |     20 |
|  7839 | KING  | PRESIDENT | NULL | 1981-11-17 | 5000.00 | NULL |     10 |
|  7902 | FORD  | ANALYST   | 7566 | 1981-12-03 | 3000.00 | NULL |     20 |
+-------+-------+-----------+------+------------+---------+------+--------+
6 rows in set (0.00 sec)


```


```SQL
45. list all employees who earn more than average sal of dept 10

mysql> SELECT * FROM EMP
    -> WHERE SAL>(SELECT AVG(SAL) FROM EMP
    -> WHERE DEPTNO=10)
    -> ;
+-------+-------+-----------+------+------------+---------+------+--------+
| empno | ename | job       | mgr  | hire       | sal     | comm | deptno |
+-------+-------+-----------+------+------------+---------+------+--------+
|  7566 | JONES | MANAGER   | 7839 | 1981-04-02 | 2975.00 | NULL |     20 |
|  7788 | SCOTT | ANALYST   | 7566 | 1982-12-09 | 3000.00 | NULL |     20 |
|  7839 | KING  | PRESIDENT | NULL | 1981-11-17 | 5000.00 | NULL |     10 |
|  7902 | FORD  | ANALYST   | 7566 | 1981-12-03 | 3000.00 | NULL |     20 |
+-------+-------+-----------+------+------------+---------+------+--------+
4 rows in set (0.00 sec)
```


```SQL

46. list all employees who earn more than average sal of Alan' department

mysql> SELECT * FROM EMP
    -> WHERE SAL>(SELECT AVG(SAL) FROM EMP WHERE DEPTNO = (SELECT DEPTNO FROM EMP WHERE ENAME='ALLEN'));
+-------+-------+-----------+------+------------+---------+--------+--------+
| empno | ename | job       | mgr  | hire       | sal     | comm   | deptno |
+-------+-------+-----------+------+------------+---------+--------+--------+
|  7499 | ALLEN | SALESMAN  | 7698 | 1981-02-20 | 1600.00 | 300.00 |     30 |
|  7566 | JONES | MANAGER   | 7839 | 1981-04-02 | 2975.00 |   NULL |     20 |
|  7698 | BLAKE | MANAGER   | 7839 | 1981-05-01 | 2850.00 |   NULL |     30 |
|  7782 | CLARK | MANAGER   | 7839 | 1981-06-09 | 2450.00 |   NULL |     10 |
|  7788 | SCOTT | ANALYST   | 7566 | 1982-12-09 | 3000.00 |   NULL |     20 |
|  7839 | KING  | PRESIDENT | NULL | 1981-11-17 | 5000.00 |   NULL |     10 |
|  7902 | FORD  | ANALYST   | 7566 | 1981-12-03 | 3000.00 |   NULL |     20 |
+-------+-------+-----------+------+------------+---------+--------+--------+
7 rows in set (0.00 sec)





```



```SQL

47. list all employees who are working in purchase department


SELECT * FROM EMP
WHERE DEPTNO = (SELECT DEPTNO FROM DEPT WHERE DNAME='PURCHASE')



INSERT INTO DEPT VALUE (50,'PURCHASE','INDIA');



```

```SQL

mysql> SELECT * FROM EMP e
    -> WHERE SAL > (SELECT AVG(SAL) FROM EMP r where r.deptno=e.deptno )
    -> ;
+-------+-------+-----------+------+------------+---------+--------+--------+
| empno | ename | job       | mgr  | hire       | sal     | comm   | deptno |
+-------+-------+-----------+------+------------+---------+--------+--------+
|  7499 | ALLEN | SALESMAN  | 7698 | 1981-02-20 | 1600.00 | 300.00 |     30 |
|  7566 | JONES | MANAGER   | 7839 | 1981-04-02 | 2975.00 |   NULL |     20 |
|  7698 | BLAKE | MANAGER   | 7839 | 1981-05-01 | 2850.00 |   NULL |     30 |
|  7788 | SCOTT | ANALYST   | 7566 | 1982-12-09 | 3000.00 |   NULL |     20 |
|  7839 | KING  | PRESIDENT | NULL | 1981-11-17 | 5000.00 |   NULL |     10 |
|  7902 | FORD  | ANALYST   | 7566 | 1981-12-03 | 3000.00 |   NULL |     20 |
+-------+-------+-----------+------+------------+---------+--------+--------+
6 rows in set (0.00 sec)
```


```sql

49. list all employees who earn sal < than their managers salary


mysql> SELECT * FROM EMP E
    ->         WHERE SAL < (SELECT SAL FROM EMP R WHERE R.EMPNO=E.MGR);
+-------+--------+----------+------+------------+---------+---------+--------+
| empno | ename  | job      | mgr  | hire       | sal     | comm    | deptno |
+-------+--------+----------+------+------------+---------+---------+--------+
|  7369 | SMITH  | CLERK    | 7902 | 1980-12-17 |  800.00 |    NULL |     20 |
|  7499 | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600.00 |  300.00 |     30 |
|  7521 | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250.00 |  500.00 |     30 |
|  7566 | JONES  | MANAGER  | 7839 | 1981-04-02 | 2975.00 |    NULL |     20 |
|  7654 | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00 | 1400.00 |     30 |
|  7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 2850.00 |    NULL |     30 |
|  7782 | CLARK  | MANAGER  | 7839 | 1981-06-09 | 2450.00 |    NULL |     10 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500.00 |    0.00 |     30 |
|  7876 | ADAMS  | CLERK    | 7788 | 1983-01-12 | 1100.00 |    NULL |     20 |
|  7900 | JAMES  | CLERK    | 7698 | 1981-12-03 |  950.00 |    NULL |     30 |
|  7934 | MILLER | CLERK    | 7782 | 1982-01-23 | 1300.00 |    NULL |     10 |
+-------+--------+----------+------+------------+---------+---------+--------+
11 rows in set (0.00 sec)


```


```SQL

50. list all employees who are earning more than average salary of their job

      mysql>   SELECT * FROM EMP E
    ->         WHERE SAL > (SELECT AVG(SAL) FROM EMP R WHERE R.JOB=E.JOB)
    -> ;
+-------+--------+----------+------+------------+---------+--------+--------+
| empno | ename  | job      | mgr  | hire       | sal     | comm   | deptno |
+-------+--------+----------+------+------------+---------+--------+--------+
|  7499 | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600.00 | 300.00 |     30 |
|  7566 | JONES  | MANAGER  | 7839 | 1981-04-02 | 2975.00 |   NULL |     20 |
|  7698 | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 2850.00 |   NULL |     30 |
|  7844 | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500.00 |   0.00 |     30 |
|  7876 | ADAMS  | CLERK    | 7788 | 1983-01-12 | 1100.00 |   NULL |     20 |
|  7934 | MILLER | CLERK    | 7782 | 1982-01-23 | 1300.00 |   NULL |     10 |
+-------+--------+----------+------+------------+---------+--------+--------+
6 rows in set (0.00 sec)



```


```SQL

51. display employee name and department
mysql> SELECT E.ENAME,D.DNAME
    -> FROM EMP E , DEPT D
    -> WHERE E.DEPTNO=D.DEPTNO;
+--------+------------+
| ENAME  | DNAME      |
+--------+------------+
| SMITH  | RESEARCH   |
| ALLEN  | SALES      |
| WARD   | SALES      |
| JONES  | RESEARCH   |
| MARTIN | SALES      |
| BLAKE  | SALES      |
| CLARK  | ACCOUNTING |
| SCOTT  | RESEARCH   |
| KING   | ACCOUNTING |
| TURNER | SALES      |
| ADAMS  | RESEARCH   |
| JAMES  | SALES      |
| FORD   | RESEARCH   |
| MILLER | ACCOUNTING |
+--------+------------+
14 rows in set (0.00 sec)



```