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
---
## jQuery事件
jQuery事件函数
jQuery 事件处理方法是 jQuery 中的核心函数。

事件处理程序指的是当 HTML 中发生某些事件时所调用的方法。术语由事件“触发”（或“激发”）经常会被使用。

通常会把 jQuery 代码放到 &lt;head>部分的事件处理方法中：
```html
<html>
<head>
<script type="text/javascript" src="jquery.js">
<script type="text/javascript">
$(document).ready(function(){
  $("button").click(function(){
    $("p").hide();
  });
});
</script>

</head>

<body>
<h2>This is a heading</h2>
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
<button>Click me</button>
</body>

</html>
```
当按钮的点击事件被触发时会调用一个函数：
```
$("button").click(function(){$("p").hide();});
```
当点击button按钮时会让所有影藏所有的&lt;p>元素。
### **单独文件中的函数**
如果您的网站包含许多页面，并且您希望您的 jQuery 函数易于维护，那么请把您的 jQuery 函数放到独立的 .js 文件中。
### **jQuery命名冲突**
jQuery 使用 $ 符号作为 jQuery 的简介方式。

某些其他 JavaScript 库中的函数（比如 Prototype）同样使用 $ 符号。

jQuery 使用名为 noConflict() 的方法来解决该问题。

var jq=jQuery.noConflict()，帮助您使用自己的名称（比如 jq）来代替 $ 符号。
### **总结**
由于 jQuery 是为处理 HTML 事件而特别设计的，那么当您遵循以下原则时，您的代码会更恰当且更易维护：

- 把所有 jQuery 代码置于事件处理函数中
- 把所有事件处理函数置于文档就绪事件处理器中
- 把 jQuery 代码置于单独的 .js 文件中
- 如果存在名称冲突，则重命名 jQuery 库

### **jQuery事件**
Event函数|绑定函数至
--:|:--
$(document).ready(function)|将函数绑定到文档的就绪事件（当文档完成加载时）
$(selector).click(function)|触发或将函数绑定到被选元素的点击事件
$(selector).dblclick(function)|触发或将函数绑定到被选元素的双击事件
$(selector).focus(function)|触发或将函数绑定到被选元素的获得焦点事件
$(selector).mouseover(function)|触发或将函数绑定到被选元素的鼠标悬停事件
---
## **jQuery效果**
### jQuery hide() 和 show()
可以使用 hide() 和 show() 方法来隐藏和显示 HTML 元素：
```
$("#hide").click(function(){
  $("p").hide();
});

$("#show").click(function(){
  $("p").show();
});
```
**语法：**
```
$(selector).hide(speed,callback);
$(selector).show(speed,callback);
```
可选的 speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是隐藏或显示完成后所执行的函数名称。

**实例：**
```
$("button").click(function(){
  $("p").hide(1000);
});
```
## jQuery toggle()

使用 toggle() 方法来切换 hide() 和 show() 方法

显示被隐藏的元素，并隐藏已显示的元素：
```
$("button").click(function(){
  $("p").toggle();
});
```
语法：
```
$(selector).toggle(speed,callback);
```
可选的 speed 参数规定隐藏/显示的速度，可以取以下值："slow"、"fast" 或毫秒。

可选的 callback 参数是 toggle() 方法完成后所执行的函数名称。
## jQuery效果-淡入淡出
jQuery Fading 方法

通过 jQuery，您可以实现元素的淡入淡出效果。

jQuery 拥有下面四种 fade 方法：
- fadeIn()
- fadeOut()
- fadeToggle()
- fadeTo()

jQuery fadeIn() 方法

jQuery fadeIn() 用于淡入已隐藏的元素。
语法：
```
$(selector).fadeIn(speed,callback);
```
jQuery fadeOut() 方法

jQuery fadeOut() 方法用于淡出可见元素。

语法：
```
$(selector).fadeOut(speed,callback);
```
jQuery fadeToggle() 方法

jQuery fadeToggle() 方法可以在 fadeIn() 与 fadeOut() 方法之间进行切换

语法：
```
$(selector).fadeToggle(speed,callback);
```
jQuery fadeTo() 方法

