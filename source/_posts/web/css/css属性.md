---
title: css属性
date: 2021/09/04 20:46:25
categories:
- [前端]
tags:
---

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>03-文字属性</title>
    <style>
        p{
            font-style: italic;
            font-weight: bold;
            font-size: 10px;
            font-family:"楷体";
        }
    </style>
</head>
<body>
<!--
1.规定文字样式的属性
格式：font-style: italic;
取值：
normal ： 正常的， 默认就是正常的
italic :  倾斜的
快捷键：
fs font-style: italic;
fsn font-style: normal;

2.规定文字粗细的属性
格式： font-weight: bold;
单词取值:
bold 加粗
bolder  比加粗还要粗
lighter 细线， 默认就是细线
数字取值：
100-900之间整百的数字

快捷键
fw font-weight:;
fwb font-weight: bold;
fwbr  font-weight: bolder;

3.规定文字大小的属性
格式：font-size: 30px;
单位：px（像素 pixel）
注意点： 通过font-size设置大小一定要带单位， 也就是一定要写px
快捷键
fz font-size:;
fz30 font-size: 30px;

4.规定文字字体的属性
格式：font-family:"楷体";
注意点：
1.如果取值是中文， 需要用双引号或者单引号括起来
2.设置的字体必须是用户电脑里面已经安装的字体
快捷键
ff font-family:;

-->
<i>我是文字</i>
<b>我是文字</b>
<p>abc我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>04-字体属性补充</title>
    <style>
        p{
            /*
            被注释掉的内容
            */
            /*font-family:"乱七八糟的字体", "微软雅黑";*/
            /*font-family: Arial, "微软雅黑";*/
            font-family:"Microsoft YaHei";
        }
    </style>
</head>
<body>
<!--
1.如果设置的字体不存在, 那么系统会使用默认的字体来显示
默认使用宋体

2.如果设置的字体不存在, 而我们又不想用默认的字体来显示怎么办?
可以给字体设置备选方案
格式:font-family:"字体1", "备选方案1", ...;

3.如果想给中文和英文分别单独设置字体, 怎么办?
但凡是中文字体, 里面都包含了英文
但凡是英文字体, 里面都没有包含中文
也就是说中文字体可以处理英文, 而英文字体不能处理中文
**注意点: 如果想给界面中的英文单独设置字体, 那么英文的字体必须写在中文的前面

4.补充在企业开发中最常见的字体有以下几个
中文: 宋体/黑体/微软雅黑
英文: "Times New Roman"/Arial

还需要知道一点, 就是并不是名称是英文就一定是英文字体
因为中文字体其实都有自己的英文名称, 所以是不是中文字体主要看能不能处理中文
宋体 SimSun
黑体 SimHei
微软雅黑 Microsoft YaHei
-->
<p>abc我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>05-文字属性的缩写</title>
    <style>
        p{
            /*
            font-style: italic;
            font-weight: bold;
            font-size: 10px;
            font-family:"楷体";
            */
            font:bold italic 10px "楷体";
        }
    </style>
</head>
<body>
<!--
缩写格式:
font: style weight size family;
例如:
font:italic bold 10px "楷体";

注意点:
1.在这种缩写格式中有的属性值可以省略
sytle可以省略
weight可以省略
2.在这种缩写格式中style和weight的位置可以交换
3.在这种缩写格式中有的属性值是不可以省略的
size不能省略
family不能省略
4.size和family的位置是不能顺便乱放的
size一定要写在family的前面, 而且size和family必须写在所有属性的最后
-->
<p>abc我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>06-文本属性</title>
    <style>
        p{
            text-decoration: none;
            text-align: left;
            text-indent: 2em;

        }
        a{
            text-decoration: none;
        }
    </style>
</head>
<body>
<!--
1.文本装饰的属性
格式:text-decoration: underline;
取值:
underline 下划线
line-through 删除线
overline 上划线
none 什么都没有, 最常见的用途就是用于去掉超链接的下划线
快捷键:
td  text-decoration: none;
tdu text-decoration: underline;
tdl text-decoration: line-through;
tdo text-decoration: overline;

