previous knowledge:- [[02 Data frames and series basics]], [[01 Getting Started]] and  [[00 Why pandas]]

1)- Setting an index:- You can set any column of your data frame as an index. To temporarily see  how it will look you can just type  `df.set_index('column name')`. To permanently set that column as index you must set inplace value to True :- `df.set_index('column name', inplace = True)`.  You can access rows in loc by using the rows name as index. iloc will still function the same. 
![[Pasted image 20260122224725.png]]

2)- Reset an index:- To reset the index to previous one you can use:- `df.reset_index(inplace = True)`

3)- Setting index while reading the data:- U can set a column name as index in the reading data step only in such way:- `df = pd.DataFrame(data, index.col = 'Name')`

4)- Jupyter will always show incomplete entries if they are very long. for example in a column a entry is a long paragraph and you want to read the complete para. You can write `df.loc[index, 'column name' ]` to access the complete text.

5)-` df.sort_index(inplace = True)` = This will sort your indexes in ascending order according to their first alphabet. 

