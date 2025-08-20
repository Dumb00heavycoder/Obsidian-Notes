`import numpy`  
`r1 = [1, 2, 3]`  
`r2 = [4, 5, 6]`  
`r3 = [7, 8, 9]`  
`A= []`  
`s1 = [10, 20, 30]`  
`s2 = [40, 50, 60]`  
`s3 = [70, 80, 90]`  
`B = []`  
`A.append(r1)`  
`A.append(r2)`  
`A.append(r3)`  
`B.append(s1)`  
`B.append(s2)`  
`B.append(s3)`  
`C = [[0,0,0] ,[0,0,0] ,[0,0,0]]`  
`X= numpy.asmatrix(A)`  
`Y = numpy.asmatrix(B)`  
`print(X*Y)`