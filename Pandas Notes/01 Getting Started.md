*Pandas is a data analysis library which is used to analyse data given in csv and other sort of file types. It is also a very fast library because it is built on Numpy.*

==Before getting started you should learn about package installers like [[UV package manager]]and [[Virtual environment (venv)]]==

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
**Attributes**
- `df.shape` = it gives you (rows, columns )
- `df.info` = it gives you the rows and lists the columns with their data types
- `df.head(number of rows)` = to see the first rows
- `df.tail(numbe of rows)` = to see the last rows
- `df.count()` = to display the count of entries in each column 
- `df['rowname/ columnname'].max()` = to find maximum entry of the row or column
- `df['rowname/ columnname'].min()` = to find minimum entry of the row or column
- `df['rowname/ columnname'].mean()` = to find mean of the row or column
- `df['rowname/ columnname'].sum()` = to find sum of the row or column