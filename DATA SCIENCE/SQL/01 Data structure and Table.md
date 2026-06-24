previous knowledge:- [[DATA SCIENCE/SQL/00 Introduction|00 Introduction]]
In SQL, data types define the kind of data that can be stored in a column or variable. They can be numeric, categorical, date time data type and many more. Visit https://dev.mysql.com/doc/refman/8.0/en/data-types.html for more data type.
![[Screenshot 2026-06-25 at 1.16.28 AM.png|502]]
In SQL we work in tables where our data is stored in rows and columns. Column gives us the structure/Schema of the database while rows gives us the data. 

1)- Lets create our first data base:-
To create data base use the following syntax:-
`CREATE DATABASE db_name;`
(sql is not case sensitive but we prefer writing commands in capital to highlight them)
to delete this data base we can do:-
`DROP DATABASE db_name;`
To select and use a database we use( Here we tell computer that everything we write after use will be implemented of the database we choose in use command)
`USE db_name;`

2)- Creating a table
To create a table we use the following structure:-
`CREATE TABLE table_name(`
	`column_name1 datatype constraint,`
	`column_name2 datatype constraint`
	`column_name3 datatype constraint`
`)`
constraint can be of many type, here are some popular one:-
- Primary key:- used in ids where every value should be unique
- NOT NULL:- used for columns which can not have null values

3)- Syntax for inserting data into your table:-
`INSERT INTO table_name VALUES(value1,  value2, value3)` 
here input value according to their data types. use " " for categorical data 

4)- Printing the table:-
use the following syntax:- `SELECT * FROM table_name;`

5)- Difference between varchar and char datatype:- When u use these datatypes u give them the maximum amount of characters they can store in this way:-
CHAR(50)
VARCHAR(50)
here char will go in memory and reserve space according to the limit already. it doesnt matter if its being used or not. On the other hand VARCHAR will only take the amount of space which it needs. So it is preferred to use varchar for strings. 

BLOB is also available but it is only useful for very big strings. 

6)- BIT data type is used to only store BIT values. 

7)- Signed and unsigned datatypes:- In numerical data types we have signed and unsigned data types where the signed data type are the types of variables which accept both negative and positive values while unsigned data types only accept positive values. 
Why is it useful?
In TINYINIT data type we can only take data ranging from -128 to +127 but if are using TINYINT for a variable which wont have any negative value like age or id. That time we can write `TINYINT UNSIGNED` and that will  change its range to 0 to 255. 