2.文本水平对齐的属性
格式: text-align: right;
取值:
left 左
right 右
center 中
快捷键
ta text-align: left;
tar text-align: right;
tac text-align: center;

3.文本缩进的属性
格式: text-indent: 2em;
取值:
2em, 其中em是单位, 一个em代表缩进一个文字的宽度
快捷键
ti text-indent:;
ti2e text-indent: 2em;
-->
<u>我是文字</u>
<s>我是文字</s>
<p>我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落我是段落</p>
<a href="#">我是超链接</a>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>07-颜色属性</title>
    <style>
        p{
            /*color: red;*/
            /*color: rgb(255,0,0);*/
            /*color: rgba(255,0,0,1);*/
            color: #FF0000;
            color: #F00;
            /*color: rgba(255,0,0,0.2);*/
            color: #ffee00;
            color: #fe0;
            color: #769abb;
        }
    </style>
</head>
<body>
<!--
1.在CSS中如何通过color属性来修改文字颜色
格式: color: 值;
取值:
1.1英文单词
一般情况下常见的颜色都有对应的英文单词, 但是英文单词能够表达的颜色是有限制的, 也就是说不是所有的颜色都能够通过英文单词来表达

1.2rgb
rgb其实就是三原色, 其中r(red 红色) g(green 绿色) b(blue 蓝色)
格式: rgb(0,0,0)
那么这个格式中的
第一个数字就是用来设置三原色的光源元件红色显示的亮度
第二个数字就是用来设置三原色的光源元件绿色显示的亮度
第三个数字就是用来设置三原色的光源元件蓝色显示的亮度
这其中的每一个数字它的取值是0-255之前, 0代表不发光, 255代表发光, 值越大就越亮

红色: rgb(255,0,0);
绿色: rgb(0,255,0);
蓝色: rgb(0,0,255);
黑色: rgb(0,0,0);
白色: rgb(255,255,255);

在前端开发中其实并不常用黑色
只要让红色/绿色/蓝色的值都一样就是灰色
而且如果这三个值越小那么就越偏黑色, 越大就越偏白色
例如: color: rgb(200,200,200);

1.3rgba
rgba中的rgb和前面讲解的一样, 只不过多了一个a
那么这个a呢代表透明度, 取值是0-1, 取值越小就越透明
例如: color: rgba(255,0,0,0.2);

1.4十六进制
在前端开发中通过十六进制来表示颜色, 其实本质就是RGB
十六进制中是通过每两位表示一个颜色
例如: #FFEE00 FF表示R EE表示G 00表示B

什么是十六进制?
十六进制和十进制一样都是一种计数的方式
在十进制中取值范围0-9, 逢十进一
在十六进制中取值范围0-F, 逢十六进一

9
a  10
b  11
c  12
d  13
e  14
f  15
10  16
11  17
12  18

十六进制和十进制转换的公式
用十六进制的第一位*16 + 十六进制的第二位 = 十进制
15 == 1*16 + 5 = 21
12 == 1*16 + 2 = 18
FF == F*16 + F == 15*16 + 15 == 240 + 15 = 255
00 == 0*16 + 0 = 0

1.5十六进制缩写
在CSS中只要十六进制的颜色每两位的值都是一样的, 那么就可以简写为一位
例如:
#FFEE00 == #FE0

注意点:
1.如果当前颜色对应的两位数字不一样, 那么就不能简写
#123456;

2.如果两位相同的数字不是属于同一个颜色的, 也不能简写
#122334

-->
<p>我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>33-背景颜色</title>
    <style>
        div{
            width: 500px;
            height: 500px;
        }
        .box1{
            background-color: red;
        }
        .box2{
            background-color: rgb(0,255,0);
        }
        .box3{
            background-color: rgba(0,0,255,0.7);
        }
        .box4{
            background-color: #0ff;
        }
    </style>
</head>
<body>
<!--
1.如何设置标签的背景颜色?
在CSS中有一个background-color:属性, 就是专门用来设置标签的背景颜色的

取值:
具体单词
rgb
rgba
十六进制

快捷键:
bc background-color: #fff;

