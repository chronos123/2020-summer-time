## 创建类

在类下面进行注释
```py
class Account:
    """Account class for maintaining a bank account balance."""

```

## 类中元素
利用 <code>def \_\_init\_\_(self, name, balance)</code> 函数初始化类中元素
```py
    def __init__(self, name, balance):
        """Initialize an Account object."""

        # if balance is less than 0.00, raise an exception
        if balance < Decimal('0.00'):
            raise ValueError('Initial balance must be >= to 0.00.')

        self.name = name
        self.balance = balance
```

## 类方法
通过函数定义类方法
```py
    def deposit(self, amount):
        """Deposit money to the account."""

        # if amount is less than 0.00, raise an exception
        if amount < Decimal('0.00'):
            raise ValueError('amount must be positive.')

        self.balance += amount

```
