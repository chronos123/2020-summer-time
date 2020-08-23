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

#### 画成柱形图
```py
blob = TextBlob(Path('RomeoAndJuliet.txt').read_text(encoding='UTF-8'))
from nltk.corpus import stopwords
stop_words = stopwords.words('english')

items = blob.word_counts.items()
# 统计单词个数

items = [item for item in items if item[0] not in stop_words]
# 除去不关键的词

from operator import itemgetter
# 选择元组中的排序量
sorted_items = sorted(items, key=itemgetter(1), reverse=True)

top20 = sorted_items[1:21]
# '’' 算一个单词

df = pd.DataFrame(top20, columns=['word', 'count'])  
# 变为dataframe

%matplotlib inline
axes = df.plot.bar(x='word', y='count', legend=False)

import matplotlib.pyplot as plt

plt.gcf().tight_layout()
# gcf: get current figure
```

#### 画成单词云
```py
from pathlib import Path
text = Path('RomeoAndJuliet.txt').read_text()

import imageio
mask_image = imageio.imread('mask_heart.png')


from wordcloud import WordCloud   
wordcloud = WordCloud(width=1000, height=1000, 
    colormap='prism', mask=mask_image, background_color='white')
# 定义单词云

wordcloud = wordcloud.generate(text)
# 生成单词云

wordcloud = wordcloud.to_file('RomeoAndJulietHeart.png')
# 存到文件里

%matplotlib inline
import matplotlib.pyplot as plt
plt.imshow(wordcloud)
# 显示图像
```















































