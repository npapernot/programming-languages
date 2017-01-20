[Back to home](https://npapernot.github.io/programming-languages)

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

## Proving that `fact` and `ffact` are equivalent

We want to prove that `fact` and `ffact` are equivalent.
In order to do so, we will use a proof by induction. We
cannot prove directly that for all `n>=0`, we have the
desired property that `fact(n)=ffact(n)` because this
would require that we factor in the accumulator. 

We are
going to instead prove the following property `(P)` by
induction: **for any given
`m>=0`, we have that for all `n>=0`, `m*fact(n)=tfact(n, m)`**.

First, let us deal with the base case where `n=0`. We have:
```sml
mfact(0) = m*1 = m
tfact(0,m) = m
```
which gives us that `mfact(0)=tfact(0,m)`

Now, let us prove the induction step. Assume property `(P)`
is true for all values smaller or equal than `n-1`.
We then have: 
```sml
m*fact(n) = m*n*fact(n-1)
          = (m*n)*fact(n-1)
          = tfact(n-1, (m*n))
          = tfact(n, m)
```
where we first used the definition of `fact`, then the induction
assumption. This concludes our proof of induction for `(P)`.

Setting `m=1` then yields the desired property that `fact(n)=ffact(n)`.

## Proving that `fact` and `cpsfact` are equivalent

We want to prove that `fact` and `cpsfact` are equivalent.
In order to do so, we will use a proof by induction. We
cannot prove directly that for all `n>=0`, we have the
desired property that `fact(n)=cpsfact(n)` because this
would require that we factor the multiplying factor in `fact` into
the function `K` found in `kfact`. 

We are
going to instead prove the following property `(P)` by
induction: **for any given
`m>=0`, we have that for all `n>=0`, `m*fact(n)=kfact(n, fn v => v*m)`**.

First, let us deal with the base case where `n=0`. We have:
```sml
mfact(0) = m*1 = m
kfact(0, fn v => v*m) = fn v => v*m 1 = 1*m = m
```
which gives us that `mfact(0)=kfact(0,fn v => v*m)`

Now, let us prove the induction step. Assume property `(P)`
is true for all values smaller or equal than `n-1`.
We then have: 
```sml
m*fact(n) = m*n*fact(n-1)
          = (m*n)*fact(n-1)
          = kfact(n-1, fn v => v*(m*n))
          = kfact(n, fn v => v*m)
```
where we first used the definition of `fact`, then the induction
assumption. This concludes our proof of induction for `(P)`.

Setting `m=1` then yields the desired property that `fact(n)=cpsfact(n)`.
