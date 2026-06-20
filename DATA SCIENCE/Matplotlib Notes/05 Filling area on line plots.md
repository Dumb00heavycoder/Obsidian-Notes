previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]],[[02 Bar charts and analysing data from csv]], [[03 Pie charts]], [[04 Stack plots]]
Fills are great for making plot nice and professional and can give useful insights if u use them good. 
It simply helps you to fill under the lines or above the line to compare one line from another. Lets take our old example again where we have earnings of types of developer. Lets compare earnings of python developers to earnings of average developers according to their ages. 
`import pandas as pd`
`from matplotlib import pyplot as plt`

`data = pd.read_csv('data.csv')`
`ages = data['Age']`
`dev_salaries = data['All_Devs']`
`py_salaries = data['Python']`
`js_salaries = data['JavaScript']`
`plt.plot(ages, dev_salaries, label = " All devs")`
`plt.plot(ages, py_salaries, label = "Py devs")`
`plt.fill(ages, py_salaries)`
`plt.legend()`
`plt.title('Median salaries by age')`
`plt.xlabel('Ages')`
`plt.ylabel('Median Salary')`
`plt.tight_layout()`
`plt.show()`

Here plt.fill will fill the python salaries graph. You can add a alpha argument in plt.fill to make it a little transparent like this:-
`plt.fill(age, py_salaries, alpha = 0.25)`

Now if you wish to separate this will according to the median. Which basically means that it'll first fill from below to median than from top to median like this:- 
![[Screenshot 2026-06-20 at 7.18.51 PM.png|325]]
To do this make overall median variable containing the median value and add it as an argument in the fill line:- 
`overall_median= 5487`
`plt.fill(age, py_salaries,overall_median, alpha = 0.25)`
Now if you want to fill the part where python salaries are more then median salaries than u can add an argument like this:- 
where = py_salaries > overall_median
`overall_median= 5487`
`plt.fill(age, py_salaries,overall_median, where = (py_salaries > overall_median), alpha = 0.25)`
Now u can use this to split the fill above median salary and below median salary and plot them in different colours.
`overall_median= 5487`
`plt.fill(age, py_salaries,overall_median, where = (py_salaries > overall_median),color = 'blue' alpha = 0.25)`
`plt.fill(age, py_salaries,overall_median, where = (py_salaries <= overall_median), color = 'red' alpha = 0.25)`
![[Screenshot 2026-06-20 at 7.23.21 PM.png|329]]
A better comparison would be to fill above and below average dev salaries to see in what age group people using python earn less or more than the all developer line. 
Final code:- 
`import pandas as pd`
`from matplotlib import pyplot as plt`
`data = pd.read_csv('data.csv')`
`ages = data['Age']`
`dev_salaries = data['All_Devs']`
`py_salaries = data['Python']`
`js_salaries = data['JavaScript']`
`plt.plot(ages, dev_salaries, color='#444444',`
         `linestyle='--', label='All Devs')`
`plt.plot(ages, py_salaries, label='Python')`
`overall_median = 57287`
`plt.fill_between(ages, py_salaries, dev_salaries,`
                 `where=(py_salaries > dev_salaries),`
                 `interpolate=True, alpha=0.25, label='Above Avg')`
`plt.fill_between(ages, py_salaries, dev_salaries,`
                 `where=(py_salaries <= dev_salaries),`
                 `interpolate=True, color='red', alpha=0.25, label='Below Avg')`
`plt.legend()`
`plt.title('Median Salary (USD) by Age')`
`plt.xlabel('Ages')`
`plt.ylabel('Median Salary (USD)')`
`plt.tight_layout()`
`plt.show()`