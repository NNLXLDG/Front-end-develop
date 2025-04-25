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

**当样式需要应用于很多页面时，外部样式表将是理想的选择**  

在使用外部样式表的情况下，你可以通过改变一个文件来改变整个站点的外观。每个页面使用`<link>`标签链接到样式表。 `<link>`标签在（文档的）头部：
```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```
浏览器会从文件 mystyle.css 中读到样式声明，并根据它来格式文档。

外部样式表可以在任何文本编辑器中进行编辑。文件不能包含任何的 html 标签。样式表应该以 .css 扩展名进行保存。下面是一个样式表文件的例子：
```css
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("/images/back40.gif");}
```
#### 2.2.2 内部样式表

**当单个文档需要特殊的样式时，就应该使用内部样式表。**

可以使用`<style>`标签在文档头部定义内部样式表，就像这样:
```html
<head>
<style>
hr {color:sienna;}
p {margin-left:20px;}
body {background-image:url("images/back40.gif");}
</style>
</head>
```


#### 2.2.3 内联样式表
由于要将表现和内容混杂在一起，内联样式会损失掉样式表的许多优势。请慎用这种方法，例如当样式仅需要在一个元素上应用一次时。

要使用内联样式，你需要在相关的标签内使用样式（style）属性。Style 属性可以包含任何 CSS 属性。本例展示如何改变段落的颜色和左外边距：
```html
<p style="color:sienna;margin-left:20px">这是一个段落。</p>
```

#### 2.2.4 多重样式
如果某些属性在不同的样式表中被同样的选择器定义，那么属性值将从更具体的样式表中被继承过来。 

例如，外部样式表拥有针对 h3 选择器的三个属性：
```css
h3
{
    color:red;
    text-align:left;
    font-size:8pt;
}
```
而内部样式表拥有针对 h3 选择器的两个属性：
```css
h3
{
    text-align:right;
    font-size:20pt;
}
```
假如拥有内部样式表的这个页面同时与外部样式表链接，那么 h3 得到的样式是：
```css
color:red;
text-align:right;
font-size:20pt;
```
**即颜色属性将被继承于外部样式表，而文字排列（text-alignment）和字体尺寸（font-size）会被内部样式表中的规则取代。**


#### 2.2.5 多重样式优先级
样式表允许以多种方式规定样式信息。样式可以规定在单个的 HTML 元素中，在 HTML 页的头元素中，或在一个外部的 CSS 文件中。甚至可以在同一个 HTML 文档内部引用多个外部样式表。

一般情况下，优先级如下：

**（内联样式）Inline style > （内部样式）Internal style sheet >（外部样式）External style sheet > 浏览器默认样式**


style.css 文件样式代码如下：
```css
h3 {
    color:blue;
}
```

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
<!-- 外部样式 style.css -->
<link rel="stylesheet" type="text/css" href="https://static.jyshare.com/libs/assets/css/css-howto/style.css"/>
<!-- 设置：h3{color:blue;} -->
<style type="text/css">
/* 内部样式 */
h3{color:green;}
</style>
</head>
<body>

<h3>显示绿色，是内部样式</h3>

</body>
</html>
```

注意：如果外部样式放在内部样式的后面，则外部样式将覆盖内部样式，实例如下：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
<!-- 设置：h3{color:blue;} -->
<style type="text/css">
/* 内部样式 */
h3{color:green;}
</style>
<!-- 外部样式 style.css -->
<link rel="stylesheet" type="text/css" href="https://static.jyshare.com/assets/css/css-howto/style.css"/>
</head>
<body>

<h3>显示蓝色，是外部样式</h3>

</body>
</html>
```


### 2.3 背景属性

CSS 属性定义背景效果:  
+ background-color  
+ background-image  
+ background-repeat  
+ background-attachment  
+ background-position  


#### 2.3.1 background-color
background-color 属性定义了元素的背景颜色.

页面的背景颜色使用在body的选择器中:
```css
body {background-color:#b0c4de;}
```

