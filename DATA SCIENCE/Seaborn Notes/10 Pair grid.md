previous knowledge:- previous knowledge:- [[DATA SCIENCE/Seaborn Notes/00 Introduction]], [[01 Distribution Plot]], [[02 Joint Plot]], [[03 KDE PLOT]], [[04 Pair Plot]], [[05 Rug plots]], [[06 Styling]], [[07 Categorical plots]], [[08 Heatmaps]], [[09 Clustermaps]]

`PairGrid` is a Seaborn class used to create a matrix of subplots for visualizing pairwise relationships between variables. Unlike `pairplot()`, it allows different plot types to be mapped to the diagonal, upper triangle, and lower triangle sections of the grid.
Pair grid is like a customisable version of pair plot. 
In pair grid you decide:- 
- What plot goes on diagonal
- What plot goes above diagonal
- What plot goes below diagonal
eg:- 
`plt.figure(figsize=(8,6))`
`sns.set_context('paper', font_scale=1.4)`
`iris_g = sns.PairGrid(iris, hue="species",`
                      `x_vars=["sepal_length", "sepal_width"],`
                      `y_vars=["petal_length", "petal_width"])`
`iris_g.map(plt.scatter)`
`iris_g.add_legend()`

eg2:- 
`import seaborn as sns`
`import matplotlib.pyplot as plt`

`iris = sns.load_dataset("iris")`

`g = sns.PairGrid(iris)`

`g.map_diag(sns.histplot)`
`g.map_upper(sns.scatterplot)`
`g.map_lower(sns.kdeplot)`

`plt.show()`


The map_upper and map_lower puts those types of graph in upper triangle of the figure and lower triangle of the figure respectively. 
