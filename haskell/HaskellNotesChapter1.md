# Haskell Notes - Chapter 1

- Purely functional programming language: What is pure??
- Haskell is lazy. Calculates when really required. get more on it??
- Haskell is statically typed and type inference is in place.
- Haskell is elegant and concise.

You load up those functions by typing in :l myfunctions or :r

## Operators

- `+ - * /` all usual stuff
- Use brackets with -

### Logical Ops

- == && || not the usual stuff...True False  
   5/=5 returns False --i think its not equal to!!!
- Incompatible types are not compared.

### Functions

- Functions are usually prefix eg succ 8

  ```haskell
  min 9 10
  min 3.4 3.2
  max 100 101
  ```

- Function application has the highest precedence of them all.
- If a function takes two parameters, we can also call it as an infix function by surrounding it with back ticks. eg 92 `div` 10
- bar(bar(3)) will be in Haskell as bar (bar 3)
- Functions in Haskell don't have to be in any particular order
- The difference between Haskell's if statement and if statements in imperative languages is that the else part is mandatory in Haskell.
- Another thing about the if statement in Haskell is that it is an expression.
- We usually use ' to either denote a strict version of a function (one that isn't lazy) or a slightly modified version of a function or a variable eg: conanO'Brien = "It's a-me, Conan O'Brien!" is valid function
- That's because functions can't begin with uppercase letters.
- The second thing is that this function doesn't take any parameters. When a function doesn't take any parameters, we usually say it's a definition (or a name) Because we can't change what names (and functions) mean once we've defined them

### Lists

- Lists are a homogenous data structure. It stores several elements of the same type. eg let nums=[2,3,4]
- Adding two lists is done with ++ operator, adding is done at the end
- : operator is used to add at the beginning eg 'A':" Small Cat" ...takes one element and a list an input
- [], [[]] and[[],[],[]] are all different things. The first one is an empty list, the seconds one is a list that contains one empty list, the third one is a list that contains three empty lists.
- If you want to get an element out of a list by index, use !!. The indices start at 0.
- But if you try to get the sixth element from a list that only has four elements.
- The lists within a list can be of different lengths but they can't be of different types.
- Lists can be compared if the stuff they contain can be compared.
- head takes a list and returns its head.
- tail takes a list and returns its tail. In other words, it chops off a list's head.
- last takes a list and returns its last element.
- init takes a list and returns everything except its last element.
- length takes a list and returns its length,
- null checks if a list is empty. If it is, it returns True, otherwise it returns False.
- reverse reverses a list.
- take takes number and a list. It extracts that many elements from the beginning of the list.
- drop works in a similar way, only it drops the number of elements from the beginning of a list.
- maximum takes a list of stuff that can be put in some kind of order and returns the biggest element.
- minimum returns the smallest.
- sum takes a list of numbers and returns their sum.
- product takes a list of numbers and returns their product.
- elem takes a thing and a list of things and tells us if that thing is an element of the list.

### Ranges

- To make a list containing all the natural numbers from 1 to 20, you just write [1..20]
- cycle takes a list and cycles it into an infinite list.
- repeat takes an element and produces an infinite list of just that element.

### List Comprehensions

- `[x*2 | x <- [1..10]]`
- Now let's add a condition (or a predicate) to that comprehension.  
   `[x*2 | x <- [1..10], x*2 >= 12]`
- `[ x | x <- [50..100], x` mod `7 == 3]`
- `boomBangs xs = [ if x < 10 then "BOOM!" else "BANG!" | x <- xs, odd x]`
- `[ x | x <- [10..20], x /= 13, x /= 15, x /= 19]`
- `[ x*y | x <- [2,5,10], y <- [8,10,11]]`
- `[ x*y | x <- [2,5,10], y <- [8,10,11], x*y > 50]`
- `length' xs = sum [1 | _ <- xs]`
- `removeNonUppercase st = [ c | c <- st, c`elem`['A'..'Z']]`
- `let xxs = [[1,3,5,2,3,1,2,4,5],[1,2,3,4,5,6,7,8,9],[1,2,4,2,1,6,3,1,3,2,3,6]]`
- `[ [ x | x <- xs, even x ] | xs <- xxs]`

### Tuples

- A list of numbers is a list of numbers. That's its type and it doesn't matter if it has only one number in it or an infinite amount of numbers.
- Are used when you know exactly how many values you want to combine and its type depends on how many components it has and the types of the components.
- Another key difference is that they don't have to be homogenous.
- Use tuples when you know in advance how many components some piece of data should have.
- While there are singleton lists, there's no such thing as a singleton tuple.
- Only you can't compare two tuples of different sizes, whereas you can compare two lists of different sizes.
- fst takes a pair and returns its first component.
- snd takes a pair and returns its second component. Surprise!
- zip. It takes two lists and then zips them together into one list by joining the matching elements into pairs.
- let rightTriangles = [ (a,b,c) | c <- [1..10], b <- [1..c], a <- [1..b], a^2 + b^2 == c^2]