颜色的三种定义方式:
+ 十六进制 - 如：`#ff0000`
+ RGB - 如：`rgb(255,0,0)`
+ 颜色名称 - 如：`red`

以下实例中, h1, p, 和 div 元素拥有不同的背景颜色:
```css
h1 {background-color:#6495ed;}
p {background-color:#e0ffff;}
div {background-color:#b0c4de;}
```

#### 2.3.2 background-image
background-image 属性描述了元素的背景图像.

默认情况下，背景图像进行平铺重复显示，以覆盖整个元素实体.

页面背景图片设置实例:
```css
body {background-image:url('paper.gif');}
```


默认情况下 background-image **属性会在页面的水平或者垂直方向平铺**

一些图像如果在水平方向与垂直方向平铺，这样看起来很不协调，如下所示: 
```css
body
{
background-image:url('gradient2.png');
}
```

![](2025-04-23-00-20-19.png)

如果图像只在水平方向平铺 (repeat-x), 页面背景会更好些:
```css
body
{
background-image:url('gradient2.png');
background-repeat:repeat-x;
}
```
![](2025-04-23-00-20-42.png)


#### 2.3.3 background-repeat

让背景图像不影响文本的排版

不想让图像平铺时，可以使用 background-repeat 属性
```css
body
{
background-image:url('img_tree.png');
background-repeat:no-repeat;
}
```
以上实例中，背景图像与文本显示在同一个位置，为了让页面排版更加合理，不影响文本的阅读，我们可以改变图像的位置。


![](2025-04-23-00-19-00.png)


#### 2.3.4 background-position
可以利用 background-position 属性改变图像在背景中的位置:
```css
body
{
background-image:url('img_tree.png');
background-repeat:no-repeat;
background-position:right top;
}
```
![](2025-04-23-00-19-35.png)



#### 2.3.5 background-attachment
指定一个固定的背景图像
```css
body
{ 
    background-image:url('smiley.gif');
    background-repeat:no-repeat;
    background-attachment:fixed;
}
```
![](2025-04-23-00-27-12.png)


#### 简写属性


在以上实例中我们可以看到页面的背景颜色通过了很多的属性来控制。

为了简化这些属性的代码，我们可以将这些属性合并在同一个属性中.

背景颜色的简写属性为 "background":
```css
body {background:#ffffff url('img_tree.png') no-repeat right top;}
```

当使用简写属性时，属性值的顺序为：
+ background-color
+ background-image
+ background-repeat
+ background-attachment
+ background-position




### 2.4 文本格式

#### 2.4.1 文本颜色
颜色属性被用来设置文字的颜色。  
颜色是通过CSS最经常的指定：

+ 十六进制值 - 如: ＃FF0000
+ 一个RGB值 - 如: RGB(255,0,0)
+ 颜色的名称 - 如: red


