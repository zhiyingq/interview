# SQL5 - DATA MODIFICATION
#sql

```sql
Insert Into Table Values (A1, A2, ..., An)
Insert Into Table Select-Statement

INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

INSERT INTO table_name
VALUES (value1, value2, value3, ...);

Delete From Table Where Condition

Update Table 
Set Attr = Expression, A2 = Expr2, ..., An = Exprn 
Where Condition

insert into table (select ..... )

// insert multiple columns
insert into Rating (rID, mID, stars, ratingDate)
select rID, mID, 5, NULL
from Movie, Reviewer
where Reviewer.name = "James Cameron"
```


Create table
```sql
create table Student(sID int primary key, sName text unique); // to make sName unique
create table Student(sID int, sName text, GPA real not null, primary key (sID, sName));
create table Student(sID int, sName text, GPA real not null, unique (sID, sName));

# char(size): Holds a fixed length string (can contain letters, numbers, and special characters). The fixed size is specified in parenthesis. Can store up to 255 characters
# varchar(size): Holds a variable length string (can contain letters, numbers, and special characters). The maximum size is specified in parenthesis. Can store up to 255 characters. Note: If you put a greater value than 255 it will be converted to a TEXT type
# text: Holds a string with a maximum length of 65,535 characters

CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255) 
);

CREATE TABLE TestTable AS
SELECT customername, contactname
FROM customers;
```















