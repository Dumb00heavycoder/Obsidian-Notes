previous knowledge:- [[DATA SCIENCE/Seaborn Notes/00 Introduction]]

Distribution plots provide univariate distribution for one variable. 

1)- To plot a distribution plot of any variable in our data frame we use the following command:- 
`sns.distplot(df['variable'])`
![[Screenshot 2026-06-23 at 10.29.33 PM.png|298]]
2)- This simply displays a histogram with a kernel density estimation line which helps u make better estimations. To remove it u can just add `kde= False` argument in ur plot line
`sns.distplot(df['variable'], kde = False)`

3)- Changing bins in ur histogram:- add a bin argument in the plot line
`sns.distplot(df['variable'], bins = 5)`
