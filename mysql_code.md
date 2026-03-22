create database collage;
use collage;
create table students(
class int check (class>=1 and class <= 12),
rollno int primary key,
name varchar(50),
marks int check (marks >= 0 and marks <=100),
grade float check (grade >= 0 and grade <= 10),
city varchar(50)
);
insert into students 
(class,rollno,name,marks,grade,city)
values
(10,29,"anmol",44,7.6,"delhi"),
(11,24,"anmol0",45,7.7,"delhi1"),
(12,25,"anmol1",46,7.8,"delhi3"),
(10,26,"anmol2",47,7.9,"delhi1"),
(9,27,"anmol3",48,7.1,"delhi3"),
(8,28,"anmol4",49,7.2,"delhi4")
;
select * from students where (grade >= 7.3);
select name from students;
select distinct city from students;
select * from students where marks between 45 and 48;
select * from students where city in ("delhi1","delhi2");
select * from students limit 3;
select * from students order by grade asc;
select max(marks) from students;
select avg(marks) from students;
select min(marks) from students;
select sum(marks) from students;
select count(marks) from students;

select city from students group by city;
select city,avg(marks) from students group by city order by city;
select count(name),city from students group by city having max(marks) > 43 ;  
set sql_safe_updates = 0 ;
update students set grade = 8 where grade >= 7.3;
update students set grade = grade - 1 ;
delete from students where grade < 7;
alter table students add column age int not null default 19;
alter table students modify column age varchar (2);
alter table students drop column age ;
alter table students rename to student;
create view view1 as select rollno,marks from student;
select name from student where marks > (select avg(marks) from student);
select name from student where rollno % 2 = 0;


create database collage;
use collage;
create table students(
class int check (class>=1 and class <= 12),
rollno int primary key,
name varchar(50),
marks int check (marks >= 0 and marks <=100),
grade float check (grade >= 0 and grade <= 10),
city varchar(50)
);
insert into students 
(class,rollno,name,marks,grade,city)
values
(10,29,"anmol",44,7.6,"delhi"),
(11,24,"anmol0",45,7.7,"delhi"),
(12,25,"anmol1",46,7.8,"delhi1"),
(10,26,"anmol2",47,7.9,"delhi1"),
(9,27,"anmol3",48,7.1,"delhi3"),
(8,28,"anmol4",49,7.2,"delhi4")
;
create table department(
id int primary key,
name varchar(50));
create table teacher(
id int primary key,
name varchar(50),
did int,
foreign key (did) references department(id)
on update cascade
on delete cascade
);


create database office;
use office ;
create table employee(
id int primary key,
name varchar(50));
insert into employee
(id,name)
value
(1,"anmol"),
(2,"ayush"),
(3,"dubey"),
(4,"ji");

create table salary(
id int primary key,
salaary int);
insert into salary
(id,salaary)
values
(1,10000),
(2,20000),
(3,30000),
(4,40000);

select * from employee inner join salary on employee.id = salary.id;
select * from employee left join salary on employee.id = salary.id;
select * from employee right join salary on employee.id = salary.id;
select * from employee left join salary on employee.id = salary.id union select * from employee right join salary on employee.id = salary.id;


