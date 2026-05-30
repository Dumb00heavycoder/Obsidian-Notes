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

3)- 4 methods of changing data:-
- Apply is a method which allows you to apply a function over a column. For example you wish to the length of every element in a column. You can do it in this way for series objects:-
	  `df['email'].apply(len)`
	  This will give length of every entry in email column.
	This can be used to update every entry in a column by making your own function and applying it on the column. 
	eg:- 
		`def update_case(email):`
			`return email.upper()`
		`df['email'].apply(update_case)`
	You can also straight up use the lambda function in this way:-
		`df['email'] = df['email'].apply(lamda x: x.lower())`
	Now lets focus on how apply will work with data frames
	If you try `df.apply(len)` then you would expect to get length of entries in every column but instead it would end up giving you the amount of entries in every column. it'll give u the result of `len(df['email']`  
	You can also use a minimum function like this:- 
		`df.apply([pd.Series.min])`
		it'd give u the minimum values of every column
		U can get the same result with this lambda function:-
		`df.apply(lambda x: x.min())`
	So in conclusion applying apply to a series will apply the funciton to every element in that series and applying apply to a dataframe will apply the function to the series or columns.  

- Applymap:- In apply section we saw how if we use apply on a dataframe it'll apply function the series and not the entries in the columns. Applymap is used on a dataframe to apply function on every entry in the dataframe. this is helpful when u wish to update entries with the help of a function.  
	 eg:- `df.applymap(len)`
		This will return a data frame with length of every element in df.
- Map:- Map is used on series to change the values with a dictionary. This will replace values according to the dictionary that yo mention
	 `df['first'].map({'dhruv' : 'shreyas', 'jane': 'mary' })`
	This will replace the values you mentioned in dictionary but if you did not mentioned a value in dictionary which is present in df. For example it might be a third value. That value will then go to NaN.  
- Replace:- Now if you want to use the map method but only change few values without getting other values to NaN. Then you should use replace method.  
	 `df['first'].replace({'dhruv' : 'shreyas', 'jane' : 'mary'})`
-  