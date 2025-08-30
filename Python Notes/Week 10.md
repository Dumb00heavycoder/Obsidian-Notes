Previous knowledge :- [[Week 1]] [[Week 2]] [[Week 3]] [[Week 4]] [[Week 5]] [[Week 6]] [[Week 8]] [[Week 9]] 
***Introduction to object oriented programming***
Object oriented programming is considered as a standard way to program. It considers every real time object (living and non living) as a core living entity. for example me, my laptop, my bottle. these objects have attributes and behaviours which makes them unique.
these attributes can be stored with variables and we can write functions for these objects for manipulation and calculations. All these variables are different for every object in a class which makes every object unique. Everything in oop revolves around the object and translates real life problems in programming.

***Classes and objects***
For example an architecture engineer develops a blueprint of a house and uses that blueprint in 100 houses. now the structure of all the house will be same but colour, name, location, interior will be different. Classes work exactly like the blueprint and objects work like the 100 house.
*standard tip*:- keep class name's first letter capital 

Lets understand how all of this works with a standard example:- 

eg1-
`class Students:`
	`roll_no = None #attribute`
	`name = None #attribute` 
`s0 = Students() #This is student() is a constructor`
`s0.roll_no = 0 #object 1`
`s0.name = 'Dhruv'` 
`s1 = Students()  #object 2`
`s1.roll_no = 1` 
`s1.name = 'Ditya'`
`s2 = Students()`
`s2.roll_no = 50`
`s2.name = 'Prakhar' #object 3`
`print( s0.roll_no, s0.name)`
`print( s1.roll_no, s1.name)`
`print( s2.roll_no, s2.name)`

First we make our class and name it. as soon as the class is created python creates a function named Students(). This function is known as a constructor as it helps constructing an object. then we create attribute roll number and name of our class students. then we create 3 objects s0, s1 and s2. now lets see how to add behaviour to this class.

eg2-
`class Students:`
	`def __init__(self, roll_no, name, total): #init method`
		`self.roll_no = roll_no`
		`self.name = name`
		`self.total = total`
	`def display(self):` 
		`print( self.roll_no, self.name)`
	`def result(self): #behaviour` 
		`if self.total > 120:`
			`print('Pass')`
		`else:`
			`print('Fail')`

`s0 = Students(0, dhruv, 130)` 
`s0.display()`
`s0.result()`

`s1 = Students(1, Ditya, 150)`
`s1.display()`
`s1.result()`

`s2 = Students(2, Mick, 80)`
`s2.display()`
`s2.result()`

In this class we created 3 methods (we refer methods to the functions which are present in a class). 1st we created `__init__`  which works as a default input function with constructor. any parameter you put in constructor will fall into this function and its usually used to construct the object. display method just displays the output and result method is the only method which works as a behaviour as it decides behaviour of the objects. who will pass who will fail etc. 

***Inheritance and method overriding***
Lets start with an example:- You and your brother inherit alot of things from your mom and dad. Your mom is naturally good at painting which is something you have inherited from your mother. Your father has brown hair which is something your brother inherited from your father. now you wish to learn basketball and you end up adding another skill to your skill set which already consists of something which was given by your mom. and your brother gets his hair coloured to blonde which completely replaces his fathers inherited hair colour. What you did is inheritance and adding on and what your brother did is method overriding. 
eg:- 
`class Person: #parent class / super class`
	`def __init__(self, roll_no, name):`
		`self.roll_no = roll_no`
		`self.name = name`
	`def display(self):`
		`print(self.roll_no, self.name)`
`class Schl_student(Person): #child class / sub class`
	`def __init__(self, roll_no, name, total marks):`
		`super().__init__(roll_no, name)`
		`self.totalmarks = totalmarks`
	`def display (self):`
		`super().display()`
		`print(totalmarks)`
`class Clg_student(Person): #child class / sub class`
	`def __init__(self, roll_no, name, cgpa):`
		`super().__init__(roll_no, name)`
		`self.cgpa= cgpa`
	`def display (self):`
		`print(self.roll_no, self.name, self.cgpa) #method override`
`s = Schl_student(0, 'Dhruv', 700 )`
`s.display()`

`c = Clg_student(1, 'DItya'. 9.5)`
`c.display`

In this first we create a parent function person which consists of roll number and name in its init function and displays them in its display function. Then comes the first sub class schl_student which inherits Person class and uses its init and display function. Clg_students only uses init function and it overrides the display function.

To create private members all you have to is use two underscores before the member. for example write `self.__age` . this will make age member a private member to the Person class.


Now lets discuss something interesting. Last code is very big for my small head so i would love to make different folders containing different classes and use them in my main.py. I can create a person.py, Clg_student.py and Schl_student.py and put the classes in these folders. Then i can write From Clg_students import Clg_student and From Schl_student import Schl_student in my main.py .  This will import these classes from other folders and use them in main.py. In my clg and schl student files i will have to import person too so they can use person as a parent class. 


***Types of inheritance***
![[Pasted image 20250830190504.png]]
![[Pasted image 20250830190514.png]]
![[Pasted image 20250830190525.png]]
![[Pasted image 20250830190534.png]]


at last comes hybrid inheritance which is just a mixture of all of these. 

Task:- Create a OOP project. Make different files and use everything you have learned. 