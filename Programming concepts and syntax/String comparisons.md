Python compares strings lexicographically, which is similar to how words are ordered in a dictionary.

`print('apple' < 'banana')  # True → 'a' < 'b'`
`print('cat' < 'catalog')   # True → 'cat' is a prefix of 'catalog'`
`print('dog' < 'do')        # False → 'g' > (no character, so 'do' is shorter)`
`print('hello' < 'Hello')   # False → lowercase > uppercase in Unicode`
