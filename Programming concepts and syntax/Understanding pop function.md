pop function in list i used to remove and return the last element of a list. 
a statement like `print(l.pop())` will return the last element of the list and a statement after that like `print(l)` will print the list without the last element
You can also list the index of the element you want to remove in the brackets. 

eg:- 
	`l = [10, 20, 30]`
	`x = l.pop()  # Removes 30`
	`print(x)     # Output: 30`
	`print(l)     # Output: [10, 20]`

	l = [10, 20, 30]
	`x = l.pop(0)  # Removes item at index 0, which is 10`
	`print(x)      # Output: 10`
	`print(l)      # Output: [20, 30]`
