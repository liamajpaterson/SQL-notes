# SQL-notes
A collection of notes relating to SQL

# Introduction
SQL (Structured Query Language) is a programming language designed to manage data stored in relational databases. A relational database is a database that organizes information into one or more tables. All data stored in a relational database is of a certain data type. Some of the most common data types are:
* INTEGER, a positive or negative whole number
* TEXT, a text string
* DATE, the date formatted as YYYY-MM-DD for the year, month and day
* REAL, a decimal value

Important to note - statements always end in a semi-colon ;.

One of the core purpoess of the SQL language is to retrieve information stored in a database. This is commonly referred to as auqerying. Queries allow us to communicate with the database by asking questions and having the result set return data relevant to the question.

# Constraints
Constraints that add information about how a column can be used are invoked after specifying the data type for a column. They can be used to tell the database to reject inserted data that does not adhere to a certain restriction.

1. PRIMARY KEY columns can be used to uniquely identify the row. Attempts to insert a row with an identical value to a row already in the table will result in a constraint violation which will not allow you to insert the new row.
2. UNIQUE columns have a different value for every row. This is similar to PRIMARY KEY except a table can have many different UNIQUE columns.
3. NOT NULL columns must have a value. Attempts to insert a row without a value for a NOT NULL column will result in a constraint violation and the new row will not be inserted.
4. DEFAULT columns take an additional argument that will be the assumed value for an inserted row if the new row does not specify a value for that column.

# Operators
Operators create a condition that can be evaluated as either true or false.
* "=" equal to
* "!=" not equal to
* ">" greater than
* "<" less than
* ">=" greater than or equal to
* "<=" less than or equal to

# SQL Statements

## Select data from relational database
```
SELECT * FROM
celebs;
```
>Note: * is a wildcard character that allows you to select every column in the table. To select individual columns, type their names after SELECT with a comma between.

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
>Note: Null can be used to delete all rows with data missing in one column. It is not possivle to test for NULL values with comparison opertors.

## Create an alias for a column or table
```
SELECT column_name AS 'alias'
FROM table_name;
```
>Note: The columns have not been renamed in the table - the aliases only appear in the result

## Return unique values only in a specified column
```
SELECT DISTINCT column_name
FROM table_name;
```
## Restrict results of queries
```
SELECT column_1
FROM table_name
WHERE column_2 condition;
```
## Select similar outputs
```
SELECT column_1
FROM table_name
WHERE column_2 LIKE 'condition';
```
>Note: a condition such as 'Se_en' can be used. _ represents an individual wildcard character.

>Note: a condition such as 'A%' can be used. % represents a wildcard character that matches zero or more missing letters in the pattern, thus returning all results beginning with A. This can also be used before or after a pattern, e.g. '%man%.

## Search for NULL values
```
SELECT column_1
FROM table_name
WHERE column_2 IS NULL;
```

>Note: alternatively, IS NOT NULL can be used.

## Filter a dataset within a range
```
SELECT column_1
FROM table_name
WHERE column_2 BETWEEN 'criteria_1' AND 'criteria_2';
```
>Note: when criteria relates to letters: begins from criteria_1 up to, but not including, criteria_2.

>Note: when criteria relates to numbers: begins from criteria_1 up to and including criteria_2.

## Multiple Conditions
```
criteria_1 AND criteria_2
```
## OR Function
```
criteria_1 OR criteria_2
```
## Order results in ascending order
```
ORDER BY column_1 ASC;
```
## Order results in descending order
```
ORDER BY column_1 DESC;
```
> Note: the column doesn't have to be one of the columns displayed

> Note: ORDER BY must be after WHERE if WHERE is present

## Limit the number of results
```
SELECT column_name
FROM table_name
LIMIT number;
```
> Note: always goes at the end of the query.

## If-then logic
```
SELECT column_1
CASE
WHEN column_1 > value_1
THEN 'name_1'
ELSE 'name_2'
END AS 'result_name'
FROM table_name; 
```
> Note: Must end with END.

> Note: it is ideal to rename the result as otherwise it displays the entire query
