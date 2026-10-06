## Introduction to Machine learning:-
Machine learning is a sub field of artificial intelligence concerned with design of algorithm and statistical model that allows computer to learn from and make predictions or decisions based on that data. It utilizes mathematical optimization, algorithms, and computational models to analyze and understand patterns in data and make predictions about future outcomes.
Machine learning is data-driven. The mere presence of data is not enough, what we do with the data matters. Machine learning is the science of learning from data. In the previous problem, no learning is involved.

Why machine learning:- 
Machine Learning is used to automate tasks that would otherwise require human intelligence, to process vast amounts of data, and to make predictions or decisions with greater accuracy than traditional approaches. It also has surged in popularity in recent years. 

Where machine learning:-
Machine Learning is applied in various fields such as computer vision, natural language processing, finance, and healthcare, among others.

What machine learning:-
Machine Learning departs from traditional procedural approaches, instead it is driven by data analysis. Rather than memorizing specific examples, it seeks to generalize patterns in the data. Machine Learning is not based on magic, rather it relies on mathematical principles and algorithms.
## Broad Paradigms of Machine Learning
1)- Supervised Learning:-
Supervised Machine Learning is a type of machine learning where the algorithm is trained on a labeled dataset, meaning that the data includes both inputs and their corresponding outputs. The goal of supervised learning is to build a model that can accurately predict the output for new, unseen input data.
For example, suppose we want to predict whether a student will pass.
We give the model:

| Hours studied | Attendance | Result |
| ------------- | ---------- | ------ |
| 2             | 60%        | Fail   |
| 5             | 80%        | Pass   |
| 7             | 90%        | Pass   |
| 1             | 50%        | Fail   |

Here:
- Inputs/features = hours studied, attendance
- Output/label/target = Pass or Fail
The model looks at many such examples and learns a pattern/relationship between the inputs and the known output.
Then we give it a new student:
Hours studied = 4  
 Attendance = 75%
The correct answer isn't given this time.
The trained model might predict:
 Pass

2)- Unsupervised Learning:- 
Unsupervised Machine Learning is a type of machine learning where the algorithm is trained on an unlabeled dataset, meaning that only the inputs are provided and no corresponding outputs. The goal of unsupervised learning is to uncover patterns or relationships within the data without any prior knowledge or guidance.

For example, imagine we have information about customers:

| Age | Spending |
| --- | -------- |
| 20  | ₹2,000   |
| 22  | ₹2,500   |
| 21  | ₹1,800   |
| 45  | ₹20,000  |
We don't tell the model:
"These three customers are Group A and those three are Group B."
Instead, we simply give it the data.
The model might notice:
```
          Customers
              │
        ┌─────┴─────┐
        ↓           ↓
   Low spending   High spending
     younger        older
```
It has discovered groups/patterns by itself.


3)- Sequential Learning:-
Sequential Machine Learning (also known as timeseries prediction) is a type of machine learning that is focused on making predictions based on sequences of data. It involves training the model on a sequence of inputs, such that the predictions for each time step depend on the previous time steps.
Instead of giving the model the entire dataset at once, data arrives sequentially, and the model can update what it has learned as new data arrives.
For example, imagine predicting tomorrow's stock price:
```
Day 1 → ₹100
Day 2 → ₹103
Day 3 → ₹101
Day 4 → ₹106
       ↓
   Model keeps
   learning/updating
       ↓
Day 5 → prediction
```
The model uses the information it has seen so far and then learns from the next observation.
Here are some types of machine learning problems:-
![[Screenshot 2026-10-06 at 3.43.16 AM.png|461]]

## Unsupervised Learning:- Representation learning
In the topic of unsupervised learning we first study about representation learning. 
To get a better practice of this topic make sure you write and calculate everything on a paper

Representation learning is a fundamental sub-field of machine learning that is concerned with acquiring meaningful and compact representations of intricate data, facilitating various tasks such as dimensionality reduction, clustering, and classification.
Here our goal is to understand something useful about any given data set. 

In this topic our running theme is 
*Comprehension is compression* - George Chaitin
Lets look at a very famous problem:-

In this topic we will refer dimensions/features of every datapoint with d and the number of data points with n.
![[Screenshot 2026-10-06 at 5.05.30 PM.png|580]]
In this example we compress our data set x which has 4 datapoints with 2 features. This compression helps us to store 4 numbers with 2 representation number, in total 6 number which is far better than storing 8 numbers. When data points have alot of features and we are dealing with millions of data points we can achieve almost 50% compression.

We can plot these data points on a line in such a fashion:- 
![[Screenshot 2026-10-06 at 5.08.59 PM.png|608]]
As you can see any vector along the purple line can be chosen as a representative. 
You can also see how we have compared the compressions we performed. 
Earlier without compression we had to store d * n numbers
but after compression representation we are storing d + n numbers
### Dealing with data points which are not on the line
Now lets look at a very interesting example:-
![[Screenshot 2026-10-06 at 5.12.27 PM.png|644]]
Lets first focus on the compression which we did here. as you can see we have a line with points x1 x2 x3 and x4 on it but a data point x5 is not on the line. When we try to compress and represent the line we do get a compressed form but with such compression we are storing more numbers than we were storing without compression. here we will have to store 14 numbers in this compression and earlier we had 10 without compression. So is this compression even worth it? 
We used the 
`{[1 0] [0 1]}` representation so we could easily represent the point x5 which is not on the line. 
Because of this one point x5 our representation suddenly got complicated and we are not able to form a representation which would be in a compressed form. Now we decide to settle on a representation which is not perfect but can be taken as an approximate and that can only be done when x5 lies on the blue line. hence we try to take a x5 proxy point which would be the closest point on the blue line of x5. which we can also call our projection of x5 on the blue line.
![[Screenshot 2026-10-06 at 5.25.19 PM.png|522]]

