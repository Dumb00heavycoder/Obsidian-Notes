previous knowledge required:- [[00 Why pandas]] and [[01 Getting Started]]

Source:- IITM BS DATA SCIENCE python course week 11 3rd lecture

Data frame is a 2 dimensional data structure used to store tabular data and the rows of a single column in this data frame are known as series. 
Series:- 
![[Pasted image 20260122220754.png]]
Dataframe:- 
![[Pasted image 20260122220819.png]]
Here i'll be writing some of the examples i did in my class which are complex and helpful.
 here are these examples:- 
 
 1)- Printing a column:-  just use the following syntax `print(dataframe['column name'])

2)- To access a data frame inside a data frame you can use lists.
	eg:- `df[['last' , 'email']]`
	 We are calling this data frame in the same way we call a series instead we are just adding a list which contains the columns. Now this will no longer be a series as it will give us multiple columns. 
3)- To access a column we can use `df.columns` but to get rows we use a special function named `iloc`(integer location) or `loc`. 
	eg:- `df.iloc[0]`
	this will print row of 0th index in a series format 
if you wish to access some specific columns rows then you can use the following syntax:-
	eg:- `df.iloc[[0, 1], 2]`
	This would access 0th and 1st row of 2nd column and print it as a data frame. here 2nd index is mentioned for the column on 2nd index. we use the index instead of the name. 
	![[Pasted image 20260122221509.png]]
	![[Pasted image 20260122221549.png]]
In loc you can use the actual name of columns and rows instead of using the index. You can even change the order. for example you can ask for column on 3rd index and then for 2nd index too. 

Slicing to is possible in loc, instead of writing `df.loc[[0,1,2,3,4], 'email']` you can just write `df.loc[0:4, 'email']`. This can be done with columns too. eg:- `df.loc[0:4, 'name' : 'email']`
![[Pasted image 20260122223404.png]]
