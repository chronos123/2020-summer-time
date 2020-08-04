## 读和写CSV文件
```py
df = pd.read_csv('accounts.csv', 
                 names=['account', 'name', 'balance'])
# names作为第一行的名字，存在dataframe中

df.to_csv('accounts_from_dataframe.csv', index=False)
# 用dataframe创建csv文件
```

## 



