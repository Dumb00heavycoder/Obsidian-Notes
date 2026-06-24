
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

