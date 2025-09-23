`import numpy as np`
`df uniform(n, m):`
	`return np.random.randint(1, n+1, size m)`

`no_heads = 0` 
`for i in range(1000):`
	`#this is for head and tail, you can change it according to situation`
	`if uniform(2, 1) == 1:`
		`no_heads = no_heads + 1`
`print('Probability estimation = ', no_heads/1000 )` 
