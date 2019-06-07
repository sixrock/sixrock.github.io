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
## 文本
### 缩进文本
 text-indent 属性，该属性可以方便地实现文本缩进

 通过使用 text-indent 属性，所有元素的第一行都可以缩进一个给定的长度，甚至该长度可以是负值

 这个属性最常见的用途是将段落的首行缩进，下面的规则会使所有段落的首行缩进 5 em
 ```
 p {text-indent:5em;}
 ```
 不过在为 text-indent 设置负值时要当心，如果对一个段落设置了负值，那么首行的某些文本可能会超出浏览器窗口的左边界。为了避免出现这种显示问题，建议针对负缩进再设置一个外边距或一些内边距：
 ```
 p {text-indent:5em; padding:5em;}
 ```
 **使用百分比**
text-indent 可以使用所有长度单位，包括百分比值

百分数要相对于缩进元素父元素的宽度。换句话说，如果将缩进值设置为 20%，所影响元素的第一行会缩进其父元素宽度的 20%

在下例中，缩进值是父元素的 20%，即 100 个像素：
```html
div {width: 500px;}
p {text-indent: 20%;}

<div>
<p>这是一个P标签</p>
</div>
```
**继承**
```html
div#outer {width: 500px;}
div#inner {text-indent: 10%;}
p {width: 200px;}

<div id="outer">
<div id="inner">some text. some text. some text.
<p>this is a paragragh.</p>
</div>
</div>
```
以上标记中的段落也会缩进 50 像素，这是因为这个段落继承了 id 为 inner 的 div 元素的缩进值

### **水平对齐**

text-align 是一个基本的属性，它会影响一个元素中的文本行互相之间的对齐方式。它的前 3 个值相当直接，不过第 4 个和第 5 个则略有些复杂

值 left、right 和 center 会导致元素中的文本分别左对齐、右对齐和居中

水平对齐的属性：justify

### **字间隔**

word-spacing 属性可以改变字（单词）之间的标准间隔。其默认值 normal 与设置值为 0 是一样的

word-spacing 属性接受一个正长度值或负长度值。如果提供一个正长度值，那么字之间的间隔就会增加。为 word-spacing 设置一个负值，会把它拉近：

p.spread {word-spacing: 30px;}
p.tight {word-spacing: -0.5em;}
```html
<p class="spread">
字与字之间的间距为50px
</p>

<p class="tight">
字与字之间重叠半个字的长度
</p>
```
### **字符转换**
text-transform 属性处理文本的大小写
- none(对文本不做任何改动)
- uppercase(全大写)
- lowercase(全小写)
- capitalize(单词的首字母大写)
```
h1 {text-transfrom:uppercass}
```
优点：
- 只需简单规则来修改无须改变单词的本身
- 方便后期更改
### **文本装饰**

text-decoration 属性

text-decoration 有 5 个值：
- none
- underline
- overline
- line-through
- blink

**underline** 会对元素加下划线，就像 HTML 中的 U 元素一样。

**overline** 的作用恰好相反，会在文本的顶端画一个上划线。

**line-through** 则在文本中间画一个贯穿线，等价于 HTML 中的 S 和 strike 元素。

**blink** 会让文本闪烁。
none 值会关闭原本应用到一个元素上的所有装饰
```
a {text-decoration:none}
```
还可以在一个规则中结合多种装饰。如果希望所有超链接既有下划线，又有上划线，则规则如下
```
a {text-decoration:underline overline;}
```
**处理空白符**

white-space 属性会影响到用户代理对源文档中的空格、换行和 tab 字符的处理
```html
P{width-space:nomal;}

<p>This     paragraph has    many
    spaces           in it.</p>
```
当 white-space 属性设置为 normal 时，会合并所有的空白符，并忽略换行符
```html
P{width-space:pre;}

<p>This     paragraph has    many
    spaces           in it.</p>
```
当write-space 属性设置为 pre 时，浏览器不会合并空白符，也不会忽略换行符
```
P{write-space:nowrap;}

<p>This     paragraph has    many
    spaces           in it.</p>
<p>This     paragraph has    many
    spaces           in it.</p>
<p>This     paragraph has    many
    spaces           in it.</p>    
```
它会防止元素中的文本换行，除非使用了一个 br 元素
```html
p {write-space:pre-warp;}
<p>
dsfaf dsf af asfgrh rh tr  hfdg r grt 
gfdg gddfg dg tr
tgr hh   trhy uj
ju yhtr 
gtrrht hth  eh dsght d wgw   y gdsga a grw fgsr
</p>
```
当 white-space 属性设置为 pre-wrap 时，浏览器不仅会保留空白符并保留换行符，还允许自动换行
```
p {write-space:pre-line;}
<p>
保留  换行  符
允许自动换行
合并  空格
</p>
```
当 white-space 属性设置为 pre-line 时，浏览器会保留换行符，并允许自动换行，但是会合并空白符

**总结**
值|空白符|换行符|自动换行
--:|:--:|:--:|:--
pre-line|合并|保留|允许
normal|合并|忽略|允许
nowrap|合并|忽略|不允许
pre|保留|保留|不允许
pre-wrap|保留|保留|允许
**文本方向**

