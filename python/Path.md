## path类
```py
from pathlib import Path
path = Path('.').joinpath('card_images')
# 从当前文件找下去

path.resolve()
# 找到完整路径

str(path.resolve())
# 可传参的路径
```
