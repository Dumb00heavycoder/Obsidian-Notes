### Introduction to Machine learning:-
Machine learning is a sub field of artificial intelligence concerned with design of algorithm and statistical model that allows computer to learn from and make predictions or decisions based on that data. It utilizes mathematical optimization, algorithms, and computational models to analyze and understand patterns in data and make predictions about future outcomes.
Machine learning is data-driven. The mere presence of data is not enough, what we do with the data matters. Machine learning is the science of learning from data. In the previous problem, no learning is involved.

Why machine learning:- 
Machine Learning is used to automate tasks that would otherwise require human intelligence, to process vast amounts of data, and to make predictions or decisions with greater accuracy than traditional approaches. It also has surged in popularity in recent years. 

Where machine learning:-
Machine Learning is applied in various fields such as computer vision, natural language processing, finance, and healthcare, among others.

What machine learning:-
Machine Learning departs from traditional procedural approaches, instead it is driven by data analysis. Rather than memorizing specific examples, it seeks to generalize patterns in the data. Machine Learning is not based on magic, rather it relies on mathematical principles and algorithms.
### Broad Paradigms of Machine Learning
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

### Unsupervised Learning:- Representation learning
In the topic of unsupervised learning we first study about representation learning. 
Representation learning is a fundamental sub-field of machine learning that is concerned with acquiring meaningful and compact representations of intricate data, facilitating various tasks such as dimensionality reduction, clustering, and classification.
Here our goal is to understand something useful about any given data set. 

In this topic our running theme is 
*Comprehension is compression* - George Chaitin
