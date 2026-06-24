
To study styling we must take an example. We will be using car crash built in seaborn data set to learn about styling:- 
`crash_df = sns.load_dataset('car_crashes')`
`sns.set_style ('white')` setting style for axis and grid. u can use darkgrid, dark, whitegrid and many more.
`sns.jointplot(x = 'speeding', y = 'alcohol', data = crash_df, kind = 'reg')`

1)- Changing size:- 
eg:- `plt.figure(figsize = (8,4))`

2)- Changing style of label, text and design with one line:- 
eg:- `sns.set_context('paper', font_scale = 1.4)`
other styles u can add here are poster and talk. 

3)- removing x an y axis lines:- 
`sns.despine(left  = True, bottom = True)`
 u can also use top and right arguments

4)- Palettes:- 
Lets understand palettes with some other example.  Here we will use tips data frame which is a built in seaborn data frame containing data of tips given in a restaurant.
Its always a good practice to first load your figure, style, and context.
eg:- 
`plt.figure(figsize = (8,5))`
`sns.set_style('dark')`
`sns.set_context('paper')`
`sns.stripplot(x= 'day', y = 'total_bill, data = tips_df, hue = 'sex'`)

This will give you a default graph with ur style, figure and context choices. Now lets try changing the colours by setting palettes.
https://matplotlib.org/stable/users/explain/colors/colormaps.html Use this link to see different colour maps
Lets use magma colourmap with palette magma.
`sns.stripplot(x= 'day', y = 'total_bill, data = tips_df, hue = 'sex', palette = 'magma')`


5)- Change legend:- You can change location of ur legend with matplot lib function 
`plt.legend(loc = 0)`
enter different locations like u did in matplot lib 