-->
<div class="box1"></div>
<div class="box2"></div>
<div class="box3"></div>
<div class="box4"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>34-背景图片</title>
    <style>
        div{
            width: 500px;
            height: 500px;
        }
        .box1{
            background-image: url(images/girl.jpg);
            /*background-image: url(http://img4.imgtn.bdimg.com/it/u=2278032206,4196312526&fm=21&gp=0.jpg);*/
        }
    </style>
</head>
<body>
<!--
1.如何设置背景图片?
在CSS中有一个叫做background-image: url();的属性, 就是专门用于设置背景图片的

快捷键:
bi background-image: url();

注意点:
1.图片的地址必须放在url()中, 图片的地址可以是本地的地址, 也可以是网络的地址
2.如果图片的大小没有标签的大小大, 那么会自动在水平和垂直方向平铺来填充
3.如果网页上出现了图片, 那么浏览器会再次发送请求获取图片
-->
<div class="box1"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>35-背景平铺属性</title>
    <style>
        /*
        div{
            width: 500px;
            height: 500px;
        }
        .box1{
            background-image: url(images/girl.jpg);
            background-repeat: repeat-y;
        }
        */
        /*
        body{
            background-image: url(images/bg2.jpg);
        }
        */
        div{
            width: 980px;
            height: 60px;
            background-image: url(images/1.png);
        }
    </style>
</head>
<body>
<!--
1.如何控制背景图片的平铺方式?
在CSS中有一个background-repeat属性, 就是专门用于控制背景图片的平铺方式的

取值:
repeat 默认, 在水平和垂直都需要平铺
no-repeat 在水平和垂直都不需要平铺
repeat-x 只在水平方向平铺
repeat-y 只在垂直方向平铺

快捷键
bgr background-repeat:

应用场景:
可以通过背景图片的平铺来降低图片的大小, 提升网页的访问速度
-->
<div class="box1"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>36-背景定位属性</title>
    <style>
        div{
            /*width: 500px;*/
            height: 500px;
        }
        .box1{
            /*background-color: red;*/
            /*background-image: url(images/girl.jpg);*/
            /*background-repeat: no-repeat;*/
            /*background-position: left top;*/
            /*background-position: right top;*/
            /*background-position: right bottom;*/
            /*background-position: left bottom;*/
            /*background-position: center center;*/
            /*background-position: left center;*/
            /*background-position: center top;*/
            /*background-position: 100px 0;*/
            /*background-position: 100px 200px;*/
            /*background-position: -100px -100px;*/
            background-image: url(images/yxlm.jpg);
            background-position: center top;
        }
    </style>
</head>
<body>
<!--
1.如何控制背景图片的位置?
在CSS中有一个叫做background-position:属性, 就是专门用于控制背景图片的位置

2.格式:
background-position: 水平方向 垂直方向;

3.取值
2.1具体的方位名词
水平方向: left center right
垂直方向: top center bottom

2.2具体的像素
例如: background-position: 100px 200px;
记住一定要写单位, 也就是一定要写px
记住具体的像素是可以接收负数的

快捷键:
bp background-position: 0 0;

注意点:
同一个标签可以同时设置背景颜色和背景图片, 如果颜色和图片同时存在, 那么图片会覆盖颜色
-->

<div class="box1">
    <!--<img src="images/yxlm.jpg" alt="">-->
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>37-背景缩写</title>
    <style>
        div{
            /*width: 500px;*/
            /*height: 500px;*/
            /*
            background-color: red;
            background-image: url(images/girl.jpg);
            background-repeat: no-repeat;
            background-position: left bottom;
            */
            /*background: red url(images/girl.jpg) no-repeat left bottom;*/
            /*background: red;*/
            /*background: url(images/girl.jpg);*/
        }

        body{
            background-image: url(images/girl.jpg);
            background-repeat: no-repeat;
            /*background-attachment: scroll;*/
            background-attachment:fixed;
        }
    </style>
</head>
<body>
<!--
1.背景属性缩写的格式
background: 背景颜色 背景图片 平铺方式 关联方式 定位方式;

快捷键:
bg+ background: #fff url() 0 0 no-repeat;

2.注意点：
background属性中， 任何一个属性都可以被省略

