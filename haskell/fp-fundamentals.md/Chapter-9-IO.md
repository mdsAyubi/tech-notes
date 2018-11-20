# IO Monads

Haskell functions are pure. In order to enable programs t interact with their environment, the `IO` monad comes into play. It wraps the object and returns the type. For example, an IO monad of type `a` will return `a` after some computation or interaction with its environment.

## Basic Actions

- `getChar :: IO Char` : Reads a character from the keyboard, prints on the screen and returns the character read from the screen.
- `putChar :: Char -> IO ()` : Writes a character to the screen and returns nothing.
- `return :: a -> IO a` : Simply returns the value v without performing any interactions

## Derived Primitives

```haskell
getLine :: IO String
getLine = do x <- getChar
            if x == '\n' then
                return []
            else
                do xs <- getLine
                    return (x: xs)

puStr :: String -> IO ()
putStr [] = return ()
putStr (x:xs) = do putChar x
                    putStr xs

putStrLn :: String -> IO ()
putStrLn xs = do putStr xs
                putChar '\n'
```

---
