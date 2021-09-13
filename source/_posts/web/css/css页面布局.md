---
title: css网页布局
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
    <title>58-网页的布局方式</title>
    <style>
        /*
        div,h1,p{
            border: 1px solid #000;
        }
        span,strong,b{
            border: 1px solid #000;
        }
        */
        *{
            margin: 0;
            padding: 0;
        }
        .box1{
            width: 100px;
            height: 100px;
            background-color: red;
            /*display: inline-block;*/
            float: left;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: blue;
            /*display: inline-block;*/
            /*margin-left:930px;*/
            float: right;
        }
    </style>
</head>
<body>
<!--
1.什么是网页的布局方式?
网页的布局方式其实就是指浏览器是如何对网页中的元素进行排版的

1.标准流(文档流/普通流)排版方式
1.1其实浏览器默认的排版方式就是标准流的排版方式
1.2在CSS中将元素分为三类, 分别是块级元素/行内元素/行内块级元素
1.3 在标准流中有两种排版方式, 一种是垂直排版, 一种是水平排版
垂直排版, 如果元素是块级元素, 那么就会垂直排版
水平排版, 如果元素是行内元素/行内块级元素, 那么就会水平排版

2.浮动流排版方式
2.1浮动流是一种"半脱离标准流"的排版方式
2.2浮动流只有一种排版方式, 就是水平排版. 它只能设置某个元素左对齐或者右对齐

注意点:
1.浮动流中没有居中对齐, 也就是没有center这个取值
2.在浮动流中是不可以使用margin: 0 auto;

特点:
1.在浮动流中是不区分块级元素/行内元素/行内块级元素的
无论是级元素/行内元素/行内块级元素都可以水平排版
2.在浮动流中无论是块级元素/行内元素/行内块级元素都可以设置宽高
3.综上所述, 浮动流中的元素和标准流中的行内块级元素很像

