previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]],[[02 Bar charts and analysing data from csv]], [[03 Pie charts]], [[04 Stack plots]], [[05 Filling area on line plots]]
For example you take a survey and now u want to see the age groups that responded to the survey and to plot this bar chart will not be a good idea as it would  include 100 different possible ages which means 100 different bars which wont suit. So we use histograms
Histograms work in bins or a range. for example x axis will have readings of 20-25 and a bar will be there showing how many people in our survey are in the age group of 20-25. 
Here is how to make a basic histogram plot:-
`plt.hist(ages, bin = 5, edgecolor= 'black')`
This would divide all our ages into 5 regions.  
To make custom bins u can create a bin list containing ur bins
`bin = [10, 20,30,40,50]`
`plt.hist(ages, bin = bin, edgecolor = 'black')`
 If some of ur values are really big then the other small values will not be visible on ur histogram. So u can use log scale to not make it so extreme.
 `bin = [10, 20,30,40,50]`
`plt.hist(ages, bin = bin,log = True, edgecolor = 'black')`

Now lets try adding a line to the median age so we can see which age groups have alot of response above the median age. 
`plt.axvline(median_age, color=color, label='Age Median', linewidth=2)`
`plt.legend()`
