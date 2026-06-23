previous knowledge:- [[00 Introduction to Matplotlib]], [[01 Creating and customising our first plot]],[[02 Bar charts and analysing data from csv]], [[03 Pie charts]], [[04 Stack plots]], [[05 Filling area on line plots]], [[06- Histograms]] [[07 Scatter plots]], [[08 Plotting Time Series and Data]]

Lets first see how live data and animations work together with a dummy example.

`import random`
`from itertools import count`
`import pandas as pd`
`import matplotlib.pyplot as plt`
`from matplotlib.animation import FuncAnimation
`plt.style.use('fivethirtyeight')`
`x_vals = []`
`y_vals = []`
`index = count() #count function updates index variable with a +1` 
`def animate(i)`
	`x_vals.append(next(index))`
	`y_vals.append(random.randint(0,5))`
	`plt.cla() #plt.cla() helps u clear the axis so that eveyrytime ur plot animates it doesnt change the colour`
	`plt.plot(x_vals, y_vals)`
`ani = FuncAnimation(plt.gcf(), animate, interval = 1000) #1 thousand intervals mean 1 second` 
`plt.tight_layout()`
`plt.show()`

count() creates index variable an iterater. 

def animate(i) function is responsible for running every frame and decides how it will behave. i here is the frame number. 

plt.cla() removes axis as everytime animation runs it redraws over the last drawing which can cause inaccuracy. 

ani = FuncAnimation( plt.gcf(), animate, interval=1000) creates an animation object. plt.gcf() means get current figure which helps us to get the figure. it is important as inside figure we have axis and inside axis we have plot. animate is our function which we are calling again and again. Interval gives the time after which funct animation will recall our function animate.

Here is the flow:- 
FuncAnimation starts    
v  
Call animate(0)  
v  
add x=0  
add random y  
clear graph  
draw graph  
v  
wait 1000 ms  
v  
Call animate(1)  
v  
add x=1  
add random y  
clear graph  
draw graph  
v  
repeat forever

You can create your own python scripts which generate data and run them. then u can create a live/realtime plot on it. 
Lets take an example:- 
Here is a script that u can create:- 
`import csv` 
`import random`
`import time`
`x_value = 0` 
`total_1 = 1000` 
`total_2 = 1000`
built in csv modules are used here. Study about them to learn more
`fieldnames = ['x_vales', 'total_1', 'total_2']`
`with open('data.csv', 'w') as csv_file:`
	`csv_writer = csv.DictWritter(csv_files, fieldnames =fieldnames)`
	`csv_writer.writeheader()`
`while True:`
	`with open('data.csv', 'a') as csv_file:`
        `csv_writer = csv.DictWriter(csv_file, fieldnames=fieldnames)`

        info = {
            "x_value": x_value,
            "total_1": total_1,
            "total_2": total_2
        }

        csv_writer.writerow(info)
        print(x_value, total_1, total_2)

        x_value += 1
        total_1 = total_1 + random.randint(-6, 8)
        total_2 = total_2 + random.randint(-5, 6)

    time.sleep(1)

After this script edit ur matplotlib file:-
`import random`
`from itertools import count`
`import pandas as pd`
`import matplotlib.pyplot as plt`
`from matplotlib.animation import FuncAnimation`

`plt.style.use('fivethirtyeight')`
`x_vals = []`
`y_vals = []`
`index = count()`
`def animate(i):`
    `data = pd.read_csv('data.csv')`
    `x = data['x_value']`
    `y1 = data['total_1']`
    `y2 = data['total_2']`
    `plt.cla()`

    plt.plot(x, y1, label='Channel 1')
    plt.plot(x, y2, label='Channel 2')

    plt.legend(loc='upper left')
    plt.tight_layout()


`ani = FuncAnimation(plt.gcf(), animate, interval=1000)`

`plt.tight_layout()`
`plt.show()`