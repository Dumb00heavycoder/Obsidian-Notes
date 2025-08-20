Previous knowledge:- [[Week 1]] [[Week 2]] [[Week 3]] [[Week 4]]
***Dictionary*** 
- Dictionaries are used to store data values in key:value pairs.
- A dictionary is a collection which is ordered, changeable and do not allow duplicates.
	syntax :- `d = {'key': 'value'}`
- eg:- `d = {dhruv: 90, ditya: 94, prakhar: 94, shryeas: 89}`
- printing methods:- `1)-print(d)` 
				`2)- for key in d:`
					`print(key, d[key])`

- [[Dictionaries Functions]]
- [[Find out the maximum and minimum times a word occurs in a paragraph]]

***COLLECTION SUMMARY***
![[Pasted image 20250717212148.png]]


***Problem solving with functions***
It is usually preferred to breakdown big problems in small parts and then solve them in parts. Lets consider the sorting problem. In sorting problem you have to take the most minimum number from a list and then put it in a list x then remove it from the original list and keep doing it until original list is empty. This will result a list x which will have all numbers of original list in ascending order.
There are two ways to solve this problem
1)-  [[Sorting list problem (way1)]]
2)- [[sorting list problem (way2)]]

both of the ways will give you the same output but executing 2nd one is more efficient and easy on the brain as you are tackling one problem at a time.
Hence breaking down problems in parts and tackling one problem with one function is much easy on the brain.

***Matrix multiplication***
![[Pasted image 20250820171131.png]]
The image above shows our basic understanding of matrix multiplication where any entry in a product is a dot product of ith row and jth column of A and B. Here we identity some patterns like how when we find $C[3][2]$ the dot product calculation will have constant i for all A and constant j for all B. this is marked with blue and brown dots. These pattern recognition will help us to write down a program for matrix multiplication. 
$C[I][J]$ is the dot product of ith row of A and jth column of B.
$C[I][J]$ $= A[I][K]  Dot product  B[K][J]$

You can do matrix multiplication with numpy very easily but here we'll try doing it without any library and purely solving it by logic.
[[Matrix multiplication (without numpy)]]
[[Matrix multiplication with numpy]]
