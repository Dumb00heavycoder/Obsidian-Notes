previous knowledge:- previous knowledge:- [[DATA SCIENCE/Seaborn Notes/00 Introduction]], [[01 Distribution Plot]], [[02 Joint Plot]], [[03 KDE PLOT]]

A pair plot creates a grid of plots where:

- Every numerical column is compared with every other numerical column.
- The diagonal shows the distribution of each feature (histogram or KDE).
- The off-diagonal plots show the relationship between two features (usually scatter plots).

Loading a pair plot:- `sns.pairplot(crash_df)`
![[Screenshot 2026-06-24 at 7.22.01 PM.png|575]]
Why use it?
Before doing any analysis or machine learning, pair plots help you:
-  Find correlations
-  Detect clusters
-  Spot outliers
-  Understand feature distributions
-  See class separation (using `hue`)

Using hue:- 
`import seaborn as sns`
`iris = sns.load_dataset("iris")`
`sns.pairplot(iris, hue = 'species')`

now points will be coloured according to species intensity. 

Lets learn some more features of pair plot:-
1)- selecting columns:-  You can select multiple columns like this with vars argument
`sns.pairplot(`
    `iris,`
    `vars=['sepal_length', 'sepal_width', 'petal_length']`
`)`

2)- Changing diagonal plot:- u can change diagonal plot with diag_kind argument.
`sns.pairplot( iris,  diag_kind='kde' )`

3)- Change non diagonal plot:- Use kind argument
`sns.pairplot(iris,kind='reg')`

When should you use it?
Use pair plots:
- Right after loading a dataset
- During EDA
- For datasets with few numerical features(2–8 columns)
Avoid pair plots when:
- You have many columns (20+)
- Dataset is huge (can become slow)