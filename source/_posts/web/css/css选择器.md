---
title: css选择器
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
    <title>08-标签选择器</title>
    <style>
        p{
            color: red;
        }
        h1{
            color: blue;
        }
    </style>
</head>
<body>
<!--
1.什么是标签选择器?
作用: 根据指定的标签名称, 在当前界面中找到所有该名称的标签, 然后设置属性

格式:
标签名称{
    属性:值;
}

注意点:
1.标签选择器选中的是当前界面中所有的标签, 而不能单独选中某一个标签
2.标签选择器无论标签藏得多深都能选中
3.只要是HTML中的标签就可以作为标签选择器(h/a/img/ul/ol/dl/input....)
-->
<p>我是段落</p>
<p>我是段落</p>
<p>我是段落</p>
<p>我是段落</p>
<ul>
    <li>
        <ul>
            <li>
                <ul>
                    <li>
                        <p>我是段落</p>
                    </li>
                </ul>
            </li>
        </ul>
    </li>
</ul>
<h1>我是标题</h1>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>09-id选择器</title>
    <style>
        #identity1{
            color: red;
        }
        #identity2{
            color: green;
        }
        #identity3{
            color: blue;
        }
        #identity4{
            color: yellow;
        }
    </style>
</head>
<body>
<!--
1.什么是id选择器?
作用: 根据指定的id名称找到对应的标签, 然后设置属性

格式:
#id名称{
    属性:值;
}

注意点:
1.每个HTML标签都有一个属性叫做id, 也就是说每个标签都可以设置id
2.在同一个界面中id的名称是不可以重复的
3.在编写id选择器时一定要在id名称前面加上#
4.id的名称是有一定的规范的
4.1id的名称只能由字母/数字/下划线
a-z 0-9 _
4.2id名称不能以数字开头
4.3id名称不能是HTML标签的名称
不能是a h1 img input ...
5.在企业开发中一般情况下如果仅仅是为了设置样式, 我们不会使用id ,因为在前端开发中id是留给js使用的
-->
<p id="identity1">迟到毁一生</p>
<p id="identity2">早退穷三代</p>
<p id="identity3">按时上下班</p>
<p id="identity4">必成高富帅</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>10-类选择器</title>
    <style>
        .pp{
            color: red;
        }
        .ppp{
            color: green;
        }
        .pppp{
            color: blue;
        }
        .ppppp{
            color: yellow;
        }
        .para1{
            font-size: 100px;
        }
        .para2{
            font-style: italic;
        }
    </style>
</head>
<body>
<!--
1.什么是类选择器?
作用: 根据指定的类名称找到对应的标签, 然后设置属性

格式:
.类名{
    属性:值;
}

注意点:
1.每个HTML标签都有一个属性叫做class, 也就是说每个标签都可以设置类名
2.在同一个界面中class的名称是可以重复的
3.在编写class选择器时一定要在class名称前面加上.
4.类名的命名规范和id名称的命名规范一样
5.类名就是专门用来给CSS设置样式的
6.在HTML中每个标签可以同时绑定多个类名
格式:
<标签名称 class="类名1 类名2 ...">
错误的写法:
<p class="para1" class="para2">
-->
<p class="pp">迟到毁一生</p>
<p class="ppp">早退穷三代</p>
<p class="pppp">按时上下班</p>
<p class="ppppp">必成高富帅</p>

<p class="para1 para2">我是段落</p>
<p class="para1 para2">我是段落</p>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>11-id选择器和class选择器</title>
    <style>
        /*
        .para1{
            color: red;
            font-size: 30px;
        }
        .para2{
            font-size: 30px;
            text-decoration: underline;
        }
        .para3{
            color: red;
            text-decoration: underline;
        }
        */
        .colorR{
            color: red;
        }
        .size30{
            font-size: 30px;
        }
        .line{
            text-decoration: underline;
        }
    </style>
