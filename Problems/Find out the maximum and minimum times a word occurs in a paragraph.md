`l = ['You', 'can', 'never', 'know', 'a', 'single', 'person', 'fully', 'not', 'even', 'yourself', 'Even', 'if', 'you', 'think', 'you', 'know', 'yourself', 'in', 'your', 'safe', 'glass', 'castle', 'you', 'don’t', 'know', 'yourself', 'in', 'the dirt', 'Even', 'if', 'you', 'hustle', 'and', 'make', 'it', 'in', 'the', 'rough', 'you', 'have', 'no', 'idea', 'if', 'you', 'would', 'thrive', 'or', 'die', 'in', 'the', 'light', 'of', 'real', 'riches', 'if', 'your', 'cleverness', 'would', 'outlive', 'your', 'desperation']`  
`s = set(l)`  
`d = {}`  
`for x in s:`  
    `d[x]=0`  
`maximum = 0`  
`for x in l:`  
    `d[x]= d[x]+1`  
    `if d[x]>maximum:`  
        `maximum = d[x]`  
        `maximum_keyy = x`  
`print ("The most repeated word in the above paragraph is ", maximum_keyy, ". It is repeated ", maximum, " times")`