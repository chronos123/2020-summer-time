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
## 正则表达式re
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
[ ][ ]* 必含第一个中括号，可不含第二个，可含多个第二个<br>
[^ ] 不含中括号内容<br>
[ ] 含第一个中括号内容<br>
[ ][ ]+ 有第一个括号至少含一个第二个括号<br>
[a?] a可以有也可以没有<br>
\t+ 一个或多个单一字符
```py
'Valid' if re.fullmatch('[A-Z][a-z]*', 'Wally') else 'Invalid'
# 匹配以大写字母开头的字符串

'Match' if re.fullmatch('[^a-z]', 'A') else 'No match'


'Valid' if re.fullmatch('[A-Z][a-z]+', 'Wally') else 'Invalid'
# 匹配大写开头要跟小写的字符串
```
####  re.sub
```py
re.sub(r'\t', ', ', '1\t2\t3\t4')
# 替换后面的\t为,

re.sub(r'\t', ', ', '1\t2\t3\t4', count=2)
# 替换指定个数

re.split(r',\s*', '1,  2,  3,4,    5,6,7,8')
# 通过字符匹配分割

re.split(r',\s*', '1,  2,  3,4,    5,6,7,8', maxsplit=3)
# 分割到有限个
```

#### re.search
```py
result = re.search('Python', 'Python is fun')
result.group() if result else 'not found'
# 搜索到就非None, 找第一个匹配的子串，group显示

result3 = re.search('Sam', 'SAM WHITE', flags=re.IGNORECASE)
# 忽略字母大小写

result = re.search('^Python', 'Python is fun')
# ^意味着寻找是否为开头

result = re.search('fun$', 'Python is fun')
# $意味着寻找是否为结尾
```
#### re.findall 和 re.finditer
```py
contact = 'Wally White, Home: 555-555-1234, Work: 555-555-4321'
re.findall(r'\d{3}-\d{3}-\d{4}', contact)
# 找出所有符合的，返回列表

for phone in re.finditer(r'\d{3}-\d{3}-\d{4}', contact):
    print(phone.group())
# 返回（一个可遍历的）lazy iterator 用group打出
```
#### 寻找匹配的一部分
```py
text = 'Charlie Cyan, e-mail: demo1@deitel.com'
pattern = r'([A-Z][a-z]+ [A-Z][a-z]+), e-mail: (\w+@\w+\.\w{3})'
result = re.search(pattern, text)
result.groups()
# ('Charlie Cyan', 'demo1@deitel.com') 返回一个元组

result.group()
# 全部包含

result.group(1)
# 'Charlie Cyan'

result.group(2)
# 'demo1@deitel.com'
```

## 例子
分割算式
#### 输入
```py
import re
str1 = '10 + 5'
pattern = r'(\d+) ([\+\-\*\/]) (\d+)' 或 pattern = r'(\d+) ([+-/*]) (\d+)'
result = re.search(pattern, str1)
result.groups()
```
#### 输出
```py
('10', '+', '5')
```






















