jQuery fadeTo() 方法允许渐变为给定的不透明度（值介于 0 与 1 之间）

语法：
```
$(selector).fadeTo(speed,opacity,callback);
```
fadeTo() 方法中必需的 opacity 参数将淡入淡出效果设置为给定的不透明度（值介于 0 与 1 之间）。

可选的 callback 参数是该函数完成后所执行的函数名称
## jQuery效果-滑动
jQuery 滑动方法

通过 jQuery，可以在元素上创建滑动效果。

jQuery 拥有以下滑动方法：
- slideDown()
- slideUp()
- slideToggle()

jQuery slideDown() 方法

jQuery slideDown() 方法用于向下滑动元素。

语法：
```
$(selector).slideDown(speed,callback);
```
jQuery slideUp() 方法

jQuery slideUp() 方法用于向上滑动元素。

语法：
```
$(selector).slideUp(speed,callback);
```
jQuery slideToggle() 方法

jQuery slideToggle() 方法可以在 slideDown() 与 slideUp() 方法之间进行切换

语法：
```
$(selector).slideToggle(speed,callback);
```
## jQuery效果-动画
jQuery 动画 - animate() 方法

jQuery animate() 方法允许您创建自定义的动画。

语法：
```
$(selector).animate({params},speed,callback);
```
必需的 params 参数定义形成动画的 CSS 属性

可选的 speed 参数规定效果的时长。它可以取以下值："slow"、"fast" 或毫秒

可选的 callback 参数是动画完成后所执行的函数名称

下面的例子演示 animate() 方法的简单应用；它把 &lt;div> 元素移动到左边，直到 left 属性等于 250 像素为止
```
$("button").click(function(){
  $("div").animate({left:'250px'});
}); 
```
jQuery animate() - 操作多个属性

生成动画的过程中可同时使用多个属性：
```
$("button").click(function(){
  $("div").animate({
    left:'250px',
    opacity:'0.5',
    height:'150px',
    width:'150px'
  });
});
```
### **注意：**

当使用 animate() 时，必须使用 Camel 标记法书写所有的属性名，比如，必须使用 paddingLeft 而不是 padding-left，使用 marginRight 而不是 margin-right，等等

jQuery animate() - 使用相对值

定义相对值（该值相对于元素的当前值）。需要在值的前面加上 += 或 -=：
实例：
```
$("button").click(function(){
  $("div").animate({
    left:'250px',
    height:'+=150px',
    width:'+=150px'
  });
});
```
jQuery animate() - 使用队列功能

这意味着如果在彼此之后编写多个 animate() 调用，jQuery 会创建包含这些方法调用的“内部”队列。然后逐一运行这些 animate 调用
```
$("button").click(function(){
  var div=$("div");
  div.animate({height:'300px',opacity:'0.4'},"slow");
  div.animate({width:'300px',opacity:'0.8'},"slow");
  div.animate({height:'100px',opacity:'0.4'},"slow");
  div.animate({width:'100px',opacity:'0.8'},"slow");
});
```
下面的例子把 &lt;div> 元素移动到右边，然后增加文本的字号
```
$("button").click(function(){
  var div=$("div");
  div.animate({left:'100px'},"slow");
  div.animate({fontSize:'3em'},"slow");
});
```
## jQuery 停止动画
jQuery stop() 方法

jQuery stop() 方法用于停止动画或效果，在它们完成之前

语法：
```
$(selector).stop(stopAll,goToEnd);
```
jQuery Callback 函数

当动画 100% 完成后，即调用 Callback 函数
语法：
```
$("p").hide(1000,function(){
alert("The paragraph is now hidden");
});
```
jQuery - Chaining

jQuery 方法链接
```
$("#p1").css("color","red").slideUp(2000).slideDown(2000);
```
## jQuery 获取
jQuery - 获得内容和属性

jQuery DOM 操作

jQuery 中非常重要的部分，就是操作 DOM 的能力。

jQuery 提供一系列与 DOM 相关的方法，这使访问和操作元素和属性变得很容易。

提示：DOM = Document Object Model（文档对象模型）

