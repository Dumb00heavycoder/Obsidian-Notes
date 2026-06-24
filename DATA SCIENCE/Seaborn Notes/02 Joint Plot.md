previous knowledge:- [[DATA SCIENCE/Seaborn Notes/00 Introduction]], [[01 Distribution Plot]]

Joint plot is created with two variables from the data set where we can compare them with different kinds and density estimators. 
1)- plotting:-
`sns.jointplot(x= 'variable1', y = 'variable 2', data = dataframe, kind = 'reg')`
![[Screenshot 2026-06-23 at 10.38.39 PM.png|309]]

In this u get a histogram on the sides of both the variable with dotted plots in center. This is because our kind here is regression.

2)- Types of kind:- 
- Scatter:- Creates a scatter plot with marginal histograms. To see relationship between two numeric variables
- kde:- Creates a Kernel Density Estimate plot. To visualise data density and distribution
- hist:- Creates a 2d histogram plot. Useful when there are many data points
- hex:- Creates a hexbin plot. Useful for large data set where scatter becomes crowded
- reg:- Creates a regression plot with trend line. to analyse correlation and linear trend 
