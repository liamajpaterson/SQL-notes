# SQL-notes
A collection of notes relating to SQL

# Introduction
SQL (Structured Query Language) is a programming language designed to manage data stored in relational databases. A relational database is a database that organizes information into one or more tables. All data stored in a relational database is of a certain data type. Some of the most common data types are:
* INTEGER, a positive or negative whole number
* TEXT, a text string
* DATE, the date formatted as YYYY-MM-DD for the year, month and day
* REAL, a decimal value

Important to note - statements always end in a semi-colon ;.

# Constraints
Constraints that add information about how a column can be used are invoked after specifying the data type for a column. They can be used to tell the database to reject inserted data that does not adhere to a certain restriction.

1. PRIMARY KEY columns can be used to uniquely identify the row. Attempts to insert a row with an identical value to a row already in the table will result in a constraint violation which will not allow you to insert the new row.
2. UNIQUE columns have a different value for every row. This is similar to PRIMARY KEY except a table can have many different UNIQUE columns.
3. NOT NULL columns must have a value. Attempts to insert a row without a value for a NOT NULL column will result in a constraint violation and the new row will not be inserted.
4. DEFAULT columns take an additional argument that will be the assumed value for an inserted row if the new row does not specify a value for that column.




# SQL Statements

## Select data from relational database
```
SELECT * FROM
celebs;
```
>Note: * is a wildcard character that allows you to select every column in the table.

## Create table
```
CREATE TABLE table_name (
column_1 data_type, 
column_2 data_type, 
column_3 data_type
);
```

## Insert row into table
```
INSERT INTO table_name (column_1, column_2, column_3)
VALUES (value_1, value_2, value_3);
```

## Update information in a table
```
UPDATE table_name
SET column_2 = value_2
WHERE column_1 = value_1;
```

## Insert new column into table
```
ALTER TABLE table_name
ADD COLUMN column_name
data_type;
```

## Delete rows from table
```
DELETE FROM table_name
WHERE column_name IS value;
```
>Note: Null can be used to delete all rows with data missing in one column
