1.使用注解@ControllerAdvice和@ExceptionHandler()

```java
@Slf4j
@ControllerAdvice
@ResponseBody
public class HttpExceptionHandler {

    @ExceptionHandler()
    public Result<String> httpExecption(HttpServletResponse httpServletResponse,NullPointerException e){
        log.info("status:{}",httpServletResponse.getStatus());
        return Result.error(e.getMessage());
    }
}
```

2.使用ErrorController类实现

```java
@Slf4j
@RestController
@ResponseBody
public class NUllExceptionHandler implements ErrorController {

    @RequestMapping(path  = "/error" )
    public Result<String> error(HttpServletRequest request, HttpServletResponse response){
        return Result.error("404");
    }

}
```

```
1.注解@ControllerAdvice方式只能处理控制器抛出的异常。此时请求已经进入控制器中。

2.类ErrorController方式可以处理所有的异常，包括未进入控制器的错误，比如404,401等错误

3.如果应用中两者共同存在，则@ControllerAdvice方式处理控制器抛出的异常，类ErrorController方式未进入控制器的异常。

4.@ControllerAdvice方式可以定义多个拦截方法，拦截不同的异常类，并且可以获取抛出的异常信息，自由度更大。
```

