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
But agar hum simply deviations ka average lein, positive aur negative values cancel ho jayengi. Isliye deviation ko square karte hain:
(X−μ)^2
that in terms of expected value will turn out to be:- 
$$ \boxed{\operatorname{Var}(X)=E[(X-E[X])^2]} $$

Which means 
Standard deviation:- 
$$ \boxed{\sigma_X=\sqrt{\operatorname{Var}(X)}} $$

Properties:- 
1)- $V(ax) = a^2 v(x)$
2)- $SD(ax) = |a| SD(x)$
3)- $V(x+a) = V(x)$
4)- $SD(x+a) = SD(x)$

We can also simplify the variance formula to:-
$$ \boxed{\operatorname{Var}(X)=E(X)^2-(E[X])^2} $$

#### Independent random variable expected values formulas:-
1)- $E[X+Y] = E(x)+E(y)$
2)- $E(xy) = E(x)E(y)$
3)- $V(x+y) = v(x) +v(y)$
4)- $V(x-y) = v(x) + v(y)$

| Distribution        | Expected Value | Variance          |
| ------------------- | -------------- | ----------------- |
| Bernoulli (p)       | $p$            | $p(1-p)$          |
| Binomial (n,p)      | $np$           | $np(1-p)$         |
| Poisson ($\lambda$) | $\lambda$      | $\lambda$         |
| Geometric (p)       | $\frac{1}{p}$  | $\frac{1-p}{p^2}$ |

### Standardized random variable:- 
A **standardized random variable** is a random variable that has been transformed in such a way that its **mean is 0 and standard deviation is 1**.
If X has mean μ and standard deviation σ, its standardized form is:
$Z=(X−μ )/ σ$ 
where:
- μ=E[X] → Mean
- σ= SD(X)→ Standard deviation
Therefore:
E[Z]=0 
SD(Z)=
#### Interpretation
The standardized value Z tells us how many standard deviations X is away from its mean.
For example, Z=2 means the value is 2 standard deviations above the mean, while Z=−1.5 means it is 1.5 standard deviations below the mean.

Haan, iska intuition actually **bahut simple** hai. Formula dekhke confusing lagta hai, but iska kaam basically **different scales wali values ko same scale par lana** hai.

Maan lo tumhare paas students ke marks hain:

- Class A ka average = **50**, SD = **10**
- Class B ka average = **80**, SD = **5**

Ab kisi student ke marks **70** hain.

Sirf 70 dekhke kuch khaas nahi pata. Kyunki Class A me 70 bahut achhe marks hain, lekin Class B me 70 average se neeche hain.
#### Read this for intuition 
Standardization ye problem solve karta hai
Hum poochte hain:
Ye value apne average se kitni SD door hai?
Formula:
Z=X−μ/σ
For Class A:
Z=(70−50)/10=2
Matlab:
70 marks = **mean se 2 standard deviations above**
Class B:
Z=(70−80)/5=−2
Matlab:
70 marks = **mean se 2 standard deviations below**
Toh actual intuition:
Normal value:
 **"Mere marks 70 hain."**
Standardized value:
**"Mere marks class ke average se 2 SD upar hain."**


### Covariance and correlation:-
#### Covariance:- 
Let X and Y be two random variable. To know if X and Y move in same direction or opposite we use Covariance. Do they increase or decrease at same rates when values are changed is the question we ask here. 
The formula to find covariance is:- $$ \text{Cov}(X, Y) = E\big[(X - E[X])(Y - E[Y])\big] $$
The intuition of this formula is very simple. We first check the variance of X and Y independently (Asking ki x aur y ki values unke average se kitni dur hai). Then we multiply them and find the results expected value.
This multiplication helps us multiply their directions which helps us to identify what kind of variance do they have. 

If Cov(x,y) > 0, Then there is a positive covariance 
If Cov(x,y) < 0, Then there is a negative covariance
If Cov(x,y)= 0, Then there is no covariance

#### Properties of Covariance
1)- $Cov(X,X) = V(X)$
2)- $Cov(X,Y) = E(XY) - E(X)E(Y)$ (Use this formula for maximum solving )
3)- $Cov(x, ay + bz) = a Cov(x,y) + b Cov(x,z)$
4)- $Cov(ax + by,z) = a Cov(x,z) + b Cov(y,z)$

