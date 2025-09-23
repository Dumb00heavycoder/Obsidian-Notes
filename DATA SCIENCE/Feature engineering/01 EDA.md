***EXPLORATORY DATA ANALYSIS STEPS:-***
EDA is a step of analysis where we observe our data. This can be done in such a structure:- i)- Numerical features count {Historgrams, pdf function}
ii)- Categorical features count 
iii)-  locate Missing values or visualise all graphs and observe {Visualise all graphs}
iv)- outliers {Box plot}
v)- cleaning 


A very basic workflow is to observe the following things first:-
1)- Missing values
2)- All the numerical variables 
3)- Distribution of the numerical variables 
4)- Categorical variables
5)- Cardinality of Categorical variable 
6)- Outliers
7)- Relationship between independent and dependent feature(SalePrice)


***Finding missing values:-*** 
First we need to find the missing values in our data and for that we will try to find out the percentage of NaN values in all the features . 

`#1 Collecting the features with NaN values`
`features_with_Na = [features for features in df.columns if df[features].isnull().sum()>1]`
`#2 print features name and percentage of missing values`
`for features in features_with_Na:`
	`print(feature, np.round(dataset[feature].isnull().mean(), 4), '% missing values')`
