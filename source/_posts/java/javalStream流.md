---
title: javaStream流
date: 2021/08/24 20:46:25
categories:
- [Java, 笔记]
tags:
---



stream() 生成串行流

parallelStream()生成并行流

**1.stream不存储数据**

**2.stream不改变源数据**

**3.stream的延迟执行特性**

stream->filter->sorted->map->collect

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020110911333574.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L211X3dpbmQ=,size_16,color_FFFFFF,t_70#pic_center)

![img](https://img-blog.csdnimg.cn/20181223012834784.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3lfa195,size_16,color_FFFFFF,t_70)

### 中间操作符

map(mapToInt,mapToLong,mapToDouble) 转换操作符，把比如A->B，这里默认提供了转int，long，double的操作符。

flatmap(flatmapToInt,flatmapToLong,flatmapToDouble) 拍平操作比如把 int[]{2,3,4} 拍平 变成 2，3，4 也就是从原来的一个数据变成了3个数据，这里默认提供了拍平成int,long,double的操作符。

limit 限流操作，比如数据流中有10个 我只要出前3个就可以使用。

distint 去重操作，对重复元素去重，底层使用了equals方法。

filter 过滤操作，把不想要的数据过滤。

peek 挑出操作，如果想对数据进行某些操作，如：读取、编辑修改等。

skip 跳过操作，跳过某些元素。

sorted(unordered) 排序操作，对元素排序，前提是实现Comparable接口，当然也可以自定义比较器

### 终止操作符

collect 收集操作，将所有数据收集起来，这个操作非常重要，官方的提供的Collectors 提供了非常多收集器，可以说Stream 的核心在于Collectors。

count 统计操作，统计最终的数据个数。

findFirst、findAny 查找操作，查找第一个、查找任何一个 返回的类型为Optional。

noneMatch、allMatch、anyMatch 匹配操作，数据流中是否存在符合条件的元素 返回值为bool 值。

min、max 最值操作，需要自定义比较器，返回数据流中最大最小的值。

reduce 规约操作，将整个数据流的值规约为一个值，count、min、max底层就是使用reduce。

forEach、forEachOrdered 遍历操作，这里就是对最终的数据进行消费了。

toArray 数组操作，将数据流的元素转换成数组。

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.regex.Pattern;
import java.util.stream.Stream;

public class StreamTest {
    public static void main(String[] args) {
        //创建流的方式
        ArrayList<String> arrayList=new ArrayList<>();
        arrayList.add("1");
        arrayList.add("2");
        arrayList.add("3");
        arrayList.add("4");

        //方式一，使用stream()创建串行流
        Stream<String> stream1=arrayList.stream();

        //方式二，使用parallelStream创建并行流
        Stream<String> stream2=arrayList.parallelStream();

        //方式三，使用stream的静态方法
        Stream<String> stream3=Stream.of("1","2","3","4");
        Stream<Integer> stream4=Stream.iterate(0,(x)->x+2).limit(4);
        Stream<Double> stream5=Stream.generate(Math::random).limit(4);

        //方式四,使用Arrays.stream()方法
        Integer num[]=new Integer[4];
        num[0]=1;
        num[1]=2;
        num[2]=3;
        num[3]=4;
        Stream<Integer> stream6= Arrays.stream(num);

        //方式五，使用 Pattern.splitAsStream() 方法 ，将字符串转换成流
        Pattern pattern = Pattern.compile(",");
        Stream<String> stream = pattern.splitAsStream("a,b,c,d");
        
    }
}

```

```java
public void CollectStream(){

        class Student{
            String name;

            public Student(String name, int age, int type) {
                this.name = name;
                this.age = age;
                this.type = type;
            }

            public String getName() {
                return name;
            }

            public void setName(String name) {
                this.name = name;
            }

            public int getAge() {
                return age;
            }

            public void setAge(int age) {
                this.age = age;
            }

            public int getType() {
                return type;
            }

            public void setType(int type) {
                this.type = type;
            }

            int age;
            int type;
        }
        
        Student s1=new Student("aa",10,1);
        Student s2=new Student("bb",20,2);
        Student s3=new Student("cc",30,3);

        List<Student> list=Arrays.asList(s1,s2,s3);

        //转为list
        List<Integer> ageList=list.stream().map(Student::getAge).collect(Collectors.toList());

        //转为set
        Set<Integer> ageSet=list.stream().map(Student::getAge).collect(Collectors.toSet());

        //转为map
        Map<String,Integer> studentMap=list.stream().collect(Collectors.toMap(Student::getName,Student::getAge));

        //字符串分割连接
        String joinName=list.stream().map(Student::getName).collect(Collectors.joining(",","(",")"));

        //聚合操作
        //1.求学生总数
        Long count=list.stream().collect(Collectors.counting());
        //2.求最大年龄
        Integer maxAge=list.stream().map(Student::getAge).collect(Collectors.maxBy(Integer::compare)).get();
        //3.求所有人的年龄
        Integer sumAge=list.stream().collect(Collectors.summingInt(Student::getAge));
        //4.求平均年龄
        Double averageAge=list.stream().collect(Collectors.averagingDouble(Student::getAge));

        //分组
        Map<Integer,List<Student>> ageMap=list.stream().collect(Collectors.groupingBy(Student::getAge));
        //多重分组
        Map<Integer,Map<Integer,List<Student>>> typeAgeMap=list.stream().collect(Collectors.groupingBy(Student::getType,Collectors.groupingBy(Student::getAge)));

        //分区
        Map<Boolean,List<Student>> partMap=list.stream().collect(Collectors.partitioningBy(v->v.getAge()>5));

        //规约
        Integer allAge=list.stream().map(Student::getAge).collect(Collectors.reducing(Integer::sum)).get();
    }
```





参考文章：https://www.jianshu.com/p/3dc56886c2eb
