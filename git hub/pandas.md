

## Pandas data 

-데이터분석 툴!  데이터를 다루기 위한 시리즈(`Series`) 클래스와 데이터프레임(`DataFrame`) 

## 목차

### 1.데이터 입출력

- ```python
  #시리즈 생성
  import numpy as np
  import pandas as pd
  ```

```python
import numpy as np
import pandas as pd


data = {
    "2015": [9904312, 3448737, 2890451, 2466052],
    "2010": [9631482, 3393191, 2632035, 2431774],
    "2005": [9762546, 3512547, 2517680, 2456016],
    "2000": [9853972, 3655437, 2466338, 2473990],
    "지역": ["수도권", "경상권", "수도권", "경상권"],
    "2010-2015 증가율": [0.0283, 0.0163, 0.0982, 0.0141]
}
columns = ["지역", "2015", "2010", "2005", "2000", "2010-2015 증가율"]
index = ["서울", "부산", "인천", "대구"]
df = pd.DataFrame(data, index=index, columns=columns)
df

data = np.arange(24).reshape(4,6)
columns = ["지역", "2015", "2010", "2005", "2000", "2010-2015 증가율"]
index = ["서울", "부산", "인천", "대구"]
df = pd.DataFrame(data, index=index, columns=columns)
df


df.values

df['2015'].values

df.index.name = '도시'
df.columns.name = '특성'
df

df.T

df['2010-2015 증가율'] = df['2010-2015 증가율'] * 100
df

df['2020'] = [1,2,3,4]
df

del df['2020']
df

df[['지역','2015']]

type(df['지역']), type(df[['지역']])


df['부산'::]

df.head(3)

df['2015']['서울'], df['2015'][0]

data = {
    "국어": [80, 90, 70, 30],
    "영어": [90, 70, 60, 40],
    "수학": [90, 60, 80, 70],
}
columns = ["국어", "영어", "수학"]
index = ["춘향", "몽룡", "향단", "방자"]
df = pd.DataFrame(data, index=index, columns=columns)

df['수학']

df[['국어','영어']]

np.mean(df.values, axis=1).round(1)

df['평균'] = np.mean(df.values, axis=1).round(1)
df

df.groupby('1234').mean()

del df['평균']
df.영어[3] = 80

df['평균'] = np.round(df.mean(axis=1),1)
df

df[0:1]

df.head(3).tail(2)

df.T['향단']

df['영어']['방자']
```



### 2.데이터프레임 고급인덱싱

### 3.데이터조작

### 4.인덱스조작

### 5.합성

### 6. 피벗테이블과 그룹분석

### 7.시계열 자료

