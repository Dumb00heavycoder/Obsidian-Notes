1)Joint PMF:- Suppose we have two random variables with their pmfs and we wish to calculate probabilities of these two random variables taking some certain values at same time. This will give us joint pmfs of these 2 random variables. Example:- You wish to roll a die 6 times and want to see how many times three will come but you also want to record how many 2 will come. so you make 2 random variables x (for number of times we get 3) and y (for number of times we get 2). Now to calculate probability of getting 3 on 2 rolls and getting a 2 on 1 roll out of 6 rolls we will have to calculate their joint pmf. 

$fxy = P(x=T1, y = T2$), t1 E Tx, ty E Ty
properties of joint pmf:- 
- 0 <= fxy(x,y) <= 1
- Summation of all the joint probabilities should be equal to 1

![[Screenshot 2026-07-18 at 6.51.31 PM.png]]


2)Marginal PMF:- Finding pmf of one variable from joint pmf gives us the marginal pmf of that variable. To get marginal pmf we add the values accordingly. 
![[Screenshot 2026-07-18 at 6.53.26 PM.png|476]]

3)- Conditional PMF:- Calculating probability of one variable in a joint system when a condition has been applied on the other variable. For example what will be the probably of x being 0 when y is 1.
	we know in sets:- $P(A|B) = P(A$ & $B) / P(B)$
	apply same here :- $P(Y=y | X=x) = P(Y=y, X=x)/ P(X>x)$
	hence Conditional = Joint/ Marginal

4)- Joint Probability of Multiple variables:- 
Fx1,x2,x3,...,xn (t1,t2,t3,...,tn) = P(x1 = t1, x2 = t2, x3 = t3, .... , xn = tn)
ti E Txi

5)- Marginal Pmf of multiple variables:- 
Suppose $x1, x2, x3$ ~ $fx1, x2,x3$ 
then 
$Fx1,x2(t1,t2) = P(x1 = t1, x2 = t2) = ∑fx1,x2,x3 E (t1,t2,t3),T3 E tx3,$ where u fix t1 and t2. 

Now for Fx1(t1)
$Fx1(t1) = P(x1= t1) = ∑fx1,x2,x3 E (t1,t2,t3), T2 E tx2, T3 E tx3$ where u fix t1 

6)- Conditional pmf of multiple variables:-
- Applying condition on 1 variable:- 
		$Fx1,x2|x3= t3, (t1,t2) = fx1,x2,x3(t1,t2,t3)/ fx3 (t3)$
- Applying condition on 2 variables:-  
		$Fx1| x2 = t2, x3 = t3 (t1) = fx1,x2,x3(t1,t2,t3)/ fx2x3(t2,t3)$

Let N ~ Poisson (λ) 
given N = n, toss a fair coin n times and denote the number of Heads with x. then
FN(n) = (e^-λ *  λ^n)/ n!, n = 0 - Infinity$ 
now 
$X|N=n ~ Bin (n, 1/2)$
$nCk p^k (1-p)^n-k$
$X|N =n = nCk (1/2)^n$

