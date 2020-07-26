## Documentation

https://pandas.pydata.org/docs/pandas.pdf

## 创建

```py
grades = pd.Series([87, 100, 94])
'''
0     87
1    100
2     94
dtype: int64
'''

pd.Series(98.6, range(3))
'''
0    98.6
1    98.6
2    98.6
dtype: float64
'''

grades[0]
# 87
```

## 类方法,函数

```py
grades.count()
# total elemens
grades.mean()
grades.min()
grades.max()
grades.std()

grades.describe()
# give some basic info

grades.map(function)
# 对序列每个对象进行函数的运算，创建新的序列
```

## 自定义下标(Custom indices)

```py
grades = pd.Series([87, 100, 94], index=['Wally', 'Eva', 'Sam'])
# 两种形式
grades = pd.Series({'Wally': 87, 'Eva': 100, 'Sam': 94})
'''
Wally     87
Eva      100
Sam       94
dtype: int64
'''

grades.Wally
# 87

grades['Eva']
# 100

grades.dtype
# int64

grades.values
# array([ 87, 100,  94], dtype=int64)
```

## 字符串序列

```py
hardware = pd.Series(['Hammer', 'Saw', 'Wrench'])
'''
0    Hammer
1       Saw
2    Wrench
dtype: object
'''
```

#### Series.str类方法类似于python string 

```py
hardware.str.contains('a')
'''
0     True
1     True
2    False
dtype: bool
'''

hardware.str.upper()
'''
0    HAMMER
1       SAW
2    WRENCH
dtype: object
'''
```

























