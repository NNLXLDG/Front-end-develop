# CSS学习

## 1 第一章：引入

### 1.1 CSS发展历史
+ 从HTML被发明开始，样式就以各种形式存在。不同的浏览器结合它们各自的样式语言为用户提供页面效果的控制。最初的HTML只包含很少的显示属性。
+ 随着HTML的成长，为了满足页面设计者的要求，HTML添加了很多显示功能。但是随着这些功能的增加，HTML变的越来越杂乱，而且HTML页面也越来越臃肿。于是CSS便诞生了。
+ 1994年哈坤·利提出了CSS的最初建议。而当时伯特·波斯（Bert Bos）正在设计一个名为Argo的浏览器，于是他们决定一起设计CSS。
+ 其实当时在互联网界已经有过一些统一样式表语言的建议了，但CSS是第一个含有“层叠”丰意的样式表语言。在CSS中，一个文件的样式可以从其他的样式表中继承。读者在有些地方可以使用他自己更喜欢的样式，在其他地方则继承或“层叠”作者的样式。这种层叠的方式使作者和读者都可以灵活地加入自己的设计，混合每个人的爱好。
+ 哈坤于1994年在芝加哥的一次会议上第一次提出了CSS的建议，1995年的www网络会议上CSS又一次被提出，博斯演示了Argo浏览器支持CSS的例子，哈肯也展示了支持CSS的Arena浏览器。

### 1.2 什么是CSS
+ 标准答案：**CSS 指层叠样式表 (Cascading Style Sheets)**
+ 样式定义如何显示 HTML 元素
+ 样式通常存储在样式表中
+ 把样式添加到 HTML 4.0 中，是为了解决内容与表现分离的问题
+ 外部样式表可以极大提高工作效率
+ 外部样式表通常存储在 CSS 文件中
+ 多个样式定义可层叠为一个

**丰富的样式定义**  
+ CSS提供了丰富的文档样式外观，以及设置文本和背景属性的能力；允许为任何元素创建边框，以及元素边框与其他元素间的距离，以及元素边框与元素内容间的距离；允许随意改变文本的大小写方式、修饰方式以及其他页面效果。  
  
**易于使用和修改**  
+ CSS可以将样式定义在HTML元素的**style属性**中，也可以将其定义在HTML文档的**header部分**，也可以将样式声明在一个专门的**CSS文件**中，以供HTML页面引用。总之，CSS样式表可以将所有的样式声明统一存放，进行统一管理。另外，可以将相同样式的元素进行归类，使用同一个样式进行定义，也可以将某个样式应用到所有同名的HTML标签中，也可以将一个CSS样式指定到某个页面元素中。如果要修改样式，只需要在样式列表中找到相应的样式声明进行修改。
+ 多页面应用CSS样式表可以单独存放在一个CSS文件中，这样就可以在多个页面中使用同一个CSS样式表。CSS样式表理论上不属于任何页面文件，在任何页面文件中都可以将其引用。这样就可以实现多个页面风格的统一。

**层叠**  
+ 简单的说，层叠就是对一个元素多次设置同一个样式，这将使用最后一次设置的属性值。例如对一个站点中的多个页面使用了同一套CSS样式表，而某些页面中的某些元素想使用其他样式，就可以针对这些样式单独定义一个样式表应用到页面中。这些后来定义的样式将对前面的样式设置进行重写，在浏览器中看到的将是最后面设置的样式效果。  

**页面压缩**  
+ 在使用HTML定义页面效果的网站中，往往需要大量或重复的表格和font元素形成各种规格的文字样式，这样做的后果就是会产生大量的HTML标签，从而使页面文件的大小增加。而将样式的声明单独放到CSS样式表中，可以大大的减小页面的体积，这样在加载页面时使用的时间也会大大的减少。另外，CSS样式表的复用更大程度的缩减了页面的体积，减少下载的时间。

### 1.3 来个实例
这是一段HTML代码
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
<style>
body {
	background-color:#d0e4fe;
}
h1 {
	color:orange;
	text-align:center;
}
p {
	font-family:"Times New Roman";
	font-size:20px;
}
</style>
</head>

<body>

<h1>CSS 实例!</h1>
<p>这是一个段落。</p>

</body>
</html>

```
**其中`<style>`部分就是CSS样式表**
```css
body {
    background-color:#d0e4fe;
}
h1 {
    color:orange;
    text-align:center;
}
p {
    font-family:"Times New Roman";
    font-size:20px;
}
```

## 第二章：语法

### 2.1 选择器
先来看两个实例：

**实例一**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
<style>
body {background-color:yellow;}
h1   {font-size:36pt;}
h2   {color:blue;}
p    {margin-left:50px;}
</style>
</head>

<body>

<h1>这个标题设置的大小为 36 pt</h1>
<h2>这个标题设置的颜色为蓝色：blue</h2>

<p>这个段落的左外边距为 50 像素：50px</p> 

</body>
</html>
```
得到的效果如下：
![alt text](image.png)

