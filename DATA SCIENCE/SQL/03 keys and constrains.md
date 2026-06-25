previous knowledge:- [[DATA SCIENCE/SQL/00 Introduction|00 Introduction]], [[01 Data structure and Table]], [[02 COMMANDS]]

1)- There are two types of keys in basic sql. First is our primary key and second is Foreign key.
- Primary key is used for columns which are supposed to have unique values and they will also not accept any null values. 
- Foreign keys:- When primary key of one table is used in another table where repetition of that column is allowed. That key is known as a foreign key. For example you created a table of cities with city ids and city names and both of these are primary keys. Means they can not have repeated values. now u use these two columns in ur students data set where u use city id and city names. just because many students are from same city so city id and city names repeat here. 
![[Screenshot 2026-06-25 at 7.49.57 PM.png|581]]

2)- SQL constraints are used to specify rules for data in a table. Lets study some constraints:- 
- NOT NULL - Columns can not have null values  `(column_1 int NOT NULL);`
- UNIQUE - Columns can not have duplicate values (`column_1 int UNIQUE);`
- PRIMARY KEY- Columns can not have duplicate and null values `(column_1 int PRIMARY KEY);`
- FOREIGN KEY- Link primary key of one tale to another. 
	 eg:- `CREATE TABLE student(`
		`student_id int,`
		`FOREIGN KEY (student_id) references student_ids(id)` 
		`);`
		Here we reference other table. in this example we reference student_ids table and the id column in it.
- DEFAULT- sets a default value of a column `(salary int DEFAULT(25000));`
- CHECK - It helps u to limit values allowed in columns. 
		eg:- 1)-`CREATE TABLE student(`
		 `age int` 
		 `CONSTRAINT age_check  CHECK (age>=18 AND age<= 70)`
		 `);`
		 2)- `CREATE TABLE student(`
		 `age int check (age >= 18)`
		 `);`
		 