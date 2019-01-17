# SQL 2 - WHERE, subquery
#sql
```sql
select sID, sName
from Stduent
where sID in (select sID from Apply where major = 'CS');

select sName
from Student
where sID in (select sID from Apply where major = 'CS');

// duplicates really matters!
select sID, sName
from Student
where sID in (select sID from Apply where major = 'CS')
and sID not in (select sID from Apply where major = 'EE');
//  not sID in

select cName, state
from College C1
where exists 
(select * from College C2 where C2.state = C1.state and C1.cName <> C2.cName)；

// select the largest enrollment school
select cName
from College C1
where not exists (select * from College C2
					 where C2.enrollment > C1.enrollment);

// select highest GPA
select sName, GPA
from Student
where GPA >= all (select GPA from Student);

// you can change all to any (any one satisfies)

```
