Lets find out this projection:-

Lets represent our line with :-
```
[W1]
[W2]
```
So our projection of x5 on line `[w1 w2 ]` will be some 
```
C*[W1]
  [W2] 
```
Now we need to find this C. 
The orange line in above figure which is between X5 and X5 projection is our error vector which is the error between x5 and x5 projection. We want length of this error vector to be minimum which will give us the minimum C and the closest projection of x5. ![[Screenshot 2026-10-06 at 5.38.30 PM.png]]
![[Screenshot 2026-10-06 at 5.36.59 PM.png|598]]

This error vector will be:-
`[X1 - Cw1]`
`[X2 - Cw2]`
where x1 and x2 are coordinates of x5 
Why did we length^2

![[Screenshot 2026-10-06 at 5.43.44 PM.png|520]]
![[Screenshot 2026-10-06 at 5.44.33 PM.png|466]]

Now getting back to error vector
After solving we will get these results:-
![[Screenshot 2026-10-06 at 5.46.58 PM.png|409]]
Where we would notice that the numerator is inner product of x and w and denominator is length of w1 w2.
Hence C* can be written as inner product of w and x divided by length of w.
Now that we have C* we can easily write X5 proxy as:-
![[Screenshot 2026-10-06 at 5.51.51 PM.png]]
x transpose is written because u can not directly multiply 2x1 2x1 matrix u will have to take transpose of x and then multiply it in w

As we discussed earlier that we can pick any w1 and w2 on the line. So how about we pick w1 and w2 whose length is 1.
This gives us an advantage and makes our formula easier
![[Screenshot 2026-10-06 at 5.54.38 PM.png]]
Hence C* becomes product of X^t and w multiplied into ``[w1 w2]``

### Finding the best representative line
Till now we have assumed a line in our examples but in real life we will only have data sets with data points and no line would be provided. we will have to draw the data points, draw line and calculate which line is best for representing our data. Lets see how we can do this:-
![[Screenshot 2026-10-06 at 7.46.53 PM.png|505]]

In this present example we have plotted different points and we have made a blue line and a red line for representation. now how can we decide which line is better for representation.
As we know that there will be an reconstruction error in our representation of the line. now logically whichever line has the least reconstruction error will be the best line for representation. 
Now lets find the line with least reconstruction error:-
![[Screenshot 2026-10-07 at 12.19.44 AM.png|629]]
Here we take a dataset, then we try to find the all the reconstruction errors for a line in that dataset. we take summation of all the xi reconstruction error from that line. mtlb jitne bhi x hai data set me unke respective proxy lete wkt kya kya errors ayenge uss line se jispe abhi ham calculations kar rhe hai un sabka summation lena. then we write error of xi which we studied earlier. then we take norm of this and after expanding we reach our final term. xi transpose * xi is a constant and upon minimisation because of differentiating it will become 0 so we can ignore it. 
hence we get the final formulas 
![[Screenshot 2026-10-07 at 12.23.38 AM.png|570]]

If we further expand it we will get this result
![[Screenshot 2026-10-07 at 12.26.35 AM.png|572]]

Upon solving we reach to a point where we see that our result is $w^t C w$. 
Where C is covariance matrix. 
==🔴Hence hamare dataset ka jo covarience matrix hai uske jab ham eigen value nikalenge aur hame uska maximum eigen value milega. aur iss maximum eigen value ka eigen vector jo hoga wo hamara w hai for our dataset.==
These results will only satisfy 2d conditions. 
### Finding best representative line for 3d
Lets see how things will change in 3d:-
![[Screenshot 2026-10-07 at 12.52.08 AM.png|650]]

We make our line here which represents our data and leaves representative errors. In case of 3d these errors might contain important data. so we need some sort of plane rather than a line. If we see carefully we can notice that these error vectors would lie on a line and this line would contain important information which we might want to extract and hence in case of 3d we develop an algorithm to extract all the information.
![[Screenshot 2026-10-07 at 12.56.47 AM.png|539]]

here we develop an algorithm where we first find our w line then we put $(x - (x^t * w)  * w )$ in place of xi and repeat the processes of finding w to extract all the information. here $(x - (x^t * w)  * w )$ is simply our error vectors. 

A problem with this method is that not every data point is near our origin and any data point away from origin might cause a problem. So bringing all the data points to the centre might help us solve this problem.
We can do this by finding mean of our data set the subtracting every data point of our data set from the mean. 
and hence our final algorithm will look like this:-
![[Pasted image 20261007010533.png|422]]

Questions we wish to deal with further this weak:-
![[Screenshot 2026-10-07 at 1.09.26 AM.png|411]]
1)- How to solve MaxW =  $W^t * C* W$

2)- How many times we repeat the procedure in 3d to find best representative line. 

3)- Where exactly is compression happening?

4)- What "representations" are we learning?