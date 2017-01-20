[Back to home](https://npapernot.github.io/programming-languages)

## Recursion

**Question: can recursion always be converted into iteration?**
In theory, any recursive function can be made iterative. In practice, 
it is easiest to convert tail-recursive functions into iterative
blocks of code. The result can then be returned immediately without
first making all recursive calls and then traversing the stack to retrieve
the result. 