3.定位流排版方式
-->
<!--
<div>我是div</div>
<h1>我是标题</h1>
<p>我是段落</p>
-->
<!--
<span>我是span</span>
<strong>我是强调</strong>
<b>我是加粗</b>
-->
<span class="box1"></span>
<span class="box2"></span>
</body>
</html>
```

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>59-浮动元素的脱标</title>
    <style>
        .box1{
            float: left;
            width: 100px;
            height: 100px;
            background-color: red;
        }
        .box2{
            width: 150px;
            height: 150px;
            background-color: blue;
        }
    </style>
</head>
<body>
<!--
1.什么是浮动元素的脱标?
脱标: 脱离标准流
当某一个元素浮动之后, 那么这个元素看上去就像被从标准流中删除了一样, 这个就是浮动元素的脱标

2.浮动元素脱标之后会有什么影响?
如果前面一个元素浮动了, 而后面一个元素没有浮动 , 那么这个时候前面一个元就会盖住后面一个元素
-->
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
    <title>60-浮动元素排序规则</title>
    <style>
        .box1{
            float: left;
            width: 50px;
            height: 50px;
            background-color: red;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: pink;
        }
        .box3{
            float: left;
            width: 150px;
            height: 150px;
            background-color: yellow;
        }
        .box4{
            float: left;
            width: 200px;
            height: 200px;
            background-color: tomato;
        }
    </style>
</head>
<body>
<!--
1.浮动元素排序规则
1.1相同方向上的浮动元素, 先浮动的元素会显示在前面, 后浮动的元素会显示在后面
1.2不同方向上的浮动元素, 左浮动会找左浮动, 右浮动会找右浮动
1.3浮动元素浮动之后的位置, 由浮动元素浮动之前在标准流中的位置来确定
-->
<div class="box1">1</div>
<div class="box2">2</div>
<div class="box3">3</div>
<div class="box4">4</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>61-浮动元素贴靠现象</title>
    <style>
        .father{
            width: 400px;
            height: 400px;
            border: 1px solid #000;
        }
        .box1{
            float: left;
            width: 50px;
            height: 300px;
            background-color: red;
        }
        .box2{
            float: left;
            width: 50px;
            height: 100px;
            background-color: green;
        }
        .box3{
            float: left;
            width: 250px;
            height: 100px;
            background-color: blue;
        }
    </style>
</head>
<body>
<!--
1.什么是浮动元素贴靠现象?
1.如果父元素的宽度能够显示所有浮动元素, 那么浮动的元素会并排显示
2.如果父元素的宽度不能显示所有浮动元素, 那么会从最后一个元开始往前贴靠
3.如果贴靠了前面所有浮动元素之后都不能显示, 最终会贴靠到父元素的左边或者右边
-->
<div class="father">
    <div class="box1"></div>
    <div class="box2"></div>
    <div class="box3"></div>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>62-浮动元素字围现象</title>
    <style>
        div{
            float: left;
            width: 100px;
            height: 100px;
            /*background-color: red;*/
            border: 1px solid #000;
        }
        p{
            width: 500px;
            height: 500px;
            background-color: yellow;
        }
        img{
            float: left;
        }
    </style>
</head>
<body>
<!--
1.什么是浮动元素字围现象?
浮动元素不会挡住没有浮动元素中的文字, 没有浮动的文字会自动给浮动的元素让位置,这个就是浮动元素字围现象
-->

<!--<div></div>-->
<img src="images/girl.jpg" alt="">
<p>1999年-2002年范冰冰一共出演了《青春出动》、《小李飞刀》、《秦始皇》、《中关村风云》、《少年包青天2》《尘埃落定》等十七部电视剧[12]  ，以及《河东狮吼》等三部电影[13]  。
    2003年在由梁羽生小说改编的电视剧《萍踪侠影》中饰演女主角云蕾。同年在冯小刚执导的贺岁档电影《手机》中饰演女主角武月[14]  。
    2004年凭借电影《手机》获得第27届大众电影百花奖最佳女主角奖，同时《手机》也获得大众电影百花奖最佳故事片奖。[2]  9月，出演根据古龙小说改编的古装剧《小鱼儿与花无缺》，饰演女主角铁心兰[15]  。同年出演《大唐芙蓉园》中的杨玉环等五部电视剧，以及电影《千机变2》和《情癫大圣》[16]  。
    2005年发行首张个人专辑《刚刚开始》，这张处女大碟由圈内多位音乐人联袂制作，包含了多种风格迥异的音乐元素。[3]  同年主演由张之亮执导的古装片《墨攻》，饰演女主角逸悦。[17]
    2006年出演电视剧《封神榜之凤鸣岐山》，饰演女主角苏妲己。之后接连拍摄《苹果》、《导火线》、《心中有鬼》等六部电影[18]  。
    2007年2月，主演的电影《苹果》入围第57届柏林国际电影节主
    范冰冰
    范冰冰(23张)
    竞赛单元，导演李玉，女主演范冰冰，男主演佟大为共同出席本届电影节。[19]  6月，范冰冰与华谊约满，自组工作室，投资拍摄民国剧《胭脂雪》，并首次担当制片人，同时饰演女主角文玉禾[20]  。10月，凭借电影《苹果》获得第四届欧亚国际电影节最佳女演员奖。[21]  同年出演《合约情人》、《精舞门》、《新宿事件》等五部电影[22]  。同年凭借电影《心中有鬼》获得第44届台湾电影金马奖最佳女配角[4]  。</p>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>63-浮动练习</title>
    <style>
        body,div,dl,dt,dd,ul,ol,li,h1,h2,h3,h4,h5,h6,pre,code,form,fieldset,legend,input,textarea,p,blockquote,th,td{
            margin:0;padding:0
        }
        .header{
            width: 980px;
            height: 100px;
            /*background-color: red;*/
            margin:0 auto;
        }
        .header .logo{
            width: 250px;
            height: 100px;
            background-color: pink;
            float: left;
        }
        .header .language{
            width: 150px;
            height: 50px;
            background-color: skyblue;
            float: right;
        }
        .header .nav{
            width: 650px;
            height: 50px;
            background-color: purple;
            float: right;
        }
        .content{
            width: 980px;
            height: 400px;
            /*background-color: green;*/
            margin:0 auto;
            margin-top: 10px;
        }
        .content .aside{
            width: 320px;
            height: 400px;
            background-color: yellow;
            float: left;
        }
        .content .article{
            width: 650px;
            height: 400px;
            /*background-color: pink;*/
            float: right;
        }
        .content .article .articleTop{
            width: 650px;
            height: 350px;
            /*background-color: blue;*/
        }
        .content .article .articleTop .articleTopLeft{
            width: 400px;
            height: 350px;
            /*background-color: red;*/
            float: left;
        }
        .content .article .articleTop .articleTopLeft .new1{
            width: 400px;
            height: 200px;
            background-color: deepskyblue;
        }
        .content .article .articleTop .articleTopLeft .new2{
            width: 400px;
            height: 140px;
            background-color: tomato;
            margin-top: 10px;
        }
        .content .article .articleTop .articleTopRight{
            width: 240px;
            height: 350px;
            background-color: green;
            float: right;
        }
        .content .article .articleBottom{
            width: 650px;
            height: 40px;
            background-color: darkgoldenrod;
            margin-top: 10px;
        }
        .footer{
            width: 980px;
            height: 40px;
            background-color: tomato;
            margin:0 auto;
            margin-top:10px;
        }
    </style>
</head>
<body>
<!--
1.企业开发中什么时候使用标准流什么时候使用浮动流?
垂直方向使用标准流, 水平方向使用浮动流

2.拿到一个很复杂的界面如何入手?
2.1从上至下布局
2.2从外向内布局
2.3水平方向可以先划分为一左一右再对左边或者右边进行进一步布局
-->
<div class="header">
    <div class="logo"></div>
    <div class="language"></div>
    <div class="nav"></div>
</div>
<div class="content">
    <div class="aside"></div>
    <div class="article">
        <div class="articleTop">
            <div class="articleTopLeft">
                <div class="new1"></div>
                <div class="new2"></div>
            </div>
            <div class="articleTopRight"></div>
        </div>
        <div class="articleBottom"></div>
    </div>
</div>
<div class="footer"></div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>64-浮动元素高度问题</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            border: 1px solid #000;
        }
        p{
            float: left;
            width: 50px;
            height: 50px;
            background-color: red;
        }
    </style>
</head>
<body>
<!--
1.在标准流中内容的高度可以撑起父元素的高度
2.在浮动流中浮动的元素是不可以撑起父元素的高度的
-->
<div>
    <p></p>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>65-清除浮动方式一</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box1{
            height: 20px;
            background-color: red;
        }
        .box2{
            background-color: green;
        }
        .box1 p{
            width: 100px;
            background-color: blue;
        }
        .box2 p{
            width: 100px;
            background-color: yellow;
        }
        p{
            float: left;
        }
    </style>
</head>
<body>
<!--
1.清除浮动的第一种方式
给前面一个父元素设置高度

注意点:
在企业开发中, 我们能不写高度就不写高度, 所以这种方式用得很少
-->
<div class="box1">
    <p>我是文字1</p>
    <p>我是文字1</p>
    <p>我是文字1</p>
</div>

<div class="box2">
    <p>我是文字2</p>
    <p>我是文字2</p>
    <p>我是文字2</p>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>66-清除浮动方式二</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        body{
            border: 1px solid #000;
        }
        .box1{
            background-color: red;
        }
        .box2{
            background-color: green;
            clear: both;
            margin-top: 28px;
        }
        .box1 p{
            width: 100px;
            background-color: blue;
        }
        .box2 p{
            width: 100px;
            background-color: yellow;
        }
        p{
            float: left;
        }
        /*
        .dd{
            width: 500px;
            height: 500px;
            background-color: red;
            border: 1px solid #000;
        }
        .ddd{
            width: 200px;
            height: 200px;
            background-color: blue;
            margin-top: 100px;
        }
        */
    </style>
</head>
<body>
<!--
1.清除浮动的第二种方式
给后面的盒子添加clear属性

clear属性取值:
none: 默认取值, 按照浮动元素的排序规则来排序(左浮动找左浮动, 右浮动找右浮动)
left: 不要找前面的左浮动元素
right: 不要找前面的右浮动元素
both: 不要找前面的左浮动元素和右浮动元素

注意点:
当我们给某个元素添加clear属性之后, 那么这个属性的margin属性就会失效
-->

<div class="box1">
    <p>我是文字1</p>
    <p>我是文字1</p>
    <p>我是文字1</p>
</div>

<div class="box2">
    <p>我是文字2</p>
    <p>我是文字2</p>
    <p>我是文字2</p>
</div>

<!--
<div class="dd">
    <div class="ddd"></div>
</div>
-->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>67-清除浮动方式三</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box1{
            background-color: red;
            /*margin-bottom: 10px;*/
        }
        .box2{
            background-color: green;
            /*margin-top: 10px;*/
        }
        .box1 p{
            width: 100px;
            background-color: blue;
        }
        .box2 p{
            width: 100px;
            background-color: yellow;
        }
        p{
            float: left;
        }
        .wall{
            clear: both;
        }
        .h20{
            height: 20px;
            background-color: skyblue;
        }
    </style>
</head>
<body>
<!--
1.清除浮动的第三种方式
隔墙法

2.外墙法
2.1在两个盒子中间添加一个额外的块级元素
2.2给这个额外添加的块级元素设置clear: both;属性

注意点:
外墙法它可以让第二个盒子使用margin-top属性
外墙法不可以让第一个盒子使用margin-bottom属性

3.内墙法
3.1在第一个盒子中所有子元素最后添加一个额外的块级元素
3.2给这个额外添加的块级元素设置clear: both;属性

注意点:
内墙法它可以让第二个盒子使用margin-top属性
内墙法它可以让第一个盒子使用margin-bottom属性

4.外墙法和内墙法区别?
外墙法不能撑起第一个盒子的高度, 而内墙法可以撑起第一个盒子的高度

5.在企业开发中不常用隔墙法来清除浮动
-->
<div class="box1">
    <p>我是文字1</p>
    <p>我是文字1</p>
    <p>我是文字1</p>
    <div class="wall h20"></div>
</div>

<!--<div class="wall h20"></div>-->

<div class="box2">
    <p>我是文字2</p>
    <p>我是文字2</p>
    <p>我是文字2</p>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>69-清除浮动方式四</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box1{
            background-color: red;
            /*margin-bottom: 10px;*/
        }
        .box2{
            background-color: green;
            /*margin-top: 10px;*/
        }
        .box1 p{
            width: 100px;
            background-color: blue;
        }
        .box2 p{
            width: 100px;
            background-color: yellow;
        }
        p{
            float: left;
        }
        .box1::after{
            /*设置添加的子元素的内容为空*/
            content: "";
            /*设置添加的子元素为块级元素*/
            display: block;
            /*设置添加的子元素的高度为0*/
            height: 0;
            /*设置添加的子元素看不见*/
            visibility: hidden;
            /*给添加的子元素设置clear: both;*/
            clear: both;
        }
        .box1{
            /*兼容IE6*/
            *zoom:1;
        }
    </style>
</head>
<body>
<!--
1.清除浮动的第四种方式
利用伪元素选择器清除浮动
本质上就是内墙法, 只不过是直接通过CSS代码添加了内墙, 其它特性和内墙法都一样

注意点:
IE6中不支持这种方式, 为了兼容IE6必须给前面的盒子添加*zoom:1;属性
-->
<div class="box1">
    <p>我是文字1</p>
    <p>我是文字1</p>
    <p>我是文字1</p>
</div>

<div class="box2">
    <p>我是文字2</p>
    <p>我是文字2</p>
    <p>我是文字2</p>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>70-清除浮动方式五</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        /*
        div{
            width: 100px;
            height: 100px;
            background-color: red;
            overflow: hidden;
        }
        */
        /*
        .box1{
            background-color: red;
            overflow: hidden;
            *zoom:1;
        }
        .box2{
            background-color: green;
        }
        .box1 p{
            width: 100px;
            background-color: blue;
        }
        .box2 p{
            width: 100px;
            background-color: yellow;
        }
        p{
            float: left;
        }
        */
        .box1{
            width: 200px;
            height: 200px;
            background-color: red;
            /*border: 1px solid #000;*/
            overflow: hidden;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: blue;
            margin-top: 20px;
        }
    </style>
</head>
<body>
<!--
1.overflow: hidden;作用
1.1可以将超出标签范围的内容裁剪掉
1.2清除浮动
1.3可以通过overflow: hidden;让里面的盒子设置margin-top之后, 外面的盒子不被顶下来
-->

<!--
<div>我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字我是文字</div>
-->

<!--
<div class="box1">
    <p>我是文字1</p>
    <p>我是文字1</p>
    <p>我是文字1</p>

</div>

<div class="box2">
    <p>我是文字2</p>
    <p>我是文字2</p>
    <p>我是文字2</p>
</div>
-->
<div class="box1">
    <div class="box2"></div>
</div>
</body>
</html>
```

