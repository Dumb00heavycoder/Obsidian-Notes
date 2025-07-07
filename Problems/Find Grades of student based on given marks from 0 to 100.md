`def grades(x):`  
    `if x < 50:`  
        `return ('F')`  
    `if x >50 and x < 60:`  
        `return ('E')`  
    `if x > 60 and x < 70:`  
        `return ('D')`  
    `if x > 70 and x < 80:`  
        `return ('C')`  
    `if x > 80 and x < 90:`  
        `return ('B')`  
    `if x > 90 and x < 95:`  
        `return ('A')`  
    `if x > 95:`  
        `return ('S')`  
  
`x = int(input("Please enter the marks of the student: "))`  
`print (grades(x))`