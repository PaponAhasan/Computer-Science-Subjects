```
  4         45  '2020/12/05'    117       148     406.0
  5         60  '2020/12/06'    102       127     300.0
  6         60  '2020/12/07'    110       136     374.0
  7        450  '2020/12/08'    104       134     253.3
  8         30  '2020/12/09'    109       133     195.1
```
### Replacing Values
```py
import pandas as pd

df = pd.read_csv('data.csv')

# Set "Duration" = 45 in row 7
df.loc[7,'Duration'] = 45

print(df.to_string())
```
##
```
To replace wrong data for larger data sets you can create some rules
```
```py
import pandas as pd

df = pd.read_csv('data.csv')

for x in df.index:
  if df.loc[x, "Duration"] > 120:
    df.loc[x, "Duration"] = 120

print(df.to_string())
```

##
```
Delete rows where "Duration" is higher than 120
```
```py
import pandas as pd

df = pd.read_csv('data.csv')

for x in df.index:
  if df.loc[x, "Duration"] > 120:
    df.drop(x, inplace = True)

#remember to include the 'inplace = True' argument to make the changes in the original DataFrame object instead of returning a copy

print(df.to_string())
```
