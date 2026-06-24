Categorical plots are used for categorical data and they help u do better analysis and get answers to many questions. 

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
	 So here ur q1 is 13 and q3 is 18. So IQR = 5. Now calculate outlier boundaries 
	 lower limit = q1 - 1.5*iqr  = 5.5 and upper limit q3 + 1.5*iqr = 25.5.
	  So whiskers usually fall outside the box but between the upper and lower outlier limit. covering every value outside the iqr. In this example being 10, 12, 18 and 20. These values fall in whiskers but value like 50 is an outlier
	  So there is a lower whisker for values below 25th percentile and upper whisker for values above 75th percentile. 
- The dots are outliers. 

4)- Violin plot:- 