------

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>75-定位流</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 100px;
            height: 100px;
        }
        .box1{
            background-color: red;
        }
        .box2{
            background-color: green;
            position: relative;
            top: 20px;
            left: 20px;
            /*right: 20px;*/
            /*margin-bottom: 20px;*/
            margin-top: 20px;
        }
        .box3{
            background-color: blue;
        }
        span{
            position: relative;
            width: 100px;
            height: 100px;
            background-color: red;
        }
        input{
            width: 200px;
            height: 50px;
        }
        img{
            width: 100px;
            height: 50px;
            position: relative;
            top: 20px;
        }
    </style>
</head>
<body>
<!--
1.定位流分类
1.1相对定位
1.2绝对定位
1.3固定定位
1.4静态定位

2.什么是相对定位?
相对定位就是相对于自己以前在标准流中的位置来移动

3.相对定位注意点
3.1相对定位是不脱离标准流的, 会继续在标准流中占用一份空间
3.2在相对定位中同一个方向上的定位属性只能使用一个
3.3由于相对定位是不脱离标准流的, 所以在相对定位中是区分块级元素/行内元素/行内块级元素
3.4由于相对定位是不脱离标准流的, 并且相对定位的元素会占用标准流中的位置, 所以当给相对定位的元素设置margin/padding等属性的时会影响到标准流的布局