获得内容 - text()、html() 以及 val()

三个简单实用的用于 DOM 操作的 jQuery 方法：
- text() - 设置或返回所选元素的文本内容
- html() - 设置或返回所选元素的内容（包括 HTML 标记）
- val() - 设置或返回表单字段的值
```
$("#btn1").click(function(){
  alert("Text: " + $("#test").text());
});
$("#btn2").click(function(){
  alert("HTML: " + $("#test").html());
});
```
下面的例子演示如何通过 jQuery val() 方法获得输入字段的值：
```
$("#btn1").click(function(){
  alert("Value: " + $("#test").val());
});
```
获取属性 - attr()
jQuery attr() 方法用于获取属性值
```
$("button").click(function(){
  alert($("#w3s").attr("href"));
});
```
---
jQuery - 设置内容和属性

设置内容 - text()、html() 以及 val()

我们将使用前一章中的三个相同的方法来设置内容：
- text() - 设置或返回所选元素的文本内容
- html() - 设置或返回所选元素的内容（包括 HTML 标记）
- val() - 设置或返回表单字段的值
```
$("#btn1").click(function(){
  $("#test1").text("Hello world!");
});
$("#btn2").click(function(){
  $("#test2").html("<b>Hello world!</b>");
});
$("#btn3").click(function(){
  $("#test3").val("Dolly Duck");
});
```
设置属性 - attr()

jQuery attr() 方法也用于设置/改变属性值。
```
$("button").click(function(){
  $("#w3s").attr("href","http://www.w3school.com.cn/jquery");
});
```
jQuery-添加元素

添加新的 HTML 内容

我们将学习用于添加新内容的四个 jQuery 方法：
- append() - 在被选元素的结尾插入内容
- prepend() - 在被选元素的开头插入内容
- after() - 在被选元素之后插入内容
- before() - 在被选元素之前插入内容

jQuery append() 方法

jQuery append() 方法在被选元素的结尾插入内容
```
$("p").append("Some appended text.");
```
jQuery prepend() 方法

jQuery prepend() 方法在被选元素的开头插入内容
```
$("p").prepend("Some prepended text.");
```
## jQuery - 删除元素
### 删除元素/内容
如需删除元素和内容，一般可使用以下两个 jQuery 方法：
- remove() - 删除被选元素（及其子元素）
- empty() - 从被选元素中删除子元素

### jQuery remove() 方法

jQuery remove() 方法删除被选元素及其子元素。

实例
```
$("#div1").remove();
```
jQuery empty() 方法
jQuery empty() 方法删除被选元素的子元素。

实例
```
$("#div1").empty();
```
### **过滤被删除的元素**
jQuery remove() 方法也可接受一个参数，允许您对被删元素进行过滤。

该参数可以是任何 jQuery 选择器的语法。

下面的例子删除 class="italic" 的所有 &lt;p> 元素：

实例
```
$("p").remove(".italic");
```
----
## jQuery CSS 类
### jQuery 操作 CSS
jQuery 拥有若干进行 CSS 操作的方法

- addClass() - 向被选元素添加一个或多个类
- removeClass() - 从被选元素删除一个或多个类
- toggleClass() - 对被选元素进行添加/删除类的切换操作
- css() - 设置或返回样式属性

### jQuery addClass() 方法
展示如何向不同的元素添加 class 属性。在添加类时，可以选取多个元素：

实例
```
$("button").click(function(){
  $("h1,h2,p").addClass("blue");
  $("div").addClass("important");
});
```
也可以在 addClass() 方法中规定多个类：

实例
```
$("button").click(function(){
  $("#div1").addClass("important blue");
});
```
### jQuery removeClass() 方法
如何在不同的元素中删除指定的 class 属性：

实例
```
$("button").click(function(){
  $("h1,h2,p").removeClass("blue");
});
```
### jQuery toggleClass() 方法
下面的例子将展示如何使用 jQuery toggleClass() 方法。该方法对被选元素进行添加/删除类的切换操作：

实例
```
$("button").click(function(){
  $("h1,h2,p").toggleClass("blue");
});
```
---
### jQuery css() 方法
返回 CSS 属性

