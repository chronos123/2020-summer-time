
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














