</head>
<body>
<!--
1.id和class的区别?
1.1
id相当于人的身份证不可以重复
class相当于人的名称可以重复
1.2
一个HTML标签只能绑定一个id名称
一个HTML标签可以绑定多个class名称

2.id选择器和class选择器区别?
id选择器是以#开头
class选择器是以.开头

3.在企业开发中到底用id选择器还是用class选择器?
id一般情况下是给js使用的, 所以除非特殊情况, 否则不要使用id去设置样式

4.在企业开发中一个开发人员对类的使用可以看出这个开发人员的技术水平
一般情况下在企业开发中要注重冗余代码的抽取, 可以将一些公共的代码抽取到一个类选择器中, 然后让标签和这个类选择器绑定即可

-->
<!--
<p class="para1">第一段文字</p>
<p class="para2">第二段文字</p>
<p class="para3">第三段文字</p>
-->
<p class="colorR size30">第一段文字</p>
<p class="size30 line">第二段文字</p>
<p class="colorR line">第三段文字</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>12-后代选择器</title>
    <style>
        /*
        div p{
            color: red;
        }
        */
        /*
        #identity p{
            color: red;
        }
        */
        /*
        .para p{
            color: blue;
        }
        */
        /*
        #identity #iii{
            color: skyblue;
        }
        */
        /*
        #identity .ccc{
            color: purple;
        }
        */
        div ul li p{
            color: red;
        }
    </style>
</head>
<body>
<!--
1.什么是后代选择器?
作用: 找到指定标签的所有特定的后代标签, 设置属性

格式:
标签名称1 标签名称2{
    属性:值;
}
先找到所有名称叫做"标签名称1"的标签, 然后再在这个标签下面去查找所有名称叫做"标签名称2"的标签, 然后在设置属性
div p{}

注意点:
1.后代选择器必须用空格隔开
2.后代不仅仅是儿子, 也包括孙子/重孙子, 只要最终是放到指定标签中的都是后代
3.后代选择器不仅仅可以使用标签名称, 还可以使用其它选择器
4.后代选择器可以通过空格一直延续下去
-->
<!--div ul li p-->
<p>我是段落</p>
<div id="identity" class="para">
    <p>我是段落</p>
    <p>我是段落</p>
    <ul>
        <li>
            <!--<p id="iii" class="ccc">我是段落</p>-->
            <p>我是段落</p>
        </li>
        <li>
            <p>我是段落</p>
        </li>
    </ul>
</div>
<p>我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>13-子元素选择器</title>
    <style>
        /*
        div>p{
            color: red;
        }
        */
        /*
        #identity>p{
            color: blue;
        }
        */
        div>ul>li>p{
            color: purple;
        }
    </style>
</head>
<body>
<!--
1.什么是子元素选择器?
作用: 找到指定标签中所有特定的直接子元素, 然后设置属性

格式:
标签名称1>标签名称2{
    属性:值;
}
先找到所有名称叫做"标签名称1"的标签, 然后在这个标签中查找所有直接子元素名称叫做"标签名称2"的元素

注意点:
1.子元素选择器只会查找儿子, 不会查找其他被嵌套的标签
2.子元素选择器之间需要用>符号连接, 并且不能有空格
3.子元素选择器不仅仅可以使用标签名称, 还可以使用其它选择器
4.子元素选择器可以通过>符号一直延续下去
-->
<!--div>ul>li>p-->
<p>我是段落</p>
<div id="identity">
    <p>我是段落</p>
    <p>我是段落</p>
    <ul>
        <li><p>我是段落</p></li>
    </ul>
</div>
<p>我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>14-后代选择器和子元素选择器</title>
</head>
<body>
<!--
1.后代选择器和子元素选择器之间的区别?
1.1
后代选择器使用空格作为连接符号
子元素选择器使用>作为连接符号
1.2
后代选择器会选中指定标签中, 所有的特定后代标签, 也就是会选中儿子/孙子..., 只要是被放到指定标签中的特定标签都会被选中
子元素选择器只会选中指定标签中, 所有的特定的直接标签, 也就是只会选中特定的儿子标签

