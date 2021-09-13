---
title: css3D转换模块
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
    <title>106-3D转换模块</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .father{
            width: 200px;
            height: 200px;
            background-color: red;
            border: 1px solid #000;
            margin: 100px auto;
            perspective: 500px;
            /*
            1.什么是2D和3D
            2D就是一个平面, 只有宽度和高度, 没有厚度
            3D就是一个立体, 有宽度和高度, 还有厚度
            默认情况下所有的元素都是呈2D展现的
            2.如何让某个元素呈3D展现
            和透视一样, 想看到某个元素的3d效果, 只需要给他的父元素添加一个transform-style属性, 然后设置为preserve-3d即可
            */
            transform-style: preserve-3d;
            transform: rotateY(0deg);
        }
        .son{
            width: 100px;
            height: 100px;
            background-color: blue;
            border: 1px solid #000;
            margin: 0 auto;
            margin-top: 50px;
            transform: rotateY(45deg);
        }
    </style>
</head>
<body>
<div class="father">
    <div class="son"></div>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>107-3D转换模块-正方体</title>
    <style>
    *{
        margin: 0;
        padding: 0;
    }
    ul{
        width: 200px;
        height: 200px;
        border: 1px solid #000;
        box-sizing: border-box;
        margin: 100px auto;
        position: relative;
        transform: rotateY(0deg) rotateX(0deg);
        transform-style: preserve-3d;
    }
    ul li{
        list-style: none;
        width: 200px;
        height: 200px;
        font-size: 60px;
        text-align: center;
        line-height: 200px;
        position: absolute;
        left: 0;
        top: 0;
    }
    ul li:nth-child(1){
        background-color: red;
        transform: translateX(-100px) rotateY(90deg);
    }
    ul li:nth-child(2){
        background-color: green;
        transform: translateX(100px) rotateY(90deg);
    }
    ul li:nth-child(3){
        background-color: blue;
        transform: translateY(-100px) rotateX(90deg);
    }
    ul li:nth-child(4){
        background-color: yellow;
        transform: translateY(100px) rotateX(90deg);
    }
    ul li:nth-child(5){
        background-color: purple;
        transform: translateZ(-100px);
    }
    ul li:nth-child(6){
        background-color: pink;
        transform: translateZ(100px);
    }

</style>
</head>
<body>
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li>6</li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>108-3D转换模块-正方体终极</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        ul{
            width: 200px;
            height: 200px;
            border: 1px solid #000;
            box-sizing: border-box;
            margin: 100px auto;
            position: relative;
            transform: rotateY(0deg) rotateX(0deg);
            transform-style: preserve-3d;
        }
        ul li{
            list-style: none;
            width: 200px;
            height: 200px;
            font-size: 60px;
            text-align: center;
            line-height: 200px;
            position: absolute;
            left: 0;
            top: 0;
        }
        ul li:nth-child(1){
            background-color: red;
            transform: rotateX(90deg) translateZ(100px);
        }
        ul li:nth-child(2){
            background-color: green;
            transform: rotateX(180deg) translateZ(100px);
        }
        ul li:nth-child(3){
            background-color: blue;
            transform: rotateX(270deg) translateZ(100px);
        }
        ul li:nth-child(4){
            background-color: yellow;
            transform: rotateX(360deg) translateZ(100px);
        }
        ul li:nth-child(5){
            background-color: purple;
            transform: translateX(-100px) rotateY(90deg);
        }
        ul li:nth-child(6){
            background-color: pink;
            transform: translateX(100px) rotateY(90deg);
        }

    </style>
