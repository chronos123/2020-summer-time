## 可读性判断
notdalechall_count 越高越不易读懂
polysyblword_count 越高越不易读懂

flesch_score 90+ 易懂  30以下不易懂

smog_score 几年教育
dalechall_score 读懂的年纪数
```py
from pathlib import Path
text = Path('RomeoAndJuliet.txt').read_text()

from textatistic import Textatistic
readability = Textatistic(text)
%precision 3
readability.dict()
```
