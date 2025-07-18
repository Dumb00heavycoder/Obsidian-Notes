An object is **hashable** if:
1. It has a hash value that never changes during its lifetime (via `__hash__()`).
2. It can be compared to other objects (via `__eq__()`).
3. It can be used as a key in a dictionary or as an element in a set.

Its like a permanent id of a variable. Int, str, float and doubles are hashable. sets, list and dict are all not hashable but mutable. Tuples can be hashable only if elements inside it are hashable 
