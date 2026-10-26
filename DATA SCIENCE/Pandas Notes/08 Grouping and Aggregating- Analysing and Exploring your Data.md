z previous knowledge:- [[00 Why pandas]], [[01 Getting Started]], [[02 Data frames and series basics]], [[03 Indexes- How to set, use and reset indexes]], [[04 Filtering - Using Conditionals to filer rows and columns]], [[05  Updating Columns and Data in Rows]], [[06 Add Remove columns and rows from data frame]], [[07 Sorting data]]

1)- Some aggregate functions:-
You can use these functions on series. If you use them on a data frame they will themselves look for columns with numerical datatype and execute the function. They ignore NaN values.
- mean()
- mode()
- median()
-  describe()
- value_counts()
Using median is better than using mean to describe data sets as mean can be heavily altered by outliers.

2)- Grouping:- In pandas grouping executes these 3 functions in combinations :- Splitting the object, applying  the functions and combining the results. In python you can group elements of column. 
Example 1:-
	Lets take an example from stack overflow data set. Now you wish to know popularity of social media apps according to the countries. So you start on by grouping the countries. First we make a variable for countries:- `country_grp = df.groupby(['Country'])`. This will group data set according to countries. Like a group of USA or a group of India. We can grab these group in this way:- `country_grp.get_group('United States')`. This will return a data frame containing entries from unites states only. It works exactly like a country == 'United States' filter But it is easier to use as it creates a variable which can be used to perform further grouping or functioning. Now we can simply use this code:- `country_grp['Social Media'].value_counts()`. This will then give you the value counts of social medias according to their countries. It'll return a series containing countries and their social media counts. Which will help u to determine which sort of social media is popular in which country. You can also used `country_grp['Social Media'].value_counts().loc['India']` to get social media value counts of india.  Why is it better? Because you can now see social media value counts of every country without having to run a filter on every country. Now you can use the same method to calculate mean, mode, and other stuff on other columns. For example you can now see the median of salaries from every country, value count of employment of every country and much more. 

How to run Multiple aggregate functions on a group:-  
	`country_grp['Salary'].agg(['Mean', 'Median', 'Mode'])`
This will give you the mean, median and mode of every country's salary in a data frame format. 
You can also access these for a specific country in this way
	`countr_grp['Salary'].agg(['Mean', 'Median', 'Mode]).loc['India']`

Example 2:- 
	Now you wish to know how many people in each country know how to use python. 
	We'll do it with both filter and group approach to understand the difference between two
		1)- Filter approach:- first we create our country filter for india and then we apply the programming language filter.
		`filt = df['Country'] == 'India'`
		`df.loc[filt]['LanguageWorkedWith'].str.contains('Python').sum()`
		We used sum here on a boolean statement because sum technically counts True as 1 and False as 0. So output of this code will be the number of people in india who know python.
		2)- Groupby approach:- In groupby you can not use the str function as they are not a series they are a seriesgroupby object. So here we use the apply method in this way:-
		`country_grp['LanguageWorkedWith'].apply(lambdax:`
		`x.str.contains('Python').sum())`
		Here we applied a lamba function on the group. X here works as a series so we can apply str function on it and we'll get The number of people who know python from
		each country. 
	Now lets experiment more with the groupby approach. The number people who know python from each country wont give you any idea of how much more or less people from one country know python than the other. So we might need percentages to compare all the countries. Lets try creating a data frame for this. First lets create a variable Named country respondent which would contain the number of people from each country. 
	`country_respondents = df['Country'].value_counts()`
	`country_respondents`
	This will return a series of countries and people responding from those countries.
	Now lets create a variable named Country_python_users which would contain the number of people who use python from each country
	`Country_python_users = country_grp['LanguageWorkedWith].apply(lambda x: x.str.contains('Python').sum())`
	`Country_python_users`
	Now lets combine Country_python_users and country_respondents with a concat function to make a bigger dataframe.
	`py_df = pd.concat([country_respondent, Country_python_users], axis = columns, sort = False)` 
	Use of axis = Columns is important as it would otherwise contact these two in rows. 
	`py_df` would now return a data frame where these two series have been concatenated according to their countries on the same indexes. You can now change the columns name to make it readable. 
	Now lets try adding a percentage column in this data frame.
	`py_df['Percentage_people_knowing_python'] = (py_df[country_respondent]/py_df[Country_python_users ]) * 100`
	This will now add a column with percentage of people that use python in the countries.

You can now access countries, sort values and what not on this data frame. 