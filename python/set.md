### definition
set is mutable; frozen set is immutable

```py
colors = {'red', 'orange', 'yellow', 'green', 'red', 'blue'}
len(colors)
'red' in colors

# iterable
for color in colors:
    print(color.upper(), end=' ')
    
for word in sorted(set(words)):
    print(word, end=' ')
```
主要用来判断元素在不在其中

### example

```py
numbers = list(range(10)) + list(range(5))
set(numbers)
```
output
```py
{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
```

### empty set
```py
set()
```

### comparison

小于号成立意味着小的是真子集
```py
{1, 3, 5} == {3, 5, 1}
{1, 3, 5} < {7, 3, 5, 1}
{1, 2}.issubset({3, 5, 1})
{1, 3, 5}.issuperset({3, 5, 1})
```

### set（集合）数学运算
union  并集 
```py
{1, 3, 5} | {2, 3, 4}

{1, 3, 5}.union([20, 20, 3, 40, 40])
```
intersection  交集 
```py
{1, 3, 5} & {2, 3, 4}

{1, 3, 5}.intersection([1, 2, 2, 3, 3, 4, 4])
```
difference 差集 
```py
{1, 3, 5} - {2, 3, 4}

{1, 3, 5, 7}.difference([2, 2, 3, 3, 4, 4])
```
Symmetric Difference  去掉公共元素（对称差分）
```py
{1, 3, 5} ^ {2, 3, 4}

{1, 3, 5, 7}.symmetric_difference([2, 2, 3, 3, 4, 4])
```
disjoint  不相交集 
```py
{1, 3, 5}.isdisjoint({4, 6, 1})
```

### mutable set operators 可变集运算符
 | 运算符   | 函数   | 意义 |
 | :-----:   | :-----: |:----:|
 | \|=       | update | 并集 |
 | &=       |intersection_update| 交集|
 | -=       |difference_update|差集|
 | ^=       |symmetric_difference_update|差分|
```py
numbers = {1, 3, 5}
numbers |= {2, 3, 4}
numbers.update(range(10))
```
### method 类方法

add 只添加集合中原来不存在的元素
```py
numbers.add()
numbers.remove()
numbers.pop()
numbers.clear()
```

### set comprehension 集合解析

与列表解析和字典解析类似
```py
numbers = [1, 2, 2, 3, 4, 5, 6, 6, 7, 8, 9, 10, 10]
evens = {item for item in numbers if item % 2 == 0}
```



































