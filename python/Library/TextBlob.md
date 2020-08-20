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
blob.sentiment.polarity
blob.sentiment.subjectivity
# 判断主观性和正面反面

blob.detect_language()

chinese = blob.translate(to='zh')
```

##  NaiveBayesAnalyzer分析器
```py
from textblob.sentiments import NaiveBayesAnalyzer

blob = TextBlob(text, analyzer=NaiveBayesAnalyzer())
blob.sentiment
# sentiment分析方法不同
```

## Word类
```py
from textblob import Word

index = Word('index')
index.pluralize()
cacti = Word('cacti')
cacti.singularize()
# 单数复数转换

animals = TextBlob('dog cat fish bird').words
animals.pluralize()

word.spellcheck()
# 检查拼写

word.correct()
# 用概率最大的替代

word.stem()
# 词根

word.lemmatize()
# 原词

blob = TextBlob(Path('RomeoAndJuliet.txt').read_text(encoding='UTF-8'))
blob.word_counts()
# 单词计数
```




































































