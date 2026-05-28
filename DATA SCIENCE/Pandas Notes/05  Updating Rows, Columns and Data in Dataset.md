previous knowledge:- [[00 Why pandas]], [[01 Getting Started]], [[02 Data frames and series basics]], [[03 Indexes- How to set, use and reset indexes]], [[04 Filtering - Using Conditionals to filer rows and columns]] ,

1)- Updating Column names in dataset:-
- You can manually change the names of columns in format of a list in this way:-
	 Column names:- 'First', 'Last', 'Email'
	 to change:-
		`df.columns = ['First_name', 'Second_name', 'Email_address']`
		This can only be used when u are changing every name and all column name must exist int his one. 
	 This will change the column names in the dataframe to but this can only be used in small dataframes
- You can change the case of the column names from capital to small or vice a versa with this line of code:- 
	 `df.columns =  [x.upper() for x in df.columns]
	 `df.columns = [x.lower() for x in df.columns]`
- You can change letters with string methods. For example if every column name has underscore instead of space you can just replace the underscore with space by this method:-
     `df.columns = df.columns.str.replace('_' , ' ')`
 - If you wish to change only specific column name you can use this rename method:- 
	  `df.remane(columns = {'first_name' : 'first', 'second_name' : 'second',}, inplace = True)`

2)- Updating the data in rows 