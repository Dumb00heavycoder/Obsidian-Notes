prev knowledge:- [[Week 1]] [[Week 2]] [[Week 3]] [[Week 4]] [[Week 5]] [[Week 6]] and week 7 was just a bunch of questions.

***Introduction to file handling***
 File handling is all about how to handle files using python. 
 
 Example for context:- there is a big library with 1000s of book and then comes your book shelf with 10 books.  Library is a huge repo of books but it is hard to access and book shelf is easy to access but has limited space 

1)- Basics:- In file handling the very first basic is just reading and writing files. In the tutorial we are using ipython. As i have already covered most of the things about ipython in my python for data science notes so i wont go over it again. 
	a)- Write:-  
	Lets look at how to create and write a file.
	`f = open('Testing.txt', 'w')` (w = write)
	Here we create a variable f which opens a txt file named testing in write format. So we can use this to write to the txt file with the help of our ipython shell
	We can write in that txt file like this:- `f.write('Hi')`
	after writing it down we can write `f.close()` to close the variable. 
	b)- Read:- 
	Lets look at how to read the file we created
	`x = open('Testing.txt', 'r) (r= read)`
	Here we create a variable x and open our txt file in it in reading format.
	now we can create another variable s which will store x in a read function like this
	`s = x.read()`
	printing this s will result in everything written in that file
	![[Pasted image 20250829162812.png]]
	c)- appending:- 
	Now once you are done making and saving the text file to change it and rewrite it you can use 'a' instead of 'w' while opening the variable. then continue using write function to write new lines in that file


	