previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]],[[02 Bar charts and analysing data from csv]], [[03 Pie charts]], [[04 Stack plots]], [[05 Filling area on line plots]], [[06- Histograms]]

Scatter plots are great when u wanna see the relationship between two values and see if they are correlated.

1)- Use plt.scatter() to plot a scatter plot.

2)- s argument can be used to change the size of the markers. 
`plt.scatter(x, y, s = 100)`

3)- c argument can be used to change the colour of the plot:-
`plt.scatter(x,y, c = 'green')`

4)- marker argument can be used to change the default circle marker to something else like a x.
`plt.scatter(x,y marker = 'X ')`

5)- edgecolor argument is used to give colour to the edge which can further contain linewidth argument and alpha(responsible for softness of color) argument.
`plt.scatter(x,y, edgecolor = 'black', linewidth = 1, alpha = 0.75)`

6)- Using colours to show intensity:- Lets take an e commerce example to understand this well. We have taken a survey of our most loyal customers asking them about their reorders and satisfaction with our company. Let x = number of times a customer ordered kurta and y = number of times a customer ordered dupata. now let satisfaction = how much customers are satisfied with our services (0-10 with 0 being least satisfied). now u can plot a scatter plot of x and y in this way:-
`x = [3,4,5,6,3,8,9,10,4,6,8]`
`y = [6,8,9,5,4,3,7,1,3,5,6]`
`satisfaction= [7,8,5,4,9,3,6,8,9,6,7]`
`plt.scatter(x, y, c = satisfaction,cmap = 'Greens')`
`cbar.set_label('Satisfaction')`
`plt.show()`
cmap is used to change the colour of intensity and cbar.set_label() is used to set label for the satisfaction variable and make it visible in the scatter plot. 

7)- Earlier we used colour to show intensity of a point. We can also use sizes to do the same in this way:- 
`x = [3,4,5,6,3,8,9,10,4,6,8]`
`y = [6,8,9,5,4,3,7,1,3,5,6]`
`satisfaction= [7,8,5,4,9,3,6,8,9,6,7]`
`plt.scatter(x, y, s = satisfaction,cmap = 'Greens')`
`cbar.set_label('Satisfaction')`
`plt.show()`

But this is only useful when ur satisfaction data has values ranging from 0-100 or more as that will help actually show size variability. in 0-10 u will not see alot of size difference between the points