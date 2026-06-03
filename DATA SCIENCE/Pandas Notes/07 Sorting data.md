previous knowledge:- [[00 Why pandas]], [[01 Getting Started]], [[02 Data frames and series basics]], [[03 Indexes- How to set, use and reset indexes]], [[04 Filtering - Using Conditionals to filer rows and columns]], [[05  Updating Columns and Data in Rows]], [[06 Add Remove columns and rows from data frame]]

1)- Sorting data frame based on one column:- 
	`df.sort_values(by = 'Column name',)`
	For descending you can do this:-
	`df.sort_values(by = 'Column name', ascending = False)`

This will sort the data frame according to the column 
2)- Sorting data frame based on two column:- 
	`df.sort_values(by = ['Column name 1', 'Column name 2'])`
	This will sort data frame according to these two columns
3)- Sorting ascending with one column and descending with second column:- 
	`df.sort_values(by = ['Column name 1', 'Column name 2', ascending = ['False', 'True']])`
	You can add comma and write inplace = True to make it permanent. 
4)- 