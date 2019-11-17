# Why learn SQL?
In this data-driven world, people derive insights and make decisions through data. I have prepared a short introduction to the basics of SQL. 

# What is SQL?
SQL stands for Structured Query Language. SQL is a database language used to design and manage data in the relational database. All the relational databases such as MySQL, Oracle, Postgres, SQL Server use SQL as their standard database language. The data in RDBMS stores in database objects called tables. A table is a collection of related data entries, and it consists of columns and rows.

# What Can SQL do?
* Allows users to access data in the relational database management systems.
* Allows users to define the data in a database and manipulate that data.
* Allows embedding within other programming languages using SQL modules, libraries & pre-compilers.

# CREATE TABLE
Creating a basic table involves 
* naming the table
* defining its columns and each column's data type.

The rules to apply to the table.
* ```PRIMARY KEY``` constraint can be used to identify the row uniquely.
* ```NOT NULL``` columns must have a value.
* ```DEFAULT``` assigns a default value for the column when no value is specified.

## Syntax
```
CREATE TABLE table_name(
   column1 datatype,
   column2 datatype,
   column3 datatype,
   .....
   columnN datatype,
   PRIMARY KEY( one or more columns )
);
```

## Example 
```
CREATE TABLE Person (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255),
    PRIMARY KEY(PersonID)
);
```

# INSERT 
Insert new records in a table.

## Syntax
```
INSERT INTO TABLE_NAME (column1, column2, column3,...columnN)  
VALUES (value1, value2, value3,...valueN);

INSERT INTO TABLE_NAME
VALUES (value1, value2, value3,...valueN);
```

## Example 
```
INSERT INTO Person (PersonID,LastName,FirstName,Address,City)
VALUES (1, 'Wilson', 'Anna', 'Block 8, Beach Road', 'Singapore');
INSERT INTO Person (PersonID,LastName,FirstName,Address,City)
VALUES (2, 'Yoong', 'Li Yen', 'Tampines', 'Singapore');
```

# SELECT 
Select queries are our best friend when we want to fetch data from the database.

## Syntax
```
SELECT column1, column2, columnN FROM TABLE_NAME;
SELECT * FROM TABLE_NAME;

SELECT column1, column2, columnN 
FROM TABLE_NAME
WHERE [condition];
```

```WHERE``` clause, allowing us to filter data depending on a condition.
Also, the logical operators (AND,OR) and math-like comparisons (=,<,>,<=,>=,<>).

## Example
```
SELECT * FROM Person;
SELECT LastName, FirstName FROM Person;
```

# UPDATE
Change or amend the data in some of the rows or entire table in the database. The usage of UPDATE consists of
* Selecting the table where the record we want to change.
* Setting new value(s) for the wanted column(s).
* Selecting with ```WHERE``` condition, which of the rows we want to update. If this is omitted, all rows in the table will change.

## Syntax
```
UPDATE TABLE_NAME
SET column1 = value1, column2 = value2...., columnN = valueN
WHERE [condition];

UPDATE TABLE_NAME
SET column1 = value1, column2 = value2...., columnN = valueN;
```

## Example
```
UPDATE Person
SET Address = 'Tampines Ave 9'
WHERE PersonID = 2;
```

# DELETE 
Delete existing records from a table. Be careful when deleting records from a table. If the ```WHERE``` condition is omitted, all rows in the table will delete.

## Syntax
```
DELETE FROM TABLE_NAME
WHERE [condition];

DELETE FROM TABLE_NAME;
```

## Example
```
DELETE FROM Person
WHERE PersonID = 2;
```

# TRUNCATE TABLE 
If you want to delete all the rows in the table, you can perform a ```TRUNCATE TABLE``` statement. This statement truncates (removes) all the data inside the table, and the table remains in the database.

## Syntax
```
TRUNCATE TABLE TABLE_NAME;
```

# DROP TABLE
If you want to delete a table, you can perform a ```DROP TABLE``` statement. This statement delete the entire table from the database.

## Syntax
```
DROP TABLE TABLE_NAME;
```

# Advance Basic SQL
SQL is packed with functions that do all sorts of helpful stuff. Here are some of the most regularly used ones:

* COUNT() - returns the number of rows
* SUM() - returns the total sum of a numeric column
* AVG() - returns the average of a set of values
* MIN() / MAX() - gets the minimum/maximum value from a column

# References
* https://www.w3schools.com/sql/default.asp
* https://www.tutorialspoint.com/sql/index.htm
