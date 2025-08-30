previous knowledge required:- [[01 Getting Started]]

Source:- IITM BS DATA SCIENCE python course week 11 3rd lecture

Data frame is a 2 dimensional data structure used to store tabular data and the columns in this data frame are known as series. 
Here i'll be writing some of the examples i did in my class which are complex and helpful.
 here are these examples:- 
 
 1)- Printing a column:-  just use the following syntax `print(dataframe['column name'])


2)- Printing details of a particular entry:- 
use the following syntax `print(dataframe[ dataframe['column'] == 'name of the entry'])`. It can be used in scores data set where you wish to find out all the scores of a particular kid. This line inside the `data frame[] is` gonna work like a boolean statement. it will go through the rows of the column you mentioned and generate true and false statement then it is gonna return whatever says true. You can filter students score, gender wise data and what not


3)- Applying 2 filters:- Lets consider the score data set and for example now you wish to see total marks of all the male and female students.we can breakdown this problem in 2 parts. First we filter gender and then we filter total marks. With the help of previous example we can write a small code `print(score[score['Gender'] == 'M'])` to apply the gender filter. now to add total filter we can just add `['Total']` after the gender filter line.
hence we get = `print(score[score['Gender'] == 'M'] ['Total'])`
General syntax = `print(df[df['column'] == 'name of the entry']['another column]')`
Now you can add more layers to it for example after total you write .max() to get highest total score by a male student and many more filters. 


4)- Using relational  operators:- Lets reconsider the score dataset and now you wish to grade these students in physics . So you create a category with students above 85, students between 75 and 85, students between 50 and 75. You can use relational operator in this way:- `print(score[score['Physics'] > 85])` for between 75 and 85 you can use .between(lower limit, upper limit) function like this:- `print(score[score['Physics'].between(70, 85)])` and you can do it further. you can also use .shape function just get the number of students in these category. shape gives you rows and columns in the printed dataframe so you can just add .`shape[0]` after your filter to get the number of students (rows in data frame) in the filtered data frame you printed. 
eg:- `print(score[score['Physics'].between(70, 85)].shape[0])`

You can even ==use &== operator to add more filters. For example lets now try printing number of  male students who got marks between 70 and 85 in physics. `print(score[(score['Gender'] == 'M') & (score['Physics'].between(70, 85))].shape[0])`
you can try using or too in your project.

5)- Using for loops:- Now in last example try printing number of male students who's marks are between 70 and 85 in physics math and chemistry. now you can copy paste it but the right way would be to make a for loop. You can create a list L containing 3 subjects Math, Physics, Chemistry. Then iterate through this list and put the variable in place of the subject you wrote in last example. 
L = ['Math', 'Chemistry', 'Physics']
for sub in L:
	print('number of male students with marks Between 70 and 85', sub)
	`print(score[(score['Gender'] == 'M') & (score['sub'].between(70, 85))].shape[0])`	

