Slicing means extracting a substring from a string using a specific range of indices.

`string[start:stop:step]`
- `start`: index to start from (inclusive)
    
- `stop`: index to stop at (exclusive)
    
- `step`: how many characters to skip (default is 1)

eg:-
`word = "data science"`    
`print(word[0:4]) # slices data`  
`print(word[5:]) #slices science`  
`print(word[::-1]) #reverses the string`  
`print(word[1::2]) #slices a string where 2 steps are taken and then the letter is taken in substring which allows us to take a step`
 