# EXPERIMENT 2
**Date:** 31-01-2026  

# Perform Following Queries using Employee Table (Retrieving Data)

## 1. List all distinct jobs in Employee.

```sql
SELECT DISTINCT job FROM emp;
```

```
+-----------+
| job       |
+-----------+
| CLERK     |
| SALESMAN  |
| MANAGER   |
| ANALYST   |
| PRESIDENT |
+-----------+
```

---

## 2. List all information about employees in Department Number 30.

```sql
SELECT * FROM emp WHERE deptno = 30;
```

```
+-------+--------+----------+------+------------+------+------+--------+
| empno | ename  | job      | mgr  | hiredate   | sal  | comm | deptno |
+-------+--------+----------+------+------------+------+------+--------+
| 7499  | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600 | 300  | 30     |
| 7521  | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250 | 300  | 30     |
| 7654  | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250 | 1400 | 30     |
| 7698  | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 2850 | NULL | 30     |
| 7844  | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500 | 0    | 30     |
| 7900  | JAMES  | CLERK    | 7698 | 1981-12-03 | 950  | NULL | 30     |
+-------+--------+----------+------+------------+------+------+--------+
```

---

## 3. Find all jobs of employees working in departments greater than 20.

```sql
SELECT job FROM emp WHERE deptno > 20;
```

```
+----------+
| job      |
+----------+
| SALESMAN |
| SALESMAN |
| SALESMAN |
| MANAGER  |
| SALESMAN |
| CLERK    |
+----------+
```

---

## 4. Find all information about managers as well as clerks in department 30.

```sql
SELECT * FROM emp
WHERE job IN ('MANAGER','CLERK')
AND deptno = 30;
```

```
+-------+-------+---------+------+------------+------+------+--------+
| empno | ename | job     | mgr  | hiredate   | sal  | comm | deptno |
+-------+-------+---------+------+------------+------+------+--------+
| 7698  | BLAKE | MANAGER | 7839 | 1981-05-01 | 2850 | NULL | 30     |
| 7900  | JAMES | CLERK   | 7698 | 1981-12-03 | 950  | NULL | 30     |
+-------+-------+---------+------+------------+------+------+--------+
```

---

## 5. List employee name, employee number and department of all clerks.

```sql
SELECT empno, ename, deptno FROM emp WHERE job = 'CLERK';
```

```
+-------+-------+--------+
| empno | ename | deptno |
+-------+-------+--------+
| 7369  | SMITH | 20     |
| 7876  | ADAMS | 20     |
| 7900  | JAMES | 30     |
+-------+-------+--------+
```

---

## 6. Find all managers not in department 30.

```sql
SELECT * FROM emp
WHERE job = 'MANAGER'
AND deptno != 30;
```

```
+-------+-------+---------+------+------------+------+------+--------+
| empno | ename | job     | mgr  | hiredate   | sal  | comm | deptno |
+-------+-------+---------+------+------------+------+------+--------+
| 7566  | JONES | MANAGER | 7839 | 1981-04-02 | 2975 | NULL | 20     |
| 7782  | CLARK | MANAGER | 7839 | 1981-06-09 | 2450 | NULL | 20     |
+-------+-------+---------+------+------------+------+------+--------+
```

---

## 7. List employees in department 10 who are not managers or clerks.

```sql
SELECT * FROM emp
WHERE deptno = 10
AND job NOT IN ('MANAGER','CLERK');
```

```
Empty set
```

---

## 8. Find employees and jobs earning between 1200 and 1400.

```sql
SELECT ename, job
FROM emp
WHERE sal BETWEEN 1200 AND 1400;
```

```
+--------+----------+
| ename  | job      |
+--------+----------+
| WARD   | SALESMAN |
| MARTIN | SALESMAN |
+--------+----------+
```

---

## 9. List name and department number of clerks, analysts or salesmen.

```sql
SELECT ename, deptno
FROM emp
WHERE job IN ('CLERK','ANALYST','SALESMAN');
```

```
+--------+--------+
| ename  | deptno |
+--------+--------+
| SMITH  | 20     |
| ALLEN  | 30     |
| WARD   | 30     |
| MARTIN | 30     |
| SCOTT  | 20     |
| TURNER | 30     |
| ADAMS  | 20     |
| JAMES  | 30     |
| FORD   | 20     |
+--------+--------+
```

---

## 10. List name and department number of employees whose names begin with M.

```
