# Relational Model (RM)   
it organises the data in the form of relations (tables).   

> A relational DB consists of collection of tables, each of which is assigned a unique name.
> Relation Schema: defines the design and structure of the relation, contains the name of the relation and all the
columns/attributes.

> A row in a table represents a relationship among a set of values, and table is collection of such relationships.
>. Tuple: A single row of the table representing a single data point / a unique record.
>  Columns: represents the attributes of the relation. Each attribute, there is a permitted value, called domain of the
attribute.
> Relation Schema: defines the design and structure of the relation, contains the name of the relation and all the
columns/attributes.
7. Common RM based

> Degree of table: number of attributes/columns in a given table/relation.

> Relational Model Keys
1. Super Key (SK): Any P&C of attributes present in a table which can uniquely identify each tuple.
2. Candidate Key (CK): minimum subset of super keys, which can uniquely identify each tuple. It contains no
redundant attribute.
1. CK value shouldn’t be NULL.
3. Primary Key (PK):
1. Selected out of CK set, has the least no. of attributes.
4. Alternate Key (AK)
1. All CK except PK.
5. Foreign Key (FK)
1. It creates relation between two tables.
2. A relation, say r1, may include among its attributes the PK of an other relation, say r2. This attribute is called FK
from r1 referencing r2.
3. The relation r1 is aka Referencing (Child) relation of the FK dependency, and r2 is called Referenced (Parent)
relation of the FK.
4. FK helps to cross reference between two different relations.
6. Composite Key: PK formed using at least 2 attributes.
7. Compound Key: PK which is formed using 2 FK.
8. Surrogate Key:
1. Synthetic PK.
2. Generated automatically by DB, usually an integer value.
3. May be used as PK.  
