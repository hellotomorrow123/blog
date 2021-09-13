---
title: css盒子模型
date: 2021/09/05 20:46:25
categories:
- [前端，css]
tags:
---

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>48-CSS盒子模型</title>
    <style>
        span,a,b,strong{
            display: inline-block;
            width: 100px;
            height: 100px;
            border: 6px solid #000;
            padding: 20px;
            margin: 20px;
        }

    </style>
</head>
<body>
<!--
1.什么是CSS盒子模型?
CSS盒子模型仅仅是一个形象的比喻, HTML中所有的标签都是盒子

结论
1.在HTML中所有的标签都可以设置
宽度/高度  == 指定可以存放内容的区域
内边距  == 填充物
边框  == 手机盒子自己
外边距  == 盒子和盒子之间的间隙
-->
<span>我是span</span>
<a href="#">我是超链接</a>
<b>我是加粗</b>
<strong>我是强调</strong>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>49-盒子模型宽度和高度</title>
</head>
<body>
<!--
1.内容的宽度和高度
就是通过width/height属性设置的宽度和高度

2.元素的宽度和高度
宽度 = 左边框 + 左内边距 + width + 右内边距 + 右边框
高度 同理可证

3.元素空间的宽度和高度
宽度 = 左外边距 + 左边框 + 左内边距 + width + 右内边距 + 右边框 + 右外边距
高度 同理可证
-->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>50-盒子宽高练习</title>
    <style>
        /*判断是否是内容宽高为100的盒子
        只需要看width/height是否为100即可*/
        .box1{
            width:50px;
            height: 50px;
            padding: 25px;
            background-color: green;
        }
        .box2{
            width: 96px;
            height: 96px;
            border: 2px solid #000;
        }
        .box3{
            width: 100px;
            height: 100px;
            background-color: yellow;
        }
        /*判断是否是元素宽高为200的盒子
        只需要看 边框 + 内边距 + 内容宽度/内容高度 时候等于200即可*/
        .box4{
            width: 100px;
            height: 100px;
            margin: 50px;
            background-color: red;
        }
        .box5{
            /*25+25+150 = 200*/
            width: 150px;
            height: 150px;
            border: 25px solid #000;
        }
        .box6{
            /*25+25+150 = 200*/
            /*5+5+20+20+150=200*/
            width: 150px;
            height: 150px;
            /*padding: 25px;*/
            padding:20px;
            border: 5px solid #000;
            background-color: blue;
        }
        /*判断是否是元素空间宽高为300的盒子
        只需要看 外边距+边框+内边距+内容宽度/内容高度*/
        .box7{
            width: 300px;
            height: 300px;
            background-color: purple;
        }
        .box8{
            /*
            50+50+25+25+25+25+100
            100 +50 +50 + 100
            300
            */
            width: 100px;
            height: 100px;
            padding: 25px;
            border: 25px solid #000;
            margin: 50px;
        }
        /*现有如下盒子模型, 要求增加padding属性为25之后仍然保持元素宽高为200

        元素宽高 = 边框 + 内边距 + 内容宽高
                 = 0 + 0 + 200 = 200
                 = 0 + 25 + 25 + 200 = 250
                 = 0 + 25 + 25 + 150 = 200
         规律:
         1.增加了padding之后元素的宽高也会发生变化
         2.如果增加了padding之后还想保持元素的宽高, 那么就必须减去内容的宽高
        */
        .box9{
            width: 150px;
            height: 150px;
            padding: 25px;
            background-color: red;
        }
        /*现有如下盒子模型, 要求增加border属性为20之后仍然保持元素宽高为200
        元素宽高 = 边框 + 内边距 + 内容宽高
                 = 0 + 0 + 200 = 200
                 = 0 + 20 + 20 + 200 = 240
                 = 0 + 20 + 20 + 160 = 200
          规律:
         1.增加了border之后元素的宽高也会发生变化
         2.如果增加了border之后还想保持元素的宽高, 那么就必须减去内容的宽高
        */
        .box10{
            width: 160px;
            height: 160px;
            border: 20px solid #000;
            background-color: deepskyblue;
        }
    </style>
