previous knowledge:- [[00 Introduction to Numpy]], [[01 What is Numpy]], [[02 The basics]], [[03 Acessing Changing specific rows, columns, elements, etc]], [[04 Initialise all different types of arrays]]

1)- Operation on array:- You can do operations like addition, substraction, multiplication and division on an array with numpy. 
`a = [1,2,3,4]`

`a+ 2 (will add 2 to every element)`

`a*3(will multiply 3 to every element)`

`a**2(for power)`

`b = np.array([1,0,1,0])`

`a + b`
You can also use increment and decrement operators:- 
`a+= 2`

 You can also use trigno functions:-
`np.sin(a)`

`np.cos(a)`

 2)- Linear algebra
You can multiply two matrices with np.matmul(a,b):-

	`a = np.ones((2,3))`
	`print(a)`
	`b = np.full((3,2), 2)`
	`print(b)`
	`np.matmul(a,b)`
You can find determinant with np.linalg.det(c):-
	`c = np.identity(3)`
	`np.linalg.det(c)`

Reference docs (https://docs.scipy.org/doc/numpy/reference/routines.linalg.html)
 You can find:-
	 Determinant
	 Trace
	 Singular Vector Decomposition
	 Eigenvalues
	 Matrix Norm
	 Inverse
	 Etc...

 3)- Statistics:- 
 You can do basic min, max and sum operation an  array in numpy. u can pass in axis argument for better results:-
	 np.max(stats, axis=1)
	 np.min(stats, axis=1)
	 np.sum(stats, axis=0)
	