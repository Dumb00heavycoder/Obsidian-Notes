previous knowledge required:- [[Week 1]]
**More on variables, operators and expressions** 
- Key words can not be used as variable names 
- variable names are  ==case sensitive== 
- you can multi assign multi variables 
	 eg:- `x,y = 6,7`
	 `x=y=z=10`
- you can delete variables by using ==del== keyword
	 eg:- `del x`
- short hand operator:- `x += 1` will add 1 in the value of x, you can do the same for multiplication, subtraction and division 
- ==in== operator can be used to check if some characters are present in some variable.
- chaining operator can be used to chain 2 relational operator in one line
	 eg:- `10 < x < 20`
  
**ESCAPE CHARACTER & TYPE OF QUOTES***
- Escape characters are special characters which can be interpreted in a different way by the language. So to avoid this confusing interpretation we use "/". 
	- [[Escape characters]]
- To ask the compiler to read multiple lines as a string we use triple quotes 
	- [[Reading multi-line in python]]

**String Methods or Functions**
- [[String Functions list]]
- String letters can be called like array elements 
- modulo can be used to repeat string letters
- For better understanding of calling out strings and playing with them understand [[Caesar cipher]]

**If Statement**
- Syntax :-
	- `if ( condition):`
		 `statement`
	 `else:`
		`statement`
Problems to practice
- [[Even or odd problem]]
- [[Given number ends with 0 or 5 return true]]
- [[Find Grades of student based on given marks from 0 to 100]]

**Some-Libraries**
- [[Math library]]
- [[Random library]]
- [[Calendar library]]
- To use functions of libraries without importing them simply type `from (library) import (function)`
- You can even change name of the function by writing `as (alias)` in the import line
