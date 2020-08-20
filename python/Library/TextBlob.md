# textblob库
## TextBlob类
```py
from textblob import TextBlob
text = 'Today is a beautiful day. Tomorrow looks like bad weather.'
blob = TextBlob(text)

blob.sentences
blob.words

blob.tags
# 在www.clips.uantwerpen.be/pages/MBSP-tags插标签意义

blob.noun_phrases

blob.sentiment
# 判断主观客观
```