4.相对定位应用场景
4.1用于对元素进行微调
4.2配合后面学习的绝对定位来使用
-->

<!--
<div class="box1"></div>
<div class="box2"></div>
<div class="box3"></div>

<span>我是span</span>
-->

<input type="text" name="" id="">
<img src="images/vcode.jpg" alt="">
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>76-定位流-绝对定位</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 100px;
            height: 100px;
        }
        .box1{
            background-color: red;
        }
        .box2{
            background-color: green;
            position: absolute;
            /*float: left;*/
            left: 0;
            /*right: 0;*/
            /*top: 0;*/
            bottom: 0;
        }
        .box3{
            background-color: blue;
        }
        span{
            position: absolute;
            width: 100px;
            height: 100px;
            background-color: yellow;
        }
    </style>
</head>
<body>
<!--
1.什么是绝对定位?
绝对定位就是相对于body来定位

2.绝对定位注意点
2.1绝对定位的元素是脱离标准流的
2.2绝对定位的元素是不区分块级元素/行内元素/行内块级元素
-->
<div class="box1"></div>
<div class="box2"></div>
<div class="box3"></div>
<!--<span>我是span</span>-->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>77-绝对定位-参考点</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .box1{
            width: 300px;
            height: 300px;
            background-color: red;
            position: relative;
        }
        .box2{
            width: 200px;
            height: 200px;
            background-color: green;
            position: relative;
        }
        .box3{
            width: 100px;
            height: 100px;
            background-color: blue;
            position: absolute;
            left: 0;
            bottom: 0;
          }
    </style>
