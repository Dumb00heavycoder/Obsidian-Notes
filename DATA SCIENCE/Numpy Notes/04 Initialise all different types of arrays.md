previous knowledge:- [[00 Introduction to Numpy]], [[01 What is Numpy]], [[02 The basics]], [[03 Acessing Changing specific rows, columns, elements, etc]]

1)- Null matrix:-
	`np.zeros((dimension), dtype)`
	eg:- `np.zeros((2,3))`
2)- All 1s matrix:-
	`np.ones((dimension), dtype)`
	eg:- `np.ones((4,2,2), dtype='int32')`
3)- All any number matrix:-
	`np.full((dimension), number)`
	Using another array as dimension:-
	`np.full_like(a, number)`
4)- Random decimal numbers:-
	np.random.rand(dimension)
	eg:-`np.random.rand(4,2)`
5)- Random integer numbers:-
	`np.random.randint(from which number to which, dimension)`
	eg:- `np.random.randint(-4,8, size=(3,3))`
6)- Identity Matrix:-
	`np.identity(dimension)`
	You must mention single dimension as identity matrix are square matrix 
7)- Repeat an array:-
	`arr = np.array([1,2,3])`
	`r1 = np.repeat(arr, repeat times,  axis)`
8)- copying array( Be careful when copying):-
	`a = np.array([1,2,3])`
	`b = a.copy()`
	If you make changes to b they will take place in a also so be careful when using it

Practice Question:-
1)- Print the following matrix with the help of methods u learned in this section:- 
	![[Screenshot 2026-06-07 at 9.16.32 PM.png]]
Ans:- 