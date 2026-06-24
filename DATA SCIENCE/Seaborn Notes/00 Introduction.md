previous knowledge:- [[10 Subplots]], [[Week 11]]
You use Seaborn with matplot lib. Think of matplot lib as the engine and seaborn as fancy ui on top of matplotlib. Seaborn makes plotting complex graphs easier and it is very powerful to use both of them together
1)- Importing seaborn:- 
	`import seaborn as sns`
	
2)- Seaborn has built in data sets in it which helps u to test seaborn.
U can see these datasets with the following command:-
`print(sns.get_dataset_names())`

3)- Loading the default data set:-
`crash_df = sns.load_dataset('car_crashes')`
