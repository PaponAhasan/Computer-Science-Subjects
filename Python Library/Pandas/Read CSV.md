```
A simple way to store big data sets is to use CSV files. CSV files contains plain text.
```
[CSV Dataset](https://www.w3schools.com/python/pandas/data.csv.txt)

```py
import pandas as pd

df = pd.read_csv('data.csv')

print(df.to_string()) 

# Tip: use to_string() to print the entire DataFrame.
```
```py

# If you have a large DataFrame with many rows, Pandas will only return the first 5 rows, and the last 5 rows

import pandas as pd

df = pd.read_csv('data.csv')

print(df)

```
