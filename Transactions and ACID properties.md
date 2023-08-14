# transaction

> A unit of work done against the DB in a logical sequence     

> It is a logical unit of work that contains one or more SQL statements. The result of all these statements in a
transaction either gets completed successfully (all the changes made to the database are permanent) or if at any
point any failure happens it gets rollbacked (all the changes being done are undone.)

## ACID Properties

> To ensure integrity of the data, we require that the DB system maintain the following properties of the transaction.

### Atomicity
> Either all operations of transaction are reflected properly in the DB, or none are.

### Consistency 
> Integrity constraints must be maintained before and after transaction.
> DB must be consistent after transaction happens.

### Isolation
> Multiple transactions can happen in the system in isolation, without interfering each other.

> Even though multiple transactions may execute concurrently, the system guarantees that, for every pair of transactions Ti and Tj, it appears to Ti that either Tj finished execution before Ti started, or Tj started execution after Ti finished. Thus, each transaction is unaware of other transactions executing concurrently in the system.

### Durability 
> After transaction completes successfully, the changes it has made to the database persist, even if there are system failures.

<hr/>

<br/>
<br/>

## How to implement Atomicity and Durability in Transactions