</head>
<body>
<!--
1.规律
1.默认情况下所有的绝对定位的元素, 无论有没有祖先元素, 都会以body作为参考点

2.如果一个绝对定位的元素有祖先元素, 并且祖先元素也是定位流, 那么这个绝对定位的元素就会以定位流的那个祖先元素作为参考点
2.1只要是这个绝对定位元素的祖先元素都可以
2.2指的定位流是指绝对定位/相对定位/固定定位
2.3定位流中只有静态定位不行

3.如果一个绝对定位的元素有祖先元素, 并且祖先元素也是定位流, 而且祖先元素中有多个元素都是定位流, 那么这个绝对定位的元素会以离它最近的那个定位流的祖先元素为参考点
-->
<div class="box1">
    <div class="box2">
        <div class="box3"></div>
    </div>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>78-绝对定位-注意点</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        /*
        .box1{
            width: 100px;
            height: 100px;
            background-color: red;
            position: absolute;
            right: 0;
            bottom: 0;
        }
        .box2{
            width: 2000px;
            height: 100px;
            background-color: green;
        }
        .box3{
            width: 100px;
            height: 2000px;
            background-color: blue;
        }
        */
        .box1{
            width: 300px;
            height: 300px;
            background-color: red;
            border: 10px solid #000;
            padding: 30px;
            position: relative;
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: green;
            position: absolute;
            left: 0;
            top: 0;
        }
    </style>
</head>
<body>
<!--
1.如果一个绝对定位的元素是以body作为参考点, 那么其实是以网页首屏的宽度和高度作为参考点, 而不是以整个网页的宽度和高度作为参考点

