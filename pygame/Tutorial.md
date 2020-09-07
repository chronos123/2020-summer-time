## 参考网站
https://blog.csdn.net/enderman_xiaohei/article/details/87708373



## First game window

pygame.display.update 只改变要改的
pygame.display.flip 刷新全屏
```py
import pygame

pygame.init()

screen = pygame.display.set_mode(800, 600)

while True:
    pass
```

## 关闭窗口
```py
import pygame

pygame.init()

size = width, height = 800, 600

screen = pygame.display.set_mode(size)

running = True

while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
```

## Tilte Icon Logle





















