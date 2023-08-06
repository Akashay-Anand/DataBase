> Different types of databases use different data structures to efficiently store and manage data. Here are some common data structures used in various types of databases:  

## Relational Databases (RDBMS):

> Tables: In relational databases, data is organized into tables with predefined columns and rows. Each row represents a record, and each column represents a field of data.   

> The tables in a relational database don't use a specific data structure like a linked list, array, or hashmap to store data internally. Instead, the database management system (DBMS) employs various data structures and algorithms to efficiently store and manage the data within the tables.

> Internally, a relational database may use data structures such as B-trees, indexes, and hash tables to optimize data retrieval, insertion, and updates. These data structures allow the DBMS to quickly locate and access specific rows and columns in the table based on keys and perform operations efficiently.

> The choice of internal data structures depends on the DBMS implementation, storage engine, and the specific requirements of the database...   

#### where new row will be inserted in the table
>  the decision on where to insert new data is made by the DBMS based on the defined table structure, primary key, indexes, storage model, and concurrency control mechanisms to ensure efficient data management and retrieval.

> Primary Key: If the table has a primary key, which is a unique identifier for each record (row), The DBMS may use the primary key's value to determine where the new record should be inserted.

> Indexes: If the table has any indexes defined on specific columns, the DBMS may use these indexes to speed up data retrieval and insertion. For example, a B-tree index allows for efficient search and insertion based on indexed column values.

> n most cases, new entities (rows) are appended at the end of the table, especially in heap-based storage models. This is because appending new data at the end is more efficient and reduces the need for data movement when new records are inserted.
> However, in some scenarios, the data may not be inserted at the end. For example:
>> If a table is indexed, the DBMS may insert new data at the appropriate position within the index to maintain the index's sorted order.  
>> If the table has a clustered index (common in some database systems), new data may be inserted in a specific location based on the index structure.
>> 
