Previous knowledge required:- [[Week 1]] [[Week 2]] [[Week 3]] 
***List []***
In Python, a list is a built-in dynamic sized array (automatically grows and shrinks). We can store all types of items (including another list) in a list. A list may contain mixed type of items, this is possible because a list mainly stores references at contiguous locations and actual items maybe stored at different locations.

- List can contain duplicate items.
- List in Python are Mutable. Hence, we can modify, replace or delete the items.
- List are ordered. It maintain the order of elements based on how they are added.
- Accessing items in List can be done directly using their position (index), starting from 0.
- List can be used to create matrix
- You can do modifications as `L[len(L) - 1]` to access last item.
Understanding the workflow:-
a = [10, 20, "GfG", 40, True]
![[Pasted image 20250707155449.png]]
This sort of formation makes storing different types of data in one list possible. 

Lets learn some more features of list:-
	1. You can multiply a list 
	2. You can use relational operators to compare 2 lists (elements are compared entries wise)
	3. [[Duplicating a list]]
	4. In a function we pass lists not their values. which changes the list completely after completion of function
	5. [[List methods]]

***Sets {}***
Sets in python are much like the sets you come across in Math. The sets module provides classes for constructing and manipulating unordered collections of unique elements. Common uses include membership testing, removing duplicates from a sequence, and computing standard math operations on sets such as intersection, union, difference, and symmetric difference.
	- Sets only take unique entries 
	- It is slower than list when it comes to creating big range
	- It is faster than list when it comes to searching through elements to check
	- a set is mutable but elements being added should not be mutable or hashable
	- subset & super-sets can be created, you can also use issubset or issuperset commands
	- unions and intersections can be done in such ways :-
			`C1 = A.union(B)`
			`C2 = A | B`
			`C1 = A.intersection(B)`
			`C2 = A & B`
	- You can also find differences in two sets by using `A.difference(B)` or `A - B`
**Few Differences between list and sets**

| Sets                                                               | List                                                   |
| ------------------------------------------------------------------ | ------------------------------------------------------ |
| Creation is slow                                                   | Creation is fast                                       |
| Search is really fast                                              | Search is slow                                         |
| Takes more storage                                                 | Takes less storage                                     |
| not subscript-able                                                 | subscript-able                                         |
| use when alot of searching through <br>unique elements is involved | use when alot of elements are involved<br>in the array |

Note:- You can `import sys` and use `sys.getsizeof()` to get the size of your list or set

***Tuples ()***
A tuple in Python is an immutable ordered collection of elements. Tuples are similar to lists, but unlike lists, they cannot be changed after their creation (i.e., they are immutable). Tuples can hold elements of different data types. The main characteristics of tuples are being **ordered*** , **heterogeneous** (can store multiple data types) and **immutable**.
	- They occupy lesser storage than list
	- use it for big immutable data for less storage
	- [[Packing and unpacking in tuples]]
	- a tuple with single value is considered as a single variable but to make it a tuple you can add comma after that single value. (Q:- [[Size of tuple compared to variable]])
	- Tuples can store list in them
	- list inside tuple can be mutated (Q:-[[Mutate a list inside a tuple]])

***Functional Programming or list comprehension***
Functional programming in Python involves writing code using functions as first-class citizens, emphasising immutability and avoiding side effects. 
Some ways of functional programming:- 
	1. Instead of writing if else block for identifying smaller number from a & b we can use the following code:- `small = a if a < b else b`   
	2. Try this problem :- [[Fruits with N in them]]
This topic can be explored in much depth when studying advance python but for now we are gonna leave it here.

***Introduction to Functions***
In python we use Def to create functions. 

problems:- [[Append list 2 in list 1 in a new list]]
[[Find average of a list]]
[[print lists maximum number]]
[[print lists minimum element]]
[[Return middle value of a list]]

Lets study some types of function arguments:- 
	1. You can give the values as the arguments
	2. You can give variables as arguments
	3. You can also create variables and assign values in form of arguments 

Lets explore some types of functions
	1. In built functions:- They are the functions which are already present in python by default.
	2. Library functions:- Functions which are present in specific libraries. 
	3. User defined functions:- Functions created by users in the program.