### Cumulative distribution function (CDF)
We already know about pmf. It talks about the distribution of probability among the values of a random variable. It helps us to exactly pin point probability of a particular value of a random variable. 

In some cases we might want to know the probability of range of value of x. For example we might ask a question that what is the probability of X being smaller than this number or greater than this number. That is exactly what CDF tells us. 

$FX​(x)=P(X≤x)$

The word cumulative is important, it means adding up all probabilities up to x. 
For example:- 
$FX​(3)=P(X≤3)$ 
Which means
$FX(3) = P(X=1) + P(X=2) + P(X=3)$
This example is of Continuous discrete random variable 
#### Properties of CDF
1. **Non-decreasing**
   As $x$ increases, $F_X(x)$ can only increase or remain constant.
   $$
   x_1 < x_2 \Rightarrow F_X(x_1) \leq F_X(x_2)
   $$
2. **Bounded between 0 and 1**   $$
   0 \leq F_X(x) \leq 1
   $$
3. **Limit at $-\infty$**
   $$
   \lim_{x\to-\infty}F_X(x)=0
   $$
4. **Limit at $+\infty$**
   $$
   \lim_{x\to\infty}F_X(x)=1
   $$
5. **Right-continuous**
   $F_X(x)$ is continuous from the right.

We have already worked on CDF os a discrete random variable so here we will focus on CDF of a continuous random variable. 


### Continuous Random Variable 
In discrete random variable we had individual possible values and their probabilities but what if these list of values becomes extremely big. So big that doing calculations on a discrete value becomes impossible. Thats when we introduce continuous random variable which helps to describe probabilities of random variables with big list of values.
In CRN probability of one exact value is generally 0 so here we calculate probabilities of intervals. 

A random variable X is called a continuous random variable if its CDF FX(x) is continuous at every x.
- f(x) is non decreasing 
- P(X < a) = F(a)
- P(X=x) = 0
- P(a =< x =< b) = P(x =< b) - P(x =< a) = F(b) - F(a) 
- As P(X = a) = 0 and P(X = b) = 0 :- $P(a < X < b) = P(a \le X < b) = P(a < X \le b) = P(a \le X \le b)$

#### Some scenarios for continuous models:-
- Throw a dart onto a circular board - distance of the point of impact
- from the center of the board.
- Weight of a metoerite hitting earth
- Weight of a human being, height of a human being
- Speed of a delivery in cricket
- Price of a stock
- Many discrete random variables are well-approximated by continuous random variables that are much simpler to describe

![[Screenshot 2026-09-11 at 3.59.36 AM.png|562]]