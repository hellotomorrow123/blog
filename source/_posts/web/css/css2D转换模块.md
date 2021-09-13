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
    <title>93-2D转换模块</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        ul{
            width: 800px;
            height: 500px;
            border: 1px solid #000;
            margin: 0 auto;
        }
        ul li{
            list-style: none;
            width: 100px;
            height: 50px;
            background-color: red;
            margin: 0 auto;
            margin-top: 50px;
            text-align: center;
            line-height: 50px;
        }
        ul li:nth-child(2){
            /*其中deg是单位, 代表多少度*/
            transform: rotate(45deg);
        }
        ul li:nth-child(3){
            /*
            第一个参数:水平方向
            第二个参数:垂直方向
            */
            transform: translate(100px, 0px);
        }
        ul li:nth-child(4){
            /*
            第一个参数:水平方向
            第二个参数:垂直方向
            注意点:
            如果取值是1, 代表不变
            如果取值大于1, 代表需要放大
            如果取值小于1, 代表需要缩小
            如果水平和垂直缩放都一样, 那么可以简写为一个参数
            */
            /*transform: scale(0.5, 0.5);*/
            transform: scale(1.5);
        }
        ul li:nth-child(5){
            /*
            注意点:
            1.如果需要进行多个转换, 那么用空格隔开
            2.2D的转换模块会修改元素的坐标系, 所以旋转之后再平移就不是水平平移的
            */
            transform: rotate(45deg) translate(100px, 0px) scale(1.5, 1.5);
            /*transform: translate(100px, 0px);*/
        }
    </style>
</head>
<body>
<ul>
    <li>正常的</li>
    <li>旋转的</li>
    <li>平移的</li>
    <li>缩放的</li>
    <li>综合的</li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>94-2D转换模块-形变中心点</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        ul{
            width: 200px;
            height: 200px;
            border: 1px solid #000;
            margin: 100px auto;
            position: relative;
        }
        ul li{
            list-style: none;
            width: 200px;
            height: 200px;
            position: absolute;
            left: 0;
            top: 0;
            /*
            第一个参数:水平方向
            第二个参数:垂直方向
            注意点
            取值有三种形式
            具体像素
            百分比
            特殊关键字
            */
            /*transform-origin: 200px 0px;*/
            /*transform-origin: 50% 50%;*/
            /*transform-origin: 0% 0%;*/
            /*transform-origin: center center;*/
            transform-origin: left top;
        }
        ul li:nth-child(1){
            /*
            默认情况下所有的元素都是以自己的中心点作为参考来旋转的, 我们可以通过形变中心点属性来修改它的参考点
            */
            background-color: red;
            transform: rotate(30deg);
        }
        ul li:nth-child(2){
            background-color: green;
            transform: rotate(50deg);
        }
        ul li:nth-child(3){
            background-color: blue;
            transform: rotate(70deg);
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
    <title>95-2D转换模块-旋转轴向</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        ul{
            width: 800px;
            height: 500px;
            margin: 0 auto;

        }
        ul li{
            list-style: none;
            width: 200px;
            height: 200px;
            margin: 0 auto;
            margin-top: 50px;
            border: 1px solid #000;
            /*
            1.什么是透视
            近大远小
            2.注意点
            一定要注意, 透视属性必须添加到需要呈现近大远小效果的元素的父元素上面
            */
            perspective: 500px;
        }
        ul li img{
            width: 200px;
            height: 200px;
            /*perspective: 500px;*/
        }
        ul li:nth-child(1){
            /*默认情况下所有元素都是围绕Z轴进行旋转*/
            transform: rotateZ(45deg);
        }
        ul li:nth-child(2) img{
            transform: rotateX(45deg);
        }
        ul li:nth-child(3) img{
            /*
            总结:
            想围绕哪个轴旋转, 那么只需要在rotate后面加上哪个轴即可
            */
            transform: rotateY(45deg);
        }
    </style>
</head>
<body>
<ul>
    <li><img src="images/rotateZ.jpg" alt=""></li>
    <li><img src="images/rotateX.jpg" alt=""></li>
    <li><img src="images/rotateY.jpg" alt=""></li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>96-2D转换模块-练习</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 310px;
            height: 438px;
            border: 1px solid #000;
            background-color: skyblue;
            margin: 100px auto;
            perspective: 500px;
        }
        div img{
            transform-origin: center bottom;
            transition: transform 1s;
        }
        div:hover img{
            transform: rotateX(80deg);
        }
    </style>
</head>
<body>
<div>
    <img src="images/pk.png" alt="">
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>97-2D转换模块-相片墙</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        ul{
            height: 400px;
            border: 1px solid #000;
            background-color: skyblue;
            margin-top: 100px;
            text-align: center;
        }
        ul li{
            list-style: none;
            width: 150px;
            height: 200px;
            background-color: red;
            display: inline-block;
            margin-top: 100px;
            transition: all 1s;
            position: relative;
            box-shadow: 0 0 10px;
        }
        ul li:nth-child(1){
            transform: rotate(30deg);
        }
        ul li:nth-child(2){
            transform: rotate(-40deg);
        }
        ul li:nth-child(3){
            transform: rotate(10deg);
        }
        ul li:nth-child(4){
            transform: rotate(45deg);
        }
        ul li img{
            width: 150px;
            height: 200px;
            border: 5px solid #fff;
            box-sizing: border-box;
        }
        ul li:hover{
            /*transform: rotate(0deg);*/
            /*transform: none;*/
            transform: scale(1.5);
            z-index: 998;
        }
    </style>
</head>
<body>
<ul>
    <li><img src="images/1.jpg" alt=""></li>
    <li><img src="images/2.jpg" alt=""></li>
    <li><img src="images/3.jpg" alt=""></li>
    <li><img src="images/4.jpg" alt=""></li>
</ul>
</body>
</html>
```

