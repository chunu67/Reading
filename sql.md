# Needed Commands
``` sql
USE DATABASES; 
SHOW DATABASES; 
DESC TABLE;
```

# CREATE 

CREATE DATABASE DatabaseName; 

> Common look for creating of a table

``` sql 
CREATE TABLE table_name(
    column1 datatype,
    column2 datatype,
    column3 datatype,
    .....
    columnN datatype,
    PRIMARY KEY( one or more columns )
);
```
> Explained 

``` sql 
CREATE TABLE table_name(
      column1 datatype, 
      id INT        Not Null ,
```
> column_name is `id`, datatype is `INT` ,`Not Null` was constrains

```sql
      NAME VARCHAR (20) NOT NULL,
```

> column_name is `NAME`, datatype is `VarChar`,And `(20)` is the size of `VARCHAR`.



> Exeact command

```sql
CREATE TABLE CUSTOMERS(
    ID   INT            NOT NULL,
    NAME VARCHAR (20)   NOT NULL,
    AGE  INT            NOT NULL,
    ADDRESS CHAR (25) ,
    SALARY DECIMAL (18, 2),
    PRIMARY KEY (ID)
);
```


# ALTER 

*ALTER TABLE command is used to add, delete or modify columns in an existing table.*

```sql
ALTER TABLE table_name
    ADD column_name datatype;
    DROP COLUMN column_name;
    MODIFY COLUMN column_name datatype;
    MODIFY column_name datatype NOT NULL;
```
*The syntax of an ALTER TABLE command to ADD UNIQUE CONSTRAINT to a table
is as follows.*

```sql
ADD CONSTRAINT MyUniqueConstraint UNIQUE(column1, column2...);
```

# DROP or DELETE Table 
*DROP TABLE statement is used to remove a table definition and all the data,
indexes, triggers, constraints and permission specifications for that table.*

```sql
DROP TABLE table_name;
```

# INSERT INTO 

*The SQL INSERT INTO Statement is used to add new rows of data to a table in the
database.*

``` sql
INSERT INTO TABLE_NAME (
    column1, column2, column3,...columnN )]
VALUES (
    value1, value2, value3,...valueN );
```

e.g command 

```sql

INSERT INTO CUSTOMERS (ID,NAME,AGE,ADDRESS,SALARY)
VALUES (1, 'Ramesh', 32, 'Ahmedabad', 2000.00 );
```

> WithOut Table_Name , Put all values in VALUES field It insert all values 

```sql
INSERT INTO CUSTOMERS
VALUES (7, 'Muffy', 24, 'Indore', 10000.00 );
``` 

##### Populate one table using another table 
*You can populate the data into a table through the select statement over another table
. like import your data*

```sql  
INSERT INTO first_table_name [(column1, column2, ... columnN)]
SELECT column1, column2, ...columnN
FROM second_table_name
[WHERE condition];
```

# SELECT 
*SELECT statement is used to fetch the data from a database table which returns
this data in the form of a result table.*

```sql
SELECT column1, column2, columnN FROM table_name;
SELECT * FROM table_name; >for all column
```

# WHERE CLAUSE

*The SQL WHERE clause is used to specify a condition while fetching the data from a single
table or by joining with multiple tables. If the given condition is satisfied, then only it
returns a specific value from the table. You should use the WHERE clause to filter the
records and fetching only the necessary records.
The WHERE clause is not only used in the SELECT statement, but it is also used in the UPDATE, DELETE statement.
When you use programing language like nodejs and use `sequlize` module for accessing the databases.*
 

```sql
SELECT ID, NAME, SALARY
FROM CUSTOMERS
WHERE SALARY > 2000;
```


# AND & OR Conjunctive Operators 
*The SQL AND & OR operators are used to combine multiple conditions to narrow data in
an SQL statement.*
### AND

``` sql 
SELECT column1, column2, columnN
FROM table_name
WHERE [condition1] AND [condition2]...AND [conditionN];
``` 
*Following is an example, which would fetch the ID, Name and Salary fields from the
CUSTOMERS table, where the salary is greater than 2000 and the age is less than 25 years.*
Condition : [ WHERE SALARY > 2000 AND age < 25; ]

### OR 
*The OR operator is used to combine multiple conditions in an SQL statement's WHERE
clause. same as and operator*

``` sql
... WHERE [condition1] OR [condition2] OR [conditionN]
```


# UPDATE 
*The SQL UPDATE Query is used to modify the existing records in a table. You can use the
WHERE clause with the UPDATE query to update the selected rows, otherwise all the rows
would be affected.*

``` sql
UPDATE table_name
SET column1 = value1, column2 = value2...., columnN = valueN
WHERE [condition];
``` 
e.g 

``` sql
UPDATE CUSTOMERS
SET ADDRESS = 'Pune' > SET ADDRESS = 'Pune', SALARY = 1000.00;
WHERE ID = 6;
```

# DELETE 
*DELETE Query is used to delete the existing records from a table.
You can use the WHERE clause with a DELETE query to delete the selected rows, otherwise
all the records would be deleted.*
```sql
DELETE FROM table_name
WHERE [condition];
```

#### DELETE all

```sql
DELETE FROM CUSTOMERS;
```

# Create User and permission for `mysql` database.

### *Creating user*

``` shell
MariaDB [(none)]> 

CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';
```
### *Add Permissions for the user*

```sql
GRANT ALL PRIVILEGES ON * . * TO 'user'@'localhost';
```

### *Apply All The Chagement*

``` sql
FLUSH PRIVILEGES;
```
