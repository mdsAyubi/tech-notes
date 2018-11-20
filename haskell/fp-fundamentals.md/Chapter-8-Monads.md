# Functional Parsers

> Richard Burks : Functional Pro

## What is a Parser

Program that analyses a piece of text to determine its syntactic structure. Almost all programs use some form of parsing.

## The Parser Type

Parsers can be viewed as functions. E.g `type Parser = String -> Tree`

However, a parser might not require all of its input string, so we also return any unused input: `type Parser = String -> (Tre, String)`. To generalize this result, since the string can be arsed in many ways.

`type Parser = String -> [(Tree, String)]`

If the string can't be parsed, we return a Maybe which is defined as follows

```haskell
data Maybe a = Nothing
    | Just a
```

## Basic Parser

The parser item fails if the input is empty, and consumes he first character otherwise:

```haskell
item :: Parser Char
item  = \inp -> case inp of
            [] -> []
            (x:xs) -> [(x, xs)]

-- A parser that always fails

failure :: Parser a
failure = \inp -> []

-- A parser which always succeeds

return :: a -> Parser a
return v = \inp -> [(v, inp)]
```

## Sequencing

Sequence of parsers can be combined as a single composite parser using the keyword `do`.

```haskell
p :: Parser (Char, Char)
p = do x <- item
    item
    y <- item
    return (x, y)
```

- Each parser must begin in the same column -- the layout rule applies
- Values returned by intermediate parsers are discarded by default, but if required can be named
- The value returned by the last parser is the value returned by the whole parser.
- The `do` notation can be used with any monadic type
- If any sequence fails, the whole parser fails

---
