## 段落标签
```py
 <h1> </h1>  <h6> </h6>  标题

 <p> </p>  段落
 
 <span> </span> 组合行内元素
```

## 粗体和斜体
```py
斜体：
<em> </em> 动词斜体强调  special meaning

<i> </i>  visually italics 专有名词斜体

粗体：
<strong> </stromg>  紧急，强调  special meaning

<b> </b>  形式粗体
```

## 列表
```py
<li> </li> 列表每行

<ul> </ul> unordered lsit
'''
列子：
<ul>
  <li> </li>
  <li> </li>
</ul>
'''

<ol> </ol> ordered list

defination list
<dl>
    <dt> term </dt>
        <dd> defination<dd>
        <dd> </dd>
    <dt> term2 </dt>
        <dd> </dd>
</dl>
```

## 引用

```py
<cite> people </cite> 引用

一块引用:
<blockquote>  
  <p>
  
  </p>
  <cite>    </cite>
</blockquote>



<q> </q>  段内引用
```

## 类别
inline 和 block-level 标签

## 时间
```py
<time> </time>

<time datetime="2015-05-08 19:15:22-20:30:15">8 May 2020 </time>
```


## 转义字符
1. &copy;

2. &trade;

3. &star;
```py
<code>   </code> 显示代码

转义字符
< : &lt;
> : &gt;
& : &amp;
换行不拆开 : &nbsp;

1. &copy;
2.&trade;
3.&star;
```


## 缩进排版
```py
<br>  (无结束字符)换行符

<pre>  </pre>  插入缩进(format)
```

## 上下标
mathML 处理数学公式
```py
<sub> </sub>  下标

<sup>  </sup>  上标

<small> </small>  不重要的意义 special meaning （例如日期，参考文献）
```

## 注释
```py
<!-- 开始
-->  结束
```

## 超链接
```py
<a href="Page.html">Link </a>

url:
../  向上寻找

设立主页
<nav role="navigation" aria_role="main menu">  
   <a href="\"> home </a>
   <a href="\page1"> page1 </a>
</nav>

设置relative url
<footer>
   <a href="/about/page1"> page1 </a>
   <a href>="/about/page2"> page2 </a>
</footer>
```
## 图片

#### &lt;img&gt;
```py
<img src="" alt="" width="" height="" srcset="" sizes="">  
src            图片的链接
alt substute   图片的替代
width          宽度（数字）
height         长度（数字）

srcset = "链接 2x,链接 3x,链接 4x"  用来根据显示器像素密度选择图片像素


srcset = "链接 480w,链接 960w,链接 1440w, 链接 1920w" 根据显示器宽度选择图片大小

sizes = "(max-width: 480px) 240px"  选择不同情况下图片大小
```
#### &lt;picture&gt
用来在不同屏幕，不同设备上显示不同图片
```py
<picture>
    <source media="(min-width: 600px)" 
    srcset="">
    设备满足时第一个图片加载，不满足时第二个加载:用来加载不同图片
    <source srcset="">
    
    <img src=""
    alt=""
    width="" height="">
    
</picture>
```
#### &lt;figure&rt; 和 &lt;figcaption&rt;
给图片附上配图文字
```py
<figure>
    <img>
    
    <figcaption>
    </figcaption>
</figure>
```

## 音频
#### 函数
```py
controls loop autoplay
```
#### 应用
```py
<audio controls src=""> </audio>

<audio controls loop autoplay>
    <source src="" type="">
    <source src="" type=""; codec>
    
    Sorry you browser doesn't support 格式不支持显示文本
</audio>
```

## 视频
需要进一步了解
```py
<video src="" controls> </video>

<video controls>
    <source src="" type="">
    <source src="" type="">
    
    <track src="" 通常为vtt格式字幕
    kind="captions"
    label="english"  显示标签
    srclang="en"  文本语言
    default>
    
    加入不同字幕
    <track src="" 通常为vtt格式字幕
    kind="subtitles"  还有dexcriptions 描述 chapters 换节
    label="english"
    srclang="en"
    default>
   
    
  <p> this is a video </p> 格式不支持显示文本
</video>
```

## 嵌入embed
```py
<iframe width="" height="" src="" frameboder="" allow="" allowfullscreen>

</iframe>
```




















