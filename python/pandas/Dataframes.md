
## 创建

```py
grades_dict = {'Wally': [87, 96, 70], 'Eva': [100, 87, 90],
               'Sam': [94, 77, 90], 'Katie': [100, 81, 82],
               'Bob': [83, 65, 85]}
grades = pd.DataFrame(grades_dict)
'''
	Wally	Eva	Sam	Katie	Bob
0	87	100	94	100	83
1	96	87	77	81	65
2	70	90	90	82	85
'''
# 每列是Series

grades.index = ['Test1', 'Test2', 'Test3']
# 给行附上index
'''
Wally	Eva	Sam	Katie	Bob
Test1	87	100	94	100	83
Test2	96	87	77	81	65
Test3	70	90	90	82	85
'''
```


## 访问

#### 对列访问
```py
grades['Eva']
'''
Test1    100
Test2     87
Test3     90
Name: Eva, dtype: int64
'''

grades.Sam
'''
Test1    94
Test2    77
Test3    90
Name: Sam, dtype: int64
'''
```
#### 对行访问
推荐使用loc和iloc对行访问
```py
grades.loc['Test1']
'''
Wally     87
Eva      100
Sam       94
Katie    100
Bob       83
Name: Test1, dtype: int64
'''

grades.iloc[1]
# 第二行
'''
Wally    96
Eva      87
Sam      77
Katie    81
Bob      65
Name: Test2, dtype: int64
'''
```

## 选择行用loc和iloc
#### 只选几行
```py
grades.loc['Test1':'Test3']
# include row Test3

grades.iloc[0:2]
# don't include row 2(从0开始)

grades.loc[['Test1', 'Test3']]

grades.iloc[[0, 2]]
# 第0行和第2行
```
#### 几行几列一起选
```py
grades.loc['Test1':'Test2', ['Eva', 'Katie']]
'''
        Eva	Katie
Test1	100	100
Test2	87	81
'''
grades.iloc[[0, 2], 0:3]
'''
       Wally	Eva	Sam
Test1	87	100	94
Test3	70	90	90
'''
```
## 条件选择(Boolean Indexing)
#### 输入
```py
grades[grades >= 90]
```
#### 输出
NaN是一个缺失的数据
```py
	Wally	Eva	Sam	Katie	Bob
Test1	NaN	100.0	94.0	100.0	NaN
Test2	96.0	NaN	NaN	NaN	NaN
Test3	NaN	90.0	90.0	NaN	NaN
```
#### 输入
且要用 & 而不用 and
```py
grades[(grades >= 80) & (grades < 90)]
```
#### 输出
Numpy会显示所有符合条件的数据
```py
        Wally	Eva	Sam	Katie	Bob
Test1	87.0	NaN	NaN	NaN	83.0
Test2	NaN	87.0	NaN	81.0	NaN
Test3	NaN	NaN	NaN	82.0	85.0
```

## 访问一个数据
```py
grades.at['Test2', 'Eva']
# 82

grades.iat[2, 0]
# 70(第二行第0列)

grades.at['Test2', 'Eva'] = 100
# 改变这一元素值

grades.iat[1, 1] = 87
# 改变一个元素值
```
## 类方法

#### 描述
```py
grades.describe()
'''
	Wally	        Eva	        Sam	        Katie   	Bob
count	3.000000	3.000000	3.000000	3.000000	3.000000
mean	84.333333	92.333333	87.000000	87.666667	77.666667
std	13.203535	6.806859	8.888194	10.692677	11.015141
min	70.000000	87.000000	77.000000	81.000000	65.000000
25%	78.500000	88.500000	83.500000	81.500000	74.000000
50%	87.000000	90.000000	90.000000	82.000000	83.000000
75%	91.500000	95.000000	92.000000	91.000000	84.000000
max	96.000000	100.000000	94.000000	100.000000	85.000000
'''
pd.set_option('precision', 2)
# 设置精度

grades.mean()
'''
Wally    84.33
Eva      92.33
Sam      87.00
Katie    87.67
Bob      77.67
dtype: float64
'''
```
#### 转置
```py

```





































