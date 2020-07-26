## 数据有效性
#### 整体验证Series
```py
zips = pd.Series({'Boston': '02215', 'Miami': '3310'})
zips.str.match(r'\d{5}')
'''
Boston     True
Miami     False
'''
```
#### 验证是否含有
```py
cities = pd.Series(['Boston, MA 02215', 'Miami, FL 33101'])
cities.str.contains(r' [A-Z]{2} ')
'''
0    True
1    True
'''
```
#### 重新对数据建立格式
```py
contacts = [['Mike Green', 'demo1@deitel.com', '5555555555'],
            ['Sue Brown', 'demo2@deitel.com', '5555551234']]
            
contactsdf = pd.DataFrame(contacts, 
                          columns=['Name', 'Email', 'Phone'])

def get_formatted_phone(value):
    """对电话号码重新安排格式"""
    result = re.fullmatch(r'(\d{3})(\d{3})(\d{4})', value)
    # fullmatch返回的值可以group
    return '-'.join(result.groups()) if result else value


formatted_phone = contactsdf['Phone'].map(get_formatted_phone)
contactsdf['Phone'] = formatted_phone
```





















