## Day 21 - 12 Oct 2020

### Databases

* This course focuses on relational databases, and specifically we will use PostgreSQL
* However, SQL (Structured Query Language) is standard and usable with all commercially-popular RDBMS
* In a relational database, data is stored in *tables*, where each *row* is a record and each *column* is a property
* After learning databases, we will have all of the tools necessary to build a whole web application: client-side/front-end, server code, database
* *Entity Relation Diagram* (ERD) - a graphical representation of how data is related to each other, important to do one before creating a database

### Important Commands and Syntax

* SELECT: make queries
* ORDER BY: orders the query results
* JOIN ____ ON ___ = _____: joins data from two different databases
  * After a JOIN, the ID of the second table (the one right after "JOIN" in the command) is used to display the results
* Remember: the equality operator is '=' (not '===' as in Javascript) and only single quotes are permitted
* There is a specific order that SQL commands in a query must be written (e.g. SELECT comes before WHERE)
* However, the SQL commands are not actually executed in the same order as they are written! (For example: WHERE commands execute before SELECT, so if you attempt to create a custom column using SELECT ____ AS ____, and attempt to order by the same column with a WHERE, it will throw an error)
* INNER JOIN: Inner joining A to B means "find all the records in A that match records in B, and return only those" (so records which are only found in A and have no relation to any data in B will not return)
* LEFT JOIN: Returns all data from table A, and all records in table B that have a relation to some data in A
* RIGHT JOIN: Returns all data from table B, and all records in table A that have a relation to some data in B
* OUTER JOIN: Returns all data in A or B, regardless of whether it matches the other table
* LIMIT N: limits results to first N results
* OFFSET: use with "limit" to get the second page of results (LIMIT 10 OFFSET 10 shows the 11th to 20th records); these go at the end

### Hafiz's Tips

* NOW() in Postgres for the current date/time
* 'ORDER BY -name' alias of 'ORDER BY name DESC' in postgres
* Commands are not run in the same order that they are typed