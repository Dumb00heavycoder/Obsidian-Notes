previous knowledge:- [[02 Data frames and series basics]], [[01 Getting Started]] and  [[00 Why pandas]]

1)- Setting an index:- You can set any column of your data frame as an index. To temporarily see  how it will look you can just type  `df.set_index('column name')`. To permanently set that column as index you must set inplace value to True :- `df.set_index('column name', inplace = True)`.  You can access rows in loc by using the rows name as index. iloc will still function the same. 
![[Pasted image 20260122224725.png]]