2.一个绝对定位的元素会忽略祖先元素的padding
-->

<!--
<div class="box1"></div>
<div class="box2"></div>
<div class="box3"></div>
-->

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
    <title>79-绝对定位-子绝父相</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        ul{
            list-style: none;
            width: 800px;
            height: 50px;
            margin: 0 auto;
            margin-top: 100px;
            background-color: red;
        }
        ul li{
            float: left;
            width: 150px;
            line-height: 50px;
            text-align: center;
            background-color: #ccc;
        }
        ul li:nth-of-type(4){
            background-color: yellow;
            position: relative;
        }
        ul li img{
            /*
            相对定位弊端:
            相对定位不会脱离标准流, 会继续在标准流中占用一份空间, 所以不利于布局界面
            */
            /*
            position: relative;
            left: -42px;
            top: -18px;
            */
            /*
            绝对定位弊端:
            默认情况下绝对定位的元素会以body作为参考点, 所以会随着浏览器的宽度高度的变化而变化
            */
            /*
            position: absolute;
            left: 526px;
            top: 90px;
            */

            /*
            子绝父相
            子元素用绝对定位, 父元素用相对定位
            */
            position: absolute;
            /*left: 40px;*/
            left: 50%;
            margin-left: -12px;
            top: -10px;
        }
    </style>
</head>
<body>
<ul>
    <li>服装城</li>
    <li>美妆馆</li>
    <li>京东超市</li>
    <li>全球购
        <img src="images/hot.png" alt="">
    </li>
    <li>闪购</li>
    <li>团购</li>
    <li>拍卖</li>
    <li>金融</li>
</ul>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>80-绝对定位-水平居中</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 300px;
            /*width: 50%;*/
            height: 50px;
            background-color: red;
            /*margin: 0 auto;*/
            position: absolute;
            left: 50%;
            margin-left: -150px;
        }
    </style>
</head>
<body>
<!--
1.如何让绝对定位的元素水平居中
只需要设置绝对定位元素的left:50%;
然后再设置绝对定位元素的 margin-left: -元素宽度的一半px;
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
    <title>81-定位练习1</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 300px;
            height: 300px;
            border: 2px solid #ccc;
            margin: 0 auto;
            margin-top: 100px;
            position: relative;
        }
        div img{
            width: 300px;
            height: 200px;
        }
        div .hot{
            width: 45px;
            height: 44px;
            background: url("images/tuangou.png") no-repeat 0px -280px;
            /*display: inline-block;*/
            position: absolute;
            left: 0;
            top: 0;
        }
        div .price{
            width: 134px;
            height: 42px;
            background: url("images/tuangou.png") no-repeat 0px -362px;
            /*display: inline-block;*/
            position: absolute;
            left: -7px;
            top: 163px;
        }
    </style>
</head>
<body>
<div>
    <img src="images/meat.jpg" alt="">
    <span class="hot"></span>
    <span class="price"></span>
    <p>【2店通用】Love Taste爱味道牛排生活馆 双人套餐，提供免费WiFi</p>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>82-定位练习2</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 520px;
            height: 280px;
            border: 2px solid gold;
            margin: 0 auto;
            margin-top: 100px;
            position: relative;
        }
        div span{
            /*margin-top: 10px;*/
            /*display: block;*/
            width: 40px;
            height: 80px;
            background-color: rgba(0,0,0,0.3);
            font-size: 50px;
            color: white;
            text-align: center;
            line-height: 80px;
        }
        div .leftArrow{
            position: absolute;
            left: 0px;
            top: 100px;
        }
        div .rightArrow{
            position: absolute;
            right: 0px;
            top: 100px;
        }
        ol{
            list-style: none;
            width: 200px;
            height: 40px;
            background-color: rgba(255,255,255,0.7);
            position: absolute;
            right: 10px;
            bottom: 10px;
        }
        ol li{
            width: 40px;
            /*height: 40px;*/
            line-height: 40px;
            text-align: center;
            border: 1px solid gold;
            box-sizing: border-box;
            float: left;
        }
    </style>
