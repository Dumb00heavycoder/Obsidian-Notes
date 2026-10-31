previous knowledge:- [[Obsidian-Notes/DATA SCIENCE/Machine Learning/Machine Learning Foundation/Week 1|Week 1]]

## Calculus:-
Before starting calculus we will refer to few notations and revise our basics:-
Theses are few building blocks of calculus which you must know very well:- 
![[Screenshot 2026-10-31 at 3.02.35 PM.png|607]]
![[Screenshot 2026-10-31 at 3.05.13 PM.png|615]]
In metric space we first concern ourself with calculating distance between two points by the distance formula. 
We know that for D(x,y):-
$D(x, y) = \|x - y\|$ = $D(x, y) = \sqrt{(x_1 - y_1)^2 + \dots + (x_d - y_d)^2}$
Here
x-y gives us a vector
$\| x - y \|$ is length of x-y vector
and D(x,y) is length between two points x and y.

Why does the formula work in any number of dimensions?[
For two dimensions, we have:

$D(x, y) = \sqrt{(x_1 - y_1)^2 + (x_2 - y_2)^2}$
For three dimensions:
$D(x, y) = \sqrt{(x_1 - y_1)^2 + (x_2 - y_2)^2 + (x_3 - y_3)^2}$
For $d$ dimensions:
$D(x, y) = \sqrt{\sum_{i=1}^{d} (x_i - y_i)^2}$
Hence:-
A **metric space** is a set of points together with a rule for measuring distances between them.

Now lets look at open and closed ball in metric space:-
Open ball:- $B(x,\epsilon) = \{y \in \mathbb{R}^d : D(x,y) < \epsilon\}$
In open ball distance between centre x and any point y inside ball will be less than Epsilon.

Closed ball:- $\bar{B}(x,\epsilon) = \{y \in \mathbb{R}^d : D(x,y) \le \epsilon\}$
In closed ball distance between centre x and any point y inside ball will be less than or equal to epsilon.
* $B$ means ball.
* $x$ is the center.
* $\epsilon$ (epsilon) is the radius.
* $D(x,y) < \epsilon$ means that the distance between the center $x$ and another point $y$ is less than the radius.
![[Screenshot 2026-10-31 at 3.06.34 PM.png|617]]
![[Screenshot 2026-10-31 at 3.37.59 PM.png|615]]
What is a sequence:- Take example of 1/n, When n = 1 we get 1, when n = 2 we get 0.5, when n = 3 we get 0.33 and if we continue this sequence we get closer and closer to zero. Now imagine same thing being done in a 2 dimensional plane. 
let sequence be:- (2,3), (1,2), (0.5, 1),.....
We see that these points in 2 dimensional space are approaching 0. So any such set of numbers approaching any point in space can be called a sequence.
This sequence can exist in any dimension. It can e $\mathbb{R}^3$ or $\mathbb{R}^d$ etc.
The sequence might not always approach something. It can also just repeat or follow a pattern as we see in the example at the bottom right of our slide where the pattern repeats and never approaches something. This is also a sequence. even though different from our first example. 

What does convergence mean?:-
$\lim_{n\to\infty} x_n = x^*$
Read this as:
"As $n$ approaches infinity, the sequence $x_n$ converges to $x^*$."
This simply means that as we move forward in this sequence we keep moving towards $x^*$ or converging towards $x^*$. The term may never be $x^*$ but it keeps converging or approaching it constantly after every point. 

Now lets look at the very formal definition of convergence which is present in the above slide:- 
This is the mathematical definition of convergence:- 
$$\forall \epsilon > 0, \quad \exists N \quad \text{s.t.}$$
$$x_n \in B(x^*, \epsilon) \quad \forall n \ge N$$
Lets look at this one by one:- 
The first term 
1)- $\forall \epsilon > 0,$ = Means that for every positive epsilon
2)- $\exists N$ = There exist a N.
This N is a index in our sequence after which ever index of our sequence is lesser than epsilon and closer to the $x^*$
Epsilon can taken as small as possible for better precision and the smaller the epsilon gets the N index will get bigger. Hence for greater accuracy we must go far down the sequence. 
3)-$x_n \in B(x^*, \epsilon)$  = Xn lies in an open ball with c = $x^*$ and radius $\epsilon$.
4)- $\forall n \ge N$ = This means every n term after N should be close to $x^*$ and greater than N.
hence:-
$\forall \epsilon > 0, \quad \exists N \quad \text{such that} \quad x_n \in B(x^*, \epsilon) \quad \forall n \ge N$  
is equal to
$\forall \epsilon > 0, \quad \exists N : D(x_n, x^*) < \epsilon \quad \forall n \ge N$

In plain english convergence is:- "No matter how close to the limit you demand the terms to be, I can find a point in the sequence after which every term remains that close."

![[Pasted image 20261031162422.png]]
Find where do these points converge to if they do. 
Lets continue our revision:- 
![[Screenshot 2026-10-31 at 4.41.53 PM.png]]
![[Screenshot 2026-10-31 at 4.42.13 PM.png]]
Graph of F(x) will be plotted in a dimenion d+1
as we get +1 from the output.
In a 1d input we get 2d output and in 2d input a 3d output.
![[Screenshot 2026-10-31 at 4.55.15 PM.png|615]]

![[Screenshot 2026-10-31 at 4.55.37 PM.png|631]]
These lines are called contours. here we are simply representing f(x) with lines on our 2d graph. 
![[Screenshot 2026-10-31 at 4.55.51 PM.png|614]]

## Continuity Of Functions:- 
$f: \mathbb{R} \to \mathbb{R}$
is continuous at $x^* \in \mathbb{R}$ if for all sequences $x_1, x_2, \dots$ converging to $x^*$ we have that $f(x_i)$ converges to $f(x^*)$
hence:-
$\lim_{i \to \infty} x_i = x^* \implies \lim_{i \to \infty} f(x_i) = f(x^*)$
which can be written down to:-
$\lim_{x \to x^*} f(x) = f(x^*)$

E.g. 1: $f(x) = x^2, \quad x^* = 2$
* $x_i$: $3, 2.5, 2.25, \dots \to 2$
* $f(x_i)$: $9, 6.25, 5.0625, \dots \to 4$
Hence it is a continuous function.

At its core continuity of a function means that a tiny change in the input produces only a tiny change in the output 
eg:- 
F(x) = 2x
if you give it different outputs
input:- 1, 1.1, 1.01, 1.001
output:- 2, 2.2, 2.02, 2.002
as input gets closer to 1 the output gets closer to 2.
So naturally discontinuity would mean that a small change in input causes a large change in output. for example when u input 2 in function u get 5 but when u input 2.1 u get 100.
The idea here is that a function is continuous if there is no sudden breaks in the relationship between input and output
In sense of sequence if 
$\lim_{i \to \infty} x_i = x^*$ 
then 
$\lim_{i \to \infty} f(x_i) = f(x^*)$

Examples:-
![[Screenshot 2026-10-31 at 5.38.03 PM.png|583]]
![[Screenshot 2026-10-31 at 5.38.19 PM.png|589]]

