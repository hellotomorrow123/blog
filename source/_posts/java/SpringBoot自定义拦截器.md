自定义切面

```java
@Component
@Slf4j
public class HttpInterceptor implements HandlerInterceptor {
    @Override
    public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws Exception {
        log.info("url:{}",request.getRequestURL().toString());
        log.info("method:{}",request.getMethod());
        log.info("ip:{}",request.getRemoteAddr());
        return true;
    }

    @Override
    public void postHandle(HttpServletRequest request, HttpServletResponse response, Object handler, ModelAndView modelAndView) throws Exception {
        System.out.println("post");
    }

    @Override
    public void afterCompletion(HttpServletRequest request, HttpServletResponse response, Object handler, Exception ex) throws Exception {
        System.out.println("after");
    }
}
```

自定义配置类

```
@Configuration
public class WebConfigurer implements WebMvcConfigurer {

    @Autowired
    private HttpInterceptor httpInterceptor;

    @Override
    public void addInterceptors(InterceptorRegistry registry) {
        registry.addInterceptor(httpInterceptor).addPathPatterns("/**").excludePathPatterns("/login","/register");
    }
}
```

