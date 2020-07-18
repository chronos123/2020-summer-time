## some trick of dictionary

### key

the key must be an immutable type (str, tupple, list of str, int, float) and the key must be unique

```py
states = {'a': 1, 
          'b': 2,
          'c': 3}
len(states) 
```

输出

```py
3
```

### manipulate dictionary

```py
roman_numerals = {'I': 1, 'II': 2, 'III': 3, 'V': 5, 'X': 100}

roman_numerals['X'] = 10


# add a pair
roman_numerals['L'] = 50


# remove a pair
del roman_numerals['III']

roman_numerals.pop('X')

# access a key

roman_numerals['V']

roman_numerals.get('III', 'III not in dictionary')


'III' in roman_numerals

'III' not in roman_numerals
```









