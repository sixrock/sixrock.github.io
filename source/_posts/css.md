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
## 后代选择器
### 通过依据元素在其位置的上下文关系来定义样式，你可以使标记更加简洁
```html
h2 strong {color: blue;}
<p>The strongly emphasized word in this paragraph is<strong>red</strong>.</p>
<h2>This subhead is also red.</h2>
<h2>The strongly emphasized word in this subhead is<strong>blue</strong>.</h2>
```
## 子元素选择器
```html
<style>
h1 > strong {color:red;}
</style>
<h1>This is <strong>very</strong> <strong>very</strong> important.</h1>
<h1>This is <em>really <strong>very</strong></em> important.</h1>
```
## 相邻兄弟选择器
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
## id选择器
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
## 类选择器
### 类选择器以一个点号显示：
```
.classname{}
```
## 属性选择器
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
### 外部样式表
```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
</head>
```
### 内部样式表
```html
<head>
<style type="text/css">
  hr {color: sienna;}
  p {margin-left: 20px;}
  body {background-image: url("images/back40.gif");}
</style>
</head>
```
### 内联样式
```html
<p style="color: sienna; margin-left: 20px">
This is a paragraph
</p>
```