</head>
<body>
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li>6</li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>109-3D转换模块-长方体</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        /*
        .father{
            width: 200px;
            height: 200px;
            border: 1px solid #000;
            margin: 100px auto;
        }
        .son{
            width: 200px;
            height: 200px;
            background-color: rgba(255,0,0,0.3);
            transform: scale(1.5, 1);
        }
        */
        ul{
            width: 200px;
            height: 200px;
            border: 1px solid #000;
            box-sizing: border-box;
            margin: 100px auto;
            position: relative;
            transform: rotateY(0deg) rotateX(0deg);
            transform-style: preserve-3d;
        }
        ul li{
            list-style: none;
            width: 200px;
            height: 200px;
            font-size: 60px;
            text-align: center;
            line-height: 200px;
            position: absolute;
            left: 0;
            top: 0;
        }
        ul li:nth-child(1){
            background-color: red;
            transform: rotateX(90deg) translateZ(100px) scale(2, 1);
        }
        ul li:nth-child(2){
            background-color: green;
            transform: rotateX(180deg) translateZ(100px) scale(2, 1);
        }
        ul li:nth-child(3){
            background-color: blue;
            transform: rotateX(270deg) translateZ(100px) scale(2, 1);
        }
        ul li:nth-child(4){
            background-color: yellow;
            transform: rotateX(360deg) translateZ(100px) scale(2, 1);
        }
        ul li:nth-child(5){
            background-color: purple;
            transform: translateX(-200px) rotateY(90deg);
        }
        ul li:nth-child(6){
            background-color: pink;
            transform: translateX(200px) rotateY(90deg);
        }
    </style>
</head>
<body>
<!--
<div class="father">
    <div class="son"></div>
</div>
-->
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li>6</li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>110-3D转换模块-练习</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        body{
            /*想看到整个立方的近大远小效果, 就给ul的父元素添加透视*/
            perspective: 500px;
        }
        ul{
            width: 200px;
            height: 200px;
            box-sizing: border-box;
            margin: 100px auto;
            position: relative;
            transform: rotateY(0deg) rotateX(0deg);
            transform-style: preserve-3d;
            animation: sport 5s linear 0s infinite normal;
        }
        ul li{
            list-style: none;
            width: 200px;
            height: 200px;
            font-size: 60px;
            text-align: center;
            line-height: 200px;
            position: absolute;
            left: 0;
            top: 0;
        }
        ul li:nth-child(1){
            background-color: red;
            transform: rotateX(90deg) translateZ(100px) scale(2, 1);
        }
        ul li:nth-child(2){
            background-color: green;
            transform: rotateX(180deg) translateZ(100px) scale(2, 1);
        }
        ul li:nth-child(3){
            background-color: blue;
            transform: rotateX(270deg) translateZ(100px) scale(2, 1);
        }
        ul li:nth-child(4){
            background-color: yellow;
            transform: rotateX(360deg) translateZ(100px) scale(2, 1);
        }
        ul li:nth-child(5){
            background-color: purple;
            transform: translateX(-200px) rotateY(90deg);
        }
        ul li:nth-child(6){
            background-color: pink;
            transform: translateX(200px) rotateY(90deg);
        }
        ul li img{
            /*
            注意点:
            只要父元素被拉伸了,子元素也会被拉伸
            */
            width: 200px;
            height: 200px;
        }
        @keyframes sport {
            from{
                transform: rotateX(0deg);
            }
            to{
                transform: rotateX(360deg);
            }
        }
    </style>
</head>
<body>
<ul>
    <li><img src="images/banner1.jpg" alt=""></li>
    <li><img src="images/banner2.jpg" alt=""></li>
    <li><img src="images/banner3.jpg" alt=""></li>
    <li><img src="images/banner4.jpg" alt=""></li>
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
    <title>111-3D播放器上</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        body{
            background: url("images/jacky/bg.jpg") no-repeat;
            background-size:cover;
        }
        ul{
            width: 200px;
            height: 200px;
            /*background-color: red;*/
            position: absolute;
            bottom: 100px;
            left: 50%;
            margin-left:-100px;
            transform-style: preserve-3d;
            /*transform: rotateX(-10deg);*/
            animation: sport 6s linear 0s infinite normal;
        }
        ul li{
            list-style: none;
            width: 200px;
            height: 200px;
            font-size: 60px;
            text-align: center;
            line-height: 200px;
            position: absolute;
            left: 0;
            top: 0;
        }
        ul li:nth-child(1){
            background-color: green;
            transform: rotateY(60deg) translateZ(200px);
        }
        ul li:nth-child(2){
            background-color: blue;
            transform: rotateY(120deg) translateZ(200px);
        }
        ul li:nth-child(3){
            background-color: yellow;
            transform: rotateY(180deg) translateZ(200px);
        }
        ul li:nth-child(4){
            background-color: pink;
            transform: rotateY(240deg) translateZ(200px);
        }
        ul li:nth-child(5){
            background-color: purple;
            transform: rotateY(300deg) translateZ(200px);
        }
        ul li:nth-child(6){
            background-color: gold;
            transform: rotateY(360deg) translateZ(200px);
        }
        ul li img{
            width: 200px;
            height: 200px;
            border: 5px solid skyblue;
            box-sizing: border-box;
        }
        @keyframes sport {
            from{
                /*
                注意点:
                1.动画中如果有和默认样式中同名的属性, 会覆盖默认样式中同名的属性
                2.在编写动画的时候, 固定不变的值写在前面, 需要变化的值写在后面
                */
                transform: rotateX(-10deg) rotateY(0deg);
            }
            to{
                transform: rotateX(-10deg) rotateY(360deg);
            }
        }
    </style>
