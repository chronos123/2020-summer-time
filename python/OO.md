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


## 创建私有变量
利用
<code>
 @property @name.setter
</code>
两个关键字， 防止直接输入无效数据
```py
class Time:
    """Class Time with read-write properties."""

    def __init__(self, hour=0, minute=0, second=0):
        """Initialize each attribute."""
        self.hour = hour  # 0-23
        self.minute = minute  # 0-59
        self.second = second  # 0-59
        
    @property
    def hour(self):
        """Return the hour."""
        return self._hour

    @hour.setter
    def hour(self, hour):
        """Set the hour."""
        if not (0 <= hour < 24):
            raise ValueError(f'Hour ({hour}) must be 0-23')

        self._hour = hour
```
#### 改变值
```py
    def set_time(self, hour=0, minute=0, second=0):
        """Set values of hour, minute, and second."""
        self.hour = hour
        self.minute = minute
        self.second = second
```
#### 利用元组
```py
    @property
    def time(self):
        return (self.hour, self.minute, self.second)
    
    
    @time.setter
    def time(self, time):
        self.time_setter(*time)
```
## print 一个实例

```py
    def __str__(self):
        """Print Time in 12-hour clock format."""
        return (('12' if self.hour in (0, 12) else str(self.hour % 12)) + 
                f':{self.minute:0>2}:{self.second:0>2}' + 
                (' AM' if self.hour < 12 else ' PM'))

```

## 实例变量的值

```py
    def __repr__(self):
        """Return Time string for repr()."""
        return (f'Time(hour={self.hour}, minute={self.minute}, ' + 
                f'second={self.second})')
```
## 对输出进行格式控制
```py
    def __format__(self, format):
        """Return formatted string representation for str()."""
        return f'{str(self):{format}}'       
```
#### 输入
```py
class Date_time():
    format_dict = {
        'ymd':"{0.year}-{0.mon}-{0.day}",
        "mdy":"{0.day}:{0.mon}:{0.year}"
    }

    def __init__(self,year,mon,day):
        self.year = year
        self.mon = mon
        self.day = day

    def __format__(self, format_spec='ymd'):
        try:
            return self.format_dict[format_spec].format(self)
        except KeyError :
            return '{0.year}-{0.mon}-{0.day}'.format(self)

xx = Date_time('2018','10','14')

print(xx.__format__('ymd'))
print(xx.__format__('mdy'))
print(xx.__format__())
```
## 输出
```py
2018-10-14
14:10:2018
2018-10-14
```

## 继承
```py
class SalariedCommissionEmployee(CommissionEmployee):
    """An employee who gets paid a salary plus 
    commission based on gross sales."""

    def __init__(self, first_name, last_name, ssn, 
                 gross_sales, commission_rate, base_salary):
        """Initialize SalariedCommissionEmployee's attributes."""
        super().__init__(first_name, last_name, ssn, 
                         gross_sales, commission_rate)
        self.base_salary = base_salary  # validate via property
# super().__init__ 用父类的初始化方法
```











