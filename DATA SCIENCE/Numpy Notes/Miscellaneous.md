1)- Load data from file:- `np.genfromtxt("filename", delimiter = ',')` will load any data u type out. delimiter is the seprator.  u can create a variable of this data and change its data type with `astype()` method.

2)- Advance indexing and Boolean masking:- 
Indexing in numpy is possible and calling out with indexes is also possible just like it was with lists in python. 
`a = np.array([1,2,3])`
`a[0,2]`, this code will return 1 and 3. With the help of indexing we can do boolean asking to check some values in our loaded data. 
eg:- `file = np.genfromtxt("filename", delimited = ',')`
`file[file>50]`, This will return a data frame with true and false statement where it'll put each and every element in in our condition and return true if file element is bigger than 50 or false if otherwise. You can use np.any or np.all to run these boolean statements on ur data for better results. Running conditions on np.any will return true if even one element satisfy the condition and false if none does. In np.all u will get a True statement only when all elements in column or row satisfy the condition. 
eg:- `np.any(file > 50, axis = 0 )`
 You can now also use &, | and  ~ operators to form better conditions and do better boolean masking 