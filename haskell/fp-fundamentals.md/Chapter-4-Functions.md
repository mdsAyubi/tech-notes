# Defining Functions

## Conditional Expressions

Functions can be defined with conditional expressions.

```haskell
abs :: Int -> Int
abs n = if n > 0 then n else -n
```

Conditional expression can of course be nested. In Haskell, conditional expressions must always have an else branch.

## Guarded Equations

Alternative to conditionals, functions can be expressed using guarded equations.

```haskell
abs n   | n >= 0 = n
        | otherwise = -n
```

These make the code easier to read. `otherwise` is defined in prelude as `otherwise = True`.

## Pattern Matching

We can do pattern matching on the arguments. For example,

```haskell
not :: Bool -> Bool
not False = True
not True = False
```

Analogous to dynamic dispatch in OO languages. Any function written with parenthesis can be used as infix operator,, like `(&&)`. `_` can be used for don't care parameters.

```haskell
(&&) :: Bool -> Bool -> Bool
True && True = True
_ && _ = False
```

OR

```haskell
True && b = b
False && _ = False
```

Patterns are matched in order, left to right. For example, the following expression always returns False.

```haskell
_ && _ = False
True && True = True
```

Patterns may not repeat variables. Following is an error,

```haskell
b && b = b
_ && _ = False
```

## List Patterns

Internally, every non empty list is constructed by repeated use of an operator `:` called the 'cons', that adds an element to the beginning of the list.

```haskell
[1,2,3,4] :: [Int]
1:(2:(3:(4:[])))

head :: [a] -> a
head (a : _) = a

tail :: [a] -> [a]
tail (_ : as) = as
```

Read: Theorems For Free! by Phil Wadler

## Integer Patterns

Functions on integers can be defined using n+k patterns, where n is an integer variable and k>0 is an integer constant.

```haskell
pred :: Int -> Int
pred (n + 1) = n
```

* n + k patterns only match integers >= k
* n + k patterns must be parenthesised, because function application has priority over +.

## Lambda Expression

Functions can be constructed without naming them using the lambda expressions.

```haskell
\x -> x + x
```

## Sections

An operator written between its two arguments can be converted into a curried function written before its two arguments by using parentheses. For example,

```haskell
1+2
(+) 1 2
```

---
