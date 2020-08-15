## 注释测试

#### 测试类
格式：
&nbsp; >>> 测试代码 <br>
&emsp; &emsp;  &emsp;       输出

输出出错时：只要第一行和最后一行 <br>
<article>
          Traceback (most recent call last): <br>
            ...  <br>
        ValueError: Initial balance must be >= to 0.00.  
</article>

```py
class Account:
    """Account class for demonstrating doctest."""
    
    def __init__(self, name, balance):
        """Initialize an Account object.
        
        >>> account1 = Account('John Green', Decimal('50.00'))
        >>> account1.name
        'John Green'
        >>> account1.balance
        Decimal('50.00')

        The balance argument must be greater than or equal to 0.
        >>> account2 = Account('John Green', Decimal('-50.00'))
        Traceback (most recent call last):
            ...
        ValueError: Initial balance must be >= to 0.00.
        """

        # if balance is less than 0.00, raise an exception
        if balance < Decimal('0.00'):
            raise ValueError('Initial balance must be >= to 0.00.')

        self.name = name
        self.balance = balance

    def deposit(self, amount):
        """Deposit money to the account."""

        # if amount is less than 0.00, raise an exception
        if amount < Decimal('0.00'):
            raise ValueError('amount must be positive.')

        self.balance += amount
```

#### __main__函数

```py
if __name__ == '__main__':
    import doctest
    doctest.testmod(verbose=True)
# 当作为代码直接执行时，执行，进行doctest, verbose将输出一些结果
```

#### 输入
在终端ipython模式下输入
```py
%doctest_mode
```