将返回首个匹配元素的 background-color 值：

实例
```
$("p").css("background-color");
```
### 设置 CSS 属性
如需设置指定的 CSS 属性，使用如下语法：    

css("propertyname","value");

下面的例子将为所有匹配元素设置 background-color 值：

实例
```
$("p").css("background-color","yellow");
```
### 设置多个 CSS 属性
如需设置多个 CSS 属性，使用如下语法：    

css({"propertyname":"value","propertyname":"value",...});

下面的例子将为所有匹配元素设置 background-color 和 font-size：

实例
```
$("p").css({"background-color":"yellow","font-size":"200%"});
```
## jQuery 尺寸
jQuery 尺寸 方法

jQuery 提供多个处理尺寸的重要方法：

- width()
- height()
- innerWidth()
- innerHeight()
- outerWidth()
- outerHeight()

jQuery width() 和 height() 方法

width() 方法设置或返回元素的宽度（不包括内边距、边框或外边距）。

height() 方法设置或返回元素的高度（不包括内边距、边框或外边距）。

下面的例子返回指定的 &lt;div> 元素的宽度和高度：
```
$("button").click(function(){ 
  var txt=""; 
  txt+="Width: " + $("#div1").width() + "</br>"; 
  txt+="Height: " + $("#div1").height(); 
  $("#div1").html(txt); 
});
```
jQuery innerWidth() 和 innerHeight() 方法

innerWidth() 方法返回元素的宽度（包括内边距）。

innerHeight() 方法返回元素的高度（包括内边距）。

下面的例子返回指定的 &lt;div> 元素的 inner-width/height：

实例
```
$("button").click(function(){ 
  var txt=""; 
  txt+="Inner width: " + $("#div1").innerWidth() + "</br>"; 
  txt+="Inner height: " + $("#div1").innerHeight(); 
  $("#div1").html(txt); 
});
```
jQuery outerWidth() 和 outerHeight() 方法

outerWidth() 方法返回元素的宽度（包括内边距和边框）。

outerHeight() 方法返回元素的高度（包括内边距和边框）。

下面的例子返回指定的 <div> 元素的 outer-width/height：

实例
```
$("button").click(function(){ 
  var txt=""; 
  txt+="Outer width: " + $("#div1").outerWidth() + "</br>"; 
  txt+="Outer height: " + $("#div1").outerHeight(); 
  $("#div1").html(txt); 
});
```
### jquery遍历
jQuery 遍历，意为"移动"，用于根据其相对于其他元素的关系来"查找"（或选取）HTML 元素。以某项选择开始，并沿着这个选择移动，直到抵达您期望的元素为止。

下图展示了一个家族树。通过 jQuery 遍历，您能够从被选（当前的）元素开始，轻松地在家族树中向上移动（祖先），向下移动（子孙），水平移动（同胞）。这种移动被称为对 DOM 进行遍历
### jQuery 遍历 - 祖先
祖先是父、祖父或曾祖父等等。

通过 jQuery，您能够向上遍历 DOM 树，以查找元素的祖先。
jQuery parent() 方法
parent() 方法返回被选元素的直接父元素。

该方法只会向上一级对 DOM 树进行遍历。

下面的例子返回每个 &lt;span> 元素的的直接父元素：
```
$(document).ready(function(){
  $("span").parent();
});
```
jQuery parents() 方法
parents() 方法返回被选元素的所有祖先元素，它一路向上直到文档的根元素 (&lt;html>)。

下面的例子返回所有 &lt;span> 元素的所有祖先：

```
$(document).ready(function(){
  $("span").parents();
});
```
也可以使用可选参数来过滤对祖先元素的搜索。

下面的例子返回所有 &lt;span> 元素的所有祖先，并且它是 &lt;ul> 元素：

实例:
```
$(document).ready(function(){
  $("span").parents("ul");
});
```
jQuery parentsUntil() 方法
parentsUntil() 方法返回介于两个给定元素之间的所有祖先元素。

下面的例子返回介于 <span> 与 <div> 元素之间的所有祖先元素：

