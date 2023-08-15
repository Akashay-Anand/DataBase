# Indexing in DBMS

__Indexing is used to optimise the performance of a database by minimising the number of disk accesses required when a query is processed.__

* The index is a type of data structure. It is used to locate and access the data in a database table quickly.
* Speeds up operation with read operations like SELECT queries, WHERE clause etc.
* Search Key: Contains copy of primary key or candidate key
* Index file is always sorted.

## Indexing Methods

1. Primary Index (Clustering Index)

> A file may have several indices, on different search keys. If the data file containing the records is sequentially ordered, a Primary index is an index whose search key also defines the sequential order of the file.

> NOTE: The term primary index is sometimes used to mean an index on a primary key. However, such usage is nonstandard and should be avoided.

> All files are ordered sequentially on some search key. It could be Primary Key or non-primary key.


2. Secondary Index (Non-Clustering Index)

> Datafile is unsorted. Hence, Primary Indexing is not possible.
> Can be done on key or non-key attribute.
> Called secondary indexing because normally one indexing is already applied.
> It's an example of Dense index.


//////////////////////////////////////////////////////////////////////

Q) Benifits of Indexing

Ans: Faster access and retrieval of data. and IO is less

Q) Limitations of Indexing

Ans: Additional space to store index table.  
     Indexing Decrease performance in INSERT, DELETE, and UPDATE query.  

