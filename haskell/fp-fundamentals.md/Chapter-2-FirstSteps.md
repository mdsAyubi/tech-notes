# Chapter 2 - First Steps

## The Hugs System

* Hugs
* `ghci`
* <haskell.org>

All of the above with the REPL.

## The Standard Prelude

Comes with the standard functions. Some of the functions

* `tail [1,2,3]`
* Select nth element with `!!`
* First n elements with `take 3 [1,2,3,4,5]`
* `drop 3 [1,2,3,4]`
* `length [1,2,3,4]`
* `sum [1,2,3,4,5]`
* `product [1,2,3]`
* `[1,2,3] ++ [1,5]`
* `reverse [1,2,3]`

C# receiver.method(a,b,c)
Haskell `method receiver a b c` - Can pattern match into dynamic type of all the parameters

## Function Application

For example, f(a,b) + c d --> In Haskell, this can be represented as `f a b + c * d`. Some more comparison

|Mathematics | Haskell|
|:---------:|:--------:|
|f(x) | `f x`|
|f(g(x)) | `f (g x)`|
|f(x)g(y) | `f x * g y`|

## Haskell Scripts

* Define own functions
* Defined within a script
* Usually with a .hs extension

For example

```haskell
double x = x + x
quad = double . double
```

The above follows from the fact that (f.g)x = f(g(x)). The type of this function will be `quad :: Num a => a -> a`. Some more examples,

```haskell
factorial = product [1..n]

xs = take n [1..]
average = sum x `div` length x
```

## Naming Requirements

* Function and arguments names must begin with lower case letters
* By convention, list arguments have an __s__ suffix on their name
* Type names always start with upper case

## The Layout Rule

* Each definition must begin the same column
* Can use semicolon and `{`

## Useful commands

* :load name -- loads the script
* :reload -- reload the current script
* :edit name -- edit the script
* :edit -- edit current script
* :type expr -- show type of expr
* :? -- show all commands
* :quit -- quit the repl