实例:
```
$(document).ready(function(){
  $("span").parentsUntil("div");
});
```
### jQuery 遍历 - 后代
后代是子、孙、曾孙等等。

通过 jQuery，您能够向下遍历 DOM 树，以查找元素的后代。

jQuery children() 方法

children() 方法返回被选元素的所有直接子元素。

该方法只会向下一级对 DOM 树进行遍历。

下面的例子返回每个 <div> 元素的所有直接子元素：

实例:
```
$(document).ready(function(){
  $("div").children();
});
```
也可以使用可选参数来过滤对子元素的搜索。

下面的例子返回类名为 "1" 的所有 <p> 元素，并且它们是 <div> 的直接子元素：

实例:
```
$(document).ready(function(){
  $("div").children("p.1");
});
```
jQuery find() 方法

find() 方法返回被选元素的后代元素，一路向下直到最后一个后代。

下面的例子返回属于 <div> 后代的所有 <span> 元素：

实例:
```
$(document).ready(function(){
  $("div").find("span");
});
```
返回 &lt;div> 的所有后代：

实例:
```
$(document).ready(function(){
  $("div").find("*");
});
```
### jQuery 遍历 - 同胞(siblings)

同胞拥有相同的父元素。

通过 jQuery，您能够在 DOM 树中遍历元素的同胞元素。
jQuery siblings() 方法
siblings() 方法返回被选元素的所有同胞元素。

下面的例子返回 &lt;h2> 的所有同胞元素：

实例:
```
$(document).ready(function(){
  $("h2").siblings();
});
```
使用可选参数来过滤对同胞元素的搜索。

下面的例子返回属于 &lt;h2> 的同胞元素的所有 &lt;p> 元素：

实例:
```
$(document).ready(function(){
  $("h2").siblings("p");
});
```
jQuery next() 方法

next() 方法返回被选元素的下一个同胞元素。

该方法只返回一个元素。

下面的例子返回 &lt;h2> 的下一个同胞元素：

实例:
```
$(document).ready(function(){
  $("h2").next();
});
```
jQuery nextAll() 方法

nextAll() 方法返回被选元素的所有跟随的同胞元素。

下面的例子返回 &lt;h2> 的所有跟随的同胞元素：

实例:
```
$(document).ready(function(){
  $("h2").nextAll();
});
```
jQuery nextUntil() 方法

nextUntil() 方法返回介于两个给定参数之间的所有跟随的同胞元素。

下面的例子返回介于 &lt;h2> 与 &lt;h6> 元素之间的所有同胞元素：

实例:
```
$(document).ready(function(){
  $("h2").nextUntil("h6");
});
```
## jQuery 遍历- 过滤
缩小搜索元素的范围

三个最基本的过滤方法是：first(), last() 和 eq()，它们允许您基于其在一组元素中的位置来选择一个特定的元素。

其他过滤方法，比如 filter() 和 not() 允许您选取匹配或不匹配某项指定标准的元素。
jQuery first() 方法
first() 方法返回被选元素的首个元素。

下面的例子选取首个 <div> 元素内部的第一个 <p> 元素：

实例:
```
$(document).ready(function(){
  $("div p").first();
});
```
jQuery last() 方法
last() 方法返回被选元素的最后一个元素。

下面的例子选择最后一个 <div> 元素中的最后一个 <p> 元素：

实例:
```
$(document).ready(function(){
  $("div p").last();
});
```
jQuery eq() 方法
eq() 方法返回被选元素中带有指定索引号的元素。

索引号从 0 开始，因此首个元素的索引号是 0 而不是 1。下面的例子选取第二个 <p> 元素（索引号 1）：

实例:
```
$(document).ready(function(){
  $("p").eq(1);
});
```
jQuery filter() 方法

filter() 方法允许您规定一个标准。不匹配这个标准的元素会被从集合中删除，匹配的元素会被返回。

下面的例子返回带有类名 "intro" 的所有 <p> 元素：

实例:
```
$(document).ready(function(){
  $("p").filter(".intro");
});
```
jQuery not() 方法

not() 方法返回不匹配标准的所有元素。

提示：not() 方法与 filter() 相反。