一个网页的背景颜色是指在主体内的选择：
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
body {color:red;}
h1 {color:#00ff00;}
p.ex {color:rgb(0,0,255);}
</style>
</head>

<body>
<h1>这是标题 1</h1>
<p>这是一个普通的段落。请注意,本文是红色的。页面中定义默认的文本颜色选择器。</p>
<p class="ex">这是一个类为"ex"的段落。这个文本是蓝色的。</p>
</body>
</html>
```
![](2025-04-23-11-22-42.png)


#### 2.4.2 文本对齐方式
文本排列属性是用来设置文本的水平对齐方式。

文本可居中或对齐到左或右,两端对齐.

当text-align设置为"justify"，每一行被展开为宽度相等，左，右外边距是对齐（如杂志和报纸）。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
h1 {text-align:center;}
p.date {text-align:right;}
p.main {text-align:justify;}
</style>
</head>

<body>
<h1>CSS text-align 实例</h1>
<p class="date">2015 年 3 月 14 号</p>
<p class="main">“当我年轻的时候，我梦想改变这个世界；当我成熟以后，我发现我不能够改变这个世界，我将目光缩短了些，决定只改变我的国家；当我进入暮年以后，我发现我不能够改变我们的国家，我的最后愿望仅仅是改变一下我的家庭，但是，这也不可能。当我现在躺在床上，行将就木时，我突然意识到：如果一开始我仅仅去改变我自己，然后，我可能改变我的家庭；在家人的帮助和鼓励下，我可能为国家做一些事情；然后，谁知道呢?我甚至可能改变这个世界。”</p>
<p><b>注意：</b> 重置浏览器窗口大小查看 &quot;justify&quot; 是如何工作的。</p>
</body>

</html>
```
![](2025-04-23-11-24-33.png)


#### 2.4.3 文本修饰
text-decoration 属性用来设置或删除文本的装饰。

从设计的角度看 text-decoration属性主要是用来删除链接的下划线：
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
a {text-decoration:none;}
</style>
</head>

<body>
<p>链接到: <a href="https://www.runoob.com/">runoob.com</a></p>
</body>

</html>
```
![](2025-04-23-11-46-13.png)

也可以这样装饰文字：
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
h1 {text-decoration:overline;}
h2 {text-decoration:line-through;}
h3 {text-decoration:underline;}
</style>
</head>

<body>
<h1>This is heading 1</h1>
<h2>This is heading 2</h2>
<h3>This is heading 3</h3>
</body>

</html>
```
![](2025-04-23-11-47-58.png)

我们不建议强调指出不是链接的文本，因为这常常混淆用户。
#### 2.4.4 文本转换
文本转换属性是用来指定在一个文本中的大写和小写字母。

可用于所有字句变成大写或小写字母，或每个单词的首字母大写。
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
p.uppercase {text-transform:uppercase;}
p.lowercase {text-transform:lowercase;}
p.capitalize {text-transform:capitalize;}
</style>
</head>

<body>
<p class="uppercase">This is some text.</p>
<p class="lowercase">This is some text.</p>
<p class="capitalize">This is some text.</p>
</body>
</html>
```
![](2025-04-23-12-03-02.png)


#### 2.4.5 文本缩进
文本缩进属性是用来指定文本的第一行的缩进。
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
p {text-indent:50px;}
</style>
</head>
<body>

<p>In my younger and more vulnerable years my father gave me some advice that I've been turning over in my mind ever since. 'Whenever you feel like criticizing anyone,' he told me, 'just remember that all the people in this world haven't had the advantages that you've had.'</p>

</body>
</html>
```
![](2025-04-23-12-03-59.png)



### 2.5 CSS字体
CSS字体属性定义字体，加粗，大小，文字样式。


#### 2.5.1 字型
在CSS中，有两种类型的字体系列名称：
+ 通用字体系列 - 拥有相似外观的字体系统组合
    + serif 衬线字体族
    + sans-serif 无衬线字体族
    + cursive 手写字体族
    + fantasy 梦幻字体族
    + monospace 等宽字体族
+ 特定字体系列 - 一个特定的字体系列（如 "Times" 或 "Courier"）



#### 2.5.2 字体系列font-family
font-family 属性设置文本的字体系列。

font-family 属性应该设置几个字体名称作为一种"后备"机制，如果浏览器不支持第一种字体，他将尝试下一种字体。

**注意: 如果字体系列的名称超过一个字，它必须用引号，如Font Family："宋体"。**

多个字体系列是用一个逗号分隔指明：
```css
p{font-family:"Times New Roman", Times, serif;}
```

#### 2.5.3 字体样式font-style

主要是用于指定斜体文字的字体样式属性。  

这个属性有三个值：  
+ 正常 - 正常显示文本
+ 斜体 - 以斜体字显示的文字
+ 倾斜的文字 - 文字向一边倾斜（和斜体非常类似，但不太支持）
```css
p.normal {font-style:normal;}
p.italic {font-style:italic;}
p.oblique {font-style:oblique;}
```

**italic 和 oblique 的区别**  
一种字体有粗体、斜体、下划线、删除线等诸多属性。但是并不是所有字体都做了这些，一些不常用的字体，或许就只有个正常体，如果你用 italic，就没有效果了~这时候你就要用 oblique，可以理解成 italic 是使用文字的斜体，oblique 是让没有斜体属性的文字倾斜！  

**换种说法**  
italic 和 oblique 都是向右倾斜的文字, 但区别在于 italic 是指斜体字，而 oblique 是倾斜的文字，对于没有斜体的字体应该使用 oblique 属性值来实现倾斜的文字效果。


#### 2.5.4 字体大小font-size
font-size 属性设置文本的大小。

能否管理文字的大小，在网页设计中是非常重要的。**但是，你不能通过调整字体大小使段落看上去像标题，或者使标题看上去像段落。**

请务必使用正确的HTML标签，就`<h1>` - `<h6>`表示标题和`<p>`表示段落：

**字体大小的值可以是绝对或相对的大小。**
+ 绝对大小：
    + 设置一个指定大小的文本
    + 不允许用户在所有浏览器中改变文本大小
    + 确定了输出的物理尺寸时绝对大小很有用

+ 相对大小：
    + 相对于周围的元素来设置大小
    + 允许用户在浏览器中改变文字大小
    + 如果你不指定一个字体的大小，默认大小和普通文本段落一样，是16像素（16px=1em）。


“px” 是像素（Pixel）的缩写，是一种绝对长度单位，表示屏幕上的一个最小显示单元 。“em” 是相对长度单位，相对于当前元素的字体大小。在浏览器中默认的文字大小是 16px，所以在这种默认情况下，1em 和 16px 相等，即 16px=1em。当修改了父元素的字体大小时，em 会相应改变，而像素值不会改变。


设置文字的大小与像素，让您完全控制文字大小：
```css
h1 {font-size:40px;}
h2 {font-size:30px;}
p {font-size:14px;}
```
虽然可以通过浏览器的缩放工具调整文本大小，但是，这种调整是整个页面，而不仅仅是文本


#### 2.5.5 用em来设置字体大小
为了避免Internet Explorer 中无法调整文本的问题，许多开发者使用 em 单位代替像素。

em的尺寸单位由W3C建议。

**1em和当前字体大小相等。在浏览器中默认的文字大小是16px。**

因此，1em的默认大小是16px。可以通过下面这个公式将像素转换为em：px/16=em
```css
h1 {font-size:2.5em;} /* 40px/16=2.5em */
h2 {font-size:1.875em;} /* 30px/16=1.875em */
p {font-size:0.875em;} /* 14px/16=0.875em */
```
![](2025-04-23-13-52-35.png)



#### 2.5.6 字体粗细font-weight
三段文字设置不同的字体粗细
```css
p.normal {font-weight:normal;}
p.thick {font-weight:bold;}
p.thicker {font-weight:900;}
```
+ normal	默认值。定义标准的字符。
+ bold	定义粗体字符。
+ bolder	定义更粗的字符。
+ lighter	定义更细的字符。
+ 定义由细到粗的字符,400 等同于 normal，而 700 等同于 bold。
    + 100
    + 200
    + 300
    + 400
    + 500
    + 600
    + 700
    + 800
    + 900
+ inherit	规定应该从父元素继承字体的粗细。


### 2.6 CSS链接
不同的链接可以有不同的样式。

#### 2.6.1 链接样式  
链接的样式，可以用任何CSS属性（如颜色，字体，背景等）。  

特别的链接，可以有不同的样式，这取决于他们是什么状态。  

这四个链接状态是：
+ a:link - 正常，未访问过的链接
+ a:visited - 用户已访问过的链接
+ a:hover - 当用户鼠标放在链接上时
+ a:active - 链接被点击的那一刻

```css
a:link {color:#000000;}      /* 未访问链接*/
a:visited {color:#00FF00;}  /* 已访问链接 */
a:hover {color:#FF00FF;}  /* 鼠标移动到链接上 */
a:active {color:#0000FF;}  /* 鼠标点击时 */
```

当设置为若干链路状态的样式，也有一些顺序规则：
+ a:hover 必须跟在 a:link 和 a:visited后面
+ a:active 必须跟在 a:hover后面


#### 2.6.2 链接的修饰

**文本修饰**
text-decoration 属性主要用于删除链接中的下划线
```css
a:link {text-decoration:none;}
a:visited {text-decoration:none;}
a:hover {text-decoration:underline;}
a:active {text-decoration:underline;}
```

**背景颜色**
背景颜色属性指定链接背景色：
```css
a:link {background-color:#B2FF99;}
a:visited {background-color:#FFFF85;}
a:hover {background-color:#FF704D;}
a:active {background-color:#FF704D;}
```


### 2.7 CSS列表
CSS 列表属性作用如下：
+ 设置不同的列表项标记为有序列表
+ 设置不同的列表项标记为无序列表
+ 设置列表项标记为图像

#### 2.7.1 两种类型
在 HTML中，有两种类型的列表：
+ 无序列表 ul - 列表项标记用特殊图形（如小黑点、小方框等）
+ 有序列表 ol - 列表项的标记有数字或字母

使用 CSS，可以列出进一步的样式，并可用图像作列表项标记。

无序列表:
+ Coffee
+ Tea
+ Coca Cola
+ Coffee
+ Tea
+ Coca Cola

有序列表:
1. Coffee
2. Tea
3. Coca Cola
4. Coffee
5. Tea
6. Coca Cola

#### 2.7.2 列表项标记list-style-type
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
ul.a {list-style-type:circle;}
ul.b {list-style-type:square;}
ol.c {list-style-type:upper-roman;}
ol.d {list-style-type:lower-alpha;}
</style>
</head>

<body>
<p>无序列表实例:</p>

<ul class="a">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Coca Cola</li>
</ul>

<ul class="b">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Coca Cola</li>
</ul>

<p>有序列表实例:</p>

<ol class="c">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Coca Cola</li>
</ol>

<ol class="d">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Coca Cola</li>
</ol>

</body>
</html>
```
一些值是无序列表，以及有些是有序列表。
![](2025-04-23-15-05-27.png)


**作为列表项标记的图像**

要指定列表项标记的图像，使用列表样式图像属性：

```css
ul
{
    list-style-image: url('sqpurple.gif');
}
```
![](2025-04-23-15-06-43.png)


**浏览器兼容性解决方案**
```css
ul
{
    list-style-type: none;
    padding: 0px;
    margin: 0px;
}
ul li
{
    background-image: url(sqpurple.gif);
    background-repeat: no-repeat;
    background-position: 0px 5px; 
    padding-left: 14px; 
}
```

+ ul:
    + 设置列表类型为没有列表项标记
    + 设置填充和边距 0px（浏览器兼容性）
+ ul 中所有 li:
    + 设置图像的 URL，并设置它只显示一次（无重复）
    + 您需要的定位图像位置（左 0px 和上下 5px）
    + 用 padding-left 属性把文本置于列表中


#### 2.7.3 简写属性
在单个属性中可以指定所有的列表属性。这就是所谓的简写属性。

为列表使用简写属性，列表样式属性设置如下：
```css
ul
{
    list-style: square url("sqpurple.gif");
}
```
可以按顺序设置如下属性：

list-style-type
list-style-position (有关说明，请参见下面的CSS属性表)
list-style-image
如果上述值丢失一个，其余仍在指定的顺序，就没关系。


#### 2.7.4 移除默认设置
list-style-type:none 属性可以用于移除小标记。  
默认情况下列表 `<ul> `或 `<ol> `还设置了内边距和外边距，  
可使用 margin:0 和 padding:0 来移除:  
```css
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
```



### 2.8 CSS表格
使用 CSS 可以使 HTML 表格更美观。


#### 2.8.1 表格边框
指定CSS表格边框，使用border属性。

下面的例子指定了一个表格的Th和TD元素的黑色边框：
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title>
<style>
table,th,td
{
	border:1px solid black;
}
</style>
</head>

<body>
<table>
<tr>
<th>Firstname</th>
<th>Lastname</th>
</tr>
<tr>
<td>Peter</td>
<td>Griffin</td>
</tr>
<tr>
<td>Lois</td>
<td>Griffin</td>
</tr>
</table>
</body>
</html>
```
请注意，在上面的例子中的表格有双边框。这是因为表和th/ td元素有独立的边界。

为了显示一个表的单个边框，使用 border-collapse属性。

![](2025-04-25-22-44-12.png)



#### 2.8.2 折叠边框
border-collapse 属性设置表格的边框是否被折叠成一个单一的边框或隔开：
```css
table
{
    border-collapse:collapse;
}
table,th, td
{
    border: 1px solid black;
}
```

![](2025-04-25-22-46-21.png)


#### 2.8.3 表格宽度和高度
Width和height属性定义表格的宽度和高度。

下面的例子是设置100％的宽度，50像素的th元素的高度的表格：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title>
<style>
table,td,th
{
	border:1px solid black;
}
table
{
	width:100%;
}
th
{
	height:50px;
}
</style>
</head>

<body>
<table>
<tr>
<th>Firstname</th>
<th>Lastname</th>
<th>Savings</th>
</tr>
<tr>
<td>Peter</td>
<td>Griffin</td>
<td>$100</td>
</tr>
<tr>
<td>Lois</td>
<td>Griffin</td>
<td>$150</td>
</tr>
<tr>
<td>Joe</td>
<td>Swanson</td>
<td>$300</td>
</tr>
<tr>
<td>Cleveland</td>
<td>Brown</td>
<td>$250</td>
</tr>
</table>
</body>
</html>
```
![](2025-04-25-22-51-30.png)

#### 2.8.4 表格文字对齐
表格中的文本对齐和垂直对齐属性。

text-align属性设置水平对齐方式，向左，右，或中心：
```css
td
{
    text-align:right;
}
```
垂直对齐属性设置垂直对齐，比如顶部，底部或中间：
```css
td
{
    height:50px;
    vertical-align:bottom;
}
```


#### 2.8.5 表格填充
如需控制边框和表格内容之间的间距，应使用td和th元素的填充属性：
```css
td
{
    padding:15px;
}
```



#### 2.8.6 表格颜色
下面的例子指定边框的颜色，和th元素的文本和背景颜色：
```css
table, td, th
{
    border:1px solid green;
}
th
{
    background-color:green;
    color:white;
}
```




### 2.9 CSS盒子模型


#### 2.9.1 CSS 盒子模型(Box Model)
所有HTML元素可以看作盒子，在CSS中，"box model"这一术语是用来设计和布局时使用。

CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容。

盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。

下面的图片说明了盒子模型(Box Model)：
![](2025-04-25-23-01-57.png)

不同部分的说明：

+ Margin(外边距) - 清除边框外的区域，外边距是透明的。
+ Border(边框) - 围绕在内边距和内容外的边框。
+ Padding(内边距) - 清除内容周围的区域，内边距是透明的。
+ Content(内容) - 盒子的内容，显示文本和图像。

为了正确设置元素在所有浏览器中的宽度和高度，你需要知道的盒模型是如何工作的。



#### 2.9.2 元素的宽度和高度
当您指定一个 CSS 元素的宽度和高度属性时，你只是设置内容区域的宽度和高度。要知道，完整大小的元素，你还必须添加内边距，边框和外边距。

下面的例子中的元素的总宽度为 450px：
```css
div {
    width: 300px;
    border: 25px solid green;
    padding: 25px;
    margin: 25px;
}
```
让我们自己算算：
300px (宽)
+ 50px (左 + 右填充)
+ 50px (左 + 右边框)
+ 50px (左 + 右边距)
= 450px

试想一下，你只有 250 像素的空间。让我们设置总宽度为 250 像素的元素:
```css
div {
    width: 220px;
    padding: 10px;
    border: 5px solid gray;
    margin: 0; 
}
```
+ 最终元素的总宽度计算公式是这样的：  
    + 总元素的宽度=宽度+左填充+右填充+左边框+右边框+左边距+右边距
+ 元素的总高度最终计算公式是这样的：  
    + 总元素的高度=高度+顶部填充+底部填充+上边框+下边框+上边距+下边距


### 2.10 CSS边框
CSS 边框（Border）是用于定义元素边框样式的属性。

边框可以应用于任何 HTML 元素，用于增强视觉效果、分隔内容或突出显示元素。

CSS 边框属性主要包括边框宽度、边框样式、边框颜色以及简写属性。

#### 2.10.1 CSS边框属性
![](2025-04-25-23-17-42.png)


#### 2.10.2 边框样式border-style
边框样式属性指定要显示什么样的边界。

border-style 属性用于指定要显示的边框类型。

允许的值如下：
+ dotted：定义点状边框。
+ dashed：定义虚线边框。
+ solid：定义实线边框。
+ double：定义双线边框。
+ groove：定义三维沟槽边框。效果取决于 border-color 的值。
+ ridge：定义三维脊状边框。效果取决于 border-color 的值。
+ inset：定义三维嵌入边框。效果取决于 border-color 的值。
+ outset：定义三维突出边框。效果取决于 border-color 的值。
+ none：定义无边框。
+ hidden：定义隐藏边框。


**border-style 演示:**
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
p.none {border-style:none;}
p.dotted {border-style:dotted;}
p.dashed {border-style:dashed;}
p.solid {border-style:solid;}
p.double {border-style:double;}
p.groove {border-style:groove;}
p.ridge {border-style:ridge;}
p.inset {border-style:inset;}
p.outset {border-style:outset;}
p.hidden {border-style:hidden;}
p.mix {border-style: dotted dashed solid double;}
</style>
</head>

<body>
<p class="none">无边框。</p>
<p class="dotted">虚线边框。</p>
<p class="dashed">虚线边框。</p>
<p class="solid">实线边框。</p>
<p class="double">双边框。</p>
<p class="groove"> 凹槽边框。</p>
<p class="ridge">垄状边框。</p>
<p class="inset">嵌入边框。</p>
<p class="outset">外凸边框。</p>
<p class="hidden">隐藏边框。</p>
<p class="mix">混合边框</p>
</body>

</html>
```
![](2025-04-25-23-20-15.png)

#### 2.11.3 边框宽度
您可以通过 border-width 属性为边框指定宽度。

为边框指定宽度有两种方法：可以指定长度值，比如 2px 或 0.1em(单位为 px, pt, cm, em 等)，或者使用 3 个关键字之一，它们分别是 thick 、medium（默认值） 和 thin。

**注意**：CSS 没有定义 3 个关键字的具体宽度，所以一个用户可能把 thick 、medium 和 thin 分别设置为等于 5px、3px 和 2px，而另一个用户则分别设置为 3px、2px 和 1px。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title>
<style>
p.one 
{
	border-style:solid;
	border-width:5px;
}
p.two 
{
	border-style:solid;
	border-width:medium;
}
p.three
{
	border-style:solid;
	border-width:1px;
}
</style>
</head>

<body>
<p class="one">一些文本。</p>
<p class="two">一些文本。</p>
<p class="three">一些文本。</p>
<p><b>注意:</b> "border-width" 属性 如果单独使用则不起作用。要先使用 "border-style" 属性来设置边框。</p>
</body>

</html>
```
![](2025-04-25-23-24-17.png)


#### 2.11.4 边框颜色
border-color属性用于设置边框的颜色。可以设置的颜色：

name - 指定颜色的名称，如 "red"  
RGB - 指定 RGB 值, 如 "rgb(255,0,0)"  
Hex - 指定16进制值, 如 "#ff0000"  
您还可以设置边框的颜色为"transparent"。  
 
**注意： border-color单独使用是不起作用的，必须得先使用border-style来设置边框样式。**
```css
p.one
{
    border-style:solid;
    border-color:red;
}
p.two
{
    border-style:solid;
    border-color:#98bf21;
}
```
![](2025-04-25-23-30-01.png)




#### 2.11.5 边框-单独设置各边



