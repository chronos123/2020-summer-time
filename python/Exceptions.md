## 类型
```py
ZeroDivisionError 
ValueError 
```
## 处理
```py
# dividebyzero.py
"""Simple exception handling example."""

while True:
    # attempt to convert and divide values
    try:
        number1 = int(input('Enter numerator: '))
        number2 = int(input('Enter denominator: '))
        result = number1 / number2
    except ValueError:  # tried to convert non-numeric value to int
        print('You must enter two integers\n')
    except ZeroDivisionError:  # denominator was 0
        print('Attempted to divide by zero\n')
    else:  # executes only if no exceptions occur
        print(f'{number1:.3f} / {number2:.3f} = {result:.3f}')
        break  # terminate the loop
```
## Finally 语句
Finally 语句总是会执行
