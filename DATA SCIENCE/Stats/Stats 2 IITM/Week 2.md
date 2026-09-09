### Independence of two random variable:- 
Let x and y be two random variables and they will be only independent if and only if:- 
$Fxy (t1, t2) =  Fx(t1) *  Fy(t2)$
for all t1 E Tx
for all t2 E Ty

If $x1,x2,x3,.....,xn$ are all independent then $Fx1,x2,x3,.....xn(t1,t2,t3,....,tn) = fx1(t1) * fx2(t2) * fx3(t3) , ........, * fxn(tn)$.

In a general case your joint pmf is usually equal to product of marginal and conditional:-
$Fxy(t1,t2) = Fy(t2) *  Fx|y = t2 (t1)$
while in independent case 
$Fx|y = t2 (t1) = fx(t1)$

### IID (Independent and identically distributed)
Random variables x1,x2,x3,...xn are said to be iid if and only if:- 
1)- They are all independent
2)- the marginal pmf of Fxi are identical. identical here means they follow same distribution and same parameters.

### Memory less property of geometric distribution:- 
Here we will study two important cases:- 
as we know
if X ~ Geometric (P)
P(x = k) = P * (1-p)^k-1

Case 1:- P(x>n) = (1-p)^n
Proof of this is given ur register. In simpler terms this means that whenever we wish to find out probability of getting our first success after n trials we use this formula

Case 2:- P (x > m+n | x>m )  = (1-P)^n
Here we simply wish to find out the probability of getting our first success after m + n trials with condition given that our first success comes after m trials. 

### Sum of Two independent Poisson R.V:- 
X ~ Poisson (λ1) & Y ~ Poisson(λ2)
and Z = X + Y
Z ~ Poisson (λ1 + λ2)

Proof:- 
Z = X + Y
Fz = Fxy(x,y)
Fxy(x, y) = Fx(x) * Fy(y)
Fz = Fx(x) * Fy(y)
Fz = Poisson (λ1) *  Poisson (λ2)
Fz ~ Poisson (λ1 + λ2)

Now suppose that we are given z and we wish to find out the distribution of x and y 
eg  Z = 10 which means X + Y = 10 and now we wish to find out how this 10 is split among the X and Y. 
then we use these formulas :- 
Given that the total Z is n, X follows a Binomial distribution with n trials and probability
$$ X \mid Z=n \sim \operatorname{Binomial} \left( n,\frac{\lambda_1}{\lambda_1+\lambda_2} \right) $$
$$ Y \mid Z=n \sim \operatorname{Binomial} \left( n,\frac{\lambda_2}{\lambda_1+\lambda_2} \right) $$

Where  $$ P = \left ( \frac{\lambda_1}{\lambda_1+\lambda_2} \right) $$
is probability that a success belongs to X
Why binomial? 
Because here we are asking that out of 10 successes how many of those success belongs to X. 

