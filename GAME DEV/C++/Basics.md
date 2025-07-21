Context:- Do not refer these notes if you are a beginner.  I already know c++ since June 2024 so this note session is just a revisit and a virtual documentation for me to refer in future. 
Lets begin
![[Pasted image 20250721181009.png]]

C++ is a low level language created by Bjarne Storstrup. It works very close to the hardware and is great for memory management. Mostly used in competitive programming, video game development and lower end programming. 

***print program***
`#include <iostream>`
`using namespace std;`

`int main() {`
	`cout << "Hello world"<< endl;`
	`return 0;`
`}`

explanation:- 1)- our header line includes a stream of input output 
2)- namespaces are containers which contain functions. std namespace (standard namespace) is a namespace which contains the standard functions used in c++ like cout, vector, string etc.
3)- int main () is starting of our function. int tells our computer that this main function will return a integer value. This means that every time this main function will execute it will execute everything line by line and if it is done successfully it will reach the line return 0; which is a command that returns 0 to our computer to tell it that the program ran successfully. main is written to name our main function which executes the program. 
4)- cout is gonna print and endl simply means end line.  << is insertion operator which is used in inserting and >> is an extraction operator. 

***variables and comments***

- You can comment a line with // this is a comment 
- You can comment multi lines with `/*this is a comment` 
	`a multiline comment  */`

- variables are the same:- 
	int, float, string, char, double, boolean. 
	Name range is 1 to 225 char
	all name should start from letter or underscore
	after first alphabet a variable name can have numbers
	variables are case sensitive
	dont use reserved c++ words while making variable

- Because there is a function system in c++ so we also have local and global variables. They can have same names but the local variable is always preferred by the function over a global. 
- There are 3 types of data types in c++ 
	- 1)- Built in:- int, float, double,char and bool
	- 2)- user define:- struct, union, Enum
	- 3)- derived:- Array, function, Pointer
***Input***
Input syntax:- 
	`cin >> num 1;`
	`or` 
	`cout << "Enter a number ";`
	`cin >> num1;`

***Header files and operators***
system header files already exist but even users can create their own header files. 

***Operators***
Just like python we have 3 types of operators here also.
	1)- Arithmetic Operators:- +, -,  x, /, %, --a, a--, ++a and a++.
		a++, ++a, --a and --a are increment and decrement operators respectively. 
		a++ will first print/use the current value of a and after execution it will increment the value of a. ++a will first increase the value of a and then print it. same for the - one.
	2)- Comparison Operators:- `==, < , >, !=, <=, >=`
	3)- Logical operators:- && (and), || (or), !(not).
		example of ! operator:- 
				`cout << !(n1= n2) << endl;`

***Some more tips on variables***
Scope resolution operator can be used to change the scope of a variable. :: is the operator which will allow you to access the global variables. 
eg:- 
`#Include <iostream>`
`using namespace std;`
`int c = 10`
`int main () {`
`cout << ::c << endl;`
`return 0;`
`}`

every decimal in cpp is taken as a double to make it float write f after the number.
`d = 32.4f`

sizeof() function can be used in cpp


***Reference variables and typecasting***
- Reference variables:- giving different names to one data type.  
	 eg:- float x = 24.5;
		float & y = x;
- Type casting:- Changing a variables data type. 
		eg:- float b = 45.6
			cout << int(b); 

***Constant, manipulators and operator precedence***
- Operator precedence also exists in c++ just like it did in python and c.

- Constants:- constant variables are immutable variables. These can not be changed once created. eg:- `const int a = 3;`

- Manipulators:- manipulators are some inbuilt functions which improve the data display. Like endl and [[Setw (c++ manipulator)]]

***
