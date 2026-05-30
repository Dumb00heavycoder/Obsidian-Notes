previous knowledge:- [[00 Why pandas]], [[01 Getting Started]],[[02 Data frames and series basics]],[[03 Indexes- How to set, use and reset indexes]],[[04 Filtering - Using Conditionals to filer rows and columns]],[[05  Updating Columns and Data in Rows]]

1)- Adding columns:- You can add a new column in this way- 
	`df['Full Name'] = df['first'] + ' ' + df['last']`
	 You can get creative and use apply or apply map methods on other columns and create new columns with them. 
2)- Removing a column:- You can use drop method to remove columns-
	 `df.drop(columns= ['first', 'last'], inplace = True)`
3)- Making new columns by splitting existing column:- we created a full name column earlier and deleted the first and last column. So now lets try to split full name column into first and last columns in this way:- 
	 `df[['first', 'last']] = df['Full Name'].str.split(' ', expand = True)`
	 ' ' gives a message that split at space and expand = True will convert it into a dataframe form
	  