## spacy
named entity
```py
import spacy
nlp = spacy.load('en') 

document = nlp('In 1994, Tim Berners-Lee founded the ' + 
    'World Wide Web Consortium (W3C), devoted to ' +
    'developing web technologies')
    

for entity in document.ents:
    print(f'{entity.text}: {entity.label_}')
# document.ents(tuple) 


from pathlib import Path
document1 = nlp(Path('RomeoAndJuliet.txt').read_text())
document2 = nlp(Path('EdwardTheSecond.txt').read_text())


document1.similarity(document2)
# 比较文件相似性 spacy doc 对象  比较词频等
```
