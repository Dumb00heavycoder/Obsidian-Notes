previous knowledge:- [[00 Why pandas]], [[01 Getting Started]], [[02 Data frames and series basics]], [[03 Indexes- How to set, use and reset indexes]], [[04 Filtering - Using Conditionals to filer rows and columns]],[[05  Updating Columns and Data in Rows]], [[06 Add Remove columns and rows from data frame]],[[07 Sorting data]],[[08 Grouping and Aggregating- Analysing and Exploring your Data]],[[09 Cleaning data Casting data types and handling missing values]] [[10 Working with Dates and Time series Data]]

1)- CSV:- We already know how to load a csv file. Lets learn how to export a csv file. For example you created a filter data frame and now you wish to export it into a csv file:-
`filt.to_csv('Path/filt.csv')`.
2)- TSV:- 
- Exporting:- `filt.to_csv('path/filt.tsv', sep = '\t')`
-  Importing:- `df = pd.read_csv('data.tsv', sep '\t')`
3)- Excel:- 
packages you need to install before using excel:- xlwt, openpyxl, xlrd
- Exporting:- `filt.to_excel('Path/filt.xlsx')`
- Importing:- `df = pd.read_excel('path/data.xlsx')`
4)- Json:-
- Exporting:- `filt.to_json('Path/filt.json')` (dict like json)
	  `filt.to_json('Path/filt.json', orient ='records', lines = True)` (list like )
- Importing:- `df = pd.read_json('data.json',)`
5)- SQL:-  Packages needed for sql:- SQLAlchemy, psycopg2-binary
- Importing:- 
	  `from sqlalchemy import create_engine`
	  `import psycopg2`
	  `engine = create_engine('postgresql:// username:password@localhost:XXXX/sample_db ')`
	  `sql_df = pd.read_sql('Sample table', engine)`
- Exporting:- 
	 `filt.to_sql('Sample table', engine, if_exist = 'replace')`
In some cases if you have a url you can simply paste it in ur () while loading the data.  