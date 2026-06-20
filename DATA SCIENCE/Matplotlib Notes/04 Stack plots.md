previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]], [[02 Bar charts and analysing data from csv]], [[03 Pie charts]]

1)- Stacking:- Stacking plots are used when comparing many values over one attribute. stacking means placing multiple values on top of each other so they appear as one combined chart element. 
It is great for seeing and organising things over time
eg:- 
`from matplotlib import pyplot as plt`
`plt.style.use("fivethirtyeight")`
`minutes = [1, 2, 3, 4, 5, 6, 7, 8, 9]`
`player1 = [1, 2, 3, 3, 4, 4, 4, 4, 5]`
`player2 = [1, 1, 1, 1, 2, 2, 2, 3, 4]`
`player3 = [1, 1, 1, 2, 2, 2, 3, 3, 3]`
#labeling
`labels = ['player1', 'player2', 'player3']`
#settingcolour
`colors = ['#6d904f', '#fc4f30', '#008fd5']`
`plt.pie(minutes, player1,player2,player3, labels=labels, colors= colors)`
#setting_loc_for_legend
you can also add coordinates in legend
`plt.legend(loc='upper left')`
`plt.title("My Awesome Stack Plot")`
`plt.tight_layout()`
`plt.show()`  
  