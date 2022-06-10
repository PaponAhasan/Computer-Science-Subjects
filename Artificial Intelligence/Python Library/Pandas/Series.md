```
A Pandas Series is like a column in a table. It is a one-dimensional array holding data of any type.
```
##
```py
import pandas as pd

a = [1, 7, 2]

myvar = pd.Series(a)

print(myvar)

print(myvar[1])
```
<details> <summary> output </summary>
<br> 
  
```
0    1
1    7
2    2
dtype: int64

7
```
</details>

##
### Key/Value Objects
```py
import pandas as pd

calories = {"day1": 420, "day2": 380, "day3": 390}

myvar = pd.Series(calories)

print(myvar)

# only data from "day1" and "day2":
myvar = pd.Series(calories, index = ["day1", "day2"])

print(myvar)
```
<details> <summary> output </summary>
<br> 
  
```
day1    420
day2    380
day3    390
dtype: int64
--
day1    420
day2    380
dtype: int64
```
</details>

##
### Create Labels (With the index argument)
```py
import pandas as pd

a = [1, 7, 2]

myvar = pd.Series(a, index = ["x", "y", "z"])

print(myvar)

print(myvar["y"])
```
<details> <summary> output </summary>
<br> 
  
```
x    1
y    7
z    2
dtype: int64

7
```
</details>
