---
title: css2D转换模块
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
    <title>100-动画模块</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 100px;
            height: 50px;
            background-color: red;
            /*transition-property: margin-left;*/
            /*transition-duration: 3s;*/

            /*1.告诉系统需要执行哪个动画*/
            animation-name: lnj;
            /*3.告诉系统动画持续的时长*/
            animation-duration: 3s;
        }
        /*2.告诉系统我们需要自己创建一个名称叫做lnj的动画*/
        @keyframes lnj {
            from{
                margin-left: 0;
            }
            to{
                margin-left: 500px;
            }
        }

        /*div:hover{*/
            /*margin-left: 500px;*/
        /*}*/
    </style>
</head>
<body>
<!--
1.过渡和动画之间的异同
1.1不同点
过渡必须人为的触发才会执行动画
动画不需要人为的触发就可以执行动画

1.2相同点
过渡和动画都是用来给元素添加动画的
过渡和动画都是系统新增的一些属性
过渡和动画都需要满足三要素才会有动画效果
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
    <title>101-动画模块-其它属性上</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div {
            width: 100px;
            height: 50px;
            background-color: red;
            animation-name: sport;
            animation-duration: 2s;
            /*告诉系统多少秒之后开始执行动画*/
            /*animation-delay: 2s;*/
            /*告诉系统动画执行的速度*/
            animation-timing-function: linear;
            /*告诉系统动画需要执行几次*/
            animation-iteration-count: 3;
            /*告诉系统是否需要执行往返动画
            取值:
            normal, 默认的取值, 执行完一次之后回到起点继续执行下一次
            alternate, 往返动画, 执行完一次之后往回执行下一次
            */
            animation-direction: alternate;
        }
        @keyframes sport {
            from{
                margin-left: 0;
            }
            to{
                margin-left: 500px;
            }
        }
        div:hover{
            /*
            告诉系统当前动画是否需要暂停
            取值:
            running: 执行动画
            paused: 暂停动画
            */
            animation-play-state: paused;
        }
    </style>
</head>
<body>
<div class="box1"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>102-动画模块-其它属性下</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box1 {
            width: 100px;
            height: 50px;
            background-color: red;
            position: absolute;
            left: 0;
            top: 0;
            animation-name: sport;
            animation-duration: 5s;
        }
        @keyframes sport {
            0%{
                left: 0;
                top: 0;
            }
            25%{
                left: 300px;
                top: 0;
            }
            50%{
                left: 300px;
                top: 300px;
            }
            75%{
                left: 0;
                top: 300px;
            }
            100%{
                left: 0;
                top: 0;
            }
        }

        .box2{
            width: 200px;
            height: 200px;
            background-color: blue;
            margin: 100px auto;
            animation-name: myRotate;
            animation-duration: 5s;
            animation-delay: 2s;
            /*
            通过我们的观察, 动画是有一定的状态的
            1.等待状态
            2.执行状态
            3.结束状态
            */
            /*
            animation-fill-mode作用:
            指定动画等待状态和结束状态的样式
            取值:
            none: 不做任何改变
            forwards: 让元素结束状态保持动画最后一帧的样式
            backwards: 让元素等待状态的时候显示动画第一帧的样式
            both: 让元素等待状态显示动画第一帧的样式, 让元素结束状态保持动画最后一帧的样式
            */
            /*animation-fill-mode: backwards;*/
            /*animation-fill-mode: forwards;*/
            animation-fill-mode: both;
        }
        @keyframes myRotate {
            0%{
                transform: rotate(10deg);
            }
            50%{
                transform: rotate(50deg);
            }
            100%{
                transform: rotate(70deg);
            }
        }
    </style>
</head>
<body>
<div class="box1"></div>
<div class="box2"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>103-动画模块-连写</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div {
            width: 100px;
            height: 50px;
            background-color: red;
            /*animation: move 3s linear 2s 1 normal;*/
            animation: move 3s;
        }
        @keyframes move {
            from{
                margin-left: 0;
            }
            to{
                margin-left: 500px;
            }
        }
    </style>
</head>
<body>
<!--
1.动画模块连写格式
animation:动画名称 动画时长 动画运动速度 延迟时间 执行次数 往返动画;

2.动画模块连写格式的简写
animation:动画名称 动画时长;
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
    <title>104-动画模块-云层效果</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        ul{
            height: 400px;
            background-color: skyblue;
            margin-top: 100px;
            animation: change 5s linear 0s infinite alternate;
            position: relative;
            overflow: hidden;
        }
        ul li{
            list-style: none;
            width: 400%;
            height: 100%;
            position: absolute;
            left: 0;
            top: 0;
        }
        ul li:nth-child(1){
            background-image: url("images/cloud_one.png");
            animation: one 30s linear 0s infinite alternate;
        }
        ul li:nth-child(2){
            background-image: url("images/cloud_two.png");
            animation: two 30s linear 0s infinite alternate;
        }
        ul li:nth-child(3){
            background-image: url("images/cloud_three.png");
            animation: three 30s linear 0s infinite alternate;
        }
        @keyframes change {
            from{
                background-color: skyblue;
            }
            to{
                background-color: black;
            }
        }
        @keyframes one {
            from{
                margin-left: 0;
            }
            to{
                margin-left: -100%;
            }
        }
        @keyframes two {
            from{
                margin-left: 0;
            }
            to{
                margin-left: -200%;
            }
        }
        @keyframes three {
            from{
                margin-left: 0;
            }
            to{
                margin-left: -300%;
            }
        }
    </style>
</head>
<body>
<ul>
    <li></li>
    <li></li>
    <li></li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>105-动画模块-无限滚动</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 600px;
            height: 188px;
            border: 1px solid #000;
            margin: 100px auto;
            overflow: hidden;
        }

        ul{
            width: 2000px;
            height: 188px;
            background-color: black;
            animation: move 10s linear 0s infinite normal;
        }
        ul li{
            float: left;
            list-style: none;
            width: 300px;
            height: 188px;
            background-color: red;
            border: 1px solid #000;
            box-sizing: border-box;
        }
        ul:hover{
            /*动画添加给谁, 就让谁停止*/
            animation-play-state: paused;
        }
        ul:hover li{
            opacity: 0.5;
        }
        ul li:hover{
            opacity: 1;
        }
        @keyframes move {
            from{
                margin-left: 0;
            }
            to{
                margin-left: -1200px;
            }
        }
    </style>
</head>
<body>
<div>
    <ul>
        <li><img src="images/banner1.jpg" alt=""></li>
        <li><img src="images/banner2.jpg" alt=""></li>
        <li><img src="images/banner3.jpg" alt=""></li>
        <li><img src="images/banner4.jpg" alt=""></li>
        <li><img src="images/banner1.jpg" alt=""></li>
        <li><img src="images/banner2.jpg" alt=""></li>
    </ul>
</div>
</body>
</html>
```

