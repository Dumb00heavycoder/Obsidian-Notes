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
- items of a structure have un-shared memory means each variable has its own located memory. Which allows the multi-use of items
**2)Unions**:- Unions are just like struct but you can only use one of their variable at one time. 
eg:- `union money{`
		`char car;`
		`int rice;`
		`float pound;`
`}`

- Items in union share same memory that's why only one of them can be taken at a time. if taken more than two than garbage value will be returned. 
- Sharing memory of items allows it to occupy less space and increase runtime of program.

**3) Enumerations**:-  Enums are created like arrays and used inside the main function. 
eg:- 
`int main () {`
	`enum Meal {Breakfast, lunch, dinner}`
	`Meal M1= lunch;`
	`cout << Breakfast << endl;`
	`return 0;`
`}`
ps:- i really dont get their use and understand them enough rn but maybe in future. 

***Functions & functions prototypes*** 
1)- Functions are functions just like python. In c++ functions return values to the compiler depending on the type of their function. you can create void functions too which returns nothing. 

2)- Functions prototype is a prototype of our function which works like calling by name or reference use to in C. simply if your function is located below your main function or it is located below a function where it is being used. then you can mention a function prototype in the above function to tell the compiler that the function you encounter right now does exists and as you read on you will find it. so it will look for that function and make your thing work. 
[[Function prototype example]]


***Basic knowledge***:-
- actual parameters:- parameters in main functions which we actually interact with.
- formal parameters:- parameters of user defined function which we dont interact with.