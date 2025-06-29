An **iterable** object is an object that implements __ iter __ , which is expected to return an **iterator** object.

An **iterator** object implements __ next__ , which is expected to return the next element of the iterable object that returned it, and to raise a StopIteration exception when no more elements are available

functioning
- It returns itself
- It implements next
- Then the next one returns itself and does the same
- this is done till no more elements are available