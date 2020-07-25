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
#### 除去多余的空格
```py
sentence = '\t  \n  This is a test string. \t\t \n'
sentence.strip()
# 除去所有多余的

sentence.lstrip()
# 除去左边的

sentence.rstrip()
# 除去右边的 不改变本来的值
```
#### 大写
```py
'happy birthday'.capitalize()
大写首字母

'strings: a deeper look'.title()
# 每个单词首字母大写
```
#### 寻找子串
```py
sentence = 'to be or not to be that is the question'

sentence.count('that', 12, 25)
# 12个单词与25个单词之间计数

sentence.index('be') 或 sentence.find('be')
# 寻找下标

sentence.rindex('be') 或 sentence.rfind'be')
# 倒着寻找

sentence.startswith('to')
# 判断开始字符串

sentence.endswith('question')
# 判断结束字符串
```
#### 替换子串
```py
values = '1\t2\t3\t4\t5'
values.replace('\t', ',')
# '1,2,3,4,5' 返回一个新字符串
```
#### 分割和拼接子串
```py
letters = 'A, B, C, D'
letters.split(', ', 2)
# ['A', 'B', 'C, D'] 分割两次，分割字符串为列表

letters_list = ['A', 'B', 'C', 'D']
','.join(letters_list)
','.join([str(i) for i in range(10)])
# 用逗号连接列表为字符串

'Amanda: 89, 97, 92'.partition(': ')
# 从冒号划分字符串 ('Amanda', ': ', '89, 97, 92') 返回元组

url = 'http://www.deitel.com/books/PyCDS/table_of_contents.html'
protocol, separator, rest_of_url = url.partition('://')
# 分割赋值
rest_of_url, separator, document = url.rpartition('/')
# 从右边开始分割

lines = """This is line 1
This is line2
This is line3"""

lines.splitlines()
# ['This is line 1', 'This is line2', 'This is line3']

lines.splitlines(True)
# ['This is line 1\n', 'This is line2\n', 'This is line3']
```
#### 判断数据类型
```py
'-27'.isdigit()
# 字符串是否全为数字

'A9876'.isalnum()
# 字符串是否全是字母和数字
```
#### 正则表达式re
<h5>re.fullmatch</h5>
<ol>
  <b>
  <li> \d{x} x位数字字符 注意raw string</li>
  <li> \d{x, } 至少x位数字字符</li>
  <li> \d{x, y} x到y位数字字符</li>
  <li> \D 非数字字符</li>
  <li> \s 空格字符</li>
  <li> \S 非空格字符</li>
  <li> \w 大小写字母，数字，下划线</li>
  <li> \W 不是上述字符</li>
  </b>
</ol>

```py
import re
pattern = '02215'
'Match' if re.fullmatch(pattern, '02215') else 'No match'
# 'Match' 两个字符串是否相等

'Valid' if re.fullmatch(r'\d{5}', '02215') else 'Invalid'
```
#### 自定义匹配
[ ][ ]* 含第一个中括号不含第二个<br>
[^ ] 不含中括号内容<br>
[ ] 含第一个中括号内容<br>
[ ][ ]+ 有第一个括号至少含一个第二个括号<br>
[a?] a可以有也可以没有<br>
[]
```py
'Valid' if re.fullmatch('[A-Z][a-z]*', 'Wally') else 'Invalid'
# 匹配以大写字母开头的字符串

'Match' if re.fullmatch('[^a-z]', 'A') else 'No match'
```
####  




























































