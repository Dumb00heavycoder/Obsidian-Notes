1)- pyplot is most commonly used for plotting in matplot lib.
`From matplotlib import pyplot as plt` 

2)-Plotting has been completed in introduction

3)-Labeling:- Labeling your graph is very important as it makes it more readable. Here is how you would label a graph created with x and y arrays:-
`age_x = np.array([2,3,4,5,])`
`income_y = np.array([8,9,0,1])`
`plt.plot(x,y)`
`plt.xlabel('Age')`
`plt.ylabel('Income')`
`plt.show()`

4)- Representing 2 data sets:- For example we have 1 data set with column of age, developers income and python developer income. Now we wish to represent these in graphs. Instead of making 2 different graph we can do it all in one as the age is common for both. So a graph with age at x axis and Developers income and python developer income in y axis with two different lines can be created in this way:-
`age_x = np.array([24,5,67,87])`
`income_y = np.array([122,1245,5123,6434])`
`pyincome_y = np.array([1232,412321,1232,1123])`
`plt.plot(age_x, income_y)`
`plt.plot(age_x, pyincome_y)`
`plt.show()`
Now if you wish to label These 2 graphs to show differences you can add a label argument in ur plt.plot line in this way:-
`plt.plot(age_x, income_y, label = 'All devs')`
`plt.plot(age_x, pyincome_y, label = 'Py devs')`
`plt.legend()`
The legend function at the end will display these labels as legend.

4)- Format string:- 
https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html
Format string is used to change colour, marker and line of the plot. One way to do it is by adding format argument in ur plt.plot line
eg:- `plt.plot(age_x, income_y, 'b--')`
B = blue colour
-- = dashed line
U can see these on documentation

 Another explicit and readable way is to pass them as arguments:- 
 eg:- `plt.plot(age_x, income_y, color = 'b',marker = '.' , linestyle = '--')`
 You can also use hex values instead of b
 eg:- eg:- `plt.plot(age_x, income_y, color = '#4444')`

You can make lines thicker with linewidth argument (default value of linewidth is 1).
eg:- `plt.plot(age_x, income_y, linewidth = 3)`

5)- tight_layout method:- To improve padding in the graph so it represents better on other machines ad `plt.tight_layout()` method before `plt.show()`.

6)- grid method:- For better observation you can create a grid which would make ur graph more readable. eg:- `plt.grid(True)`

7)- Styles:- Matplotlib has alot built in styles in it which can be used to make your graph more beautiful and presentable. You can see the list of available styles with this:- `print(plt.style.available)`. To use a style u can type:- `plt.style.use('fivethirthyeight')`. 

You can also use the famous xkcd comic style by simply typing `plt.xkcd()`.

8)- Saving the plot through ur script:- plt.savefig(' plt.png')