</head>
<body>
<!--<div class="box1">box1</div>-->
<!--<div class="box2">box2</div>-->
<!--<div class="box3">box3</div>-->
<!--<hr>-->
<!--<div class="box4">box4</div>-->
<!--<div class="box5">box5</div>-->
<!--<div class="box6">box6</div>-->
<!--<hr>-->
<!--<div class="box7">box7</div>-->
<!--<div class="box8">box8</div>-->
<!--<hr>-->
<div class="box9">box9</div>
<div class="box10">box10</div>
</body>
</html>
```

```html
<!--<!DOCTYPE html>-->
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>51-盒子box-sizing属性</title>
    <style>
        .content{
            width: 300px;
            height: 300px;
            background-color: red;
        }
        .aside{
            width: 100px;
            height: 200px;
            background-color: green;
            float: left;
        }
        .article{
            /*
            1.CSS3中新增了一个box-sizing属性, 这个属性可以保证我们给盒子新增padding和border之后, 盒子元素的宽度和高度不变
            2.box-sizing属性是如何保证增加padding和border之后, 盒子元素的宽度和高度不变
            和我们前面学习的原理一样, 增加padding和border之后要想保证盒子元素的宽高不变, 那么就必须减去一部分内容的宽度和高度
            3.box-sizing取值
            3.1content-box
            元素的宽高 = 边框 + 内边距 + 内容宽高
            3.2border-box
            元素的宽高 = width/height的宽高
            */
            box-sizing: border-box;
            width: 200px;
            height: 200px;
            background-color: blue;
            float: right;
            border: 20px solid #000;
            padding: 20px;
        }
    </style>
</head>
<body>

<div class="content">
    <div class="aside"></div>
    <div class="article"></div>
</div>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>52-盒子模型练习2</title>
    <style>
        .big{
            /*width: 350px;*/
            /*height: 350px;*/
            width: 500px;
            height: 500px;
            background-color: red;
            /*
            box-sizing: border-box;
            padding-top:150px;
            padding-left:150px;
            */
            border: 5px solid #000;
        }
        .small{
            width: 200px;
            height: 200px;
            background-color: blue;
            /*
            注意点:
            1.如果两个盒子是嵌套关系, 那么设置了里面一个盒子顶部的外边距, 外面一个盒子也会被顶下来
            2.如果外面的盒子不想被一起定下来,那么可以给外面的盒子添加一个边框属性
            3.在企业开发中, 一般情况下如果需要控制嵌套关系盒子之间的距离, 应该首先考虑padding, 其次再考虑margin
            margin本质上是用于控制兄弟关系之间的间隙的
            */
            /*
            margin-top:150px;
            margin-left:150px;
            */
            /*
            注意点:
            1.在嵌套关系的盒子中, 我们可以利用margin: 0 auto;的方式来让里面的盒子在外面的盒子中水平居中
            2.margin: 0 auto; 只对水平方向有效, 对垂直方向无效
            */
            margin:150px auto;
        }
    </style>
</head>
<body>
<!--
需求
有一个大盒子, 元素的宽高是500
有一个小盒子, 元素的宽高是200
要求将小盒子放到大盒子中, 并且让小盒子在大盒子中水平垂直居中
-->

<div class="big">
    <div class="small"></div>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>53-盒子居中和内容居中</title>
    <style>
        .father{
            width: 800px;
            height: 500px;
            background-color: red;
            /*text-align: center;*/
            margin:0 auto;
        }
        .son{
            width: 100px;
            height: 100px;
            background-color: blue;
        }
    </style>
</head>
<body>
<!--
1.text-align:center;和margin:0 auto;区别
text-align: center;作用
设置盒子中存储的文字/图片水平居中

margin:0 auto;作用
让盒子自己水平居中
-->
<div class="father">
    我是文字<br/>
    <img src="images/girl.jpg" alt="">
    <!--<div class="son"></div>-->
</div>
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
        /*
        *{
            margin: 0;
            padding: 0;
        }
        */
        body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,legend,input,textarea,p,blockquote,th,td{
            margin:0;padding:0
        }
        p{
            width: 610px;
            height: 110px;
            background-color: #cdcdcd;
            border: 1px solid #000000;
        }
    </style>
</head>
<body>
<!--
1.为什么要清空默认边距(外边距和内边距)
在企业开发中为了更好的控制盒子的宽高和计算盒子的宽高等等, 所以在企业开发中, 编写代码之前第一件事情就是清空默认的边距

2.如何清空默认的边距
格式
*{
            margin: 0;
            padding: 0;
}

3.注意点
通配符选择器会找到(遍历)当前界面中所有的标签, 所以性能不好
企业开发中可以从这个网址中拷贝
http://yui.yahooapis.com/3.18.1/build/cssreset/cssreset-min.css

-->
<p>葬爱:非主流文化的常用词，是当今网络流行术语.且流行于非主流杀马特之中。葬，即埋葬，爱，即爱情，翻译成外语就bury love</p>
</body>
</html>
```

