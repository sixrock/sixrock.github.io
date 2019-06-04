# css
- CSS 指层叠样式表 (Cascading Style Sheets)
- 样式定义如何显示 HTML 元素
- 样式通常存储在样式表中
- 把样式添加到 HTML 4.0 中，是为了解决内容与表现分离的问题
- 外部样式表可以极大提高工作效率
- 外部样式表通常存储在 CSS 文件中
- 多个样式定义可层叠为一
## 样式表允许以多种方式规定样式信息。样式可以规定在单个的 HTML 元素中，在 HTML 页的头元素中，或在一个外部的 CSS 文件中。甚至可以在同一个 HTML 文档内部引用多个外部样式表
## 一般而言，所有的样式会根据下面的规则层叠于一个新的虚拟样式表中，其中数字 4 拥有最高的优先权。
- 浏览器缺省设置
- 外部样式表
- 内部样式表（位于 <head> 标签内部）
- 内联样式（在 HTML 元素内部）
## CSS 规则由两个主要的部分构成：选择器，以及一条或多条声明
`
selector {declaration1; declaration2; ... declarationN }
`
### 选择器通常是您需要改变样式的 HTML 元素
### 每条声明由一个属性和一个值组成
## 值的不同写法和单位
除了英文单词 red，我们还可以使用十六进制的颜色值 #ff0000：
`
p { color: #ff0000; }
`
为了节约字节，我们可以使用 CSS 的缩写形式：
`
p { color: #f00; }
`
我们还可以通过两种方法使用 RGB 值：
```
p { color: rgb(255,0,0); }
p { color: rgb(100%,0%,0%); }
```
### 每行只描述一个属性
```
p {
  text-align: center;
  color: black;
  font-family: arial;
}
```
---
## **选择器**
---
## 1.后代选择器
### 通过依据元素在其位置的上下文关系来定义样式，你可以使标记更加简洁
```html
h2 strong {color: blue;}
<p>The strongly emphasized word in this paragraph is<strong>red</strong>.</p>
<h2>This subhead is also red.</h2>
<h2>The strongly emphasized word in this subhead is<strong>blue</strong>.</h2>
```
## 2.子元素选择器
```html
<style>
h1 > strong {color:red;}
</style>
<h1>This is <strong>very</strong> <strong>very</strong> important.</h1>
<h1>This is <em>really <strong>very</strong></em> important.</h1>
```
## 3.相邻兄弟选择器
```html
<head>
<style>
li + li {font-weight:bold;}
</style>
<body>
<div>
  <ul>
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
  </ul>
  <ol>
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
  </ol>
</div>
</body>
```
## 4.id选择器

### id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式
### id 选择器以 "#" 来定义
```html
<head>
<style>
#red {color:red;}
#green {color:green;}
</style>
</head>
<body>
<p id="red">这个段落是红色。</p>
<p id="green">这个段落是绿色。</p>
</body>
```
## 5.类选择器
### 类选择器以一个点号显示：
```
.classname{}
```
## 6.属性选择器
```html
<head>
<style type="text/css">
[align]
{
color:red;
}
</style>
</head>

<body>
<p align="left">dfsahfkjaksfhieajkgfhjsdahfoi</p>
</body>
```
### 属性：
- [attribute]	用于选取带有指定属性的元素
- [attribute=value]	用于选取带有指定属性和值的元素
- [attribute~=value]	用于选取属性值中包含指定词汇的元素
- [attribute|=value]	用于选取带有以指定值开头的属性值的元素，该值必须是整个单词
- [attribute^=value]	匹配属性值以指定值开头的每个元素
- [attribute$=value]	匹配属性值以指定值结尾的每个元素
- [attribute*=value]	匹配属性值中包含指定值的每个元素
---
## 样式表

### 1.外部样式表
```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
</head>
```
### 2.内部样式表
```html
<head>
<style type="text/css">
  hr {color: sienna;}
  p {margin-left: 20px;}
  body {background-image: url("images/back40.gif");}
</style>
</head>
```
### 3.内联样式
```html
<p style="color: sienna; margin-left: 20px">
This is a paragraph
</p>
```
## css背景
---
### **背景色**
可以使用 background-color 属性为元素设置背景色。这个属性接受任何合法的颜色值

这条规则把元素的背景设为绿色：

`
p {background-color:green}
`

如果希望背景色从元素中的文本向外有所延伸，只需要增加一些内边距：

`
p {background-color:green padding:20px}
`

可以为所有的元素设置背景颜色

background-color 不能继承，其默认值是 transparent
### **背景图像**
要把图像放入背景，需要使用 background-image 属性

background-image 属性的默认值是 none，表示背景上没有放置任何图像

如果需要设置一个背景图像，必须为这个属性设置一个 URL 值

```
body {background-image: url(Picture address);}
```

为一个段落应用了一个背景，而不会对文档的其他部分应用背景

```
p.flower {background-image: url(Picture address);}
```

也可以为行内元素设置背景图像，下面的例子为一个链接设置了背景图像

```
a.radio {background-image: url(picture address)}
```
background-image 也不能继承。事实上，所有背景属性都不能继承
### **重复背景**
如果需要在页面上对背景图像进行平铺，可以使用 background-repeat 属性

属性值 repeat 导致图像在水平垂直方向上都平铺，就像以往背景图像的通常做法一样。repeat-x 和 repeat-y 分别导致图像只在水平或垂直方向上重复，no-repeat 则不允许图像在任何方向上平铺
```
body
  { 
  background-image: url(picture address);
  background-repeat: repeat-y;
  }
```
### **背景定位**
可以利用 background-position 属性改变图像在背景中的位置
### 关键字
可以使用一些关键字：top、bottom、left、right 和 center
```
p
  { 
    background-image:url(picture address);
    background-repeat:no-repeat;
    background-position:top;
  }
```
下面是等价的位置关键字：
单一关键字|等价关键字
--|:--:|--
center|center center
top|top center
bottom|bottom center
right|right center
left|left center
百分数值
用百分数值将图像在其元素中居中
```
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50% 50%;
  }
```
如果图像位于 0% 0%，其左上角将放在元素内边距区的左上角。如果图像位置是 100% 100%，会使图像的右下角放在右边距的右下角

把一个图像放在水平方向 2/3、垂直方向 1/3 处
```
body
  { 
    background-image:url(picture address);
    background-repeat:no-repeat;
    background-position:66% 33%;
  }
```
background-position 的默认值是 0% 0%，在功能上相当于 top left。这就解释了背景图像为什么总是从元素内边距区的左上角开始平铺，除非设置了不同的位置值

长度值

设置值为 50px 100px，图像的左上角将在元素内边距区左上角向右 50 像素、向下 100 像素的位置上
```
body 
  {
    background-image:url(picture address);
    background-repeat:no-repeat;
    background-position:50px 100px;
  }
```
### 背景关联
如果文档比较长，那么当文档向下滚动时，背景图像也会随之滚动。当文档滚动到超过图像的位置时，图像就会消失

您可以通过 background-attachment 属性防止这种滚动。通过这个属性，可以声明图像相对于可视区是固定的
```
body
  {
    background-image:url(picture address);
    background-repeat:no-repeat;
    background-attachment:fixed;
  }
```

### CSS背景属性
属性|描述
--:|:--:|
background|简写属性将背景设置在一个声明中
background-attachment|将背景是否固定或是随着页面的其余部分进行滚动
background-color|设置元素的背景颜色
background-image|把图像设置背景
background-position|设置背景图像的起始位置
background-repeat|设置背景图像是否及如何重复