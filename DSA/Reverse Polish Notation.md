Reverse Polish Notation or post fix notation is a mathematical notation in which operators follow their operands unlike Polish notation where operators precede their operands. This was first used in a German computer known as Z3 in 1941 created by Konard Zuse. 
eg:- 
1)- 2 + 5
ans = 2 5 +
2)- 3 + 5 + 5
3 5 5 +
3)- 2 - 3 + 7
2 3 - 7 + 
*Explanation*
We will use the example of [[Stack]] to understand it better. The evaluation in RPN is done from left to right. For example we take the expression 3 + 4 - 5 which in RPN will be written as 3 4 + 5 -. We can imagine this expression in a stack where we first push 3 then we push 4, so now 3 is below 4 and then we use the add operator which will pop 3 and 4 and put 7 on the stack now. Then we can push 5 and then use subtraction operator  to pop 7 and 5 and the result will be 2. 
Another example:-
(3+4)x(5+6)
3 4 + 5 6 + x

*Practical Implication*
You can imagine functioning of RPN as a slide rule (an analogue computer used for calculations ). Rpn computers were always faster because there is no use of parenthesises. which requires few key strokes for calculations. 
[Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra "Edsger W. Dijkstra") invented the [[Shunting Yard Algorithm]]to convert infix expressions to postfix expressions (reverse Polish notation), so named because its operation resembles that of a railroad shunting yard

Famous software calculators based on rpn:-
Atari calculator 
Mac OS X Calculator 
Unix system Calculator 


