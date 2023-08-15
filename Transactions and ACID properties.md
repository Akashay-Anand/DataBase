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


### Shadow-copy scheme
> Based on making copies of DB (aka, shadow copies).  
> Assumption only one Transaction (T) is active at a time.  
> A pointer called db-pointer is maintained on the disk; which at any instant points to current copy of DB.
> T, that wants to update DB first creates a complete copy of DB.  
> All further updates are done on new DB copy leaving the original copy (shadow copy) untouched.
> If at any point the T has to be aborted the system deletes the new copy. And the old copy is not affected.   

> If T success, it is committed as,  
>> * OS makes sure all the pages of the new copy of DB written on the disk.
>> * DB system updates the db-pointer to point to the new copy of DB.
>> * New copy is now the current copy of DB.
>> * The old copy is deleted.
>> * The T is said to have been COMMITTED at the point where the updated db-pointer is written to disk.

> Atomicity
>> * If T fails at any time before db-pointer is updated, the old content of DB are not affected.
>> * T abort can be done by just deleting the new copy of DB.
>> * Hence, either all updates are reflected or none.

> Durability
>> * Suppose, system fails are any time before the updated db-pointer is written to disk.
>> * When the system restarts, it will read db-pointer & will thus, see the original content of DB and none of the effects of T will be visible.
>> * T is assumed to be successful only when db-pointer is updated.
>> * If system fails after db-pointer has been updated. Before that all the pages of the new copy were written to disk. Hence, when system restarts, it will read new DB copy.

> The implementation is dependent on write to the db-pointer being atomic. Luckily, disk system provide atomic updates to entire block or at least a disk sector. So, we make sure db-pointer lies entirely in a single sector. By storing db-pointer at the beginning of a block.

> __Inefficient__, as entire DB is copied for every Transaction

### Log-based recovery methods

> The log is a sequence of records. Log of each transaction is maintained in some stable storage so that if any failure occurs, then it can be recovered from there.  
> If any operation is performed on the database, then it will be recorded in the log.   
> But the process of storing the logs should be done before the actual transaction is applied in the database.
> __Stable storage__ is a classification of computer data storage technology that guarantees atomicity for any given write operation and allows software to be written that is robust against some hardware and power failures.

> Deferred DB Modifications   
>> * Ensuring atomicity by recording all the DB modifications in the log but deferring the execution of all the write operations until the final action of the T has been executed.
>> * Log information is used to execute deferred writes when T is completed.
>> * If system crashed before the T completes, or if T is aborted, the information in the logs are ignored.
>> * If T completes, the records associated to it in the log file are used in executing the deferred writes.
>> * If failure occur while this updating is taking place, we preform redo.

> Immediate DB Modifications
>> * DB modifications to be output to the DB while the T is still in active state.
>> * DB modifications written by active T are called uncommitted modifications.
>> * In the event of crash or T failure, system uses old value field of the log records to restore modified values.
>> * Update takes place only after log records in a stable storage.
>> * Failure handling
>>> * System failure before T completes, or if T aborted, then old value field is used to undo the T.
>>> * If T completes and system crashes, then new value field is used to redo T having commit logs in the logs.