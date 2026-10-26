previous knowledge:- [[00 Why pandas]], [[01 Getting Started]],[[02 Data frames and series basics]],[[03 Indexes- How to set, use and reset indexes]],[[04 Filtering - Using Conditionals to filer rows and columns]],[[05  Updating Columns and Data in Rows]]

1)- Adding columns:- You can add a new column in this way- 
	`df['Full Name'] = df['first'] + ' ' + df['last']`
	 You can get creative and use apply or apply map methods on other columns and create new columns with them. 
2)- Removing a column:- You can use drop method to remove columns-
	 `df.drop(columns= ['first', 'last'], inplace = True)`
3)- Making new columns by splitting existing column:- we created a full name column earlier and deleted the first and last column. So now lets try to split full name column into first and last columns in this way:- 
	 `df[['first', 'last']] = df['Full Name'].str.split(' ', expand = True)`
	 ' ' gives a message that split at space and expand = True will convert it into a dataframe form
4)- adding and removing rows in data:-  You can add a new row in your data frame with the following syntax:- 
	`df.append({'first': 'Dhruv', 'last': 'Chaudhary', ignore_index = True})`
	ignore index is important otherwise you'll get error. here we have only passed values of first and last name and no email value has been passed. Which means that email value will be NaN in the result. 
5)- appending one dataframe on another:- for example you have df which has email, fullname, first and last column and you also have df2 which has first, last and email column. U can append df2 in df in such a way:-
	df.append(df2, ignore_index =True)
	as there is no fullname column in df2. Full name values of df2 will be NaN after appending.
6)- Removing rows:- 
	`df.drop(index = 4)`
	You can also remove rows with conditionals in this way:-
	`df.drop(index = df[df['last'] == 'chaudhary'].index)`
	