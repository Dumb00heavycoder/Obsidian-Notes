previous knowledge:- [[DATA SCIENCE/SQL/00 Introduction|00 Introduction]], [[01 Data structure and Table]]
1)- Types of SQL commands:-  There are 5 category of commands in sql. knowing these categories is only good for theory part it wont actually help u in any practical way.
1. DQL (Data Query Language) : Used to retrieve data from databases. (SELECT)
2. DDL (Data Definition Language) : Used to create, alter, and delete database objects
	like tables, indexes, etc. (CREATE, DROP, ALTER, RENAME, TRUNCATE)
3. DML (Data Manipulation Language): Used to modify the database. (INSERT,
	UPDATE, DELETE)
4. DCL (Data Control Language): Used to grant & revoke permissions. (GRANT,
	REVOKE)
5. TCL (Transaction Control Language): Used to manage transactions. (COMMIT,
	ROLLBACK, START TRANSACTIONS, SAVEPOINT)

2)- DataBase Related queries:- 
 whenever making or deleting a data base it is a good practice to use IF EXIST and IF NOT EXIST with them. these will warn you instead of giving errors.
 syntax:- 
 `CREATE DATABASE IF NOT EXIST df_name;`
 `DROP DATABASE IF EXIST df_name;`

`SHOW DATABASE;` can be used to see all the data base in ur sql
`SHOW TABLES;` can be used to see all the tables in the data base u are using

3)- Table related queries:- 
 We have already seen how to create a table schema, how to see the table and add values to the table. Now lets see how to add multiple values to the table with our INSERT command.
 syntax:- 
 `INSERT INTO table_name
 (column_name1, column_name2, column_name3)
  VALUES
  (value1,  value2, value3),
  (value1,  value2, value3),
  (value1,  value2, value3);


PRACTICE QUESTION 1:- Create a database of ur company xyz. with table and 3 columns (id, name, salary). add the following information:- 
1 ,"adam", 25000
2, "bob", 35000
3, "casey", 15000
then select and view all your table data. 