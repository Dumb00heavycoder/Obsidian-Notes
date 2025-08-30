Previous knowledge :- [[Week 1]] [[Week 2]] [[Week 3]] [[Week 4]] [[Week 5]] [[Week 6]] [[Week 8]] [[Week 9]] 
***Introduction to object oriented programming***
Object oriented programming is considered as a standard way to program. It considers every real time object (living and non living) as a core living entity. for example me, my laptop, my bottle. these objects have attributes and behaviours which makes them unique.
these attributes can be stored with variables and we can write functions for these objects for manipulation and calculations. All these variables are different for every object in a class which makes every object unique. Everything in oop revolves around the object and translates real life problems in programming.

***Classes and objects***
For example an architecture engineer develops a blueprint of a house and uses that blueprint in 100 houses. now the structure of all the house will be same but colour, name, location, interior will be different. Classes work exactly like the blueprint and objects work like the 100 house.
*standard tip*:- keep class name's first letter capital 

Lets understand how all of this works with a standard example:- 
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
