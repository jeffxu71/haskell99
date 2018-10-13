# haskell99

Solutions to problems listed in https://wiki.haskell.org/H-99:_Ninety-Nine_Haskell_Problems

## Q1-28 Lists

#### Q1 Find the last element of a list.

```haskell
myLast :: [a] -> a
myLast [] = error "The list can't be empty"
myLast [a] = a
myLast (a : as) = myLast as
```

#### Q2: Find the last but one element of a list.

```haskell
lastButOne :: [a] -> a
lastButOne [] = error "The list must have at least 2 elements"
lastButOne [a] = lastButOne []
lastButOne [a, _] = a
lastButOne (a : as) = lastButOne as
```

#### Q3: Find the K'th element of a list. The first element in the list is number 1.

```haskell
kthElement :: [a] -> Int -> a
kthElement [] n = error "list too short"
kthElement (a : as) 1 = a
kthElement (a : as) n | length as < (n-1) = error "list too short"
                      | otherwise = kthElement as (n-1)
```

#### Q4: Find the number of elements of a list.

```haskell
myLength :: [a] -> Int
myLength [] = 0
myLength (a: as) = 1 + myLength as
```

#### Q5: Reverse a list.

```haskell
myReverse :: [a] -> [a]
myReverse [] = []
myReverse [a, b] = [b, a]
myReverse (a : as) = myReverse(as) ++ [a]
```

#### Q6: Find out whether a list is a palindrome. A palindrome can be read forward or backward; e.g. (x a m a x).

```haskell
isPalindrome :: (Eq a) => [a] -> Bool
isPalindrome [] = True
isPalindrome [_] = True
isPalindrome (a : as) | a == (last as) = isPalindrome (init as)
                      | otherwise = False
```

#### Q7: Flatten a nested list structure.Transform a list, possibly holding lists as elements into a 'flat' list by replacing each list with its elements (recursively).

#### Q8: Eliminate consecutive duplicates of list elements.

```haskell
compress :: (Eq a) => [a] -> [a]
compress [a,b] = if (a == b) then [b] else [a,b]
compress (a : as) = if (a == head as) then compress as else a : compress as
```

#### Q9: Pack consecutive duplicates of list elements into sublists. If a list contains repeated elements they should be placed in separate sublists.

```haskell
```

#### Q10: Run-length encoding of a list. Use the result of problem P09 to implement the so-called run-length encoding data compression method. Consecutive duplicates of elements are encoded as lists (N E) where N is the number of duplicates of the element E.

```haskell
```

## Q31-41 Arithmetic

## Q46-50 Logic and codes

## Q54A-69 Binary trees

## Q70B-73 Multiway trees

## Q80-89 Graphs

## Q90-99 Misc. problems
