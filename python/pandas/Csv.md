## 读和写CSV文件
```py
df = pd.read_csv('accounts.csv', 
                 names=['account', 'name', 'balance'])
# names作为第一行的名字，存在dataframe中

titanic = pd.read_csv('https://vincentarelbundock.github.io/' +
    'Rdatasets/csv/carData/TitanicSurvival.csv')
# 从网站读取

df.to_csv('accounts_from_dataframe.csv', index=False)
# 用dataframe创建csv文件
# index=False说明不把index存在csv中
```

## 



