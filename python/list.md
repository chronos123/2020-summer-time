# list 的各种函数

列表简单创建
```py
numbers = list(range(1, 10))
```

列表操作
```py
numbers = [3, 7, 1, 4, 2, 8, 5, 6]
numbers *= 2
# 复制列表加到后面
numbers.index(7, 0, 4)

color_names = ['orange', 'yellow', 'green']
color_names.insert(0, 'red')
color_names.extend(['indigo', 'violet'])
color_names.append('blue')
color_names.remove('green')
color_names.clear()


sample_list = []
sample_list.extend((4, 5, 6))
sample_list.count(4)
```
模拟栈结构
```py
stack = []
stack.append('red')
stack.append('green')
stack.pop()
```
排序等操作
```py
list1 = [3, 5, -4, -1, 0, -2, -6]
list1.sort(key=lambda x: abs(x), reverse=True)
```

# lamda函数

是一种匿名的函数，被需要函数参数的函数作为变量调用

# filter用法

filter中先调用一个筛选函数
```py
numbers = [10, 3, 7, 1, 9, 4, 2, 8, 5, 6 ]
list(filter(lambda x: x % 2 != 0, numbers))
```

# map用法

map中先调用一个配对函数
```py
list(map(lambda x: x ** 2, numbers))
```

# filter 和 map 结合
```py
list(map(lambda x: x ** 2,
    filter(lambda x: x % 2 != 0, numbers)))
# first filter then map it
```

# 列表不同生成方式

有comprehension(greedy)用中括号, generator(lazy)用小括号

## comprehension
```py
numbers = [item for item in range(3, 30) if item % 3 == 0]
```

## generator

作为函数参数时，传参小括号也作为generator的括号
```py
print(list(item ** 3 for item in numbers if item % 2 == 0))
```






















