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
