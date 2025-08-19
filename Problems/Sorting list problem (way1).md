`def sorting_list (l):`  
    `x = []`  
    `while(len(l) > 0):`  
        `mini = l[0]`  
        `for i in range (len(l)):`  
            `if l[i]< mini:`  
                `mini = l[i]`  
        `x.append(mini)`  
        `l.remove(mini)`  
    `return x`  
  
`l = [23, 87, 99, 100, 23, 6]`  
`print(sorting_list(l))`