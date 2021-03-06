# Haskell Notes - Chapter 2

- The type of every expression is known at compile time, which leads to safer code
- Type inference
- A type is a kind of label that every expression has. It tells us in which category of things that expression fits.
- We'll do that by using the :t command which, followed by any valid expression, tells us its type.
- Unlike lists, each tuple length has its own type

## Functions

- Functions also have types. When writing our own functions, we can choose to give them an explicit type declaration.

```haskell
removeNonUppercase :: [Char] -> [Char]
removeNonUppercase st = [ c | c <- st, c `elem` ['A'..'Z']]
```

- The [Char] type is synonymous with String, therefore we can write like this
  `removeUpperCase::String -> String`

- Multiple parameters can be passed like this  
   `addThree :: Int -> Int ->Int ->Int`
- the last argument is the return type

- If you want to give your function a type declaration but are unsure as to what it should be, you can always just write the function without it and then check it with :t.

### Common Types

- Int:32 bit integer
- Integer -unbounded  
   `factorial::Int -> Int factorial n = product[1..n]`
- Float: is a real floating point with single precision.
- Double: is a real floating point with double the precision!
- Bool is a boolean type. It can have only two values: True and False.
- Char: represents a character. It's denoted by single quotes. A list of characters is a string.

### Type Variables

- `head :: [a] -> a` where a is the type variable
- Functions that have type variables are called polymorphic functions.
- `fst :: (a, b) -> a`

### Type Classes

- A typeclass is a sort of interface that defines some behavior.
- If a type is a part of a typeclass, that means that it supports and implements the behavior the typeclass describes.
- :t (==)  
   `(==) :: (Eq a) => a -> a -> Bool`
- Everything before the => symbol is called a class constraint.
- The Eq typeclass provides an interface for testing for equality
- All standard Haskell types except for IO (the type for dealing with input and output) and functions are a part of the Eq typeclass.

Basic type classes

- Eq: For equality
- Ord: is for types that have an ordering.
- Show: Members of Show can be presented as strings.
- Read: Read is sort of the opposite typeclass of Show. The read function takes a string and returns a type which is a member of Read.
- read "5" :: Int , read "5" :: Float ,read "(3, 'a')" :: (Int, Char)
- Enum: Enum members are sequentially ordered types — they can be enumerated. The main advantage of the Enum typeclass is that we can use its types in list ranges.
- Bounded members have an upper and a lower bound.
- Num is a numeric typeclass. Its members have the property of being able to act like numbers.
- Integral is also a numeric typeclass. Num includes all numbers, including real numbers and integral numbers, Integral includes only integral (whole) numbers. In this typeclass are Int and Integer.
- Floating includes only floating point numbers, so Float and Double
