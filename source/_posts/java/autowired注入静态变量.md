```
title: autowired注入静态变量
date: 2021/08/24 20:46:25
categories:
- [Java, 笔记]
tags:
```

方式一：

声明一个静态的变量和方法，在相应注入一个对应的变量和方法。最后PostConstruct注解在init时实现

```java
@Component
public class Test{
	private static classA classa;
	@Autowired
	private calssA classaTmp;
	
	@PostConstruct
	public void init(){
		classa=classTmp;
	}
}
```

方式二：

在set时注入

```java
@Component
public class Test{
	private static classA classa;
	
	@Value("${xx.xxx.xxx.classA}")
	public void setclassa(classA classa){
		Test.classa=classa;
	}
}
```

