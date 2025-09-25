# Writing-Basic-SELECT-Queries
# in this i have made a database company in which 2 tables employee and Department created and fetched data by select, where, or , and , between, like, order by commands. 

create database company;
use company;
create table employee(
Emp_id int not null primary key,
Fname varchar(255) not null,
Lname varchar(255) not null,
Sex varchar(7) not null,
phone_number varchar(10),
Address varchar(50) ,
salary decimal(8,2));

insert into employee(Emp_id,Fname,Lname,Sex,phone_number,Address,salary) values ('001','Ramesh','Narayan','M','8525789614','Aurangabad,Bihar','30000'),
('002','Ahmad','Jabbar','M','8978456314','Pune, Maharashtra','40000'),('003','Shruti','Sharma','F','8514789645','Patna, Bihar','20000'),
('004','Sagar','Kumar','M','7845126396','Ameerpet,Hyderabad,Telangana','25000'),('005','Mahi','Sharma','F','7889748514','Mahe, Maharashtra','28000');

select * from employee where sex='M';
select Emp_id, Fname, Address from employee where salary> 25000 and Lname like 'S%';

select * from employee where sex='M' or salary>30000;
select * from employee where salary between 35000 and 40000;
select Emp_id,Fname,Lname,salary from employee order by salary desc;

create table Department(
Emp_id int,
Department_name varchar(50),
Designation varchar(50),
Budget decimal(8,2),
Foreign key(Emp_id) References employee(Emp_id));

insert into Department (Emp_id,Department_name,Designation,Budget) values ('002','Production','Accountant','120000'),('004','Development','Clerk','200000'),('001','Management','Typist','250000'),
('003','Human Resource','Clerk','230000'),('005','Sales','Executive','300000');

select Emp_id, Department_name from Department where Budget> 210000 and Department_name like 'S%';
select * from Department where  Designation='Executive' or Department_name ='Sales';
select * from Department where Budget between 180000 and 220000; 
select * from Department order by Emp_id desc;
