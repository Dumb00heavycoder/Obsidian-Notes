1)- Reshape method:- You can use reshape method to reshape an array and form another matrix with those elements 
eg:- `before = np.array([[1,2,3,4],[5,6,7,8]])`
`after = before.reshape((2,2,2))`

2)- Vertically stacking vectors and forming matrix:-
eg:- `v1 = [1,2,3,4]`
`v2 = [5,6,7,8]`
`np.vstack([v1,v2,v1,v2])`
You can not side mismatch

3)- horizontal stack:- 
eg:- `h1 = np.zeros(2,4)`
`h2 = np.ones(2,4)`
`np.hstack([h1,h2])`
