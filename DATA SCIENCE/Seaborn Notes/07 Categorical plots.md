previous knowledge:- previous knowledge:- [[00 Introduction]], [[01 Distribution Plot]], [[02 Joint Plot]], [[03 KDE PLOT]], [[04 Pair Plot]], [[05 Rug plots]], [[06 Styling]]
Categorical plots are used for categorical data and they help u do better analysis and get answers to many questions. 
Here we will be using tips data which is an inbuilt seaborn data set. We will but it in tips_df variable.

1)- Bar plot:- Bar plot can be used for comparing one categorical data with one numerical data. it will plot according to estimator which can either be mean, median, var, covar or standard dev.
eg:- 
`sns.barplot(x = 'sex', y = 'total_bill', data = tips_df, estimator = np.cov )`
![[Screenshot 2026-06-24 at 7.51.31 PM.png|332]]

2)- Count plot:- Count plot can be used to plot the number of occurrences of some values in a variable. It is just like value_counts() function of pandas the only difference is that this plots a graph to represent it. 
`sns.countplot( x = 'sex', data = tips_df)`

3)- Box plots:- box plot allows u to compare different variable by showing quartiles of data. 
sns.boxplot(x = 'sex', y = 'total_bill', data= tips_df, hue = 'sex' )
![[Screenshot 2026-06-24 at 7.56.33 PM.png|490]]
- The line inside the box is the median/50th percentile. 
- The box contains the (IQR) observations from 25th percentile to 75th percentile. So all the observations between Q1 and Q3 are in the box. So a large box means alot of variability and small box means less variability. 
- In Seaborn and most modern boxplots, whiskers show the range of non-outlier data. 
	 eg:- Suppose your data is: [10, 12, 13, 14, 15, 16, 17, 18, 20, 50]
	 So here ur q1 is 13 and q3 is 18. So $IQR = 5$. Now calculate outlier boundaries 
	 $lower limit = q1 - 1.5*iqr  = 5.5$ and $upper limit=  q3 + 1.5*iqr = 25.5.$
	  So whiskers usually fall outside the box but between the upper and lower outlier limit. covering every value outside the iqr. In this example being 10, 12, 18 and 20. These values fall in whiskers but value like 50 is an outlier
	  So there is a lower whisker for values below 25th percentile and upper whisker for values above 75th percentile. 
- The dots are outliers. 
Stick with boxplots when you only need:
	 Median
	 Spread
	 Outliers

4)- Violin plot:- Violin plots are simply box plots + kde plots (distribution shape plot). A box plot tells u median, quartiles and outliers and kde plots tells you the shape of the distribution. Violin does both.
`sns.violinplot(x = 'day', y = 'total bill', data = tips_df, hue = 'sex')`
So this will show days on x axis, total bills on y axis and distribution shape will be according to the sex. If u wanna see the difference between shapes of male and female then add a `split = True` argument in this line. 
![[Screenshot 2026-06-24 at 8.15.26 PM.png|363]]
When to Use Violin Plot
Use when you care about:
	Distribution shape
	Multiple peaks/clusters
	Comparing distributions across categories

5)- Strip plot:- Strip plot shows u every single data point in the variable. 
`sns.stripplot(x = 'day', y = 'total bill', data = tips_df)`
![[Screenshot 2026-06-24 at 8.25.33 PM.png|389]]
To spread it a little add `jitter = True` argument.
You can also add hue to see difference between categories. 
When using variables like sex in hue u can use `dodge = True` argument for separating men and women

6)-  Swarm plot:- Earlier trip plot was only showing u data points. Swarm plot will show u these data points with the shape. It is great to use it with violin plots. 
sns.swarmplot(x = 'day', y = 'total_bill', data = tips_df)
![[Screenshot 2026-06-24 at 8.29.17 PM.png|431]]
You can add a `color` argument to change its colour. 
Using it with a violin plot will give u something like this :- 
`sns.violinplot(x='day',y='total_bill',data=tips_df)`
`sns.swarmplot(x='day',y='total_bill',data=tips_df, color='white')`
![[Screenshot 2026-06-24 at 8.30.18 PM.png|408]]
