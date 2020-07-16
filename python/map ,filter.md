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






















