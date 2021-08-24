---
title: Spring接收参数的方式
date: 2021/08/20 20:46:25
categories:
- [Java, 笔记]
tags:
---

`@RequestParam` 和 `@PathVariable` 注解是用于从request中接收请求的，两个都可以接收参数，关键点不同的是`@RequestParam` 是从request里面拿取值，而 `@PathVariable` 是从一个URI模板里面来填充

#### @RequestParam

```java
http://localhost:8080/springmvc/hello/101?param1=10&param2=20
```

@RequestParam 支持下面四种参数

    defaultValue 如果本次请求没有携带这个参数，或者参数为空，那么就会启用默认值
    name 绑定本次参数的名称，要跟URL上面的一样
    required 这个参数是不是必须的
    value 跟name一样的作用，是name属性的一个别名
#### @PathVariable

这个注解能够识别URL里面的一个模板，我们看下面的一个URL

```
http://localhost:8080/springmvc/hello/101
```

#### @PathParam

这个注解是和spring的pathVariable是一样的，也是基于模板的，但是这个是jboss包下面的一个实现，上面的是spring的一个实现，都要导包

#### @QueryParam

@QueryParam 是 JAX-RS 本来就提供的，和Spring的RequestParam作用一致

#### @ResponseBody

responseBody表示服务器返回的时候以一种什么样的方式进行返回， 将内容或对象作为 HTTP 响应正文返回，值有很多，一般设定为json

#### @RequestBody

一般是post请求的时候才会使用这个请求，把参数丢在requestbody里面

传递数组：

```java
@RestController
public class TestController {
    @PostMapping("/test")
    public String Test(@RequestParam(value = "str[]") String str[]){
        return String.valueOf(str.length);
    }
}
```

```java
@RestController
public class TestController {
    @PostMapping("/test")
    public String Test(@RequestBody String str[]){
        return String.valueOf(str.length);
    }
}
```

传递map

```java
@RestController
public class TestController {
    @PostMapping("/test")
    public String Test(@RequestBody Map<String,String> map){
        return map.toString();
    }
}
```

```java
@RestController
public class TestController {
    @PostMapping("/test")
    public String Test(@RequestParam Map<String,String> map){
        return map.toString();
    }
}
```

传递list

```java
使用@ModelAttribute+对象
@RestController
public class TestController {
    @PostMapping("/test")
    public String Test(@ModelAttribute Student student){
    }
}
```

```
使用@RequestParam
@RestController
public class TestController {
    @PostMapping("/test")
    public String Test(@RequestParam("list") List<String> list){
        return "success";
    }
}

```

```
使用@RequestBody
@RestController
public class TestController {
    @PostMapping("/test")
    public String Test(@RequestBody List<String> list){
        return "success";
    }
}
```

```
使用@RequestBody+对象
@RestController
public class TestController {
    @PostMapping("/test")
    public String Test(@RequestBody Student student){
        return "success";
    }
}
```

