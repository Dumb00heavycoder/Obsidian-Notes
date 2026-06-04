previous knowledge:- [[00 Why pandas]], [[01 Getting Started]], [[02 Data frames and series basics]], [[03 Indexes- How to set, use and reset indexes]], [[04 Filtering - Using Conditionals to filer rows and columns]], [[05  Updating Columns and Data in Rows]],[[06 Add Remove columns and rows from data frame]],[[07 Sorting data]], [[08 Grouping and Aggregating- Analysing and Exploring your Data]],[[09 Cleaning data Casting data types and handling missing values]]
Documentation link:- https://docs.python.org/3/library/datetime.html#strftime-and-strptime-behavior
Date offset codes:- https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#dateoffset-objects
Data to practice on:- https://github.com/CoreyMSchafer/code_snippets/blob/master/Python/Pandas/10-Datetime-Timeseries/ETH_1h.csv

1)- Converting columns into date time data type:- 
	`df['Column'] = pd.to_datetime(df['Date'])`
	 You can go on data offset codes to see ur data's date timing format. For example you are given a column in object type in this format :- 2006-12-4 11:00Pm
	 To convert this we'll use this syntax:-
	 `df['Column'] = pd.to_datetime(df['Date'], format =  ' %Y-%m-%d %I-%p)`
	 here I is for 12 hour clock and .P is for pm and am 
2)- Some cool Date and Time functions:-
- day_name():- This would give day name of the index. 
		eg:- `df.loc[0, 'Date'].day_name()`
3)- Setting Date time format while loading csv:-
	Here we should create a function which will parse the format through our date column
	`d_parser = lambda x : pd.datetime.strptime(x, 'Format')`
	`df = pd.read_csv('data.csv', parse_date = ['Date1', 'DATE2'], date_parser = d_parser)`
4)- Other interesting things to do with date time
- You can access dt class in date column and run methods on them
		eg:- `df['Date'].dt.day_name()`
		 This will give you all the day names of every entry in date column
-  You can create new columns named day of the week, year and month to make your data frame more expressive 
-  `df['Date'].min()` will give u the first date of the data
- You can subtract dates to see the dates between them
		examples:- `df.loc[6, 'Date']  - df.loc[3, 'Date']`
		        `df['Date'].max() - df['Date'].min()`
- Filter By dates:- 
	 You can normally filter with strings in this way:- 
		`filt = (df['Date'] >= '2020')`
		`filt = (df['Date'] >= 2019) & (df['Date'] < 2021)`
	 You can also filter by using datetime 
		`filt = df['Date'] > pd.to_datetime( '2020-12-4')`
- You can set Date as your index and do alot of cool stuff:-
	 `df.set_index('Date', inplace = True)`
	and now if you do `df['2020']`, You'll get all the results of 2020. 
	You can also now using slicing:-
	`df['2020-01' : '2020-03']`
	You can get creative with this and find means and modes in this way:-
	`df['2020-01' : '2020-03']['Column'].mean()`
- You can resample data according to days, months and weeks:- For example you have a data which is given in hourly basis. So every row is at a difference of an hour. Now you wish to see this data in basis of days. You can do it with this format:-
		`df['high'].resample('D')`
	    You can also run attributes on this 
	    `df['high'].resample('D').max()`
	    You can put this in a variable and then access that variables dates to get the direct data.
	    eg:- 
	    `High = df['high'].resample(D).max()`
	    `High['2020-01-05]`
  You can plot this with matplot lib which will make this more useful
	  `High.plot()` Will give u a plot of this

Practice questions:- 
1)- Find max high of a day
2)- Find max low of  day
3)- Find max close of a day
4)- Find max high of all data
5)- Find month Which has had overall maximum highs throughout the data. 
 Ask chatgpt to generate more questions