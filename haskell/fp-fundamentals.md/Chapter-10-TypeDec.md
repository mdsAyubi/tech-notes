# Type Declaration

New type name for an existing type. E.g `type String = [Char]`
Can't be recursive.

## Data Declaration

New type can be defined by specifying its values using a **data declaration**. E.g `data Bool = False | True`

* The values True and False are called the constructors of the ype Bool
* Type and constructor names must begin with an upper case letter.
* Data declarations are similar to CFG.

```haskell
data Maybe a = Nothing | Just a

safe_div :: Int -> Int -> Maybe Int
safe_div _ 0 = Nothing
safe_div m n = Just(m `div` n)
```

## Recursive Types

New types can be declared in terms of themselves. That is, types can be recursive. E.g `data Nat = Zero | Succ Nat`

## Arithmetic Expressions

Simple expressions built up from integers using addition and multiplication.

---