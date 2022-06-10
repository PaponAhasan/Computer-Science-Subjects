```
Empty cells can potentially give you a wrong result when you analyze data.
```
[Open dirtydata.csv](https://www.w3schools.com/python/pandas/dirtydata.csv.txt)

### Remove Rows
```
One way to deal with empty cells is to remove rows that contain empty cells. Since data sets can be very big, 
and removing a few rows will not have a big impact on the result.
```
```py
import pandas as pd

df = pd.read_csv('data.csv')

new_df = df.dropna()

print(new_df.to_string())

# Notice in the result that some rows have been removed (row 18, 22 and 28).

# These rows had cells with empty values.
```
```
Note: By default, the dropna() method returns a new DataFrame, and will not change the original.
```
```py
# If you want to change the original DataFrame, use the inplace = True argument:

import pandas as pd

df = pd.read_csv('data.csv')

df.dropna(inplace = True)

print(df.to_string())
```
### Replace Values
```
Another way of dealing with empty cells is to insert a new value instead.
```
```py
import pandas as pd

df = pd.read_csv('data.csv')

df.fillna(130, inplace = True)

print(df.to_string())

# Notice in the result: empty cells got the value 130 (in row 18, 22 and 28).
```
- #### Replace Only For Specified Columns
```py
import pandas as pd

df = pd.read_csv('data.csv')

df["Calories"].fillna(130, inplace = True)

print(df.to_string())

# This operation inserts 130 in empty cells in the "Calories" column (row 18 and 28).)
```
- #### Replace Using Mean, Median, or Mode
```py
import pandas as pd

df = pd.read_csv('data.csv')

x = df["Calories"].mean()

df["Calories"].fillna(x, inplace = True)

print(df.to_string())

# As you can see in row 18 and 28, the empty values from "Calories" was replaced with the mean: 304.68

N.T : Mean = the average value (the sum of all values divided by number of values).
```
```py
import pandas as pd

df = pd.read_csv('data.csv')

x = df["Calories"].median()

df["Calories"].fillna(x, inplace = True)

print(df.to_string())

#As you can see in row 18 and 28, the empty values from "Calories" was replaced with the median: 291.2

N.T : Median = the value in the middle, after you have sorted all values ascending.
```
```py
import pandas as pd

df = pd.read_csv('data.csv')

x = df["Calories"].mode()[0]

df["Calories"].fillna(x, inplace = True)

print(df.to_string())

#As you can see in row 18 and 28, the empty value from "Calories" was replaced with the mode: 300.0

N.T : Mode = the value that appears most frequently.
```
