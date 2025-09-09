source:- IITM bs data science degree python course week 11 last lecture

matplot lib is a useful package for data manipulation 

1)- scatter:- 
`import matplotlib.pyplot as plt`
`import numpy as np`
`x = np.array([2,5,5,6,7])`
`y = np.array([3,4,5,6,9])`
`plt.scatter(x,y)`
`plt.show()`
Scatter function will scatter x and y in a graph and plt.show will display it
it works in ipython too
You can add multiple x and y arrays with multiple values all will be plotted with different colours. colour manipulation is possible too.

2)- Bar graph:-
`import matplotlib.pyplot as plt`
`import numpy as np`
`x = np.array(['A','B','C','D','E'])`
`y = np.array([3,4,5,6,9])`
`plt.bar(x,y)`
`plt.show()`
Works exactly like the last one just displays a bar graph now

3)- histogram
plt.hist can be used to display a histogram

4)- piechart
plt.pie can be used to display a piechart

5)- Subplotting:- You can create sub plots in the visualisation area where multiple plots are present. plt.subplot() is used to get this subplot. it takes 3 parameters, first 2 parameters are number of rows and columns the plot will be divided in and 3rd parameter will tell which number of subplot is the this plot. then plt.plot(x,y) will plot the data provided above.
eg :- 
`import matplotlib.pyplot as plt`
`import numpy as np`

`x = np.array([1,2,3,4])`
`y = np.array([4,5,7,8])`

`plt.subplot(1,3, 1)`
`plt.plot(x,y)`

`x = np.array([1,2,3,4])`
`y = np.array([4,5,7,8])` 
`plt.subplot(1,3, 2)`
`plt.plot(x,y)`

`x = np.array([1,2,3,4])`
`y = np.array([4,5,7,8])`
`plt.subplot(1,3, 3)`
`plt.plot(x,y)`

`plt.show()`