**实例二**
```html

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
<style>
body {background-color:tan;}
h1   {color:maroon;font-size:20pt;}
hr   {color:navy;}
p    {font-size:11pt;margin-left:15px;}
a:link    {color:green;}
a:visited {color:yellow;}
a:hover   {color:black;}
a:active  {color:blue;}
</style>
</head>

<body>

<h1>这是标题</h1>
<hr>

<p>你可以看到这个段落是
被设定的 CSS 渲染的。</p>

<p><a href="https://www.runoob.com" 
target="_blank">这是一个链接</a></p>

</body>
</html>

```
得到的效果如下：
![alt text](image-1.png)


CSS 规则由两个主要的部分构成：**选择器**，以及一条或多条声明
```css
p {color:red;text-align:center;}
```
+ 选择器通常是您需要改变样式的 HTML 元素。
+ 每条声明由一个属性和一个值组成。
+ 属性（property）是您希望设置的样式属性（style attribute）。每个属性有一个值。属性和值被冒号分开。
+ CSS声明总是以分号 ; 结束，声明总以大括号 {} 括起来:


为了让CSS可读性更强，建议每行只描述一个属性
```css
p
{
	color:red;
	text-align:center;
} 
```



#### 2.1.1 进一步的：ID选择器
+ id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。
+ HTML元素以id属性来设置id选择器,CSS 中 id 选择器以 "#" 来定义。


以下的样式规则应用于元素属性 id="para1":
```HTML
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
#para1
{
	text-align:center;
	color:red;
} 
</style>
</head>

<body>
<p id="para1">Hello World!</p>
<p>这个段落不受该样式的影响。</p>
</body>
</html>
```

输出结果：
![alt text](image-2.png)



#### 2.1.2 进一步的：class选择器
+ class 选择器用于描述一组元素的样式，class 选择器有别于id选择器，class可以在多个元素中使用。
+ class 选择器在 HTML 中以 class 属性表示, 在 CSS 中，类选择器以一个点 . 号显示：

在以下的例子中，所有拥有 center 类的 HTML 元素均为居中：
```HTML
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
.center
{
	text-align:center;
}
</style>
</head>

<body>
<h1 class="center">标题居中</h1>
<p class="center">段落居中。</p> 
</body>
</html>
```

结果如下：
![alt text](image-3.png)

也可以指定特定的 HTML 元素使用 class。  
在以下实例中, 所有的 p 元素使用 class="center" 让该元素的文本居中:
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
p.center
{
	text-align:center;
}
</style>
</head>

<body>
<h1 class="center">这个标题不受影响</h1>
<p class="center">这个段落居中对齐。</p> 
</body>
</html>
```
效果如下:
![alt text](image-4.png)


多个 class 选择器可以使用空格分开：
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
.center {
	text-align:center;
}
.color {
	color:#ff0000;
}
</style>
</head>

<body>
<h1 class="center">标题居中</h1>
<p class="center color">段落居中，颜色为红色。</p> 
</body>
</html>
```
![alt text](image-5.png)



#### 2.1.3 进一步的：标签选择器
```css
<style>
h3{
    color:red;
}
</style>
<h3>菜鸟教程</h3>
```

#### 2.1.4 进一步的：在标签内写css代码
```css
<h3 style="color:red;">菜鸟教程</h3>
```

#### 优先级

这四种 css 选择器有修饰上的优先级，即：  
**第四种 > id > class > 第三种**


#### 补充
+ **标签选择器**       说明：选中指定标签，也叫元素选择器
+ **id选择器 #**         说明：选中id属性
+ **class选择器 .**       说明：选中class属性
+ **属性选择器   []**       说明：这样写"a[id]"，选中指定规则的属性，所在标签。
+ **包含选择器 （空格）**   说明：选中所有儿子，孙子等....
+ **子选择器  >**       说明：选中所有儿子，不选孙子等...
+ **兄弟选择器  ~**      说明：选中后面一个或多个兄弟
+ **相邻选择器  +**       说明：选中后面一个兄弟
+ **伪类选择器   :**      说明：主要根据用户动作，标签位置，标签状态来选中
+ **伪元素选择器 ::**     说明：主要选中一段文本的一行，首字，或前后添加样式



### 2.2 如何创建CSS 
当读到一个样式表时，浏览器会根据它来格式化 HTML 文档。  

**那么，如何插入一个样式表呢，或者说有哪几种方式呢？**


#### 2.2.1 外部样式表
当样式需要应用于很多页面时，外部样式表将是理想的选择。在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用`<link>`标签链接到样式表。 `<link>`标签在（文档的）头部：
```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```










