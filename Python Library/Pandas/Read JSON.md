```
Big data sets are often stored, or extracted as JSON. JSON is plain text, but has the format of an object.
JSON = Python Dictionary. JSON objects have the same format as Python dictionaries.
```
[JSON File](https://www.w3schools.com/python/pandas/data.js)
##
```py
import pandas as pd

df = pd.read_json('data.json')

print(df.to_string()) 
```
##
```py
import pandas as pd

data = {
  "Duration":{
    "0":60,
    "1":60,
    "2":60,
    "3":45,
    "4":45,
    "5":60
  },
  "Pulse":{
    "0":110,
    "1":117,
    "2":103,
    "3":109,
    "4":117,
    "5":102
  },
  "Maxpulse":{
    "0":130,
    "1":145,
    "2":135,
    "3":175,
    "4":148,
    "5":127
  },
  "Calories":{
    "0":409,
    "1":479,
    "2":340,
    "3":282,
    "4":406,
    "5":300
  }
}

df = pd.DataFrame(data)

print(df) 
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
```
</details>
