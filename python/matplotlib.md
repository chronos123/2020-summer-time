### matplotlib documentation

https://matplotlib.org/tutorials/index.html

### numpy documentation

https://numpy.org/doc/1.19/user/quickstart.html

### seaborn documentation

http://seaborn.pydata.org/tutorial.html#

### seaborn 建图例子

```py
sns.set_style('whitegrid')

axes = sns.barplot(x=values, y=frequencies, palette='bright')

axes.set_title(title)


axes.set(xlabel='Die Value', ylabel='Frequency')  


axes.set_ylim(top=max(frequencies) * 1.20)

for bar, frequency in zip(axes.patches, frequencies):
    text_x = bar.get_x() + bar.get_width() / 2.0
    text_y = bar.get_height() 
    text = f'{frequency:,}\n{frequency / len(rolls):.2%}'
    axes.text(text_x, text_y, text, 
              fontsize=11, ha='center', va='bottom')
 ```
