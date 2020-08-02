# 文件操作

## 打开文件，并写入
```py
with open('accounts.txt', mode='w') as accounts:
accounts.write('100 Jones 24.98\n')
# 文件写入

!dir accounts.txt
# 显示目录
!more accounts.txt
# 显示内容
# 命令行文件数据显示
```
##  文件读取
```py
with open('accounts.txt', mode='r') as accounts:
    print(f'{"Account":<10}{"Name":<10}{"Balance":>10}')
    for record in accounts:
        account, name, balance = record.split()
        print(f'{account:<10}{name:<10}{balance:>10}')
     
# 按行读取，file可以遍历

readlines 函数 读取所有行
遍历每行占用的内存少
```
## 文件更新
```py
accounts = open('accounts.txt', 'r')
temp_file = open('temp_file.txt', 'w')

with accounts, temp_file:
    for record in accounts:
        account, name, balance = record.split()
        if account != '300':
            temp_file.write(record)
        else:
            new_record = ' '.join([account, 'Williams', balance])
            temp_file.write(new_record + '\n')                    
import os
os.remove('accounts.txt')
os.rename('temp_file.txt', 'accounts.txt')
```
## JSON文件读写
```py
accounts_dict = {'accounts': [
    {'account': 100, 'name': 'Jones', 'balance': 24.98},
    {'account': 200, 'name': 'Doe', 'balance': 345.67}]}

import json
with open('accounts.json', 'w') as accounts:
    json.dump(accounts_dict, accounts)
    
with open('accounts.json', 'r') as accounts:
    accounts_json = json.load(accounts)
```

#### 输入
```py
with open('accounts.json', 'r') as accounts:
    print(json.dumps(json.load(accounts), indent=4))
```
#### 输出
```py
{
    "accounts": [
        {
            "account": 100,
            "name": "Jones",
            "balance": 24.98
        },
        {
            "account": 200,
            "name": "Doe",
            "balance": 345.67
        }
    ]
}
```
## CSV文件
#### 写入
```py
import csv
with open('accounts.csv', mode='w', newline='') as accounts:
    writer = csv.writer(accounts)
    writer.writerow([100, 'Jones', 24.98])
    writer.writerow([200, 'Doe', 345.67])
    writer.writerow([300, 'White', 0.00])
    writer.writerow([400, 'Stone', -42.16])
    writer.writerow([500, 'Rich', 224.62])
    
```

#### 读取
```py
with open('accounts.csv', 'r', newline='') as accounts:
    print(f'{"Account":<10}{"Name":<10}{"Balance":>10}')
    reader = csv.reader(accounts)
    for record in reader:  
    # 遍历reader的每行
        account, name, balance = record
        print(f'{account:<10}{name:<10}{balance:>10}')
        

```











































































