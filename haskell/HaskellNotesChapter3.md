# Haskell Notes - Chapter 3

## Pattern Matching

- When defining functions, you can define separate functions for different patterns
- Pattern match on any data
- Order is important when specifying patterns and it's always best to specify the most specific ones first and then the more general ones later.
- Pattern matching can also fail if ambiguously defined or non exhaustive. It will fail while calling
- When making patterns, we should always include a catch-all pattern so that our program doesn't crash if we get some unexpected input.
- you can also pattern match in list comprehensions
- There's also a thing called as patterns.
- you can't use `++` in pattern matches.

## Guards

- guards are a way of testing whether some property of a value (or several of them) are true or false.
- Guards are indicated by pipes that follow a function's name and its parameters.
- If it evaluates to True, then the corresponding function body is used. If it evaluates to False, checking drops through to the next guard and so on.
- Many times, the last guard is otherwise. otherwise is defined simply as otherwise = True and catches everything.

## Where I

- We put the keyword where after the guards (usually it's best to indent it as much as the pipes are indented) and then we define several names or functions.
- where bindings aren't shared across function bodies of different patterns.


## Let it be

- Let bindings let you bind to variables anywhere and are expressions themselves, but are very local, so they don't span across guards.
- The names that you define in the let part are accessible to the expression after the in part
- The difference is that let bindings are expressions themselves. where bindings are just syntactic constructs.
- The names defined in a let inside a list comprehension are visible to the output function (the part before the |) and all predicates and sections that come after of the binding.

## Case Expression

- case expressions are, well, expressions, much like if else expressions and let bindings.
- Not only can we evaluate expressions based on the possible cases of the value of a variable, we can also do pattern matching.
