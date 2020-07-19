### 创建
从任何序列中创建
```py
import numpy as np
numbers = np.array([2, 3, 5, 7, 11])
# 自动添加格式
# array([ 2,  3,  5,  7, 11])
# 7 前面两个空格
```
各种创建方法
```py
np.array([item for item in range(2, 21) if item % 2 == 0])

numbers = np.array([[item for item in range(2, 11) if item %2 == 0],
          [item for item in range(1, 9) if item % 2 != 0]])
```
二维数组
```py
np.array([[1, 2, 3], [4, 5, 6]])
# array([[1, 2, 3],
       [4, 5, 6]])
```

### 
























































