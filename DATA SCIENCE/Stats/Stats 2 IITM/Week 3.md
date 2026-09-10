### Expected value
Expected value if the average of a random variable. This represents the centre of a random variable. 
An official definition would be- **Expected value** (mathematical expectation) is basically the **long-run average outcome of a random experiment**.
Forumla:- $$
E[X] = \sum_{i=1}^{n} x_i P(X=x_i)
$$

#### Properties of expected value:- 
1)- $E[C] = C$, where c is a constant 

2)- Linearity of Expectation
For random variables (X) and (Y):
$$  
E[X+Y] = E[X] + E[Y]  
$$

More generally:
$$  
E[aX+bY] = aE[X] + bE[Y]  
$$
This holds even if (X) and (Y) are not independent.

3)- Constant Multiple
For a constant (c):  $E[cX] = cE[X]$ 

4)- Expectation of a Function
For any function (g(X)):
$$  
E[g(X)] = \sum_x g(x)P(X=x)  
$$
For a continuous random variable:
$$  
E[g(X)] = \int_{-\infty}^{\infty} g(x)f_X(x),dx  
$$
5)- Independence
If (X) and (Y) are independent:
$$  
E[XY] = E[X]E[Y]  
$$Independence is required for this property in general.

6)- Expectation of a Non-negative Random Variable
If (X >= 0), then:

$$  
E[X] \geq 0  
$$
7)-If (X <= Y)
If (X) is always less than or equal to (Y):
$$  
X \leq Y  
$$
then:
$$  
E[X] \leq E[Y]  
$$


#### Zero mean Random variable:- 
A zero mean random variable is simply a random variable that is always equal to zero.

X=0with probability 1
Therefore,
$E[X]=0$
More generally, for any random variable $Y$:
$E[0 * Y]=0$

It's mainly useful when understanding linearity of expectation and simplifying expressions


### Variance 
Variance basically talks about how much spread the values of random variable are around its mean.
Suppose X ka mean 
E[X]=μ
Har value X, mean se kitni door hai:
X−μ
But agar hum simply deviations ka average lein, positive aur negative values cancel ho jayengi. Isliye deviation ko **square** karte hain:
(X−μ)^2