# Recursion

> Read Why Functional Programming Matters

The order of evaluation does not matter.

```haskell
product :: [Int] -> Int
product [x] = x
product (x: xs) = x * product xs
```

## Recursive Functions

Functions which are defined in terms of themselves.

```haskell
factorial 0 = 1
factorial (n + 1) = (n + 1) * factorial n
```

Notice we are using n + k pattern matching here.

## Why is recursion useful

* SOme functions becomes simpler to define
* Natural
* Properties can be proved using mathematical techniques.

```haskell
length :: [a] -> Int
length [] = 0
length (_ : xs) = 1 + length xs

reverse :: [a] -> [a]
reverse [] = []
reverse (x: xs) = reverse xs ++ [x]
```

## Multiple Arguments

Functions with more than one argument can also be defined using recursion.

```haskell
zip :: [a] -> [b] -> [(a, b)]
zip [] _ = []
zip _ [] = []
zip (x: xs) (y:ys) = (x, y) : zip xs ys

(++) :: [a] -> [a] -> [a]
[] ++ ys = ys
(x:xs) ++ ys = x : (xs ++ ys)

drop :: Int -> [a] -> [a]
drop 0 xs = xs
drop (n+1) [] = []
drop (n+1) (_:xs) = drop n xs
```

## Finally, Quicksort

```haskell
qsort :: [Int] -> [Int]
qsort [] = []
qsort (x:xs) = qsort smaller ++ [x] ++ qsort larger
    where
        smaller = [a | a <- xs, a<=x ]
        larger = [a | b <- xs, b > x]
```

Probably the simplest implementation of quicksort in any programming language.

---