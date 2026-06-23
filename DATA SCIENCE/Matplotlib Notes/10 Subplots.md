previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]],[[02 Bar charts and analysing data from csv]], [[03 Pie charts]], [[04 Stack plots]], [[05 Filling area on line plots]], [[06- Histograms]] [[07 Scatter plots]], [[08 Plotting Time Series and Data]], [[09 Plotting real time live data]]

Figure and axis:-
- Figure is the container holding our plots (think of it as a whole window)
- axis is the plot
So a figure can hold multiple axis and multiple graphs can be represented with one figure. This is how we make subplots

Earlier we have used 
plt.gcf() :- get current figure
plt.gca :- get current axis
There are many approaches to work with multiple figures and axis. We will learn the object oriented approach. 
In this approach we create a fig and multiple axis objects which then we assign and use accordingly. 
Lets take our earlier developers example where we had java devs, all devs and python devs with their respective age and salaries. 
earlier we had all 3 of them on one plot which means all 3 were represented on one axis. Lets try to represent java and python on one axis and all devs on one. 
`import pandas as pd`
`from matplotlib import pyplot as plt`
`plt.style.use('seaborn')`
`data = pd.read_csv('data.csv')`
`ages = data['Age']`
`dev_salaries = data['All_Devs']`
`py_salaries = data['Python']`
`js_salaries = data['JavaScript']`
Here now we make our figure object and axis1 and axis two objects. we also provide the dimensions which here we are using as 2x1 dim.
`fig, (ax1, ax2) = plt.subplots(nrows = 2, ncols = 1)` 
`ax1.plot(ages, dev_salaries, color='#444444', linestyle='--', label='All Devs')`
`ax2.plot(ages, py_salaries, label='Python')`
`ax2.plot(ages, js_salaries, label='JavaScript')`
We set title only for the 1st one as it looks cleaner that way. u can do different stuff with different examples
`ax1.legend()`
`ax1.set_title('Median Salary (USD) by Age')`
`ax1.set_ylabel('Median Salary (USD)')`
`ax2.legend()`
`ax2.set_xlabel('Ages')`
`ax2.set_ylabel('Median Salary (USD)')`
`plt.tight_layout()`
`plt.show()`

If you are making a fig with only multiple rows and 1 column then u can choose to use only 1 x axis by adding argument `sharex=True` in ur object creation line.

Making multiple figures:- 
To make multiple figures you just need to add another figure object. 
In the above example u can just write 
`fig1, ax1 = plt.subplots()`
`fig2, ax2 = plt.subplots()`

This will make 2 figures with two different plots

Saving figures:-
`fig1.savefig('fig1.png')`
`fig2.savefig('fig2.png')`


