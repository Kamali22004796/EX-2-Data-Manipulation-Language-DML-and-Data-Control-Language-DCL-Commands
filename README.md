# EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands
# AIM:
To create a manager database and execute DML queries using SQL.

# DML(Data Manupulation Language)
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data

Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that

controls access to data and to the database. Basically, DCL statements are grouped with DML statements.

# List of DML commands:
INSERT: It is used to insert data into a table.

UPDATE: It is used to update existing data within a table.

DELETE: It is used to delete records from a database table.

# Create the table as given below:
```
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
# insert the following values into the table
```
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
# QUERY:
```
SQL> update manager set salary = (salary*0.10)+ salary ;
```
OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/e8329ffb-e2ec-4104-85a7-51a3f1dfc826)

Q2) Delete the records from manager table where the salary less than 2750.
# QUERY:
```
SQL> delete worker where salary<2750;
```
# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/d6936d5a-b4cc-43e0-bf34-b63f3a7f6fce)


Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)
# QUERY:
```
SQL> SELECT
2  ename AS "name",

3  salary * 12 AS "Annual Salary" 

4  FROM

5  manger ;
```

# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/e922dfce-d570-4a27-8154-506b76fb3555)


Q5) List the names of Clerks from emp table.
# QUERY:
```
SQL> select ename from empn where designation='clerk' ;

```

# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/77db399a-0fcd-4bd5-a8b1-8dd2bc0f02a4)


Q6) List the names of employee who are not Managers.
# QUERY:
```
SQL> select ename from empn where designation !='manager' ;
```
# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/febd8f25-bb96-41a7-bbc2-7a72b0ea55fd)


Q7) List the names of employees not eligible for commission.
# QUERY:
```
SQL> select ename from empn where commission=0;
```

OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/b5af2d54-c02d-4fcf-ace9-5f6d5ec9898b)


Q8) List employees whose name either start or end with ‘s’.
# QUERY:
```
SQL> select ename from empn where ename LIKE 'S%' OR ename LIKE '%s';
```

# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/a1540ba6-1f5e-489f-ae54-4436ec03c9f0)


Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
# QUERY:
```
SQL> SELECT ename, designation, deptno, hiredate

2 from empn

3 order by hiredate ASC;
```

# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/84d19286-b13a-4403-9f9e-7a9a27f75964)


Q10) List the Details of Employees who have joined before 30 Sept 81.
# QUERY:
```
SQL> SELECT * FROM empn WHERE hiredate <'30 sep 81';
```
# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/4419372d-046f-448d-9d1d-eceb0978c9f0)


Q11) List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
# QUERY:
```
SQL> SELECT ename, designation, salary from empn ORDER BY deptno ASC, salary DESC;
```
# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/7991953b-3766-4935-85fd-e2158a0e61e2)


Q12) List the names of employees not belonging to dept no 30,40 & 10
# QUERY:
```
SQL> SELECT ename from empn WHERE deptno NOT IN (30, 40, 10);
```
# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/15e03759-65ae-4358-8118-ef812766e9b1)


Q13) Find number of rows in the table EMP
# QUERY:
```
SQL> SELECT COUNT(*) AS num_rows FROM empn;
```
# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/43dca89d-d062-4d87-abb0-6167c5f9e66b)


Q14) Find maximum, minimum and average salary in EMP table.
# QUERY:
```
SQL>SELECT MAX(salary) AS max_salary.MIN(salary) AS min_salary.AVG(salary) ASavg_salary FROM empn;
```

# OUTPUT:

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/ff70311a-2805-4e64-a44a-5553ccd03d23)


Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees. QUERY : SELECT designation, COUNT() AS "Number of Employees" FROM manager GROUP BY designation ORDER BY COUNT() DESC; OUTPUT :

![image](https://github.com/Kamali22004796/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120567837/d5ff1349-7620-49fb-a0c5-9fa7fce8408a)


# RESULT :

Thus, Manager database is created and DML queries such as insertion, updation, deletion are executed using SQL.
