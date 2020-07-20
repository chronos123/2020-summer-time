## Dictionary 用法

### Key

#### The key must be an immutable type (str, tupple, list of str, int, float) and the key must be unique

```py
states = {'a': 1, 
          'b': 2,
          'c': 3}
len(states) 
```

#### Output

```py
3
```

### Manipulate dictionary

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

# search a key 
'III' in roman_numerals

'III' not in roman_numerals
```


### Dictionary 各种函数（method）
#### Get the key and value
```py

months = {'January': 1, 'February': 2, 'March': 3}

months.keys() 

month_view = months.keys()

months.values()
```
#### Create list of dictionary
```py
list(month.keys())
list(month.values())
list(month.items())
```

### Comparison
#### Input
```py
country_capitals1 = {'Belgium': 'Brussels', 'Haiti': 'Port-au-Prince'}
                        
country_capitals3 = {'Haiti': 'Port-au-Prince', 'Belgium': 'Brussels'}

country_capitals1 == country_capitals3
```   

#### Output
```py
True
```

### Use an empty diactionary
```py
text = ('this is sample text with several words '
        'this is more sample text with some different words')

word_counts = {}

# count occurrences of each unique word
for word in text.split(' '):
    if word in word_counts: 
        word_counts[word] += 1  # update existing key-value pair
    else:
        word_counts[word] = 1  # insert new key-value pair

print(f'{"WORD":<12}COUNT')

for word, count in sorted(word_counts.items()):
    print(f'{word:<12}{count}')

print('\nNumber of unique words:', len(word_counts))
```

### Collections

#### Counter

```py
from collections import Counter
text = ('this is sample text with several words '
        'this is more sample text with some different words')
counter = Counter(text.split())
# dictionary
```
example
```py
import random
from collections import Counter

list1 = [random.randrange(1, 6) for i in range(50)]
counter = Counter(list1)

for number, frequency in sorted(counter.items()):
    print(f'{number:>1}: {frequency:>12}')
```

### Update method

```py
country_codes = {}
country_codes.update({'South Africa': 'za', 'I': 1})
# can also pass in a list of two elements tuple

country_codes.update(Australia='ar')

country_codes.update(Australia='au')
```


### Dictionary comprehension

```py
months = {'January': 1, 'February': 2, 'March': 3}
months2 = {number: name for name, number in months.items()}

grades = {'Sue': [98, 87, 94], 'Bob': [84, 95, 91]}
grades2 = {k: sum(v) / len(v) for k, v in grades.items()}

{number: number ** 3 for number in range(1, 6)}
```





































