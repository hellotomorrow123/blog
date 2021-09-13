---
title: css过渡模块
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
    <title>88-过渡模块</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 100px;
            height: 50px;
            background-color: red;
            /*告诉系统哪个属性需要执行过渡效果*/
            transition-property: width, background-color;
            /*告诉系统过渡效果持续的时长*/
            transition-duration: 5s, 5s;

            /*transition-property: background-color;*/
            /*transition-duration: 5s;*/
        }
        /*:hover这个伪类选择器除了可以用在a标签上, 还可以用在其它的任何标签上*/
        div:hover{
            width: 300px;
            background-color: blue;
        }
    </style>
</head>
<body>
<!--
1,过渡三要素
1.1必须要有属性发生变化
1.2必须告诉系统哪个属性需要执行过渡效果
1.3必须告诉系统过渡效果持续时长

2.注意点
当多个属性需要同时执行过渡效果时用逗号隔开即可
transition-property: width, background-color;
transition-duration: 5s, 5s;
-->
<div></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>89-过渡模块-其它属性</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div {
            width: 100px;
            height: 50px;
            background-color: red;
            transition-property: width;
            transition-duration: 5s;
            /*告诉系统延迟多少秒之后才开始过渡动画*/
            /*transition-delay: 2s;*/
        }
        div:hover{
            width: 300px;
        }
        ul{
            width: 800px;
            height: 500px;
            margin: 0 auto;
            background-color: pink;
            border: 1px solid #000;
        }
        ul li{
            list-style: none;
            width: 100px;
            height: 50px;
            margin-top: 50px;
            background-color: blue;
            transition-property: margin-left;
            transition-duration: 10s;
        }
        ul:hover li{
            margin-left: 700px;
        }
        ul li:nth-child(1){
            /*告诉系统过渡动画的运动的速度*/
            transition-timing-function: linear;
        }
        ul li:nth-child(2){
            transition-timing-function: ease;
        }
        ul li:nth-child(3){
            transition-timing-function: ease-in;
        }
        ul li:nth-child(4){
            transition-timing-function: ease-out;
        }
        ul li:nth-child(5){
            transition-timing-function: ease-in-out;
        }
    </style>
</head>
<body>
<!--<div></div>-->
<ul>
    <li>linear</li>
    <li>ease</li>
    <li>ease-in</li>
    <li>ease-out</li>
    <li>ease-in-out</li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>90-过渡模块-连写</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div {
            width: 100px;
            height: 50px;
            background-color: red;
            /*transition-property: width;*/
            /*transition-duration: 5s;*/
            /*transition: width 5s linear 0s,background-color 5s linear 0s;*/
            /*transition: background-color 5s linear 0s;*/
            /*transition: width 5s,background-color 5s,height 5s;*/
            transition: all 5s;
        }
        div:hover{
            width: 300px;
            height: 300px;
            background-color: blue;
        }
    </style>
</head>
<body>
<!--
1.过渡连写格式
transition: 过渡属性 过渡时长 运动速度 延迟时间;

2.过渡连写注意点
2.1和分开写一样, 如果想给多个属性添加过渡效果也是用逗号隔开即可
2.2连写的时可以省略后面的两个参数, 因为只要编写了前面的两个参数就已经满足了过渡的三要素
2.3如果多个属性运动的速度/延迟的时间/持续时间都一样, 那么可以简写为
transition:all 0s;
-->
<div></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>91-过渡模块-弹性效果</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            height: 100px;
            background-color: red;
            margin-top: 100px;
            text-align: center;
            line-height: 100px;
        }
        div span{
            font-size: 80px;
            /*transition-property: margin;*/
            /*transition-duration: 3s;*/
            transition: margin 3s;
        }
        div:hover span{
            margin: 0 20px;
        }
    </style>
</head>
<body>
<!--
1.编写过渡套路
1.1不要管过渡, 先编写基本界面
1.2修改我们认为需要修改的属性
1.3再回过头去给被修改属性的那个元素添加过渡即可
-->
<div>
    <span>江</span>
    <span>哥</span>
    <span>带</span>
    <span>你</span>
    <span>狂</span>
    <span>虐</span>
    <span>H</span>
    <span>5</span>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>92-过渡模块-手风琴效果</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        ul{
            width: 960px;
            height: 300px;
            margin: 100px auto;
            border: 1px solid #000;
            overflow: hidden;
        }
        ul li{
            list-style: none;
            width: 160px;
            height: 300px;
            background-color: red;
            float: left;
            /*border: 1px solid #000;*/
            /*box-sizing: border-box;*/
            /*transition-property: width;*/
            /*transition-duration: 0.5s;*/
            transition: width 0.5s;
        }
        ul:hover li{
            width: 100px;
        }
        ul li:hover{
            width: 460px;
        }
    </style>
</head>
<body>
<ul>
    <li><img src="images/ad1.jpg" alt=""></li>
    <li><img src="images/ad2.jpg" alt=""></li>
    <li><img src="images/ad3.jpg" alt=""></li>
    <li><img src="images/ad4.jpg" alt=""></li>
    <li><img src="images/ad5.jpg" alt=""></li>
    <li><img src="images/ad6.jpg" alt=""></li>
</ul>
</body>
</html>
```

