 previous knowledge:- [[00 Why pandas]], [[01 Getting Started]], [[02 Data frames and series basics]], [[03 Indexes- How to set, use and reset indexes]], [[04 Filtering - Using Conditionals to filer rows and columns]], [[05  Updating Columns and Data in Rows]], [[06 Add Remove columns and rows from data frame]], [[07 Sorting data]]

1)- Some aggregate functions:-
You can use these functions on series. If you use them on a data frame they will themselves look for columns with numerical datatype and execute the function. They ignore NaN values.
- mean()
- mode()
- median()
-  describe()
- value_counts()
Using median is better than using mean to describe data sets as mean can be heavily altered by outliers.

2)- Grouping:- 