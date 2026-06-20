previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]], [[02 Bar charts and analysing data from csv]]

1)- `plt.pie()` is used make a piechart plot

2)- Labels:- U can create a labels variable and in the list u can add all the labels according to the data. 
eg:-
`slice = [120,40,15]`
`label = ['Apple sold', 'Banana sold', 'Grape sold']`
`plt.pie(slice, labels = label)`

3)- Wedge:- Wedge can be placed whereever the colour changes to make the pie chart look more better with wedgeprops argument. 
eg:- 
`slice = [120,40,15]`
`label = ['Apple sold', 'Banana sold', 'Grape sold']`
`plt.pie(slice, labels = label, wedgeprops={'edgecolor':'black'})`

4)- Changing color:- U can add a color list and put it as an argument to change colours according to u. U can either name them or put the hex code
eg:- 
`slice = [120,40,15]`
`label = ['Apple sold', 'Banana sold', 'Grape sold']`
`colors = ['Blue', '#0045', 'Red']`
`plt.pie(slice, labels = label,colors = colors, wedgeprops={'edgecolor':'black'})`

5)- Pie chart is only good for small data containing 5-6 items. anything more than that will need bar graphs.  

6)- Explode argument = Explode is used to put some emphasis on some particular piece in the pie chart by taking it a little away from the center of the circle. taking it 0.1 away from radius is always fine and readable. 
`slice = [120,40,15]`
`label = ['Apple sold', 'Banana sold', 'Grape sold']`
`explode [ 0, 0.1, 0]`
`plt.pie(slice, labels = label,explode = explode, wedgeprops={'edgecolor':'black'})`

This will explode banana sold section. 

7)- Shadow argument:- Shadow argument will add a shadow to make ur chart look more 3d. 
eg:- `slice = [120,40,15]`
`label = ['Apple sold', 'Banana sold', 'Grape sold']`
`plt.pie(slice, labels = label,shadow = True, wedgeprops={'edgecolor':'black'})`

8)- Start angle:- Changing start angle will shift the pie chart accordingly 
eg:- `slice = [120,40,15]`
`label = ['Apple sold', 'Banana sold', 'Grape sold']`
`plt.pie(slice, labels = label,startangle = 90, wedgeprops={'edgecolor':'black'})`

9)- Showing percentages:- 
eg:- `slice = [120,40,15]`
`label = ['Apple sold', 'Banana sold', 'Grape sold']`
`plt.pie(slice, labels = label,autopct = '%1.1f%%', wedgeprops={'edgecolor':'black'})`