3.什么是背景关联方式？
默认情况下背景图片会随着滚动条的滚动而滚动， 如果不想让背景图片随着滚动条的滚动而滚动， 那么我们就可以修改背景图片和滚动条的关联方式

4.如何修改背景关联方式？
在CSS中有一个叫做background-attachment的属性， 这个属性就是专门用于修改关联方式的

格式
background-attachment：scroll;

取值：
scroll 默认值， 会随着滚动条的滚动而滚动
fixed 不会随着滚动条的滚动而滚动

快捷键:
ba background-attachment:;
-->

<div></div>
我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字我是文字
<br>
我是文字
<br>
我是文字
<br>
我是文字
<br>
我是文字
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>38-背景图片和插入图片区别</title>
    <style>
        div{
            /*width: 150px;*/
            /*height: 170px;*/
            width: 300px;
            height: 300px;
            background-color: red;
        }
        .box1{
            background-image: url(images/girl.jpg);
            background-repeat:no-repeat;
            background-position: right bottom;
        }
    </style>
</head>
<body>
<!--
1.背景图片和插入图片区别?
1.1
背景图片仅仅是一个装饰, 不会占用位置
插入图片会占用位置

1.2
背景图片有定位属性, 所以可以很方便的控制图片的位置
插入图片没有定位属性, 所有控制图片的位置不太方便

1.3
插入图片的语义比背景图片的语义要强, 所以在企业开发中如果你的图片想被搜索引擎收录, 那么推荐使用插入图片
-->
<div class="box1">我是文字</div>
<div class="box2">
    <img src="images/girl.jpg" alt="">
    我是文字
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>39-背景图片练习</title>
    <style>
        .box1{
            width: 1024px;
            height: 768px;
            background-image: url(images/bybg.jpg);
        }
        .box2{
            /*background-color: red;*/
            width: 1024px;
            height: 768px;
            background-image: url(images/bybottom.png);
            background-position: center bottom;
            background-repeat:no-repeat;
            /*background-position: 100px 200px;*/
        }
    </style>
</head>
<body>
<div class="box1">
    <div class="box2"></div>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>42-边框属性上</title>
    <style>
        .box{
            width: 100px;
            height: 100px;
            background-color: red;
            /*border: 5px solid blue;*/
            /*border: 5px solid;*/
            /*border: 5px blue;*/
            /*border: solid blue;*/

            border-top:5px solid blue;
            border-right:10px dashed green;
            border-bottom:15px dotted purple;
            border-left:20px double pink;
        }
    </style>
</head>
<body>
<!--
1.什么边框?
边框就是环绕在标签宽度和高度周围的线条

2.边框属性的格式
2.1连写(同时设置四条边的边框)
border: 边框的宽度 边框的样式 边框的颜色;

快捷键:
bd+ border: 1px solid #000;

注意点:
1.连写格式中颜色属性可以省略, 省略之后默认就是黑色
2.连写格式中样式不能省略, 省略之后就看不到边框了
3.连写格式中宽度可以省略, 省略之后还是可以看到边框

2.2连写(分别设置四条边的边框)
border-top: 边框的宽度 边框的样式 边框的颜色;
border-right: 边框的宽度 边框的样式 边框的颜色;
border-bottom: 边框的宽度 边框的样式 边框的颜色;
border-left: 边框的宽度 边框的样式 边框的颜色;

快捷键:
bt+ border-top: 1px solid #000;
br+
bb+
bl+
-->
<div class="box"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>43-边框属性下</title>
    <style>
        .box{
            width: 500px;
            height: 500px;
            background-color: red;
            /*border-width: 5px 10px 15px 20px;*/
            /*border-style: solid dashed dotted double;*/
            /*border-color: blue green purple pink;*/
            /*border-color: blue green purple;*/
            /*border-color: blue green;*/
            /*border-color: blue;*/

            border-top-width: 5px;
            border-top-style: solid;
            border-top-color: blue;

            border-right-width: 10px;
            border-right-style: dashed;
            border-right-color: green;

            border-bottom-width: 15px;
            border-bottom-style: dotted;
            border-bottom-color: purple;

            border-left-width: 20px;
            border-left-style: double;
            border-left-color: pink;
        }
    </style>
