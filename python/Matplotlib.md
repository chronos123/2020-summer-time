### Matplotlib documentation

https://matplotlib.org/tutorials/index.html

### Numpy documentation

https://numpy.org/doc/1.19/user/quickstart.html

### Seaborn documentation

http://seaborn.pydata.org/tutorial.html#

### Seaborn 建图例子

```py
import matplotlib.pyplot as plt
import random
import seaborn as sns
import numpy as np


rolls = [random.randrange(1, 7) for i in range(600)]

values, frequencies = np.unique(rolls, return_counts=True)

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
 
 
 ### Dynamic Visualization
 FPS —— frames per second
 ```py
 from matplotlib import animation
import matplotlib.pyplot as plt
import random
import seaborn as sns
import sys

def update(frame_number, rolls, faces, frequencies):
    """Configures bar plot contents for each animation frame."""
    for i in range(rolls):
        # roll die and update frequencies
        frequencies[random.randrange(1, 7) - 1] += 1
        
    # reconfigure plot for updated die frequencies
    plt.cla()  # clear old contents contents of current Figure
    axes = sns.barplot(faces, frequencies, palette='bright')  # new bars
    axes.set_title(f'Die Frequencies for {sum(frequencies):,} Rolls')
    axes.set(xlabel='Die Value', ylabel='Frequency')  
    axes.set_ylim(top=max(frequencies) * 1.10)  # scale y-axis by 10%

    # display frequency & percentage above each patch (bar)
    for bar, frequency in zip(axes.patches, frequencies):
        text_x = bar.get_x() + bar.get_width() / 2.0  
        text_y = bar.get_height() 
        text = f'{frequency:,}\n{frequency / sum(frequencies):.3%}'
        axes.text(text_x, text_y, text, ha='center', va='bottom')

# read command-line arguments for number of frames and rolls per frame
number_of_frames = int(sys.argv[1])  
rolls_per_frame = int(sys.argv[2]) 

sns.set_style('whitegrid')  # white background with gray grid lines
figure = plt.figure('Rolling a Six-Sided Die')  # Figure for animation
values = list(range(1, 7))  # die faces for display on x-axis
frequencies = [0] * 6  # six-element list of die frequencies

# configure and start animation that calls function update
die_animation = animation.FuncAnimation(
    figure, update, repeat=False, frames=number_of_frames, interval=33,
    fargs=(rolls_per_frame, values, frequencies))

plt.show()  # display window
 ```
 
 ### image
 
 ```py
 import matplotlib.image as mpimg
 import matplotlib.pyplot as plt
 
 figure, axes_list = plt.subplots(nrows=4, ncols=13)
 # 建立一个图像区域， 返回一个元组, list为二维
 
figure.set_figwidth(16)
figure.set_figheight(9)
# 设立图像区域大小

for axes in axes_list.ravel():
# ravel降维对numpy array
    axes.get_xaxis().set_visible(False)
    axes.get_yaxis().set_visible(False)
    # 隐藏坐标轴
    image_name = deck_of_cards.deal_card().image_name
    # 调用图像名字
    img = mpimg.imread(str(path.joinpath(image_name).resolve()))
    # reslove从path实例中找到完整的路径，读取图片
    axes.imshow(img)
    # 在坐标轴上放置图片

# 已经可以展示一组牌，有很多空白的地方

figure.tight_layout()
# 减少空白的地方
 ```
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
