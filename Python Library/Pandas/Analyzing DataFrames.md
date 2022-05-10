```py
# The head() method returns the headers and a specified number of rows, starting from the top.

import pandas as pd

df = pd.read_csv('data.csv')

print(df.head(10))

# if the number of rows is not specified, the head() method will return the top 5 rows.
print(df.head())

# There is also a tail() method for viewing the last rows of the DataFrame.
# Starting from the bottom.
print(df.tail()) 

# info(), that gives you more information about the data set
print(df.info()) 
```

<details> <summary> output </summary>
<br> 
  
```
   Duration  Pulse  Maxpulse  Calories
0        60    110       130     409.1
1        60    117       145     479.0
2        60    103       135     340.0
3        45    109       175     282.4
4        45    117       148     406.0
5        60    102       127     300.5
6        60    110       136     374.0
7        45    104       134     253.3
8        30    109       133     195.1
9        60     98       124     269.0
--
  
     Duration  Pulse  Maxpulse  Calories
0        60    110       130     409.1
1        60    117       145     479.0
2        60    103       135     340.0
3        45    109       175     282.4
4        45    117       148     406.0
--
  
  
     Duration  Pulse  Maxpulse  Calories
164        60    105       140     290.8
165        60    110       145     300.4
166        60    115       145     310.2
167        75    120       150     320.4
168        75    125       150     330.4
--
  

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 169 entries, 0 to 168
Data columns (total 4 columns):
#   Column    Non-Null Count  Dtype  
---  ------    --------------  -----  
0   Duration  169 non-null    int64  
1   Pulse     169 non-null    int64  
2   Maxpulse  169 non-null    int64  
3   Calories  164 non-null    float64
dtypes: float64(1), int64(3)
memory usage: 5.4 KB
None
 
```
Result Explained :
```
The result tells us there are 169 rows and 4 columns:
  
    RangeIndex: 169 entries, 0 to 168
    Data columns (total 4 columns):
```
```
 And the name of each column, with the data type:
  
   #   Column    Non-Null Count  Dtype  
  ---  ------    --------------  -----  
   0   Duration  169 non-null    int64  
   1   Pulse     169 non-null    int64  
   2   Maxpulse  169 non-null    int64  
   3   Calories  164 non-null    float64
  
  - how many Non-Null values there are present in each column. 
  - it seems like there are 164 of 169 Non-Null values in the "Calories" column.
```
</details>
