# HOF

> Read How To Mock a Mockingbird

A function is HOF if it takes a function as an argument or returns a function as a result.

* Common idioms can be encoded in the language itself
* DSLs can be defined as the collection of HOFs
* Algebraic properties f the HOFs can be used to reason about the programs

## The Map Function

Map applies a function to every element of the a list. `map:: (a -> b) -> [a] -> [b]`

The map function can be defined in two ways

```haskell
map f xs = [f x | x <- xs]

-- OR
map f [] = []
map f (x:xs) = f x : map f xs
```

## Filter Function

Selects every element from a list that satisfies a predicate. `filter :: (a -> Bool) -> [a] -> [a]`

```haskell
filter p xs = [x | x <- xs , p x]

-- OR

filter p [] = []
filter p (x:xs)
    | p x = x : filter p xs
    | otherwise = filter p xs
```

## Foldr Function

A number of functions on lists can be defined as the following

```haskell
f [] = v
f (x:xs) = x fn f xs
```

The `foldr` function encapsulates this simple pattern of recursion with the function `fn` and value `v` as arguments.

```haskell
sum = foldr (+) 0
product = foldr (*) 1
or = foldr (||) False
and = foldr (&&) True
```

Definition of `foldr`

```haskell
foldr :: (a -> b -> b) -> b -> [b] -> b
foldr f v [] = v
foldr f v (x:xs) = f x (foldr f v xs)
```

* Recursive functions on lists are simpler to define using `foldr`
* Properties of functions can be proved using the algebraic properties of `foldr`
* Programs optimizations can be simpler if foldr is used in place of explicit recursion

## Other Library Functions

The library function `(.)` returns he composition of two functions as a single function.

```haskell
(.) :: (b -> c) -> (a -> b) -> (a -> c)
f . g = \x -> f (g x)

all :: (a -> Bool) -> [a] -> Bool
all ps xs = and [p x | x <- xs]
```

---