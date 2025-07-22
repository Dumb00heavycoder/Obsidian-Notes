Previous knowledge req:- [[Basics 1]]
![[Pasted image 20250722165556.png]]
***Structures, Unions and Enumerations***
Structures, Unions and Enums are user defined data types in c++.
**1)- Structures**:- Struct is an aggregate of elements of arbitrary types. 
eg:- 
`struct Address {`
	`const char = name;`
	`int number;`
	`const char = street;`
	`constant char = town;`
	`char state[2];`
	`const char = zip;`
`}`

this struct consist of items called/used to send someone mail in USA. So here we have created variables who's data type is address. name, number, street are all variables of data type address used for a certain function. 

Lets see how to use it:-
`void f() {`
	`Address dc;`
	`dc.name = "Dhruv chaudhary";`
	`dc.number = "00000000000"`
	`dc.street= "Rk puram"`
`}` 
here dc is our variable which is of address data type and then we use the items inside address data type to create name, number and street variables for dc variable and store value in them.

rules of struct:-
- structure variables can be accessed by anywhere hence it is not strong             on the security part. 
- You can not use functions inside a struct.
**2)Unions**:-
