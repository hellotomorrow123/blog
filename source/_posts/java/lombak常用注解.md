---
title: lombak常用注解
date: 2021/08/19 20:46:25
categories:
- [Java, 笔记]
tags:
- lombak
---



### @NonNull

使用在方法的参数或者构造器的参数上，用于生成null验证。

### @Cleanup

使用在资源之前，用于表示资源可以被完美自动释放（在代码的执行路径超出资源范围之前）。

### @Getter and @Setter

标注在字段之上，用于自动生成get、set方法。Boolean类型为is开头。

生成的get、set方法默认情况之下都是public的，但也可以手动指定范围value=AccessLevel.PUBLIC、AccessLevel.PROTECTED、AccessLevel.PRIVATE、AccessLevel.PRIVATE四种。

也能标注在类上，表示针对该类中所有的非静态字段进行get、set方法自动生成。

如果指定某个字段的AccessLevel=AccessLevel.NONE，则可以使该生成动作失效，此时可以手动实现get、set方法，这应用于在这些方法中有一些自定义逻辑的情况下。

### @ToString

标注于类之上，用于生成toString()方法。

includeFieldNames，默认为true，表示在toString输出时输出字段名称。

callSuper，默认为false，表示生成toString时不输出超类中的字段内容，若要输出超类中的内容，需要设置为true

doNotUseGetters，默认为false，表示获取字段值时通过get方法获取，设置为true表示直接通过字段获取

onlyExplicitlyIncluded，默认为false，表示输出所有非静态字段内容，如果设置为true，则只输出标注有@ToString.Include的字段和方法。

### @ToString.Include

标注于字段、方法之上，表示生成toString方法时包含该注解标注的字段和方法，需要与onlyExplicitlyIncluded一起使用。

rank，默认为0，表示级别，数字越大级别越高，高级别将会优先输出，同级别按照代码顺序输出。

name，可以为标注的成员（字段或者方法）另起一个名字。

### @ToString.Exclude

标注于字段之上，表示生成toString方法时不包含被该注解标注的字段。那么生成toString方法时会跳过这些字段。

### @EqualsAndHashCode

标注于类之上用于生成hashCode方法和equals方法。

callSuper，同上

doNotUseGetters，同上

onlyExplicitlyIncluded，同上，需要配合@EqualsAndHashCode.Include使用。

### @EqualsAndHashCode.Include

标注于字段或者方法之上，需要与onlyExplicitlyIncluded配合使用，表示将该注解标注的内容添加到实现hashCode和equals方法的内容中去。

### @EqualsAndHashCode.Exclude

标注于字段之上，用于排除不需要参与生成hashCode和equals方法的字段。可单独使用。

### @NoArgsConstructor

用于生成无参构造器，如果类中存在final字段，则会报编译错误。一般结合其他几个构造器注解一起使用提供一个无参构造器，并且不会检查@NonNull标注的字段

force,默认为false，表示是否针对final字段进行特殊处理，如果将其设置为true，则上面的编译错误将会消失，内部处理为，将final字段初始化为0\false\null

access，默认为lombok.AccessLevel.PUBLIC，表示public范围的构造器

staticName，一旦设置该值，则会生成一个静态的“构造器”工厂，其内部包裹着一个私有的构造器，对外提供创建对象的功能，这是明显的工厂模式。

### @RequiredArgsConstructor

用于按照要求生成构造器，所谓的要求就是包含final字段和类似于@NonNull约束标注的字段，会对@NonNull字段进行明确的null检查

access，同上

staticName，同上

### @AllArgsConstructor

用于生成包含所有字段的构造器。@NonNull字段会进行null判断检查。

access，同上

staticName，同上

### @Data

标注于类之上，是@ToString，@EqualsAndHashCode、@Getter、@Setter、@RequiredArgsConstructor的综合体
 　staticConstructor，同staticName

### @Value

可以看成是@Data的变体，表示生成一个不可变类（final类）。没有set方法，只有get方法，字段全部为final private的，类也是final的

等效于@Getter @FieldDefaults(makeFinal=true, level=AccessLevel.PRIVATE) @AllArgsConstructor @ToString @EqualsAndHashCode

staticConstructor，同上。

如果手工实现了任何一个注解的功能，那么该注解将失效，为了使注解起效，你可以在手共实现的方法上添加注解@lombok.experimental.Tolerate，用于将手共实现对lombok隐藏。

我们可以使用下面两种方式来重写默认为final和private的行为，一是直接在字段上添加accessLevel，二是使用@NonFinal或者@PackagePrivate注解。

### @Builder

标注于类之上，用于生成复杂的builder API，创建构建者模式。

还可用于标注于构造器和方法之上。

### @SneakyThrows

标注于方法之上用于隐藏异常抛出语句，该注解存在争议，暂不使用

### @Log

- @CommonsLog
- @Flogger
- @JBossLog
- @Log
- @Log4j
- @Log4j2
- @Slf4j
- @XSlf4j

### @Synchronized

标注于方法（只能用于静态方法和实例方法）之上，用于表示同步方法，锁可以使用默认的也可以使用自定义的锁（private final ）。

### @Accessors

配置lombok如何产生和显示getters和setters的方法，既可以注解在类上也可以注解在属性上。fluent：指定是否有前缀get/set。chain 如果设置为true,则set方法返回this,false则返回void。prefix 可以指定前缀，生成get/set方法时会去掉指定的前缀。