2.后代选择器和子元素选择器之间的共同点
2.1
后代选择器和子元素选择器都可以使用标签名称/id名称/class名称来作为选择器
2.2
后代选择器和子元素选择器都可以通过各自的连接符号一直延续下去
选择器1>选择器2>选择器3>选择器4{}

3.在企业开发中如何选择
如果想选中指定标签中的所有特定的标签, 那么就使用后代选择器
如果只想选中指定标签中的所有特定儿子标签, 那么就使用子元素选择器

-->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>15-交集选择器</title>
    <style>
        /*
        p.para1{
            color: red;
        }
        */
        .para1#identity{
            color: blue;
        }
    </style>
</head>
<body>
<!--
1.什么是交集选择器?
作用: 给所有选择器选中的标签中, 相交的那部分标签设置属性

格式:
选择器1选择器2{
    属性: 值;
}

注意点:
1.选择器和选择器之间没有任何的连接符号
2.选择器可以使用标签名称/id名称/class名称
3.交集选择器仅仅作为了解, 企业开发中用的并不多
-->

<p>我是段落</p>
<p>我是段落</p>
<p class="para1" id="identity">我是段落</p>
<p class="para1">我是段落</p>
<p>我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>16-并集选择器</title>
    <style>
        /*
        .ht{
            color: red;
        }
        .para{
            color: red;
        }
        */
        .ht,.para{
            color: red;
        }
    </style>
</head>
<body>
<!--
1.什么是并集选择器?
作用: 给所有选择器选中的标签设置属性

格式:
选择器1,选择器2{
    属性:值;
}

注意点:
1.并集选择器必须使用,来连接
2.选择器可以使用标签名称/id名称/class名称
-->

<h1 class="ht">我是标题</h1>
<p class="para">我是段落</p>
<p>我是段落</p>
<p>我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>17-兄弟选择器</title>
    <style>
        /*
        h1+p{
            color: red;
        }
        */
        h1~p{
            color: green;
        }
    </style>
</head>
<body>
<!--
1.相邻兄弟选择器 CSS2
作用: 给指定选择器后面紧跟的那个选择器选中的标签设置属性

格式:
选择器1+选择器2{
    属性:值;
}

注意点:
1.相邻兄弟选择器必须通过+连接
2.相邻兄弟选择器只能选中紧跟其后的那个标签, 不能选中被隔开的标签

2.通用兄弟选择器 CSS3
作用: 给指定选择器后面的所有选择器选中的所有标签设置属性

格式:
选择器1~选择器2{
    属性:值;
}

注意点:
1.通用兄弟选择器必须用~连接
2.通用兄弟选择器选中的是指定选择器后面某个选择器选中的所有标签, 无论有没有被隔开都可以选中
-->

<!--
<h1>我是标题</h1>
<a href="#">我是超链接</a>
<p>我是段落</p>
<p>我是段落</p>
<p>我是段落</p>
<h1>我是标题</h1>
<p>我是段落</p>
<p>我是段落</p>
<p>我是段落</p>
-->
<h1>我是标题</h1>
<a href="#">我是超链接</a>
<p>我是段落</p>
<p>我是段落</p>
<a href="#">我是超链接</a>
<p>我是段落</p>

<h1>我是标题</h1>
<p>我是段落</p>
<p>我是段落</p>
<p>我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>18-序选择器</title>
    <style>
        /*
        p:first-child{
            color: red;
        }
        */
        /*
        p:first-of-type{
            color: blue;
        }
        */
        /*
        p:last-child{
            color: red;
        }
        */
        /*
        p:last-of-type{
            color: blue;
        }
        */
        /*
        p:nth-child(3){
            color: red;
        }
        */
        /*
        p:nth-of-type(3){
            color: blue;
        }
        */
        /*
        p:nth-last-child(2){
            color: red;
        }
        */
        /*
        p:nth-last-of-type(2){
            color: red;
        }
        */
        /*
        p:only-child{
            color: purple;
        }
        */
        /*
        p:only-of-type {
            color: red;
        }
        */
        .para:only-of-type {
            color: red;
        }
    </style>
