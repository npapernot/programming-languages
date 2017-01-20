## Proofs of equivalence (by induction) for standard ML functions

Assume you are given the following function definitions
in [standard ML](https://en.wikipedia.org/wiki/Standard_ML).
The three functions all compute the factorial of an integer
n but are defined differently. 

The first function, `fact`,
is the naive tail-recursive definition of the factorial.
```sml
fun fact 0 = 1
  | fact n = n*fact(n-1);
```


The second function, `ffact`, uses an accumulator. 
```sml
fun tfact(0,k) = k
  | tfact(n,k) = tfact(n-1,n*k);
 fun ffact n = tfact(n,1);
```

And
finally, the third one, `cpsfact` is a [curried](https://en.wikipedia.org/wiki/Currying)
version of the factorial.
```sml
fun kfact(0,K) = K 1
  | kfact(n,K) = kfact(n-1, fn v=>K(v*n));
fun cpsfact n = kfact(n, fn v=> v);
```
