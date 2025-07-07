Lets try to understand the two variable concept via the following example

`L1 = [1,2,3]`
`L2 = L1`

In this example it might seem like we have created two list L1 and L2, Which is completely wrong. In reality we have just created another name for the L1 list. Python interpreter is smart and to conserve the space it will L2 as just another name for L1 list. If you do any changes in L1 they will be done in L2 automatically.

To create a duplicate or clown a list you can do this:- 
`L2 = list[L1]`
`L2 = L1[:]`
`L2 = L1.copy()`