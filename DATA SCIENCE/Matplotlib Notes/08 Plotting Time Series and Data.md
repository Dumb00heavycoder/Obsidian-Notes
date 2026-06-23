previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]],[[02 Bar charts and analysing data from csv]], [[03 Pie charts]], [[04 Stack plots]], [[05 Filling area on line plots]], [[06- Histograms]] [[07 Scatter plots]]
1)- Important libraries and methods to import when using time series data:-
`from datetime import datetime, timedelta`
`from matplotlib import dates as mpl_dates`

2)- preferred style for time series data :- `plt.style.use('seaborn')`

3)- plotting dates:-
`dates = [`
    `datetime(2019, 5, 24),`
    `datetime(2019, 5, 25),`
    `datetime(2019, 5, 26),`
    `datetime(2019, 5, 27),`
    `datetime(2019, 5, 28),`
    `datetime(2019, 5, 29),`
    `datetime(2019, 5, 30)`
`]`
`y = [23,57,78,12,24,78,21]`

`plt.plot_date(dates, y)`

This will most probably be plotted with dots. To change it into solid lines add this argument:- 
`plt.plot_dates(dates, y, linestyle = 'solid')`
u can also remove markers with `marker = none` argument 

4)- Auto formatting dates:- Dates are present in a bad and weird format so to fix it u can add this before plt.show():-
`plt.gcf().autofmt_xdate()`

5)- Changing formats of date with mpl_dates:- 
First create a variable named date format:- 
`date format = mpl_dates.DateFormatter('%b , %d %Y')`
then add it into plt.gca argument:- 
`plt.gca().xaxis.set_major_formatter(date_format)`
You can check other date time format codes from here- https://docs.python.org/3/library/datetime.html#strftime-and-strptime-behavior

6)- Whenever working with a time series data always make sure that its data type is in datetime otherwise it will not load dates in order. Use pandas to change the data type of date column and make sure to sort it also.