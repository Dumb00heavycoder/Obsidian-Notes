1)- dt.year = This method will extract year from any datetime datatype. Can be used to make year column
2)- dt.month = This method will extract month from any datetime data type.
3)- dt.month_name() = This method will extract month name from any datetime datatype
4)- pd.to_datetime(#feature#) = This method will change any int or string date datatype to datetime datatype.
5)- Describe = This method will describe any dataset. it'll give count, mean, max, standard dev, 25th quartile, 50th quartile, 75th quartle and minimum of features which numerical datatypes.
6)- .duplicated() = Finds duplicates in data frame
7)- .isna() = finds na values in data frames
8)- nlargest() = `df['Column name'].nlargest(10`)  Will give u a series of the column name it its 10 largest entries. You can also simply do `df.nlargest (10, 'Column name')` to get the completed data frame arranged according to the column mentioned in n largest. 
9)- nsmallest() = Works exactly like nlargest() but gives smallest values
10)- value_counts() = gives count of values present in the column. For example if there is a yes and no column so it'll tell how many yes and no are present in the column. eg:- `df['Hobbyist'].value_count()`. You can add normalize = True in the () to get the percentage instead of the number