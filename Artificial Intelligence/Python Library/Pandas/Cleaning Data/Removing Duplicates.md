```
  8         30  '2020/12/09'    109       133     195.1
  9         60  '2020/12/10'     98       124     269.0
  10        60  '2020/12/11'    103       147     329.3
  11        60  '2020/12/12'    100       120     250.7
  12        60  '2020/12/12'    100       120     250.7
  13        60  '2020/12/13'    106       128     345.3
  
  we can assume that row 11 and 12 are duplicates.
```
```py
# Returns True for every row that is a duplicate, othwerwise False:

import pandas as pd

df = pd.read_csv('data.csv')

print(df.duplicated())
```
```
9     False
10    False
11    False
12     True
13    False
14    False
```
##
```py
import pandas as pd

df = pd.read_csv('data.csv')

df.drop_duplicates(inplace = True)

print(df.to_string())

#Notice that row 12 has been removed from the result
```
