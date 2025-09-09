1- Ipython shell is great here are some basic commands for intro:- 
		ipython = launch
		? = introduction of ipython and features 
		%quickref = quick reference
		help = help system
		object? = details about object

Ipython shell is great with documentation. If you wanna know about some inbuilt or userbuilt python function you can easily get it in ipython by using ?. Just place ? after the function and you'll get what it does. 
![[Pasted image 20250821133826.png]]

You can use ?? to get source code of some functions. This will only work with functions which are written in python. functions like len which are written in c will just their function and no source code will be displayed.


***Shortcuts***
1)- navigation shortcuts:-
![[Pasted image 20250824000819.png]]

2)- text entry shortcuts:- 
![[Pasted image 20250824000950.png]]

3)- command history:- 
![[Pasted image 20250824001344.png]]

4)- miscellaneous:- 
![[Pasted image 20250824001406.png]]



***Magic commands***
These are some special commands of ipython which you can use over python. These are prefixed with % sign it can be single or double. line magics, which are denoted by a single % prefix and operate on a single line of input, and cell magics, which are denoted by a double %% prefix and operate on multiple lines of input. lets discuss these:- 

1)- %paste = This will paste whatever you copied with proper indentation and also execute it

2)- %cpaste = This will open up an interactive multiline prompt in which you can paste one or more chunks of code to be executed in a batch:

3)- %run = you will likely find yourself working in both IPython for interactive exploration, as well as a text editor to store code that you want to reuse. Rather than running this code in a new window, it can be convenient to run it within your IPython session. This can be done with the %run magic.
Just cd into the folder you wanna run your program in and right %run program.py

4)- %timeit = When you use this command behind a function it will tell  you the amount of execution time of that one line

5)- %%time = Works exactly like %time but for multiple lines

6)- %history = prints history of last inputs according to your need.
![[Pasted image 20250824211037.png]]


You can access documentation of magic functions with the help of ?. To access a general description of available magic functions, including some examples you can type %magic.
For a quick and simple list of all available magic functions you can type %lsmagic



***Input and output***
In ipython  the input and output is stored in form of a variable. You can access these just like other variables. 
eg:- 
![[Pasted image 20250824210109.png]]

You can also see all outputs and inputs in together
![[Pasted image 20250824210215.png]]
The In object is a list, which keeps track of the commands in order
The Out object is not a list but a dictionary mapping input numbers to their outputs
Note that not all operations have outputs: for example, import statements and print statements don’t affect the output. The latter may be surprising, but makes sense if you consider that print is a function that returns None; for brevity, any command that returns None is not added to Out.

In python underscore holds the value of last output. if you do `print(_)` you will get the previous output. in ipython shell  you can use double or triple _  to get last to last or the 3rd last output.

A shorthand for writing  `Out[x]` is `_X`

Sometimes you might wish to suppress the output of a statement (this is perhaps most common with the plotting commands that we’ll explore in Chapter 4). Or maybe the command you’re executing produces a result that you’d prefer not to store in your output history, perhaps so that it can be deallocated when other references are removed. The easiest way to suppress the output of a command is to add a semicolon to the end of the line:  `math.sin(2) + math.cos(2);` Note that the result is computed silently, and the output is neither displayed on the screen or stored in the Out dictionary.

***Ipython and shell commands***
When working interactively with the standard Python interpreter, one of the frustra‐ tions you’ll face is the need to switch between multiple windows to access Python tools and system command-line tools. IPython bridges this gap, and gives you a syn‐ tax for executing shell commands directly from within the IPython terminal. The magic happens with the exclamation point: anything appearing after ! on a line will be executed not by the Python kernel, but by the system command line. The following assumes you’re on a Unix-like system, such as Linux or Mac OS X.
(34)