##### If x and y are independent then X and Y are uncorrelated 
##### But if X and Y are uncorrelated that does not mean they are independent 

#### Correlation
Covariance has one major problem that it gives us a Digit but that digit is not sufficient enough to tell how strong that relationship is between those two variables. So we need a normalised version of covariance which is correlation.
Correlation will ask about how strongly are X and Y related in a particular direction independent of their units. 
$$ \rho_{X,Y} = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y} = \frac{E\big[(X - E[X])(Y - E[Y])\big]}{\sqrt{E[(X - E[X])^2]} \sqrt{E[(Y - E[Y])^2]}} $$
Because of dividing Cov(X,Y) with SD of x and y the correlation lies between -1 and 1.
Hence if 
$\rho$ ~ +1 the relation is strong positive 
$\rho$ ~ -1 the relation is strong negative
$\rho$ ~ 0 there is no relation

#### Correlation ≠ Causation
- Correlation between two variables does not mean that one causes the other.
- A third variable may influence both variables.
Correlation does not imply causation.

#### Covariance & Correlation in Data Science
- Used to understand relationships between variables/features.
- Helps in **Exploratory Data Analysis (EDA)**.
- Correlation can help identify:
  - Related features
  - Redundant features
  - Multicollinearity
- Covariance is important in **PCA** and covariance matrices.

### Bounds on Probability 
Often we dont know the exact distribution of our values of a random variable and in those times we are unaware of our probability. In those cases we might want to find out at least/at most how much probability lies in a particular region. 
To find these bounds of probability we use Markovs inequality and chebyshevs inequality. 

#### Markovs Inequality:- 
Let X be a random variable and X >= 0.
and for a c> 0 
$$ P(X \ge c) \le \frac{E[X]}{c} $$
This formula will give us upper bound.
For intuition lets take an example:-
Suppose average income of a company is ₹50,000
Now we wanna say something about proportion of people earning ₹2,00,000
So we use Markovs inequality:-
P(X>= 200000)<= 50000/200000 = 0.25
P(X>= 200000) = 0.25 = 25%
Hence now we can say that less than 25 percent must be earning 200000 or more. 

Markov intuition in one sentence
If the average is small, there cannot be too much probability sitting at very large values.
Because if a lot of observations were huge, the average itself would have to become huge.

Lower bound formula :- $$ P(X < a) \ge 1 - \frac{E[X]}{a} \quad \text{for all } a > 0 $$
Upper bound tells us the maximum percentage of possible values of our condition while lower bound tells us the minimum guaranteed values ki probability. 

#### Chebyshevs Inequality:- 
Markov only uses the mean While chebysheves inequality uses the variance 
$$ P(|X - \mu| \ge k\sigma) \le \frac{1}{k^2} \quad \text{for all } k > 0 $$
 Chebyshev's Intuition
- Chebyshev tells us **how much data must lie close to the mean**, regardless of the distribution's shape.
- It measures distance from the mean in terms of **standard deviations**.
- For example:
  - Within $2\sigma$ → at least **75%** of values
  - Within $3\sigma$ → at least **88.89%** of values

$$
P(|X-\mu| < k\sigma) \geq 1-\frac{1}{k^2}
$$
Intuition: The farther we move from the mean, the more values we are guaranteed to find within that range.
Why Chebyshev's Inequality is Powerful
- It works for **any probability distribution**.
- We do **not** need to know the shape of the distribution.
- It only requires:
  - Mean $\mu$
  - Standard deviation $\sigma$
**Key idea:** Even without knowing the distribution, Chebyshev gives a guaranteed minimum proportion of values near the mean.


#### Markov vs Chebyshev

|                | Markov                         | Chebyshev                                   |     |     |
| -------------- | ------------------------------ | ------------------------------------------- | --- | --- |
| Gives bound on | Large values                   | Distance from mean                          |     |     |
| Requires       | $X \geq 0$                     | Mean + variance                             |     |     |
| Formula        | $P(X\geq c)\leq\frac{E[X]}{c}$ | $P(\|X-\mu\|\geq k\sigma)\leq\frac{1}{k^2}$ |     |     |
| Main use       | Upper tail                     | Spread around mean                          |     |     |
| Strength       | More general                   | Usually tighter                             |     |     |

Remember: Markov → large values. Chebyshev → values far from the mean.


#### Practice questions:- 
![[Screenshot 2026-09-11 at 2.57.52 AM.png|568]]