</head>
<body>
<!--
CSS3中新增的选择器最具代表性的就是序选择器
1.同级别的第几个
:first-child 选中同级别中的第一个标签
:last-child 选中同级别中的最后一个标签
:nth-child(n) 选中同级别中的第n个标签
:nth-last-child(n) 选中同级别中的倒数第n个标签
:only-child 选中父元素中唯一的标签
注意点: 不区分类型

2.同类型的第几个
:first-of-type 选中同级别中同类型的第一个标签
:last-of-type  选中同级别中同类型的最后一个标签
:nth-of-type(n) 选中同级别中同类型的第n个标签
:nth-last-of-type(n)  选中同级别中同类型的倒数第n个标签
:only-of-type 选中父元素中唯一类型的某个标签
-->
<!--
<h1>我是标题</h1>
<p>我是段落1</p>
<p>我是段落2</p>
<p>我是段落3</p>
<p>我是段落4</p>
<div>
    <p>我是段落5</p>
    <p>我是段落6</p>
    <p>我是段落7</p>
    <p>我是段落8</p>
</div>
-->
<p class="para">我是段落1</p>
<div>
    <p class="para">我是段落2</p>
    <p class="para">我是段落2</p>
    <h1>我是标题</h1>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>19-序选择器下</title>
    <style>
        /*
        p:nth-child(odd){
            color: red;
        }
        p:nth-child(even){
            color: blue;
        }
         */
        /*
        p:nth-of-type(odd){
            color: red;
        }
        p:nth-of-type(even){
            color: blue;
        }
        */
        /*
        p:nth-child(2n+0){
            color: red;
        }
        p:nth-child(2n+1){
            color: blue;
        }
        */
        p:nth-child(3n+0){
            color: red;
        }
    </style>
</head>
<body>
<!--
:nth-child(odd) 选中同级别中的所有奇数
:nth-child(even) 选中同级别中的所有偶数

:nth-child(xn+y)
x和y是用户自定义的, 而n是一个计数器, 从0开始递增

-->
<p>我是项目</p>
<p>我是项目</p>
<p>我是项目</p>
<p>我是项目</p>
<p>我是项目</p>
<p>我是项目</p>
<p>我是项目</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>20-属性选择器上</title>
    <style>
        /*
        p[id]{
            color: red;
        }
        */
        p[class=cc]{
            color: blue;
        }
    </style>
</head>
<body>
<!--
1.什么是属性选择器?
作用: 根据指定的属性名称找到对应的标签, 然后设置属性

格式:
[attribute]
作用:根据指定的属性名称找到对应的标签, 然后设置属性

[attribute=value]
作用: 找到有指定属性, 并且属性的取值等于value的标签, 然后设置属性
最常见的应用场景, 就是用于区分input属性
input[type=password]{}
<input type="text" name="" id="">
<input type="password" name="" id="">
-->
<p id="identity1">我是段落1</p>
<p id="identity2" class="cc">我是段落2</p>
<p class="cc">我是段落3</p>
<p id="identity3" class="para">我是段落4</p>
<p>我是段落5</p>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>21-属性选择器下</title>
    <style>
        /*
        img[alt^=abc]{
            color: red;
        }
        */
        /*
        img[alt|=abc]{
            color: red;
        }
        img[alt$=abc]{
            color: blue;
        }
        */
        /*
        img[alt*=abc]{
            color: red;
        }
        */
        img[alt~=abc]{
            color: red;
        }
    </style>
</head>
<body>
<!--
1.属性的取值是以什么开头的
[attribute|=value] CSS2
[attribute^=value] CSS3
两者之间的区别:
CSS2中的只能找到value开头,并且value是被-和其它内容隔开的
CSS3中的只要是以value开头的都可以找到, 无论有没有被-隔开

2.属性的取值是以什么结尾的
[attribute$=value] CSS3

