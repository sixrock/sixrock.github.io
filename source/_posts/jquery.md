---
title: jquery
date: 2019-06-07 15:42:03
tags: 
---
# jQuery
## jQuery语法
### jQuery 语法是为 HTML 元素的选取编制的，可以对元素执行某些操作。

基础语法是：$(selector).action()
- 美元符号定义 jQuery
- 选择符（selector）“查询”和“查找” HTML 元素
- jQuery 的 action() 执行对元素的操作

jQuery 元素选择器

jQuery 使用 CSS 选择器来选取 HTML 元素。

- $("p") 选取 &lt;p> 元素。
- $("p.intro") 选取所有 class="intro" 的 &lt;p> 元素。
- $("p#demo") 选取所有 id="demo" 的 &lt;p> 元素。

jQuery 属性选择器
jQuery 使用 XPath 表达式来选择带有给定属性的元素。

- $("[href]") 选取所有带有 href 属性的元素。
- $("[href='#']") 选取所有带有 href 值等于 "#" 的元素。
- $("[href!='#']") 选取所有带有 href 值不等于 "#" 的元素。
- $("[href$='.jpg']") 选取所有 href 值以 ".jpg" 结尾的元素。

jQuery CSS 选择器

把所有 p 元素的背景颜色更改为红色：
```
$("p").css("background-color","red")
```
语法|描述
--:|:--
$(this)|当前HTML元素
$("p")|所有p元素
$("p.intro")|所有class="intro"的&lt;p>元素
$(".intro")|所有class="intro"的元素
$("#intro")|所有id="intro"的元素
$("ul li:first")|每个&lt;ul>的第一个&lt;li>元素
$("[href$='.jpg']")|所有的带有href属性并以.jpg结尾的元素
$("div#intro .head")|id=intro的&lt;div>中的所有class="head"的元素
