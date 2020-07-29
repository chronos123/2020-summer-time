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
```
