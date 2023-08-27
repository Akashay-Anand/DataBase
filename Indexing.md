# Indexing in DBMS

__Indexing is used to optimise the performance of a database by minimising the number of disk accesses required when a query is processed.__

> The index concept in SQL is same as the index concept in a book.

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

## Index requirments

* Indexes can search the information of the large database quickly.
* Each Index table contains only two columns. The first column is row_id, and the other is indexed-column.
* This data structure sorts the data values of columns (fields) either in ascending or descending order. And then, it assigns the entry for each value.


<hr/>

### Key points //////////////////////////////////////////////////////////////////////

> The drawback of using indexes is that they __slow down the execution time of UPDATE and INSERT statements__. But they have one advantage also as they __speed up the execution time of SELECT and WHERE statements__.

> The creation and deletion of the Index do not affect the data of the database

Q) Benifits of Indexing

Ans: Faster access and retrieval of data. and IO is less 

Q) Limitations of Indexing

Ans: Additional space to store index table.  
     Indexing Decrease performance in INSERT, DELETE, and UPDATE query.  


<hr/>
<hr/>



## Practical on Indexing 

```sql
-- EXAMPLE OF CREATING INDEX  

-- basic syntex
CREATE INDEX index_name ON table_name (column_name1, column_name2, ...);
-- index_name is the name given to the index
-- table_name is the name of the table on which the index is to be created
-- column_name1, column_name2, ... are the names of the columns to be included in the index

-- If we want to create an index on the combination of two or more columns, then the following syntax can be used in SQL:
CREATE INDEX Index_Name ON Table_Name ( column_name1, column_name2, ...., column_nameN);  

-- Employee table:
Emp_Id |	Emp_Name  | Emp_Salary   |	Emp_City  |	Emp_State
101  |	Akashay   |	65000     |	Patna     |	Bihar
102  |	Ram       |	35000     |	Lucknow   |	U.P
103  |	Sahil     |	30000     |	Jalandhar |	Punjab
104  |	Adarsh    |	55000     |	Borobali  |	Mumbai
101  |	Rohit     |	55000     |	Motihari  |	Bihar

-- Indexing for employee table (Duplicate values are allowed)

CREATE INDEX index_state ON Employee (Emp_State);  
-- [Note]  indexing is often used on columns with unique values. However, indexing can also be beneficial for columns with duplicate values, especially when those columns are frequently used for filtering, searching, or sorting operations.


-- index on the combination of the Emp_city and the Emp_State column
CREATE INDEX index_city_State ON Employee (Emp_City, Emp_State);  


-- UNIQUE INDEX for Unique Values (Duplicate values are not allowed)

CREATE UNIQUE INDEX index_salary ON Employee (Emp_Salary);   -- this id WRONG; salary have duplicate values !!!!!
-- Unique indexes are meant to enforce the uniqueness of values in a column, which means that no two rows can have the same value in the indexed column.

CREATE INDEX index_state ON Employee (Emp_Id);  

-- ////////

-- Rename an INDEX
ALTER INDEX old_Index_Name RENAME TO new_Index_Name;


-- DROP INDEX Statement (delete an index in a table.)
ALTER TABLE table_name DROP INDEX index_name;

```