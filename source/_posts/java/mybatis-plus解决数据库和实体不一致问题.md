---
title: mybatis-plus解决数据库和实体不一致
date: 2021/08/24 20:46:25
categories:
- [Java, 笔记]
tags:
---



1.数据库字段名和实体类字段名存在一定关系

数据库字段和实体类字段有对应关系，这里的对应关系就是数据库字段全为大写字母且单词之间用`_`分隔，实体类的属性名采用小驼峰式命名，一定要保证对应，例如数据库中的`USER_ID`对应实体类中的`userId`字段。

```
public class User{
	private int userId;
	private String userName;
	private String userPassword;
}
```

这种不对应的情况，Mybatis提供了一个自动驼峰命名规则的设置，但是默认是关闭的，所以当我们没有设置的时候，这样也是对应不上的。我们就需要在Mybatis的配置文件中添加如下配置。

2.数据库字段名与实体类字段名“毫无关联”

2.1 在编写sql时为字段起别名

2.2 ResultMap结果集映射

2.3 注解@TableField(value="age")

