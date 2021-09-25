# 第一类：请求路径参数

**1. @PathVariable**

获取路径参数。即url/{id}这种形式。

**2. @RequestParam**

获取查询参数。即url?name=这种形式

```java
@GetMapping("/demo/{id}")
public void demo(@PathVariable(name = "id") String id, @RequestParam(name = "name") String name) {
    System.out.println("id="+id);
    System.out.println("name="+name);
}
```

# 第二类：Body参数

**1. @RequestBody**

```java
@PostMapping(path = "/demo1")
public void demo1(@RequestBody Person person) {
    System.out.println(person.toString());
}
```

```java
@PostMapping(path = "/demo1")
public void demo1(@RequestBody Map<String, String> person) {
    System.out.println(person.get("name"));
}
```

# 第三类：请求头参数以及Cookie

**1. @RequestHeader**

```java
@GetMapping("/demo3")
public void demo3(@RequestHeader(name = "myHeader") String myHeader,
        @CookieValue(name = "myCookie") String myCookie) {
    System.out.println("myHeader=" + myHeader);
    System.out.println("myCookie=" + myCookie);
}
```

 **2. @CookieValue**

```java
@GetMapping("/demo3")
public void demo3(HttpServletRequest request) {
    System.out.println(request.getHeader("myHeader"));
    for (Cookie cookie : request.getCookies()) {
        if ("myCookie".equals(cookie.getName())) {
            System.out.println(cookie.getValue());
        }
    }
}
```

# 第四类：servlet

```java
HttpServletRequest
HttpServletResponse
```

