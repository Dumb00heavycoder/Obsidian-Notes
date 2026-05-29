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
- First we can use the same list method we used to change column name, We can use Loc and create a list on that row while updating the entries
	 `df.loc[2] = [ 'Dhruv', 'Rajput', 'dhruvrajput@gmail.com']`
	 This will only work for small datasets as you will have to manually type every entry of the row to update the row. 
- When we only wish to change specific values then we can use column names in loc to access those columns and change them.
	 `df.loc[2, ['last', 'email']] = ['Rajput', 'dhruvrajput@gmail.com']`
	 With this you can access multiple rows and their multiple columns and change their entries.
- When changing a single value you can just type the value in the variable as there will be no need of having a list
	 `df.loc[2, 'last'] = 'Rajput'`
- Whenever setting values just use iloc or loc otherwise you will run into issues or warnings. 
- You can change values in filters also in such way:-
	 `filt = (df[email] == "johndoe@gmail.com" )`
	 `df.loc [filt , 'last'] = "Smith"`
- To change multiple rows case you can do this:- 
     `df['email'] = df['email'].str.lower()` 
     `df['email'] = df['email'].str.upper()`