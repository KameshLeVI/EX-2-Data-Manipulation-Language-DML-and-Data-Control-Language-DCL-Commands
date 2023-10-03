# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/8b8fcaaf-7b1e-4b41-aa2e-3f868a750be1)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```
delete from manager where salary<2750;
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/8319c682-9627-4fdd-adeb-21bd6cb24073)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
select ename as "Name",salary*12 as "Annual salary" from manager;
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/af6e2497-245b-406b-8e91-3d939c0fce4d)

### Q5)	List the names of Clerks from emp table.


### QUERY:
```
select ename from manager where designation='clerk';
```


### OUTPUT:

![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/3d8920f1-ad7f-4257-861e-699ea29e5f8e)

### Q6)	List the names of employee who are not Managers.


### QUERY:
```
select ename from manager where designation <> 'manager';
```
### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/db26cb9b-82df-4e08-933d-dfe2a2c2e069)

### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/652ff9ae-5826-4e33-96b5-8d4cc25afed0)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/52a55bfa-6bf5-428c-9955-b6ac7368f74f)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/2aca5960-55b1-4a3f-957b-d88839995e3b)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/48bc9e7b-1c80-4a55-aca7-5245872e6769)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```

### OUTPUT:

![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/e4430d89-3b3f-4b23-b79f-5a06e0b7f1b8)

### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/ee65391a-77fb-4d42-9f95-d977b76fa75e)

### Q13) Find number of rows in the table EMP

### QUERY:
```
select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/c0c414b8-2ddf-43e4-84d2-709e81c0d192)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select max(salary) from manager;
select min(salary) from manager;
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/cec5e616-46ca-4c9a-b889-0e79f09d004f)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;
```

### OUTPUT:
![image](https://github.com/KameshLeVI/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/120780633/4ba3f03d-f308-43a4-babb-6956d517db55)
