# List Comprehensions

## Set Comprehensions

In mathematics, comprehension notation can be used to construct new sets., {x <sup>2</sup> | x in {1...5}}.

## Lists Comprehension

Similar comprehension notation can be used to construct new lists from old lists. `[x^2| x <- [1..5]]`.

`x <- [1..5]` is called the generator. Comprehensions can have multiple generators. Changing the order of generators changes the result.

## Dependent Generators

Later generators can depend on the variables that are introduced by the earlier generators. For example,

```haskell
[(x, y)| x <- [1..3], y <- [x..3]]

concat :: [[a]] -> [a]
concat xss = [x | xs <- xss, x <- xs]
```

## Guards

List comprehension can use guards to restrict the values produced by earlier generators. e.g. `[x | x <- [1..10], even x]`

```haskell
factors :: Int -> [Int]
factors n = [x | x <- [1..n], n `mod` x == 0]

prime :: Int -> Bool
prime n = factors n == [1, n]

primes :: Int -> [Int]
primes n = [x | x <- [2..n], prime x]
```

## The Zip Function

It maps two lists to a list of pairs pf their corresponding elements.

```haskell
zip :: [a] -> [b] -> [(a, b)]

pairs :: [a] -> [(a,a)]
pairs xs = zip xs (tail xs)

sorted :: Ord a => [a] -> Bool
sorted xs =  and [x <= y | (x, y) <- pairs xs ]

positions :: Eq a => a -> [a] -> [Int]
positions x xs = [i | (x', i) <- zip xs [0..n], x == x' ]
                    where n = length xs -1

where xs p = filter (zip xs [0..]) p
```

## String Comprehension

Any polymorphic operations defined on lists can be applied on strings.

---
