---
title: autowired
date: 2021/08/24 20:46:25
categories:
- [Java, 笔记]
tags:
---

依赖注入：

1.@Autowired

作用于field、setter方法、构造函数

```
public class HelloController {

    @Autowired
    private Lisi lisi;
    
    @GetMapping("/hello")
    public String getHello(){
        lisi.say();
        return "hello world;";
    }
}
```

