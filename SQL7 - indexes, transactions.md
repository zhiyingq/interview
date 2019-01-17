# SQL7 - indexes, transactions
#sql

Indexes
```sql
DBMS'S build indexes automatically on PRIMARY KEY (and sometimes UNIQUE) atrributes
Hash-based indexes: can only be used for equality conditions
Tree-based indexes: can be used for equality & less than, larger than conditions
- To improve performance on a database

Cons:
1. Extra space - marginal
2. Index creation - medium 
3. Index maintenance - can offset benefits

Create Index IndexName on T(A)
Create Index IndexName on T(A1, A2, ..., An)
CREATE INDEX idx_lastname ON Persons (LastName);
Create Unique Index IndexName on T(A)
# duplicate keys are not allowed
DROP INDEX index_name ON tbl_name

```

Tranactions
```
Transaction: a sequence of one or more SQL operations treated as a unit
ACID Properties

Atomicity: (logging)  ,ætə'misəti
	each transaction is "all-or-nothing", never left half done
	transaction rollback (=abort):
		undoes partial effects of transaction
		can be system- or cliend-initiated

Consistency:
	each client, each transaction:
	can assume all constraints hold when transaction begins
	must guarantee all constraints hold when transaction ends
	serializability => 

Isolation: Seriaizability
	(locking)
	operations may be interleaved, but execution must be equivalent to some serial order of all transactions

Durability: (logging)
	if system crashes, after transaction commits, all effects of transaction remain in database
```


```
Isolation levels

1. Read Uncommitted
A transaction may perform dirty reads
Set Transaction Isolation Level Read Uncommitted;
"The update command in T1 can update the values in either order, and the select command in T2 can compute the average at any point before, between, or after the updates."

2. Read Committed
A transaction may not perform dirty reads
still does not guarantee global serializability
可能第二个T里面的第二个statement读取了第一个Tcommited过后的结果，但是第一个statement读取了第一个T里面未commit的结果

3. Repeatable Read
	A transaction may not perform dirty reads
	An item read multiple times cannot change value
	Still does not guarantee global serializability
	<Phantom Tuples> happens when you insert blocks

4. Read Only Transactions
	Set Transaction Read Only
	
Summary:
	Standard default: Serializable
	Weaker isolation levels:
	-increased concurrency
	-decreased overhead
	-increased performance
	-weaker consistency guarantees
	
	Isolation level per transaction and "eye of the beholder"



```















