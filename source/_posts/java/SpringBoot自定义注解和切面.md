自定义注解

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
@Inherited
@Documented
public @interface LogInfo {
}
```

自定义切面

```java
@Aspect
@Component
@Slf4j
public class HttpAspect {

    @Pointcut("@annotation(com.example.springbootweb.annotation.LogInfo)")
    public void accesslog(){

    }

    @Before("accesslog()")
    public void beforePointcut(JoinPoint joinPoint){
        ServletRequestAttributes attributes= (ServletRequestAttributes) RequestContextHolder.getRequestAttributes();
        HttpServletRequest request =attributes.getRequest();
        log.info("url:{}",request.getRequestURL().toString());
        log.info("method:{}",request.getMethod());
        log.info("ip:{}",request.getRemoteAddr());
        log.info("input:{}", Arrays.asList(joinPoint.getArgs()));
    }

    @After("accesslog()")
    public void afterPointcut(JoinPoint joinPoint){

    }

    @Around("accesslog()")
    public Object aroundPointcut(ProceedingJoinPoint joinPoint) throws Throwable {
        long startTime=System.currentTimeMillis();
        Object res=joinPoint.proceed();
        log.info("output:{}",res);
        log.info("costTime:{} ms",System.currentTimeMillis()-startTime);
        return res;
    }
}

```

使用

```
@RestController
public class HelloController {

    @RequestMapping("hello")
    @LogInfo()
    public String hello(){
        System.out.println("访问成功！");
        return "hello";
    }

}
```

