### 创建
从任何序列中创建
```py
import numpy as np
numbers = np.array([2, 3, 5, 7, 11])
# 自动添加格式
# array([ 2,  3,  5,  7, 11])
# 7 前面两个空格(留出占据位置最多的空格数并右对齐)
```
各种创建方法
```py
np.array([item for item in range(2, 21) if item % 2 == 0])
# array([ 2,  4,  6,  8, 10, 12, 14, 16, 18, 20])


np.array([[2, 4, 6, 8, 10], [1, 3, 5, 7, 9]])
# array([[ 2,  4,  6,  8, 10],
#       [ 1,  3,  5,  7,  9]])
# 不使用列表解析
```
二维数组
```py
np.array([[1, 2, 3], [4, 5, 6]])
''' array([[1, 2, 3],
       [4, 5, 6]])
'''
```

### 类型 
数据类型说明

https://numpy.org/doc/stable/user/basics.types.html
```py
integers = np.array([[1, 2, 3], [4, 5, 6]])

integers.dtype
# int32
# data type of c

integers.ndim
# 2
# dimension

integers.shape
# (2, 3) (row, column)

integers.size
# 6 
# number of elements

integers.itemsize
# 4
# size of item (byte)
```

iterate 遍历
```py
for row in integers:
    for column in row:
        print(column, end='  ')
    print() 
```
二维当成一维
```py
for i in integers.flat:
    print(i, end='  ')
```

### 






















































