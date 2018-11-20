# Types and Classes

## What is a type

Collection of related values.

## Type Errors

Applying wrong functions to correct parameters.

## Types in Haskell

Every well formed expression has a type. Denoted by `e::t`. Type is inferred. Type errors are found ar compile time. The `:type` commmand calculates the type of an expression.

## Basic Types

- Bool
- Char
- String
- Int
- Integer
- Float

## List types

Sequence of values of the same type. `[False, True] :: [Bool]`

## Tuple Types

Sequence of values of different types. `(1, True, 'C') :: (Int, Bool, Char)`

## Function Types

Function is mapping from values of one type to values of another type. `not :: Bool -> Bool`. In general `:: t1 -> t2`. In a more OOP setting,

- Function< T > ~ () -> T
- Function<S,T> ~ S -> T
- Action< T > ~ T -> ()

```haskell
add::(Int, Int) -> Int
add (x,y) = x + y
add = \(x,y) -> x + y
add:: Int -> (Int -> Int)
add x y = x + y
```

Functions that take arguments one at a time are called curried functions. `multiply x y z = x * y * z`

## Why is Currying Useful

These are more flexible. Useful functions can often be made from partially applying a currried function.

## Currying Conventions

- The arrow associates to the right. `Int -> Int -> Int -> Int` means `Int -> (Int -> (Int -> Int))`
- Application of the function associates to the left

## Polymorphic Functions

A function is called polymorphic if its type contains one or more type variables. `length :: [a] -> Int`. Generic types are lower case. Types always start from capital letter. `zip :: [a] -> [b] -> [(a,b)]`. Or a constraint like `sum :: Num a => [a] -> a`

Some of the type classes

- Num
- Eq
- Ord
