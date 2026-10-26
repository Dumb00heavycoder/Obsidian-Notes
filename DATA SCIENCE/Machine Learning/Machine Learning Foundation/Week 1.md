This week we will take a look at basic terms and basic problems of this course
## What is Machine Learning
Machine learning is the study of computer algorithms that improve automatically through experience and by the use of data.
## Task Hierarchy:- 
![[Screenshot 2026-10-13 at 9.18.44 PM.png|497]]
In Task hierarchy machine learning is used to create tools to perform some tasks which are not easy to perform with a programming language and manual labour.
A weather prediction example
![[Screenshot 2026-10-13 at 9.20.41 PM.png|484]]

Is it beneficial to do every task with machine learning?
No, machine learning require vast resources and any task which can be easily done with manual labour or programming should be done with them. Ml is mostly used when we have huge amounts of data and alot of observation is needed on data to make predictions or reach at some solutions. 

## What is Data?
Data is a collection on vectors in machine learning which contain information about the data. 

## What is a model?
A model is a mathematical simplification of reality.
For example the inverse square law of gravitational attraction.

In machine learning we use models to simply reality and we have types of these models. Lets go through these types one by one:-

## Predictive Model:- 
A model which learns through data, picks up patterns and conclusions and then uses it to predict something. That is a predictive model. There are 2 types of predictive model which we will study here:-

 1)-Regression model:-
Regression is a machine learning technique used to predict a numerical value. predicting quantity, amount or any sort of number comes in regression model. 
Example:-
House pricing
temp of a certain day
marks of a student
revenue of a company in a certain time period

2)-Classification Models:-
Classification is a machine learning technique used to predict a class or a category. 
Here we predict the type of category of a certain thing.
Example:-
email spam or not
student pass or fail
cat or dog in image
loan application risk low, medium or high.

## Probabilistic Models:-
Representing uncertainty or certainty of some event using probability is a probabilistic model in machine learning. Instead of giving predictions it estimates how likely different outcomes are. 
example:-
Probability of a chosen tweet being a tweet by elon muskc
Probability of a chosen person in india being the age of 35

## Learning Algorithm 
A learning algorithm is a procedure that learns patterns from training data to build or improve a machine learning model. It also choose a correct model from collection of models with same structure but different parameters. 
This is how task hierarchy would look after learning these new terms 
![[Screenshot 2026-10-26 at 4.47.33 PM.png]]

Important notation before moving further:-
![[Screenshot 2026-10-26 at 4.31.25 PM.png]]

## Supervised learning:-
Supervised Machine Learning is a type of machine learning where the algorithm is trained on a labeled dataset, meaning that the data includes both inputs and their corresponding outputs. The goal of supervised learning is to build a model that can accurately predict the output for new, unseen input data.
But at its core
==🔴Supervised learning is curve fitting== 
In simple terms we go through our data, look at the models we have and chose the model which will have the minimum loss. which makes that model the most accurate model from all the models we have. 

There are two parts to Supresvised learning, Regression and classification. Lets first study 
### Regression:-
We already know what a regression model is. So here we will focus on how to deal with regression models and how to pick the best regression model for a dataset:-
Basics of a regression model:-

1)- Training data might look like :- `{(x1, y1), (x2,y2), (x3, y3), (x4,y4), ... , (xn, yn)}`
, Where X E R^d
and Y E R
2)- Algorithm outputs a model $f : \mathbb{R}^d \to \mathbb{R}$
3)- $\text{Loss}^{[f]} = \frac{1}{n} \sum_{i=1}^{n} (f(\mathbf{x}^i) - y^i)^2 = \text{squared loss}$
4)- $f(\mathbf{x}) = \mathbf{w}^\top \mathbf{x} + b = \sum_{j=1}^{d} w_j x_j + b$ This is a linear parameterisation.
Most models in regression are presented in this way. where w is weight, x is our input and b is a bias.

An regression model with least loss will be the best model for that data. 

Lets study some important regression illustrations which you should practice in your register:-
![[Screenshot 2026-10-26 at 5.12.32 PM.png]]
Here the core idea is to see which of these two models will our learning algorithm pick:-
In this example our x is in one dimension which means it has one vector. then we are given y and we make 2 models f(x) and g(x). Then we plot them and find out the results of x according to f(x) and g(x). Then we calculate loss and in this example f(x) clearly has less loss so it is a better model than g(x)
Lets study second example
![[Screenshot 2026-10-26 at 5.16.02 PM.png]]
In this example our x has 3 dimensions, which means 3 vectors. Rooms, area and distance. We again create two models, calculate loss and see which one is more fitting. 

### Classification:- 
We already know what a classification model is so here we will focus on how do we deal with data sets requiring classification models:- 
Basics of classification model:-
1)- Training data looks like:-  `{(x1, y1), (x2,y2), (x3, y3), (x4,y4), ... , (xn, yn)}`
Where x E R^d
and Y E {+1, -1}
2)- Algorithm outputs a model $f : \mathbb{R}^d \to \{+1, -1\}$
3)-  $\text{Loss}^{[f]} = \frac{1}{n} \sum_{i=1}^{n} \mathbb{1}(f(\mathbf{x}^i) \neq y^i) = \text{Fraction of training data classified wrongly by } f$. So here you would input the number of times f is wrong when compared to y
4)- $f(\mathbf{x}) = \text{sign}(\mathbf{w}^\top \mathbf{x} + b)$:-  $\text{Linear separator}$

Lets see some illustrations:- 
Practice these illustrations by writing them down in rough
![[Screenshot 2026-10-26 at 5.41.13 PM.png|559]]
Illustration 2:- 

![[Screenshot 2026-10-26 at 6.01.31 PM.png|594]]