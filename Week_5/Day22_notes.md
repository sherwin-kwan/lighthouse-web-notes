# Day 22 - 13 Oct 2020

* New instructor: Vasily

### Entity Relations Diagrams (ERD)

* Entity: an object that the data belongs to e.g. users
* Relation: a link showing how the data for two or more objects is related to each other

### Naming Conventions

* *snake_case* is used for tables and fields
* tables are generally named in plural form (this is a big debate among devs, but LHL goes with plural)

### Data Types

* VARCHAR
* TEXT
* INTEGER
* FLOAT
* BOOLEAN

### Vasily's Tips

* Use "SERIAL" Postgres data type to auto-increment IDs for primary keys
* For currency, use BIGINT and multiply by 100

### Relationship Types

* One-to-one: one record in table A related to one record in table B
* One-to-many: one record in Table A related to many records in table B
* Many-to-many: multiple records in Table A related to multiple records in Table B
  * In this case, we normally don't actually link two tables in a many-to-many relatinoship; we'll have a *bridge table* C that has one-to-many relationships with both A and B

### Normalization

* Way of defining databases so as to reduce data duplication and ensure integrity
* Based on the work of Edgar Cobb, it is done in stages e.g. First Normal Form (1NF), Second Normal Form (2NF), etc.