</head>
<body>
<div>
    <img src="images/ad.jpg" alt="">
    <span class="leftArrow">&lt;</span>
    <span class="rightArrow">&gt;</span>
    <ol>
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
        <li>5</li>
    </ol>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>83-定位流-固定定位</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        /*
        div{
            width: 200px;
            height: 2000px;
            border: 1px solid #000;
            background-image: url(images/girl.jpg);
            background-repeat: no-repeat;
            background-attachment: fixed;
        }
        */
        div{
            width: 100px;
            height: 100px;
        }
        .box1{
            background-color: red;
        }
        .box2{
            background-color: green;
            position: fixed;
        }
        .box3{
            background-color: blue;
        }
        /*
        span{
            width: 100px;
            height: 100px;
            background-color: yellow;
            position: fixed;
        }
        */
        .box4{
            height: 2000px;
            background-color: yellow;
        }
    </style>
</head>
<body>
<!--<div></div>-->

<!--
1.什么是固定定位?
固定定位和前面学习的背景关联方式很像, 背景定位可以让背景图片不随着滚动条的滚动而滚动, 而固定定位可以让某个盒子不随着滚动条的滚动而滚动

注意点:
1.固定定位的元素是脱离标准流的, 不会占用标准流中的空间
2.固定定位和绝对定位一样不区分行内/块级/行内块级
3.IE6不支持固定定位
-->
<div class="box1"></div>
<div class="box2"></div>
<div class="box3"></div>
<div class="box4"></div>
<!--<span>我是span</span>-->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>84-固定定位-应用场景</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .nav{
            width:100%;
            height: 45px;
            background: url("images/nav.png") no-repeat center top;
            position: fixed;
            top: 0;
            z-index: 1;
        }
        .content{
            width:100%;
            height: 8250px;
            background: url("images/content.png") no-repeat center top;
        }
        div img:first-child{
            position: fixed;
            left: 0;
            top: 200px;
        }
        div img:last-child{
            position: fixed;
            right: 0;
            top: 200px;
        }
        a{
            position: fixed;
            right: 10px;
            bottom: 10px;
            width: 50px;
            /*height: 50px;*/
            background-color: rgba(0,0,0,0.3);
            text-align: center;
            line-height: 50px;
            text-decoration: none;
        }
        .test{
            width: 100px;
            height: 100px;
            background-color: red;
            position: relative;
            left: 100px;
            top: 100px;
        }
    </style>
</head>
<body>
<div class="nav"></div>
<div class="test"></div>
<div class="content">
    <img src="images/left_ad.png" alt="">
    <img src="images/right_ad.png" alt="">
</div>
<a href="#">返回</a>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>85-定位流-z-index属性</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        /*
        div{
            width: 100px;
            height: 100px;
        }
        .box1{
            background-color: red;
            position: relative;
            left: 0;
            top: 0;
        }
        .box2{
            background-color: green;
            position: absolute;
            left: 50px;
            top: 50px;
        }
        .box3{
            background-color: blue;
            position: fixed;
            left: 100px;
            top: 100px;
        }
        */
        .father1{
            width: 200px;
            height: 200px;
            background-color: red;
            position: relative;
            z-index: 2;
        }
        .father2{
            width: 200px;
            height: 200px;
            background-color: green;
            position: relative;
            z-index: 3;
        }
        .son1{
            width: 100px;
            height: 100px;
            background-color: blue;
            position: absolute;
            left: 200px;
            top: 200px;
            z-index: 1;
        }
        .son2{
            width: 100px;
            height: 100px;
            background-color: yellow;
            position: absolute;
            left: 250px;
            top: 50px;
            z-index: 2;
        }
    </style>
</head>
<body>
<!--
1.什么是z-index属性?
默认情况下所有的元素都有一个默认的z-index属性, 取值是0.
z-index属性的作用是专门用于控制定位流元素的覆盖关系的

1.默认情况下定位流的元素会盖住标准流的元素
2.默认情况下定位流的元素后面编写的会盖住前面编写的
3.如果定位流的元素设置了z-index属性, 那么谁的z-index属性比较大, 谁就会显示在上面

注意点:
1.从父现象
1.1如果两个元素的父元素都没有设置z-index属性, 那么谁的z-index属性比较大谁就显示在上面
1.2如果两个元素的父元素设置了z-index属性, 那么子元素的z-index属性就会失效, 也就是说谁的父元素的z-index属性比较大谁就会显示在上面
-->
<!--
<div class="box1"></div>
<div class="box2"></div>
<div class="box3"></div>
-->
<div class="father1">
    <div class="son1"></div>
</div>
<div class="father2">
    <div class="son2"></div>
</div>
</body>
</html>
```

