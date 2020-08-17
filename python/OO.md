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

    def __repr__(self):
        """Return string representation for repr()."""
        return ('Salaried' + super().__repr__() +      
            f'\nbase salary: {self.base_salary:.2f}')
            
# super().__repr__ 使用父类的展示方法
```

#### 多态
```py
    def earnings(self):
        """Calculate earnings."""   
        return super().earnings() + self.base_salary

# 对SalariedCommissionEmployee类的earning的重新定义
```

#### 验证关系
```py
issubclass(SalariedCommissionEmployee, CommissionEmployee)

isinstance(s, CommissionEmployee)

isinstance(s, SalariedCommissionEmployee)
```

## 重载运算符

 <h4> 算术运算符的重载:  </h4>
 
 <ul>
   <li>         方法名      &emsp;              运算符和表达式  &emsp;      说明  </li>
     <li>        __add__(self,rhs)   &emsp;         self + rhs    &emsp;      加法    </li>
    <li>         __sub__(self,rhs)    &emsp;        self - rhs  &emsp;         减法</li>
     <li>        __mul__(self,rhs)      &emsp;      self * rhs   &emsp;        乘法</li>
      <li>       __truediv__(self,rhs)   &emsp;    self / rhs   &emsp;         除法</li>
      <li>       __floordiv__(self,rhs) &emsp;     self //rhs   &emsp;         地板除</li>
      <li>       __mod__(self,rhs)    &emsp;       self % rhs    &emsp;     取模(求余)</li>
       <li>      __pow__(self,rhs)    &emsp;       self **rhs     &emsp;      幂运算</li>
            
</ul>

```py


    def __add__(self, right):
        """Overrides the + operator."""
        return Complex(self.real + right.real, 
                       self.imaginary + right.imaginary)
                       
                       
    def __iadd__(self, right):
        """Overrides the += operator."""
        self.real += right.real
        self.imaginary += right.imaginary
        return self
```

## 数据类
利用@dataclass 修饰器，定义类变量要有冒号连接的注释ClassVar[]，表明数据类型。 <br>  变量定义不在__init__中，实例变量要用冒号标明类型 <br> 会自动生成__repr__函数
```py
from dataclasses import dataclass
from typing import ClassVar, List

@dataclass(order=True)
# 可以自动定义大于和小于
class Card:
    FACES: ClassVar[List[str]] = ['Ace', '2', '3', '4', '5', '6', '7', 
                                  '8', '9', '10', 'Jack', 'Queen', 'King']
    SUITS: ClassVar[List[str]] = ['Hearts', 'Diamonds', 'Clubs', 'Spades']

    face: str
    suit: str

    @property
    def image_name(self):
        """Return the Card's image file name."""
        return str(self).replace(' ', '_') + '.png'

    def __str__(self):
        """Return string representation for str()."""
        return f'{self.face} of {self.suit}'
    
    def __format__(self, format):
        """Return formatted string representation."""
        return f'{str(self):{format}}'
```


## 名称和作用域
```py
Local
Global
Built-In

Enclosing Namespace

# LEGB rule 寻找命名的顺序
```











































































