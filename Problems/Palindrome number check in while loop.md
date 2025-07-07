`num = int(input("Enter a number: "))`
`absnum = abs(num)`
`rev = absnum % 10` 
`absnum = absnum // 10`
`while (absnum > 0):`
    `r = absnum % 10`
    `absnum = absnum // 10`
    `rev = rev * 10 + r`
    
`rev = rev if num > 0 else -rev`
`if num == rev:`
    `print("palindrom")`
`else:`
    `print("Not palindrom")`