下面的例子返回不带有类名 "intro" 的所有 <p> 元素：

实例:
```
$(document).ready(function(){
  $("p").not(".intro");
});
```
## jQuery - AJAX 
AJAX 是与服务器交换数据的技术，它在不重载全部页面的情况下，实现了对部分网页的更新

什么是 AJAX

AJAX = 异步 JavaScript 和 XML

简短地说，在不重载整个网页的情况下，AJAX 通过后台加载数据，并在网页上进行显示。

jQuery - AJAX load() 方法

jQuery load() 方法

jQuery load() 方法是简单但强大的 AJAX 方法。

load() 方法从服务器加载数据，并把返回的数据放入被选元素中。

语法:
```
$(selector).load(URL,data,callback);
```
- URL 参数规定您希望加载的 URL
- data 参数规定与请求一同发送的查询字符串键/值对集合
- callback 参数是 load() 方法完成后所执行的函数名称

把文件 "demo_test.txt" 的内容加载到指定的 <div> 元素中：

实例:
```
$("#div1").load("demo_test.txt");
```
把 jQuery 选择器添加到 URL 参数。

下面的例子把 "demo_test.txt" 文件中 id="p1" 的元素的内容，加载到指定的 &lt;div> 元素中：

实例:
```
$("#div1").load("demo_test.txt #p1");
```
jQuery - AJAX get() 和 post() 方法

jQuery get() 和 post() 方法用于通过 HTTP GET 或 POST 请求从服务器请求数据

HTTP 请求：GET vs. POST
两种在客户端和服务器端进行请求-响应的常用方法是：GET 和 POST。

- GET - 从指定的资源请求数据
- POST - 向指定的资源提交要处理的数据

必需的 URL 参数规定您希望请求的 URL。

可选的 callback 参数是请求成功后所执行的函数名。

下面的例子使用 $.get() 方法从服务器上的一个文件中取回数据：

实例:
```
$("button").click(function(){
  $.get("demo_test.php",function(data,status){
    alert("数据: " + data + "\n状态: " + status);
  });
});
```
jQuery $.post() 方法
$.post() 方法通过 HTTP POST 请求从服务器上请求数据。

语法:
```
$.post(URL,data,callback); 
```
- URL 参数规定您希望请求的 URL。

- data 参数规定连同请求发送的数据。

- callback 参数是请求成功后所执行的函数名。

下面的例子使用 $.post() 连同请求一起发送数据：

实例:
```
$("button").click(function(){
  $.post("demo_test_post.html",
  {
    name:"Donald Duck",
    city:"Duckburg"
  },
  function(data,status){
    alert("Data: " + data + "nStatus: " + status);
  });
});
```
jQuery noConflict() 方法

noConflict() 方法会释放对 $ 标识符的控制，这样其他脚本就可以使用它了。

当然，您仍然可以通过全名替代简写的方式来使用 jQuery：

实例:
```
$.noConflict();
jQuery(document).ready(function(){
  jQuery("button").click(function(){
    jQuery("p").text("jQuery is still working!");
  });
});
```

## jQuery 选择器
请使用我们的 jQuery 选择器检测器 来演示不同的选择器。

