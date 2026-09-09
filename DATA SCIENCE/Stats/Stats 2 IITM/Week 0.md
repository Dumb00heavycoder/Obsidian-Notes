## Common Distributions 
The idea of a distribution is to assign probability to each of the individual outcomes in sample space.

1)- Bernoulli trials:- Occurrence of a event A in a sample space is considered as a success and non occurrence is considered a failure. A Bernoulli trial is a trial where we are concerned with whether the outcome of some trial will be a success or a failure. Here we use 1 for success and 0 for failure 
eg:- Will a toss of a coin result in head?
$sample space = {success, failure}$
Let $P = P(A)$
with $P(success)  = P$
and 
$P(failure)= 1-P$
2)- Repeated Bernoulli trials (n):- Performing N independent single Bernoulli(p) trial is known as repeated Bernoulli trials. 
$samplespace = 2^n$

eg:- For $n = 3$ we can get these possibilities
$2^3 = 8$
1)- $P(0,0,0) = (1-P)(1-P)(1-P) = (1-P)^3$
2)-  $P(0,1,0) = (1-P)(P)(1-P) = (1-P)^2 (P)$
.
.
.
8)- $P(1,1,1) = (P)(P)(P) = P^3$


3)- Binomial Distributions (n,p):- Here we perform n Bernoulli trials and our focus is to predict number of success which we get.  So here we are just concerned with the number of success. 
eg:- How many heads will come if we toss a coin 10 times?
Number of success is denoted with $B(n,p)$

imp formula:- P(B(n,p)= K) = $\binom{n}{k}$ $p^k (1 - P)^{(n-k)}$ 

4)- Geometric Distribution (P):- In Geometric distribution we try to find the number of trials it would take to get our first success. 
eg:- In how many balls will i hit my first six?
$P(G=n ) (1-P)^{(n-1)} P$


## Random variables 
1)- Uniform random variables:- In uniform random variable all outcomes in the set T share same probability.
x~ Uniform(t), where T is some finite set. 
Range = Finite set T
$PMF = Fx (T) = 1/|T|$ for all t E T

2)- Bernoulli random variable:- 

