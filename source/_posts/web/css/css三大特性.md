```
title: css三大特性
date: 2021/09/04 20:46:25
categories:
- [前端]
tags:
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>24-CSS三大特性之继承性</title>
    <style>
        div{
            color: red;
            text-decoration: none;
            font-size: 30px;
        }
    </style>
</head>
<body>
<!--
1.什么是继承性?
作用: 给父元素设置一些属性, 子元素也可以使用, 这个我们就称之为继承性

注意点:
1.并不是所有的属性都可以继承, 只有以color/font-/text-/line-开头的属性才可以继承
2.在CSS的继承中不仅仅是儿子可以继承, 只要是后代都可以继承
3.继承性中的特殊性
3.1a标签的文字颜色和下划线是不能继承的
3.2h标签的文字大小是不能继承的

应用场景:
一般用于设置网页上的一些共性信息, 例如网页的文字颜色, 字体,文字大小等内容
body{}
-->

<div>
    <p>我是段落</p>
</div>

<div>
    <ul>
        <li>
            <p>我是段落</p>
        </li>
    </ul>
</div>

<div>
    <a href="#">我是超链接</a>
</div>

<div>
    <h1>我是大标题</h1>
</div>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>25-CSS三大特性之层叠性</title>
    <style>
        p{
            color: red;
        }
        .para{
            color: blue;
        }
    </style>
</head>
<body>
<!--
1.什么是层叠性?
作用: 层叠性就是CSS处理冲突的一种能力

注意点:
层叠性只有在多个选择器选中"同一个标签", 然后又设置了"相同的属性", 才会发生层叠性

CSS全称 Cascading StyleSheet
-->
<p id="identity" class="para">我是段落</p>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>26-CSS三大特性之优先级</title>
    <style>
        /*
        li{
            color: blue;
        }
        ul{
            color: red;
        }
        */
        /*
        p{
            color: blue;
        }
        p{
            color: red;
        }
        */
        #identity{
            color: purple;
        }
        .para{
            color: pink;
        }
        p{
            color: green;
        }
        *{
            color: blue;
        }
        li{
            color: red;
        }
    </style>
</head>
<body>
<!--
1.什么是优先级?
作用:当多个选择器选中同一个标签, 并且给同一个标签设置相同的属性时, 如何层叠就由优先级来确定

2.优先级判断的三种方式
2.1间接选中就是指继承
如果是间接选中, 那么就是谁离目标标签比较近就听谁的
2.2相同选择器(直接选中)
如果都是直接选中, 并且都是同类型的选择器, 那么就是谁写在后面就听谁的
2.3不同选择器(直接选中)
如果都是直接选中, 并且不是相同类型的选择器, 那么就会按照选择器的优先级来层叠
id>类>标签>通配符>继承>浏览器默认
-->0
<ul>
    <li>
        <p id="identity" class="para">我是段落</p>
    </li>
</ul>
</body>
</html>
```

