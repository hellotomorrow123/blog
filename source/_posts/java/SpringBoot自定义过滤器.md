1.通过配置类

```java
public class HttpFilter implements Filter {

    @Override
    public void init(FilterConfig filterConfig) throws ServletException {
        System.out.println("init");
    }

    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("doFilter");
    }

    @Override
    public void destroy() {
        System.out.println("destroy");
    }
}
```

```java
@Configuration
public class FilterConfigurer {

    @Bean
    public FilterRegistrationBean httpFilter(){
        FilterRegistrationBean filterRegistrationBean=new FilterRegistrationBean();
        HttpFilter httpFilter=new HttpFilter();
        filterRegistrationBean.setFilter(httpFilter);
        List<String> urls=new ArrayList<>();
        urls.add("/hello/*");
        filterRegistrationBean.setUrlPatterns(urls);
        return filterRegistrationBean;
    }
}
```

2.通过@WebFilter和@ServletComponentScan

```java
@WebFilter(urlPatterns = "/hello/*",filterName = "timeFilter")
public class TimeFilter implements Filter {
    @Override
    public void doFilter(ServletRequest servletRequest, ServletResponse servletResponse, FilterChain filterChain) throws IOException, ServletException {
        System.out.println("doFilter");
    }

    @Override
    public void init(FilterConfig filterConfig) throws ServletException {
        System.out.println("init");
    }

    @Override
    public void destroy() {
        System.out.println("destroy");
    }
}

```

```java
@SpringBootApplication
@ServletComponentScan
public class SpringBootWebApplication {

    public static void main(String[] args) {
        SpringApplication.run(SpringBootWebApplication.class, args);
    }

}
```

