## 有名称元组
```py
from collections import namedtuple
Card = namedtuple('Card', ['face', 'suit'])
card = Card(face='Ace', suit='Spades')

values = ['Queen', 'Hearts']
card = Card._make(values)

card._asdict()
# OrderedDict([('face', 'Queen'), ('suit', 'Hearts')])
```
