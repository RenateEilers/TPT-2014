| Ex 1 | Ex 2 | Ex 3 | Ex 4 | Ex 5 | TOTAL |
|------|------|------|------|------|-------|
| 0.5  | 2.3  | 1.5  | 1.5  | 0    | 5.8   |


### Exercise 1                   
* OK

### Exercise 2    
                        
* Non-exhaustive patterns in function evalAlg of exercise c. You should have added 
```haskell
evalAlg _ = Nothing
```
Reduced 0.2 points.

The guards are a bit useless, since the boolean expression can be used directly. It feels like comparing the condition to True in the condition of an if-else statement.

### Exercise 3                       
* The constructor case is incorrect. The PF generated by the library using TemplateHaskell is something like this:
```haskell
data Nil = Nil
instance R.Constructor Nil where
    conName = const "Nil"

data Cons = Cons
instance R.Constructor Cons where
    conName = const "Cons"

type instance R.PF [a] = R.C Nil R.U R.:+: R.C Cons (R.K a R.:*: R.I)
```
Since the constructor case returns [] the output will always be []. Reduced 0.5 points.

### Exercise 4                    
* Your approach only works for data types with 1 recursion step per constructor. This is why we do not get all parents when we have a 
```haskell
data BinTree = BinTree Int BinTree BinTree | Leaf
```
0.5 points reduced.

### Exercise 5                   
* No submission

Mark                          5.8
