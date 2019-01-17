# SQL 1 SELECT and FROM, subquery
#sql

```sql
select distinct sName, major from Student, Apply where Student.sID = Apply.sID and major = 'CS' and cname = 'Stanford' order by sName desc, major;

select sID, major from Apply where major like '%bio%';
select * from Student, College;
select GPA*(sizeHS/1000.0) as scaledGPA from Student;

// like syntax:
select ... from ... where name like 'a%'
like:
'a%': starts with a
'%a': ends with a
'%or%': any values that have "or" in any position
'a%o': starts with a and ends with o

select column from table 
where condition
limit number

// 重命名变量
select S.sName 
from Student S, College C, Apply A
where A.sID = S.sID;

select s1.sID, s2.sID
from Student s1, Student s2
where s1.GPA = s2.GPA and s1.sID > s2.sID;

// unify the college names and student names
select cName as name from College
union all
select sName as name from Stduent
order by name;

// intersect
select sID from Apply where major = 'CS'
intersectg
select sID from Apply where major = 'EE';

// except
select sID from Apply where major = 'CS'
except
select sID from Apply where major = 'EE';


```

```sql
// function: min abs
select *
from (select GPA*(sizeHS/1000.0) as scaledGPA from Student) G
where abs(G.scaledGPA - GPA) > 1.0;

```






