direction 属性影响块级元素中文本的书写方向、表中列布局的方向、内容水平填充其元素框的方向、以及两端对齐元素中最后一行的位置
```
div {perection:rtl}
<div>
发生个梵蒂冈讽德诵功梵蒂冈
</div>
```
对于行内元素，只有当 unicode-bidi 属性设置为 embed 或 bidi-override 时才会应用 direction 属性

## CSS字体
---
### CSS 字体属性定义文本的字体系列、大小、加粗、风格（如斜体）和变形
除了各种特定的字体系列外，CSS 定义了 5 种通用字体系列：

- Serif 字体
- Sans-serif 字体
- Monospace 字体
- Cursive 字体
- Fantasy 字体

**通用字体**

如果你希望文档使用一种 sans-serif 字体，但是你并不关心是哪一种字体，以下就是一个合适的声明：
```
p {font-family:sans-serif;}
```
这样就会从 sans-serif 字体系列中选择一个字体（如 Helvetica），并将其应用到 body 元素。因为有继承，这种字体选择还将应用到 body 元素中包含的所有元素，除非有一种更特定的选择器将其覆盖

**指定字体**

通过 font-family 属性设置更具体的字体
```
h1 {font-family:georgia;}
```
如果用户代理上没有安装 Georgia 字体，就只能使用用户代理的默认字体来显示 h1 元素

我们可以通过结合特定字体名和通用字体系列来解决这个问题：
```
h1 {font-family:georgia, serif;}
```
**字体风格**

font-style 属性最常用于规定斜体文本。

该属性有三个值：

- normal - 文本正常显示
- italic - 文本斜体显示
- oblique - 文本倾斜显示
```
p {font-style:normal;}
p {font-style:italic;}
p {font-style:oblique;}
```
斜体（italic）是一种简单的字体风格，对每个字母的结构有一些小改动，来反映变化的外观。与此不同，倾斜（oblique）文本则是正常竖直文本的一个倾斜版本

**字体变形**
font-variant 属性可以设定小型大写字母

小型大写字母不是一般的大写字母，也不是小写字母，这种字母采用不同大小的大写字母
```
p {font-variant:small-caps}
```
**字体加粗**

font-weight 属性设置文本的粗细。

使用 bold 关键字可以将文本设置为粗体

关键字 100 ~ 900 为字体指定了 9 级加粗度。如果一个字体内置了这些加粗级别，那么这些数字就直接映射到预定义的级别，100 对应最细的字体变形，900 对应最粗的字体变形。数字 400 等价于 normal，而 700 等价于 bold

**字体大小**

font-size 属性设置文本的大小

使用像素设置字体大小
```
p {font-size:100px}
```
使用em来设置字体大小
```
p {font-size:3em}
```
可以使用下面这个公式将像素转换为 em：pixels/16=em

## **CSS链接**
---
链接的四种状态
- a:link - 普通的、未被访问的链接
- a:visited - 用户已访问的链接
- a:hover - 鼠标指针位于链接的上方
- a:active - 链接被点击的时刻

当为链接的不同状态设置样式时，请按照以下次序规则：

a:hover 必须位于 a:link 和 a:visited 之后
a:active 必须位于 a:hover 之后
```
a:link {color:red}
a:visited {color:green}
a:hover {color:blue}
a:active {color:yellow}
```
**文本修饰**

text-decoration 属性大多用于去掉链接中的下划线
```
a:link {text-decoration:none;}
a:visited {text-decoration:none;}
a:hiver {text-decoration:underline;}
a:active {text-decoration:underline;}
```
**背景颜色**

background-color 属性规定链接的背景色
```
a:link {background-color:red;}
a:visited {background-color:green;}
a:hover {background-color:yellow;}
a:active {background-color:red;}
```
## **CSS列表**
**列表类型**

要修改用于列表项的标志类型，可以使用属性 list-style-type：
```
ul {list-style-type:} 
```
值|属性|
--:|:--
none|无标记。
disc|默认。标记是实心圆。
circle|标记是空心圆。
square|标记是实心方块。
decimal|标记是数字。
decimal-leading-zero|0开头的数字标记。(01, 02, 03, 等。)
lower-roman|小写罗马数字(i, ii, iii, iv, v, 等。)
upper-roman|大写罗马数字(I, II, III, IV, V, 等。)
lower-alpha|小写英文字母The marker is lower-alpha (a, b, c, d, e, 等。)
upper-alpha|大写英文字母The marker is upper-alpha (A, B, C, D, E, 等。)
lower-greek|小写希腊字母(alpha, beta, gamma, 等。)
lower-latin|小写拉丁字母(a, b, c, d, e, 等。)
upper-latin|大写拉丁字母(A, B, C, D, E, 等。)
**列表项图像**
```
li {list-style-image:url(picture address)}
```
**列表标签位置**
- list-style-position:outside在文本外面
- list-style-position:inside在文本里面
```
li {list-style-position:outside}
```
**简写列表样式**
```
li {list-style:url(picture address) square inside}
```
**总结**

属性|描述
--:|:--
list-style|简写属性
list-style-image|将图像设置为列表标志
list-style-position|设置标签的位置
list-style-type|设置列表项标志的类型