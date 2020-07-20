## 创建数组
#### 从任何序列中创建
```py
import numpy as np
numbers = np.array([2, 3, 5, 7, 11])
# 自动添加格式
# array([ 2,  3,  5,  7, 11])
# 7 前面两个空格(留出占据位置最多的空格数并右对齐)
```
#### 各种创建方法
```py
np.array([item for item in range(2, 21) if item % 2 == 0])
# array([ 2,  4,  6,  8, 10, 12, 14, 16, 18, 20])


np.array([[2, 4, 6, 8, 10], [1, 3, 5, 7, 9]])
# array([[ 2,  4,  6,  8, 10],
#       [ 1,  3,  5,  7,  9]])
# 不使用列表解析
```
#### 二维数组
```py
np.array([[1, 2, 3], [4, 5, 6]])
''' array([[1, 2, 3],
       [4, 5, 6]])
'''
```

## 类型 
#### 数据类型说明

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

#### iterate 遍历
```py
for row in integers:
    for column in row:
        print(column, end='  ')
    print() 
```
#### 二维当成一维
```py
for i in integers.flat:
    print(i, end='  ')
```

## 特殊赋值创建 （Filling arrays with Specific Values）
#### 创建array([0., 0., 0., 0., 0.])
```py
np.zeros(5)
```
#### 创建array([[1, 1, 1, 1], [1, 1, 1, 1]])
```py
np.ones((2, 4), dtype=int)
```
#### 创建array([[13, 13, 13, 13, 13], [13, 13, 13, 13, 13], [13, 13, 13, 13, 13]])
```py
np.full((3, 5), 13)
```

## Creating arrays from Ranges 直接生成数组
#### 整形数据 array([0, 1, 2, 3, 4])
```py
np.arange(5)
```
#### 浮点数据 array([0.  , 0.25, 0.5 , 0.75, 1.  ])
```py
np.linspace(0.0, 1.0, num=5)
# 分成5份
# same character positions
```
#### Reshape the array 来构建矩阵

得到array([[ 1,  2,  3,  4,  5],
       [ 6,  7,  8,  9, 10],
       [11, 12, 13, 14, 15],
       [16, 17, 18, 19, 20]])
```py
np.arange(1, 21).reshape(4, 5)
```

## ipython magic
```py
%timeit -n3 -r2  # 计算运行时间 3 loops; 2 runs
%load # read code into ipython
%save # save snippets to a file
%run # execute .py file in ipython
%precision # 规定近似小数点后几位
%cd # 换盘
%edit # 打开外部编辑器
%history # 列出执行过的代码
```

## Numpy 重载运算符(Array Operators)
```py
numbers = np.arange(1, 6)
```
#### 每个数乘2
```py
numbers * 2
# 创建np.array((1, 5), 2)与前相乘
```
#### 每个数取幂指数
```py
numbers ** 3
```
#### 相加
```py
numbers += 10
```
#### 两数组相乘
```py
numbers = np.array([11, 12, 13, 14, 15])
numbers2 = np.linspace(1.1, 5.5, 5)
# 要求同一维数
numbers * numbers2
```
##### 输出
```py
array([12.1, 26.4, 42.9, 61.6, 82.5])
```
#### 比较
```py
numbers >= 13
# 输出 array([False, False,  True,  True,  True])

numbers2 < numbers
# 输出 array([ True,  True,  True,  True,  True])

numbers == numbers2
# 输出 array([False, False, False, False, False])
```
## 计算类方法 Calculation Methods
```py
import numpy as np


grades = np.array([[87, 96, 70], [100, 87, 90],
                   [94, 77, 90], [100, 81, 82]])
grades.sum()
grades.min()
grades.max()
grades.mean()
grades.std()
grades.var()
```
#### 对特别的行和列
```py
grades.mean(axis=0)
# 对列
grades.mean(axis=1)
# 对行
```

## 以数组为参数的函数 (Universal Function)
```py
numbers = np.array([1, 4, 9, 16, 25, 36])
np.sqrt(numbers)
# 输出 array([1., 2., 3., 4., 5., 6.])

numbers2 = np.arange(1, 7) * 10
np.add(numbers, numbers2)

np.multiply(numbers2, 5)
numbers3 = numbers2.reshape(2, 3)

numbers4 = np.array([2, 4, 6])
np.multiply(numbers3, numbers4)
# 一维看做列向量进行矩阵乘法
```
##































