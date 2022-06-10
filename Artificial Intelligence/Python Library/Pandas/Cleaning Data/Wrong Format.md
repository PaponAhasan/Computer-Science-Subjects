```
Cells with data of wrong format can make it difficult, or even impossible, to analyze data.
  you have two options: 
      1. remove the rows, or 
      2. convert all cells in the columns into the same format.
```
```py
  21        60  '2020/12/21'    108       131     364.2
  22        45           NaN    100       119     282.0
  23        60  '2020/12/23'    130       101     300.0
  24        45  '2020/12/24'    105       132     246.0
  25        60  '2020/12/25'    102       126     334.5
  26        60      20201226    100       120     250.0
  
  wrong format. Check out row 22 and 26, the 'Date' column 
```

### Convert all cells same format
```py
import pandas as pd

df = pd.read_csv('data.csv')

df['Date'] = pd.to_datetime(df['Date'])

print(df.to_string())
```
```py
  22        45           NaT    100       119     282.0
  23        60  '2020/12/23'    130       101     300.0
  24        45  '2020/12/24'    105       132     246.0
  25        60  '2020/12/25'    102       126     334.5
  26        60  '2020/12/26'    100       120     250.0
  
  The result, the date in row 26 was fixed, but the empty date in row 22 got a NaT (Not a Time) value( empty value. )
  One way to deal with empty values is simply removing the entire row.
```
### Removing Rows
```py
import pandas as pd

df = pd.read_csv('data.csv')

df['Date'] = pd.to_datetime(df['Date'])

df.dropna(subset=['Date'], inplace = True)

print(df.to_string())
```
