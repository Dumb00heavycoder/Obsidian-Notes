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
[[Matrix multiplication with Functions]]

***Call by value and scope of a variable***

![[Pasted image 20250820175256.png]]
Look at this example carefully and realise that line 8 is not exactly giving the expected output. We expect line 8 to print 10 but it does not. Its because when we give x variable to function1 we are just passing the value of x variable to the x variable in function1. This called call by value where a function calls a variable by its value. The value is taken by function and then used in operations. Value stored in original variable does not change. 

Here we can also discuss scope of a variable. There are two types of variable local and global. globals are declared for the whole program and local and declared for a specific function. We can use global variables in functions too by just mentioning `Global x` in the start of the function. 

***TUTORIAL OF FUNCTIONS PROBLEM STATEMENTS***
[[calculate upper case, lowercase, number of characters and number of words]]
[[Calculate area and parameter of rectangle and circle]]
[[Check whether input coordinates form triangle or not]]

***Iterators and generators***
Iterators are a special data type in python which allows you to create and iteration out of a list, dict, set or any array data type. It allows you to iterate through it with a keyword next. 
eg:- 
`l = ["apple", "banana", "watermelon", "grapes"]`
`basket = iter(l)`
`print(basket) #this will give the type of basket data type`
`print(next(basket)) #will print apple`
`print(next(basket))#will print banan`
`...`

Generators are special type of functions which allow you to generate a iterator. You can use yield keyword to generate next iteration of an iterator. 
eg:- 
`def square_cube (limit):`
	`x=0`
    `while x < limit:`
        `yield x * x`
        `yield x * x * x`
        `x += 1`
`a = square_cube(5)`
`print (next(a), next(a))`
`print(next(a), next(a))`

In this example we have created a generator function which uses the keyword yield. Generator functions stop their function when they execute the first yield and if they are called again they start from the next yield. Here when we call function first it executes till square then on 2nd call it executes the cube part and then we repeat it. This is how we create our own iteration from generator function.

***lambda functions, enumerate, zip, map filter***

1)- Lambda functions:- It is a special type of function which can be stored in a variable but it will behave like a normal function. Mostly it is used for simple functions which contain only 1 small return statement. 
eg:- 
`add = lambda x, y: x + y`
`print( add (10,23))`
Here we have used lambda function to replace our classical add function. As you can see the number of lines have been decreased which makes our program compact. The type of add variable remains as a function. 

2)- Enumerate:- enumerate function simply takes items of a list and assigns numbers to them and creates a tuple out of it. Easy for indexing through large lists.
eg :- 
![[Pasted image 20250821021813.png]]
