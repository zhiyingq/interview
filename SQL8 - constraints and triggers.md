# SQL8 - constraints and triggers
#sql

Non-null constrain
Key constrain 
Referential integrity (foreign key)
Attribute-based constrain
Tuple-based constrain
General assertions

```
Declaration & Enforcement of constraints
Declaration
	- with origin schema
Enforcement
	- check after every modification/transaction
```

Constrains
```sql
create table Student(sID int, sName text, GPA real not null, sizeHS int);
create table Student(sID int primary key, sName text, GPA real, sizeHS int);
create table Student(sID int primary key, sName text unique); // to make sName unique
create table Student(sID int, sName text, GPA real not null, primary key (sID, sName));
create table Student(sID int, sName text, GPA real not null, unique (sID, sName));

create table Student(sID int, GPA real check(GPA <= 4.0 and GPA > 0.0), size int check (size < 4000));
create table Apply(sID int, decision text, cName text, major text, check(decision = 'N' or cName <> 'Standford' or major <> 'CS'));

create assertion Key
check (....)

create table Apply(sID int references Student(sID) on delete set null, cName text references College (cName) on update cascade, major text, decision text);

drop table Student;

```


Triggers
“Event-Condition-Action Rules”
When event occurs, check condition; if true, do action
```sql
Create Trigger name
Before | After | Instead of events
[ referencing-variables ]
[ For Each Row ]
When (condition)
action



```


























