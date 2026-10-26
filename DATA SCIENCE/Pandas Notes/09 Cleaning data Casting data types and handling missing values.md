 
 previous knowledge [[00 Why pandas]],[[01 Getting Started]],[[02 Data frames and series basics]],[[03 Indexes- How to set, use and reset indexes]],[[04 Filtering - Using Conditionals to filer rows and columns]],[[05  Updating Columns and Data in Rows]],[[06 Add Remove columns and rows from data frame]],[[07 Sorting data]],[[08 Grouping and Aggregating- Analysing and Exploring your Data]]

1)- Dealing with missing values:- 
- `dropna()` :- This drops any index with missing values
- `dropna(axis = 'index', how = 'any' )`= would drop any index with even one na value. How argument asks the question of what type of index or column to be dropped. The ones that have few missing values(any) or the ones with all values missing (all).
- `dropna(axis = 'index', how = 'all')`= Drops only indexes with missing values
- `dropna(axis='columns, how = 'all')` = Drops columns which have every value missin
 - `dropna(axis='column', how= 'any')`= would drop columns with 1 or more Na values. (This might drop every column in ur data frame if you have even one index with all Nan values) 
 - NaN values are of Float type
If only some columns in a dataframe concern you and u want to drop the indexes which has those specific columns missing, You can do that in this specific way:-
`df.dropna(axis = 'index', how = 'any', subset = {'Last', 'Email})`
This would drop the rows that have last name and email missing 
You can also give Na values some other values with this:-
`df.fillna('Missing', inplace = True).This is very helpful for numerical features


2)- Dealing with customised missing values:-  For example you are taking a survey and people had no idea what to answer in some questions so they pass in strings like Na or missing values which are customised missing values. To deal with these values you can replace them with na values with the help of numpy
`df.replace('NA', np.nan, inplace = True)`
`df.replace('Missing', np.nan, inplace = True)`
You can also treat these right when you load ur csv
Create a Na_value variable and put it in ur load argument in this way:-
`na_vals = ['NA', 'Missing', 'MISSING',]`
`df = pd.read_csv('result.csv', na_values = na_vals)`

3)- Casting Datatype:- 
You can start with `df.dtypes` attribute to get data types of all features. 
If you have a object column which you wish to turn into an integer column then u can simply use this code :- `df['column'] = df[column].astype(int)`
This would only work if there is no NaN values in the column.  If Na values exist then u must replace them  or cast the column to float. 
Getting an error while casting would majorly mean that many entries in that data type can not be converted. So its important u use the unique() method and deal with these unique entries.