</head>
<body>
<ul>
    <li><img src="images/jacky/1.png" alt=""></li>
    <li><img src="images/jacky/2.jpg" alt=""></li>
    <li><img src="images/jacky/3.jpg" alt=""></li>
    <li><img src="images/jacky/4.gif" alt=""></li>
    <li><img src="images/jacky/5.jpg" alt=""></li>
    <li><img src="images/jacky/6.jpg" alt=""></li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>111-3D播放器下</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        body{
            background: url("images/jacky/bg.jpg") no-repeat;
            background-size:cover;
            overflow: hidden;
        }
        ul{
            width: 200px;
            height: 200px;
            /*background-color: red;*/
            position: absolute;
            bottom: 100px;
            left: 50%;
            margin-left:-100px;
            transform-style: preserve-3d;
            /*transform: rotateX(-10deg);*/
            animation: sport 6s linear 0s infinite normal;
        }
        ul li{
            list-style: none;
            width: 200px;
            height: 200px;
            font-size: 60px;
            text-align: center;
            line-height: 200px;
            position: absolute;
            left: 0;
            top: 0;
            background-color: black;
        }
        ul li:nth-child(1){
            transform: rotateY(60deg) translateZ(200px);
        }
        ul li:nth-child(2){
            transform: rotateY(120deg) translateZ(200px);
        }
        ul li:nth-child(3){
            transform: rotateY(180deg) translateZ(200px);
        }
        ul li:nth-child(4){
            transform: rotateY(240deg) translateZ(200px);
        }
        ul li:nth-child(5){
            transform: rotateY(300deg) translateZ(200px);
        }
        ul li:nth-child(6){
            transform: rotateY(360deg) translateZ(200px);
        }
        ul li img{
            width: 200px;
            height: 200px;
            border: 5px solid skyblue;
            box-sizing: border-box;
        }
        ul:hover{
            animation-play-state: paused;
        }
        ul:hover li img{
            opacity: 0.5;
        }
        ul li:hover img{
            opacity: 1;
        }
        @keyframes sport {
            from{
                /*
                注意点:
                1.动画中如果有和默认样式中同名的属性, 会覆盖默认样式中同名的属性
                2.在编写动画的时候, 固定不变的值写在前面, 需要变化的值写在后面
                */
                transform: rotateX(-10deg) rotateY(0deg);
            }
            to{
                transform: rotateX(-10deg) rotateY(360deg);
            }
        }
        .heart{
            width: 173px;
            height: 157px;
            position: absolute;
            left: 100px;
            bottom: 100px;
            animation: move 10s linear 0s infinite normal;
        }
        @keyframes move {
            0%{
                left: 100px;
                bottom: 100px;
                opacity: 1;
            }
            20%{
                left: 300px;
                bottom: 300px;
                opacity: 0;
            }
            40%{
                left: 500px;
                bottom: 500px;
                opacity: 1;
            }
            60%{
                left: 800px;
                bottom: 300px;
                opacity: 0;
            }
            80%{
                left: 1200px;
                bottom: 100px;
                opacity: 1;
            }
            100%{
                left: 800px;
                bottom: -200px;
            }
        }
    </style>
</head>
<body>
<ul>
    <li><img src="images/jacky/1.png" alt=""></li>
    <li><img src="images/jacky/2.jpg" alt=""></li>
    <li><img src="images/jacky/3.jpg" alt=""></li>
    <li><img src="images/jacky/4.gif" alt=""></li>
    <li><img src="images/jacky/5.jpg" alt=""></li>
    <li><img src="images/jacky/6.jpg" alt=""></li>
</ul>
<img src="images/jacky/xin.png" class="heart">
<audio src="images/jacky/江哥最爱的歌.mp3" autoplay="autoplay" loop="loop"></audio>
</body>
</html>
```

