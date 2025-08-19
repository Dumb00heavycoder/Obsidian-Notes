`def minimum (l):`  
    `mini = l[0]`  
    `for i in range(len(l)):`  
        `if l[i] < mini:`  
            `mini = l[i]`  
    `return mini`  
`def sort(l):`  
    `x = []`  
    `while (len(l) > 0):`  
        `mini = minimum(l)`  
        `x.append(mini)`  
        `l.remove(mini)`  
    `return x`  
  
`l = [1831, 831, 93, 93, 22, 1]`  
`print ( sort(l))`