
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
# don't include row 3(2+1)

grades.loc[['Test1', 'Test3']]

grades.iloc[[0, 2]]
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
## 











































