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

- #### Replace Only For Specified Columns

- #### Replace Using Mean, Median, or Mode
