## 字符串Format
#### 常见数据类型
```py
f'{17.489:.2f}'
# 17.49

f'{10:d}'
# 10

f'{65:c} {97:c}'
# 'A a'

f'{"hello":s} {7}'
'hello 7'
```
#### Decimal数据类型
```py
from decimal import Decimal

f'{Decimal("10000000000000000000000000.0"):.3f}'
# '10000000000000000000000000.000'

f'{Decimal("10000000000000000000000000.0"):.3e}'
# '1.000e+25'
```
#### 占据位数
```py
f'[{27:10d}]'
# '[        27]'

f'[{3.5:10f}]'
# '[  3.500000]' 默认六位

f'[{"hello":10}]'
# '[hello     ]' 字符串左对齐，数字右对齐

f'[{27:<15d}]'
# '[27             ]'   
# < : 左对齐
# > : 右对齐
# ^ : 居中 差一个右边空格多
```
#### 更多格式
```py
f'[{27:+10d}]'
# '[       +27]'

f'[{27:+010d}]'
# '[+000000027]'

f'{27: d}'
# 数字前面有一个空格

f'{12345678:,d}'
# '12,345,678'

f'{123456.78:,.2f}'
# '123,456.78'
```
#### 之前版本的Format
```py
'{:.2f}'.format(17.489)
# '17.49'

'{} {}'.format('Amanda', 'Cyan')
# 'Amanda Cyan'

'{0} {0} {1}'.format('Happy', 'Birthday')
# 'Happy Happy Birthday'

'{first} {last}'.format(first='Amanda', last='Gray')
# 'Amanda Gray'

'{last} {first}'.format(first='Amanda', last='Gray')
# 'Gray Amanda'
```
## 字符串处理





































































