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