3.属性的取值是否包含某个特定的值得
[attribute~=value] CSS2
[attribute*=value] CSS3
两者之间的区别:
CSS2中的只能找到独立的单词, 也就是包含value,并且value是被空格隔开的
CSS3中的只要包含value就可以找到
-->

<!--
<img src="" alt="abcdef">
<img src="" alt="abc-www">
<img src="" alt="abc ppp">
<img src="" alt="defabc">
<img src="" alt="ppp abc">
<img src="" alt="www-abc">
<img src="" alt="qq">
<img src="" alt="yy">
-->

<img src="" alt="abcwwwmmm">
<img src="" alt="wwwmmmabc">
<img src="" alt="wwwabcmmm">
<img src="" alt="www-abc-mmm">
<img src="" alt="www abc mmm">
<img src="" alt="qq">

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>22-通配符选择器</title>
    <style>
        /*
        .cc{
            color: red;
        }
        */
        *{
            color: red;
        }
    </style>
</head>
<body>
<!--
1.什么是通配符选择器?
作用: 给当前界面上所有的标签设置属性

格式:
*{
    属性:值;
}

注意点:
由于通配符选择器是设置界面上所有的标签的属性, 所以在设置之前会遍历所有的标签, 如果当前界面上的标签比较多, 那么性能就会比较差, 所以在企业开发中一般不会使用通配符选择器
-->
<!--
<h1 class="cc">我是标题</h1>
<p class="cc">我是段落</p>
<a href="#" class="cc">我是超链接</a>
-->
<h1>我是标题</h1>
<p>我是段落</p>
<a href="#">我是超链接</a>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>23-选择器练习</title>
    <style>
        /*标签选择器
        p{
            color: red;
        }
        */
        /*id选择器
        #identity1{
            color: red;
        }
        #identity2{
            color: red;
        }
        */
        /*类选择器
        .para{
            color: red;
        }
        */
        /*后代选择器
        div p{
            color: red;
        }
        */
        /*子元素选择器
        div>p{
            color: red;
        }
        */
        /*交集选择器
        p.para{
            color: red;
        }
        */
        /*并集选择器
        #identity1,#identity2{
            color: red;
        }
        */
        /*通用兄弟选择器
        h1~p{
            color: red;
        }
        */
        /*序选择器
        p:nth-of-type(n+1){
            color: red;
        }
        */
        /*属性选择器*/
        p[id]{
            color: red;
            font-size: 10px;
            text-decoration: underline;
        }
    </style>
</head>
<body>

<div>
    <h1>我是标题</h1>
    <p id="identity1" class="para">我是段落1</p>
    <p id="identity2" class="para">我是段落2</p>
</div>

</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>68-伪元素选择器</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 200px;
            height: 200px;
            background-color: red;
        }
        /*
        p{
            width: 50px;
            height: 50px;
            background-color: pink;
        }
        */

        div::before{
            content: "爱你";
            width: 50px;
            height: 50px;
            background-color: pink;
            display: block;
        }
        div::after{
            /*指定添加的子元素中存储的内容*/
            content: "么么哒";
            /*指定添加的子元素的宽度和高度*/
            width: 50px;
            /*height: 50px;*/
            /*内容是可以超出标签的范围的, 所以高度为0依然可以看见内容*/
            height:0;
            background-color: pink;
            /*指定添加的子元素的显示模式*/
            display: block;
            /*隐藏添加的子元素*/
            visibility: hidden;
        }

    </style>
</head>
<body>
<!--
1.什么是伪元素选择器?
伪元素选择器作用就是给指定标签的内容前面添加一个子元素或者给指定标签的内容后面添加一个子元素

2.格式:
标签名称::before{
    属性名称:值;
}
给指定标签的内容前面添加一个子元素

标签名称::after{
    属性名称:值;
}
给指定标签的内容后面添加一个子元素

-->
<div>
    <!--<p>爱你</p>-->
    我是文字
    <!--<p>么么哒</p>-->
</div>

</body>
</html>
```