选择器|实例|选取
--:|:--:|:--
*|$("*")|所有元素
#id|$("#lastname")|id="lastname" 的元素
.class|$(".intro")|class="intro" 的所有元素
.class,.class|$(".intro,.demo")|class 为 "intro" 或 "demo" 的所有元素
element|$("p")|所有 &lt;p> 元素
el1,el2,el3|$("h1,div,p")|所有 &lt;h1>、&lt;div> 和 &lt;p> 元素	 	 
:first|$("p:first")|第一个 &lt;p> 元素
:last|$("p:last")|最后一个 &lt;p> 元素
:even|$("tr:even")|所有偶数 &lt;tr> 元素
:odd|$("tr:odd")|所有奇数 &lt;tr> 元素 	 
:first-child|$("p:first-child")|属于其父元素的第一个子元素的所有 &lt;p> 元素
:first-of-type|$("p:first-of-type")|属于其父元素的第一个 &lt;p> 元素的所有 &lt;p> 元素
:last-child|$("p:last-child")|属于其父元素的最后一个子元素的所有 &lt;p> 元素
:last-of-type|$("p:last-of-type")|属于其父元素的最后一个 &lt;p> 元素的所有 &lt;p> 元素
:nth-child(n)|$("p:nth-child(2)")|属于其父元素的第二个子元素的所有 &lt;p> 元素
:nth-last-child(n)|$("p:nth-last-child(2)")|属于其父元素的第二个子元素的所有&lt;p> 元素，从最后一个子元素开始计数
:nth-of-type(n)|$("p:nth-of-type(2)")|属于其父元素的第二个 &lt;p> 元素的所有 &lt;p> 元素
:nth-last-of-type(n)|$("p:nth-last-of-type(2)")|属于其父元素的第二个 &lt;p> 元素的所有 &lt;p> 元素，从最后一个子元素开始计数
:only-child|$("p:only-child")|属于其父元素的唯一子元素的所有 &lt;p> 元素
:only-of-type|$("p:only-of-type")|属于其父元素的特定类型的唯一子元素的所有 &lt;p> 元素	 
parent > child|$("div > p")|&lt;div> 元素的直接子元素的所有 &lt;p> 元素
parent descendant|$("div p")	&lt;div> 元素的后代的所有 &lt;p> 元素
element + next|$("div + p")|每个 &lt;div> 元素相邻的下一个 &lt;p> 元素
element ~ siblings|$("div ~ p")|&lt;div> 元素同级的所有 &lt;p> 元素 	 
:eq(index)|$("ul li:eq(3)")|列表中的第四个元素（index 值从 0 开始）
:gt(no)|$("ul li:gt(3)")|列举 index 大于 3 的元素
:lt(no)|$("ul li:lt(3)")|列举 index 小于 3 的元素
:not(selector)|$("input:not(:empty)")|所有不为空的输入元素
:header|$(":header")|所有标题元素 &lt;h1>, &lt;h2> ...
:animated|$(":animated")|所有动画元素
:focus|$(":focus")|当前具有焦点的元素
:contains(text)|$(":contains('Hello')")|所有包含文本 "Hello" 的元素|:has(selector)|$("div:has(p)")	所有包含有 &lt;p> 元素在其内的 &lt;div> 元素
:empty|$(":empty")|所有空元素
:parent|$(":parent")|选择所有含有子元素或者文本的父级元素。 
:hidden|$("p:hidden")|所有隐藏的 <p> 元素
:visible|$("table:visible")|所有可见的表格
:root|$(":root")|文档的根元素
:lang(language)|$("p:lang(de)")|所有带有以 "de" 开头的 lang 属性值的 &lt;p> 元素
[attribute]|$("[href]")|所有带有 href 属性的元素
[attribute=value]|$("[href='default.htm']")|所有带有 href 属性且值等于 "default.htm" 的元素
[attribute!=value]|$("[href!='default.htm']")|所有带有 href 属性且值不等于 "default.htm" 的元素
[attribute$=value]|$("[href$='.jpg']")|所有带有 href 属性且值以 ".jpg" 结尾的元素
[attribute|=value]|$("[title|='Tomorrow']")|所有带有 title 属性且值等于 'Tomorrow' 或者以 'Tomorrow' 后跟连接符作为开头的字符串
[attribute^=value]|$("[title^='Tom']")|所有带有 title 属性且值以 "Tom" 开头的元素
[attribute~=value]|$("[title~='hello']")|所有带有 title 属性且值包含单词 "hello" 的元素
[attribute*=value]|$("[title*='hello']")|所有带有 title 属性且值包含字符串 "hello" 的元素 	 
:input|$(":input")|所有 input 元素
:text|$(":text")|所有带有 type="text" 的 input 元素
:password|$(":password")|所有带有 type="password" 的 input 元素	 
:checkbox|$(":checkbox")|所有带有 type="checkbox" 的 input 元素
:submit|$(":submit")|所有带有 type="submit" 的 input 元素
:reset|$(":reset")|所有带有 type="reset" 的 input 元素
:button|$(":button")|所有带有 type="button" 的 input 元素
:image|$(":image")|所有带有 type="image" 的 input 元素
:file|$(":file")|所有带有 type="file" 的 input 元素
:enabled|$(":enabled")|所有启用的 input 元素
:disabled|$(":disabled")|所有禁用的 input 元素
:selected|$(":selected")|所有选定的 input 元素	 	 
:checked|$(":checked")|所有选中的 input 元素

