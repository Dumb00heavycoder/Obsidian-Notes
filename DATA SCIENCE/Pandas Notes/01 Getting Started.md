
**Installation**
1)- `sudo pacman -S python-pandas` (This command is used for arch as I'm using arch btw.)
2)- `sudo pacman -S jupyterlab` [[Jupyter]]
3)- For data we are going to use StackOverflow Survey  (available here:- https://survey.stackoverflow.co/)

**Setting up our data and notebook**
- Create a folder of your project and put your data folder inside the project folder
- On terminal cd into the project folder and type `jupyter notebook` to start jupyter
- after opening it you can create a new notebook 

**Basics**
- Start your data analysis with importing pandas as pd
- use `df = pd.read_csv(path_to_your_csv_file)` to read your csv file 
- you can use `pd.set_option('display.max_columns or rows', number_of_rows or columns)` to see the max of columns or rows u wish to see
- df means data frames which we will be exploring in next session
- by typing df you can print your data frame
- In data you are given a schema file which contains the questions associated to the columns. to read it u can use `schema_df = pd.read_csv(path to the csv)` and write schema_df to see the schema 
- In pandas there is no and keyword like python you need to use & 
**Attributes**
- `df.shape` = it gives you (rows, columns )
- `df.info` = it gives you the rows and lists the columns with their data types
- `df['column'].nunique()` = gives the unique or discrete values in that column
- `df.head(number of rows)` = to see the first rows
- `df.tail(numbe of rows)` = to see the last rows
- `df.count()` = to display the count of entries in each column 
- `df['rowname/ columnname'].max()` = to find maximum entry of the row or column
- `df['rowname/ columnname'].min()` = to find minimum entry of the row or column
- `df['rowname/ columnname'].mean()` = to find mean of the row or column
- `df['rowname/ columnname'].sum()` = to find sum of the row or column
- `df.groupby('attribute').groups`= This forms a dictionary with keys being the attribute given by you and it puts all the data in those keys. attribute can be something like gender or more like a filter. helps in bins for example when you wish to print something 2 or 3 times and you dont wanna use loops for it. 
- iloc[n] =  Stands for integer location. It allows you to select rows and columns by their integer positions (e.g., 0 for the first row, 1 for the second, etc.).
- `idxmax()`=  returns the index (label) of the maximum value.
- `.get(index, return)` = Looks for the index and if not found will return whatever is in return section. eg = `.get('hindi', 0)`, this will look for hindi in the index and if not found it will return 0. 