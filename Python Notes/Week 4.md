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

***Sets {}***
Sets in python are much like the sets you come across in Math. The sets module provides classes for constructing and manipulating unordered collections of unique elements. Common uses include membership testing, removing duplicates from a sequence, and computing standard math operations on sets such as intersection, union, difference, and symmetric difference.
	- Sets only take unique entries 
	- It is slower than list when it comes to creating big range
	- It is faster than list when it comes to searching through elements to check

***Few Differences between list and sets***

| Sets                                                               | List                                                   |
| ------------------------------------------------------------------ | ------------------------------------------------------ |
| Creation is slow                                                   | Creation is fast                                       |
| Search is really fast                                              | Search is slow                                         |
| Takes more storage                                                 | Takes less storage                                     |
| not subscript-able                                                 | subscript-able                                         |
| use when alot of searching through <br>unique elements is involved | use when alot of elements are involved<br>in the array |

Note:- You can `import sys` and use `sys.getsizeof()` to get the size of your list or set

***Tuples ()***
