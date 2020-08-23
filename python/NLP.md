## 书库
www.gutenberg.org

## 删去无关词
```py
from nltk.corpus import stopwords
stops = stopwords.words('english')

from textblob import TextBlob
blob = TextBlob('Today is a beautiful day.')
[word for word in blob.words if word not in stops]
```
## 将词汇频率可视化
```py

```
