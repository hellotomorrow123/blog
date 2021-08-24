---
title: Java的4种内部类
date: 2021/08/18 20:46:25
categories:
- [Java, 笔记]
tags:
- 内部类
---

内部类的4个种类：

1. 常规内部类。
2. 静态内部类。
3. 局部内部类。
4. 匿名内部类。

```java
package com.cb.study;

interface say{
    void display();
}

public class InlineClass {
    //1.常规内部类
    class A{
        String type;
        public String getType() {
            return type;
        }
        public void setType(String type) {
            this.type = type;
        }
    }
    //2.静态内部类
    static class B{
        String type;
        public String getType() {
            return type;
        }
        public void setType(String type) {
            this.type = type;
        }
    }
    public void test(){
        //3.局部内部类
        class C{
            String type;
            public String getType() {
                return type;
            }
            public void setType(String type) {
                this.type = type;
            }
        }
    }

    public static void main(String[] args) {
        //4.匿名内部类
        //1.匿名内部类必须继承一个抽象类或者实现一个接口。
        //2.匿名内部类没有类名，因此没有构造方法。
        new say(){
            @Override
            public void display() {
                System.out.println("hello");
            }
        };
    }

}

```

