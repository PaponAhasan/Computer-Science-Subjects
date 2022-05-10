```
A Pandas DataFrame is a 2 dimensional data structure, like a 2 dimensional array, or a table with rows and columns.
```
##
```py
import pandas as pd

data = {
  "calories": [420, 380, 390],
  "duration": [50, 40, 45]
}

#load data into a DataFrame object:
df = pd.DataFrame(data)

print(df)

# Locate Row (loc attribute to return one or more specified row)
print(df.loc[0])

#use a list of indexes: (When using [], the result is a Pandas DataFrame.)
print(df.loc[[0, 1]])
```
<details> <summary> output </summary>
<br> 
  
```
     calories  duration
  0       420        50
  1       380        40
  2       390        45
  
  calories    420
  duration     50
  Name: 0, dtype: int64
  
       calories  duration
  0       420        50
  1       380        40
```
</details>