### jQuery 事件方法

方法|描述
--:|:--
bind()|向元素添加事件处理程序
blur()|添加/触发 blur 事件
change()|添加/触发 change 事件
click()|添加/触发 click 事件
dblclick()|添加/触发 double click 事件
delegate()|向匹配元素的当前或未来的子元素添加处理程序
die()|在版本 1.9 中被移除。移除所有通过 live() 方法添加的事件处理程序
error()|在版本 1.8 中被废弃。添加/触发 error 事件
event.currentTarget|在事件冒泡阶段内的当前 DOM 元素
event.data|包含当前执行的处理程序被绑定时传递到事件方法的可选数据
event.delegateTarget|返回当前调用的 jQuery 事件处理程序所添加的元素
event.isDefaultPrevented()|返回指定的 event 对象上是否调用了 event.preventDefault()
event.isImmediatePropagationStopped()|返回指定的 event 对象上是否调用了 event.stopImmediatePropagation()
event.isPropagationStopped()|返回指定的 event 对象上是否调用了 event.stopPropagation()
event.namespace|返回当事件被触发时指定的命名空间
event.pageX|返回相对于文档左边缘的鼠标位置
event.pageY|返回相对于文档上边缘的鼠标位置
event.preventDefault()|阻止事件的默认行为
event.relatedTarget|返回当鼠标移动时哪个元素进入或退出
event.result|包含由被指定事件触发的事件处理程序返回的最后一个值
event.stopImmediatePropagation()|阻止其他事件处理程序被调用
event.stopPropagation()|阻止事件向上冒泡到 DOM 树，阻止任何父处理程序被事件通知
event.target|返回哪个 DOM 元素触发事件
event.timeStamp|返回从 1970 年 1 月 1 日到事件被触发时的毫秒数
event.type|返回哪种事件类型被触发
event.which|返回指定事件上哪个键盘键或鼠标按钮被按下
focus()|添加/触发 focus 事件
focusin()|添加事件处理程序到 focusin 事件
focusout()|添加事件处理程序到 focusout 事件
hover()|添加两个事件处理程序到 hover 事件
keydown()|添加/触发 keydown 事件
keypress()|添加/触发 keypress 事件
keyup()|添加/触发 keyup 事件
live()|在版本 1.9 中被移除。添加一个或多个事件处理程序到当前或未来的被选元素
load()|在版本 1.8 中被废弃。添加一个事件处理程序到 load 事件
mousedown()|添加/触发 mousedown 事件
mouseenter()|添加/触发 mouseenter 事件
mouseleave()|添加/触发 mouseleave 事件
mousemove()|添加/触发 mousemove 事件
mouseout()|添加/触发 mouseout 事件
mouseover()|添加/触发 mouseover 事件
mouseup()|添加/触发 mouseup 事件
off()|移除通过 on() 方法添加的事件处理程序
on()|向元素添加事件处理程序
one()|向被选元素添加一个或多个事件处理程序。该处理程序只能被每个元素触发一次
$.proxy()|接受一个已有的函数，并返回一个带特定上下文的新的函数
ready()|规定当 DOM 完全加载时要执行的函数
resize()|添加/触发 resize 事件
scroll()|添加/触发 scroll 事件
select()|添加/触发 select 事件
submit()|添加/触发 submit 事件
toggle()|在版本 1.9 中被移除。添加 click 事件之间要切换的两个或多个函数
trigger()|触发绑定到被选元素的所有事件
triggerHandler()|触发绑定到被选元素的指定事件上的所有函数
unbind()|从被选元素上移除添加的事件处理程序
undelegate()|从现在或未来的被选元素上移除事件处理程序
unload()|在版本 1.8 中被废弃。添加事件处理程序到 unload 事件