</head>
<body>
<!--
2.3连写(分别设置四条边的边框)
border-width: 上 右 下 左;
border-style: 上 右 下 左;
border-color: 上 右 下 左;

注意点:
1.这三个属性的取值是按照顺时针来赋值, 也就是按照上右下左来赋值, 而不是按照日常生活中的上下左右
2.这三个属性的取值省略时的规律
2.1上 右 下 左 > 上 右 下 > 左边的取值和右边的一样
2.2上 右 下 左 > 上 右 > 左边的取值和右边的一样 下边的取值和上边一样
2.3上 右 下 左 > 上 > 右下左边取值和上边一样


3.非连写(方向+要素)
border-left-width: 20px;
border-left-style: double;
border-left-color: pink;
-->
<div class="box"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>44-边框练习</title>
    <style>
        div{
            width: 100px;
            height: 100px;
        }
        .box1{
            border: 5px solid black;
            /*
            border-top: 5px solid #000;
            border-right: 5px solid #000;
            border-bottom: 5px solid #000;
            border-left: 5px solid #000;
            */
            /*
            border-width:5px;
            border-style:solid;
            border-color: #000;
            */
            /*
            border-top-width: 5px;
            border-top-style: solid;
            border-top-color: #000;

            border-right-width: 5px;
            border-right-style: solid;
            border-right-color: #000;

            border-bottom-width: 5px;
            border-bottom-style: solid;
            border-bottom-color: #000;

            border-left-width: 5px;
            border-left-style: solid;
            border-left-color: #000;
            */
        }
        .box2{
            /*
            border-top: 5px solid red;
            border-right: 5px solid green;
            border-bottom: 5px solid blue;
            border-left: 5px solid purple;
            */
            border-width:5px;
            border-style:solid;
            border-color: red green blue purple;
        }

        .box3{
            border: 5px solid red;
            border-right:5px dashed red;
            /*同一个选择器中后面的边框属性会覆盖前面的边框属性*/
        }
        .box4{
            border: 5px solid red;
            border-style:solid dashed solid dashed;
            /*border-right:5px dashed red;*/
            /*border-left:5px dashed red;*/
        }
        .box5{
            border: 5px solid #000;
            border-bottom: none;
            /*none 代表不需要边框*/
        }
        .box6{
            width: 0px;
            height: 0px;
            border-width:25px;
            border-style:solid;
            border-color: red white blue white;
            border-bottom:none;
        }
    </style>
</head>
<body>

<div class="box1"></div>
<hr>
<div class="box2"></div>
<hr>
<div class="box3"></div>
<hr>
<div class="box4"></div>
<hr>
<div class="box5"></div>
<hr>
<div class="box6"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>45-内边距属性</title>
    <style>
        div{
            width: 98px;
            height: 90px;
            border: 1px solid #000;
            background-color: red;
        }
        .box1{
            padding-top: 20px;
        }
        .box2{
            padding-right:40px;
        }
        .box3{
            padding-bottom:80px;
        }
        .box4{
            padding-left:160px;
        }
        .box5{
            /*padding:20px 40px 80px 160px;*/
            /*padding:20px 40px 80px;*/
            /*padding:20px 40px;*/
            padding:20px;
        }
    </style>
</head>
<body>
<!--
1.什么是内边距?
边框和内容之间的距离就是内边距

2.格式
2.1非连写
padding-top: ;
padding-right: ;
padding-bottom: ;
padding-left: ;

2.2连写
padding: 上 右 下 左;

2.这三个属性的取值省略时的规律
2.1上 右 下 左 > 上 右 下 > 左边的取值和右边的一样
2.2上 右 下 左 > 上 右 > 左边的取值和右边的一样 下边的取值和上边一样
2.3上 右 下 左 > 上 > 右下左边取值和上边一样

注意点:
1.给标签设置内边距之后, 标签占有的宽度和高度会发生变化
2.给标签设置内边距之后, 内边距也会有背景颜色

