previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]]

1)- Overlaying bar and line charts:- You can plot some y values in bar and others in normal lines and they both will simply overlay on each other
eg:-
`age_x = np.array([24,5,67,87])`
`income_y = np.array([122,1245,5123,6434])`
`pyincome_y = np.array([1232,412321,1232,1123])`
`plt.bar(age_x, income_y)`
`plt.plot(age_x, pyincome_y)`
`plt.show()`

2)- Plotting multiple bars:- You can not simply represent two bar graph in one in the standard way like u did with lines. If u do that then the bars will stack on top of each other.  To fix with problem we use numpy and width argument of bars. We first import numpy and create a x_indexes variable which will contain the values in age_x in a array format index wise. This will help us manipulate these indexes to shift bars. Then we will create a width variable which will have width or our bar and we'll add it in our plt.bar() line to width argument. After changing age_x to x_indexes in plt.bar lines we will add or subtract the width of from x_indexes according to our graph. If we have 3 we'll subtract from first, leave 2nd as it is and add width to the 3rd one. If we have 2 graphs we'll subtract from first or add to the second. 
eg:-
`import numpy as np`
`age_x = np.array([24,5,67,87])`
`x_indexes = np.arrange(len(ages_x))`
`width = 0.25`
`income_y = np.array([122,1245,5123,6434])`
`pyincome_y = np.array([1232,412321,1232,1123])`
`plt.bar(x_indexes - width, income_y, width = width)`
`plt.bar(x_indexes, pyincome_y, width = width)`
`plt.show()`

Now they will be lined up side by side. 
Just because we have now changed our x axis to x_indexes our x axis will not be like earlier and we'll have to make some changes to fix it. For that we can use ticks method in this way:- 
plt.xticks(ticks = x_indexes, labesl = age_x) 
 This will keep x axis ticks like x_indexes  and label age_x values.
  