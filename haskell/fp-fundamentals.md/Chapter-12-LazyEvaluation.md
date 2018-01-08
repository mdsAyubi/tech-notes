# Lazy Evaluation

Church-Rosser : If `a` can reduce to both `b` and `c` , there must be a term `d` to which both `b` and `c` can be reduced.

## Termination

Call by name terminates more often than call by value.
Call by name may require more steps to calculate the result than call by value.

Can we get the best of both worlds?

That is Lazy Evaluation : Call by name + sharing, usually by let bindings in Haskell.

## Infinite Structures

`ones = 1: ones`

Lazy evaluation evaluates arguments as and when strictly necessary.

## Strict Application

```haskell
--Forces evaluation of x
(f $! x)y

--Forces evaluation of y
(f x) $! y

--Forces evaluation of both
(f $! x) $! y
```