-->
<div class="box1">我是文字我是文字我是文字我是文字我是文字我是文字我是文字</div>
<hr>
<div class="box2">我是文字我是文字我是文字我是文字我是文字我是文字我是文字</div>
<hr>
<div class="box3">我是文字我是文字我是文字我是文字我是文字我是文字我是文字</div>
<hr>
<div class="box4">我是文字我是文字我是文字我是文字我是文字我是文字我是文字</div>
<hr>
<div class="box5">我是文字我是文字我是文字我是文字我是文字我是文字我是文字</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>46-外边距属性</title>
    <style>
        *{
            padding:0;
            margin:0;
        }
        span{
            display: inline-block;
            width: 100px;
            height: 100px;
            border: 1px solid #000;
            background-color: red;
        }
        div{
            height: 100px;
            border: 1px solid #000;
        }
        .box1{
            /*
            margin-top:20px;
            margin-right:40px;
            margin-bottom:80px;
            margin-left:160px;
            */
            /*margin:20px 40px 80px 160px;*/
            /*margin:20px 40px 80px;*/
            /*margin:20px 40px;*/
            margin:20px;
        }

    </style>
</head>
<body>
<!--
1.什么是外边距?
标签和标签之间的距离就是外边距

2.格式
2.1非连写
margin-top: ;
margin-right: ;
margin-bottom: ;
margin-left: ;

2.2连写
margin: 上 右 下 左;

2.这三个属性的取值省略时的规律
2.1上 右 下 左 > 上 右 下 > 左边的取值和右边的一样
2.2上 右 下 左 > 上 右 > 左边的取值和右边的一样 下边的取值和上边一样
2.3上 右 下 左 > 上 > 右下左边取值和上边一样

注意点:
外边距的那一部分是没有背景颜色的
-->
<span class="box1">我是span</span><span class="box2">我是span</span><span class="box3">我是span</span><div class="box4"></div>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>47-外边距合并现象</title>
    <style>
        span{
            display: inline-block;
            width: 100px;
            height: 100px;
            border: 1px solid #000;
        }
        div{
            height: 100px;
            border: 1px solid #000;
        }
        .hezi1{
            margin-right:50px;
        }
        .hezi2{
            margin-left:100px;
        }
        .box1{
            margin-bottom:50px;
        }
        .box2{
            margin-top:100px;
        }
    </style>
</head>
<body>
<!--
在默认布局的垂直方向上, 默认情况下外边距是不会叠加的, 会出现合并现象, 谁的外边距比较大就听谁的
-->
<span class="hezi1">我是span</span><span class="hezi2">我是span</span>
<div class="box1">我是div</div>
<div class="box2">我是div</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>54-清空默认边距</title>
    <style>
        body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,legend,input,textarea,p,blockquote,th,td{
            margin:0;padding:0
        }
        p{
            width: 610px;
            height: 110px;
            background-color: #cdcdcd;
            border: 1px solid #000000;
        }
        div{
            box-sizing: border-box;
            width: 100px;
            height: 80px;
            border: 1px solid #000;
            line-height: 20px;
            /*line-height: 80px;*/
            padding-top:20px;
            padding-bottom:20px;
        }
    </style>
</head>
<body>
<!--
1.什么是行高?
在CSS中所有的行都有自己的行高

注意点:
行高和盒子高不是同一个概念
行高指的是每行内容的高度
盒子高指的是元素的高度

规律:
1.文字在行高中默认是垂直居中的

2.在企业开发中我们经常将盒子的高度和行高设置为一样, 那么这样就可以保证一行文字在盒子的高度中是垂直居中的
简而言之就是: 要想一行文字在盒子中垂直居中, 那么只需要设置这行文字的"行高等于盒子的高"即可

3.在企业开发中如果一个盒子中有多行文字, 那么我们就不能使用设置行高等于盒子高来实现让文字垂直居中, 只能通过设置padding来让文字居中
-->

<!--<p>葬爱:非主流文化的常用词，是当今网络流行术语.且流行于非主流杀马特之中。葬，即埋葬，爱，即爱情，翻译成外语就bury love</p>-->
<!--<div>我是文字我是文字我是文字</div>-->
<!--<div>我是文字</div>-->
<div>我是文字我是文字我是文字</div>
</body>
</html>
```

