previous knowledge:- previous knowledge:- [[00 Introduction]], [[01 Distribution Plot]], [[02 Joint Plot]], [[03 KDE PLOT]], [[04 Pair Plot]], [[05 Rug plots]], [[06 Styling]], [[07 Categorical plots]]
You can make heatmaps with matplot lib but it requires 5-6 lines to make it so we use seaborn mostly for heatmaps as its much easier. 
A heatmap is simply a table where values are represented by colors.
It shows numbers and intensity and is very good for time data analysis to see trends and density of data overtime.
You first have to create a matrix which is a data behind ur heatmap. Correlation matrix are mostly made before using a heatmap. Correlation matrix compares two variables which are then used in heatmap for exmaple u have age, income and spending variables in ur data set. now u wanna see age vs income. To u will create a correlation matrix which will see their relations and compare their values. 
DataFrame  
↓  
corr()  
↓  
Correlation Matrix  
↓  
heatmap()  
↓  
Visual Representation

There are two ways to make correlation matrix.
1)- First is making a correlation matrix of a complete dataset. For example u wanna compare every value of one data set with its every value and make a heatmap on it. So u can do it in this way:- 
Here we are using crash data frame from inbuilt seaborn dataframes 
`crash_mx = crash_df.corr()`

2)- Second method is to correlate variables of one data set. Like the example of age and income which we looked above. 
Here we are using flights data frame from inbuilt seaborn dataframes
`flights = sns.load_dataset("flights")`
`flights = flights.pivot_table(index='month', columns='year', values='passengers')`
pivot_table() function is a very powerful python function. It takes an index, values and compares them according to a value. Like here we create a index month and columns of years and then spread passenger values throughout it. 

Now to plot a heatmap u use this syntax:- 
`sns.heatmap(crash_mx, annot=True, cmap='Blues')`
We here plot crash dataframe by just mentioning the data frame and setting annot argument to true so annotations can be plotted. cmap helps u set the colour

`sns.heatmap(flights, cmap='Blues', linecolor='white', linewidth=1)`
Here we set heatmap for our flights data where we also add linecolour and  linewidth arguments. 
