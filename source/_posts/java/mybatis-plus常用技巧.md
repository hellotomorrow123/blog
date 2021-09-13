# 注解

@TableName 表名注解

|       属性       |   类型   | 必须指定 | 默认值 | 描述                                                         |
| :--------------: | :------: | :------: | :----: | ------------------------------------------------------------ |
|      value       |  String  |    否    |   ""   | 表名                                                         |
|      schema      |  String  |    否    |   ""   | schema                                                       |
| keepGlobalPrefix | boolean  |    否    | false  | 是否保持使用全局的 tablePrefix 的值(如果设置了全局 tablePrefix 且自行设置了 value 的值) |
|    resultMap     |  String  |    否    |   ""   | xml 中 resultMap 的 id                                       |
|  autoResultMap   | boolean  |    否    | false  | 是否自动构建 resultMap 并使用(如果设置 resultMap 则不会进行 resultMap 的自动构建并注入) |
| excludeProperty  | String[] |    否    |   {}   | 需要排除的属性名(@since 3.3.1)                               |

@TableId 主键注解

| 属性  |  类型  | 必须指定 |   默认值    |    描述    |
| :---: | :----: | :------: | :---------: | :--------: |
| value | String |    否    |     ""      | 主键字段名 |
| type  |  Enum  |    否    | IdType.NONE |  主键类型  |

IdType取值

|      值       |                             描述                             |
| :-----------: | :----------------------------------------------------------: |
|     AUTO      |                         数据库ID自增                         |
|     NONE      | 无状态,该类型为未设置主键类型(注解里等于跟随全局,全局里约等于 INPUT) |
|     INPUT     |                    insert前自行set主键值                     |
|   ASSIGN_ID   | 分配ID(主键类型为Number(Long和Integer)或String)(since 3.3.0),使用接口`IdentifierGenerator`的方法`nextId`(默认实现类为`DefaultIdentifierGenerator`雪花算法) |
|  ASSIGN_UUID  | 分配UUID,主键类型为String(since 3.3.0),使用接口`IdentifierGenerator`的方法`nextUUID`(默认default方法) |
|   ID_WORKER   |     分布式全局唯一ID 长整型类型(please use `ASSIGN_ID`)      |
|     UUID      |           32位UUID字符串(please use `ASSIGN_UUID`)           |
| ID_WORKER_STR |     分布式全局唯一ID 字符串类型(please use `ASSIGN_ID`)      |

@TableField

|   属性    |  类型   | 必须指定 | 默认值 |                             描述                             |
| :-------: | :-----: | :------: | :----: | :----------------------------------------------------------: |
|   value   | String  |    否    |   ""   |                         数据库字段名                         |
|    el     | String  |    否    |   ""   | 映射为原生 `#{ ... }` 逻辑,相当于写在 xml 里的 `#{ ... }` 部分 |
|   exist   | boolean |    否    |  true  |                      是否为数据库表字段                      |
| condition | String  |    否    |   ""   | 字段 `where` 实体查询比较条件,有值设置则按设置的值为准,没有则为默认全局的 `%s=#{%s}` |

|                  |                              |      |                          |                                                              |
| :--------------: | ---------------------------- | ---- | ------------------------ | ------------------------------------------------------------ |
|      update      | String                       | 否   | ""                       | 字段 `update set` 部分注入, 例如：update="%s+1"：表示更新时会set version=version+1(该属性优先级高于 `el` 属性) |
|  insertStrategy  | Enum                         | N    | DEFAULT                  | 举例：NOT_NULL: `insert into table_a(<if test="columnProperty != null">column</if>) values (<if test="columnProperty !=  null">#{columnProperty}</if>)` |
|  updateStrategy  | Enum                         | N    | DEFAULT                  | 举例：IGNORED: `update table_a set column=#{columnProperty}` |
|  whereStrategy   | Enum                         | N    | DEFAULT                  | 举例：NOT_EMPTY: `where <if test="columnProperty != null and columnProperty!=''">column=#{columnProperty}</if>` |
|       fill       | Enum                         | 否   | FieldFill.DEFAULT        | 字段自动填充策略                                             |
|      select      | boolean                      | 否   | true                     | 是否进行 select 查询                                         |
| keepGlobalFormat | boolean                      | 否   | false                    | 是否保持使用全局的 format 进行处理                           |
|     jdbcType     | JdbcType                     | 否   | JdbcType.UNDEFINED       | JDBC类型 (该默认值不代表会按照该值生效)                      |
|   typeHandler    | Class<? extends TypeHandler> | 否   | UnknownTypeHandler.class | 类型处理器 (该默认值不代表会按照该值生效)                    |
|   numericScale   | String                       | 否   | ""                       | 指定小数点后保留的位数                                       |

FileStrategy

|    值     |                           描述                            |
| :-------: | :-------------------------------------------------------: |
|  IGNORED  |                         忽略判断                          |
| NOT_NULL  |                        非NULL判断                         |
| NOT_EMPTY | 非空判断(只对字符串类型字段,其他类型字段依然为非NULL判断) |
|  DEFAULT  |                       追随全局配置                        |

FieldFill

|      值       |         描述         |
| :-----------: | :------------------: |
|    DEFAULT    |      默认不处理      |
|    INSERT     |    插入时填充字段    |
|    UPDATE     |    更新时填充字段    |
| INSERT_UPDATE | 插入和更新时填充字段 |

@Version 乐观锁注解、标记 `@Verison` 在字段上、

@EnumValue 通枚举类注解(注解在枚举字段上)

@TableLogic 表字段逻辑处理注解（逻辑删除）

|  属性  |  类型  | 必须指定 | 默认值 |     描述     |
| :----: | :----: | :------: | :----: | :----------: |
| value  | String |    否    |   ""   | 逻辑未删除值 |
| delval | String |    否    |   ""   |  逻辑删除值  |

@KeySequence 序列主键策略 `oracle`

| 属性  |  类型  | 必须指定 |   默认值   |                             描述                             |
| :---: | :----: | :------: | :--------: | :----------------------------------------------------------: |
| value | String |    否    |     ""     |                            序列名                            |
| clazz | Class  |    否    | Long.class | id的类型, 可以指定String.class，这样返回的Sequence值是字符串"1" |

@OrderBy 内置 SQL 默认指定排序，优先级低于 wrapper 条件查询

|  属性  |  类型   | 必须指定 |     默认值      |      描述      |
| :----: | :-----: | :------: | :-------------: | :------------: |
| isDesc | boolean |    否    |       是        |  是否倒序查询  |
|  sort  |  short  |    否    | Short.MAX_VALUE | 数字越小越靠前 |

------

# CRUD接口

## Service CRUD 接口

Save

```
// 插入一条记录（选择字段，策略插入）
boolean save(T entity);
// 插入（批量）
boolean saveBatch(Collection<T> entityList);
// 插入（批量）
boolean saveBatch(Collection<T> entityList, int batchSize);
```

SaveOrUpdate

```
// TableId 注解存在更新记录，否插入一条记录
boolean saveOrUpdate(T entity);
// 根据updateWrapper尝试更新，否继续执行saveOrUpdate(T)方法
boolean saveOrUpdate(T entity, Wrapper<T> updateWrapper);
// 批量修改插入
boolean saveOrUpdateBatch(Collection<T> entityList);
// 批量修改插入
boolean saveOrUpdateBatch(Collection<T> entityList, int batchSize);
```

Remove

```
// 根据 entity 条件，删除记录
boolean remove(Wrapper<T> queryWrapper);
// 根据 ID 删除
boolean removeById(Serializable id);
// 根据 columnMap 条件，删除记录
boolean removeByMap(Map<String, Object> columnMap);
// 删除（根据ID 批量删除）
boolean removeByIds(Collection<? extends Serializable> idList);
```

Update

```
// 根据 UpdateWrapper 条件，更新记录 需要设置sqlset
boolean update(Wrapper<T> updateWrapper);
// 根据 whereWrapper 条件，更新记录
boolean update(T updateEntity, Wrapper<T> whereWrapper);
// 根据 ID 选择修改
boolean updateById(T entity);
// 根据ID 批量更新
boolean updateBatchById(Collection<T> entityList);
// 根据ID 批量更新
boolean updateBatchById(Collection<T> entityList, int batchSize);
```

Get

```
// 根据 ID 查询
T getById(Serializable id);
// 根据 Wrapper，查询一条记录。结果集，如果是多个会抛出异常，随机取一条加上限制条件 wrapper.last("LIMIT 1")
T getOne(Wrapper<T> queryWrapper);
// 根据 Wrapper，查询一条记录
T getOne(Wrapper<T> queryWrapper, boolean throwEx);
// 根据 Wrapper，查询一条记录
Map<String, Object> getMap(Wrapper<T> queryWrapper);
// 根据 Wrapper，查询一条记录
<V> V getObj(Wrapper<T> queryWrapper, Function<? super Object, V> mapper);
```

List

```
// 查询所有
List<T> list();
// 查询列表
List<T> list(Wrapper<T> queryWrapper);
// 查询（根据ID 批量查询）
Collection<T> listByIds(Collection<? extends Serializable> idList);
// 查询（根据 columnMap 条件）
Collection<T> listByMap(Map<String, Object> columnMap);
// 查询所有列表
List<Map<String, Object>> listMaps();
// 查询列表
List<Map<String, Object>> listMaps(Wrapper<T> queryWrapper);
// 查询全部记录
List<Object> listObjs();
// 查询全部记录
<V> List<V> listObjs(Function<? super Object, V> mapper);
// 根据 Wrapper 条件，查询全部记录
List<Object> listObjs(Wrapper<T> queryWrapper);
// 根据 Wrapper 条件，查询全部记录
<V> List<V> listObjs(Wrapper<T> queryWrapper, Function<? super Object, V> mapper);
```

Page

```
// 无条件分页查询
IPage<T> page(IPage<T> page);
// 条件分页查询
IPage<T> page(IPage<T> page, Wrapper<T> queryWrapper);
// 无条件分页查询
IPage<Map<String, Object>> pageMaps(IPage<T> page);
// 条件分页查询
IPage<Map<String, Object>> pageMaps(IPage<T> page, Wrapper<T> queryWrapper);
```

Count

```
// 查询总记录数
int count();
// 根据 Wrapper 条件，查询总记录数
int count(Wrapper<T> queryWrapper);
```

Chain

```
query
// 链式查询 普通
QueryChainWrapper<T> query();
// 链式查询 lambda 式。注意：不支持 Kotlin
LambdaQueryChainWrapper<T> lambdaQuery(); 

// 示例：
query().eq("column", value).one();
lambdaQuery().eq(Entity::getId, value).list();

update
// 链式更改 普通
UpdateChainWrapper<T> update();
// 链式更改 lambda 式。注意：不支持 Kotlin 
LambdaUpdateChainWrapper<T> lambdaUpdate();

// 示例：
update().eq("column", value).remove();
lambdaUpdate().eq(Entity::getId, value).update(entity);
```

## Mapper CRUD 接口

Insert

```
// 插入一条记录
int insert(T entity);
```

Delete

```
// 根据 entity 条件，删除记录
int delete(@Param(Constants.WRAPPER) Wrapper<T> wrapper);
// 删除（根据ID 批量删除）
int deleteBatchIds(@Param(Constants.COLLECTION) Collection<? extends Serializable> idList);
// 根据 ID 删除
int deleteById(Serializable id);
// 根据 columnMap 条件，删除记录
int deleteByMap(@Param(Constants.COLUMN_MAP) Map<String, Object> columnMap);
```

Update

```
// 根据 whereWrapper 条件，更新记录
int update(@Param(Constants.ENTITY) T updateEntity, @Param(Constants.WRAPPER) Wrapper<T> whereWrapper);
// 根据 ID 修改
int updateById(@Param(Constants.ENTITY) T entity);
```

Select

```
// 根据 ID 查询
T selectById(Serializable id);
// 根据 entity 条件，查询一条记录
T selectOne(@Param(Constants.WRAPPER) Wrapper<T> queryWrapper);

// 查询（根据ID 批量查询）
List<T> selectBatchIds(@Param(Constants.COLLECTION) Collection<? extends Serializable> idList);
// 根据 entity 条件，查询全部记录
List<T> selectList(@Param(Constants.WRAPPER) Wrapper<T> queryWrapper);
// 查询（根据 columnMap 条件）
List<T> selectByMap(@Param(Constants.COLUMN_MAP) Map<String, Object> columnMap);
// 根据 Wrapper 条件，查询全部记录
List<Map<String, Object>> selectMaps(@Param(Constants.WRAPPER) Wrapper<T> queryWrapper);
// 根据 Wrapper 条件，查询全部记录。注意： 只返回第一个字段的值
List<Object> selectObjs(@Param(Constants.WRAPPER) Wrapper<T> queryWrapper);

// 根据 entity 条件，查询全部记录（并翻页）
IPage<T> selectPage(IPage<T> page, @Param(Constants.WRAPPER) Wrapper<T> queryWrapper);
// 根据 Wrapper 条件，查询全部记录（并翻页）
IPage<Map<String, Object>> selectMapsPage(IPage<T> page, @Param(Constants.WRAPPER) Wrapper<T> queryWrapper);
// 根据 Wrapper 条件，查询总记录数
Integer selectCount(@Param(Constants.WRAPPER) Wrapper<T> queryWrapper);
```

# 条件构造器

## AbstractWrapper

allEq

```
allEq(Map<R, V> params)
allEq(Map<R, V> params, boolean null2IsNull)
allEq(boolean condition, Map<R, V> params, boolean null2IsNull)
```

 eq

```java
eq(R column, Object val)
eq(boolean condition, R column, Object val)
```

ne

```java
ne(R column, Object val)
ne(boolean condition, R column, Object val)
```

 gt

```java
gt(R column, Object val)
gt(boolean condition, R column, Object val)
```

ge

```java
ge(R column, Object val)
ge(boolean condition, R column, Object val)
```

lt

```java
lt(R column, Object val)
lt(boolean condition, R column, Object val)
```

le

```java
le(R column, Object val)
le(boolean condition, R column, Object val)
```

between

```java
between(R column, Object val1, Object val2)
between(boolean condition, R column, Object val1, Object val2)
```

notBetween

```java
notBetween(R column, Object val1, Object val2)
notBetween(boolean condition, R column, Object val1, Object val2)
```

like

```java
like(R column, Object val)
like(boolean condition, R column, Object val)
```

notLike

```java
notLike(R column, Object val)
notLike(boolean condition, R column, Object val)
```

likeLeft

```java
likeLeft(R column, Object val)
likeLeft(boolean condition, R column, Object val)
```

likeRight

```java
likeRight(R column, Object val)
likeRight(boolean condition, R column, Object val)
```

isNull

```java
isNull(R column)
isNull(boolean condition, R column)
```

isNotNull

```java
isNotNull(R column)
isNotNull(boolean condition, R column)
```

in

```java
in(R column, Collection<?> value)
in(boolean condition, R column, Collection<?> value)
```

notIn

```java
notIn(R column, Collection<?> value)
notIn(boolean condition, R column, Collection<?> value)
```

inSql

```java
inSql(R column, String inValue)
inSql(boolean condition, R column, String inValue)
```

notInSql

```java
notInSql(R column, String inValue)
notInSql(boolean condition, R column, String inValue)
```

groupBy

```java
groupBy(R... columns)
groupBy(boolean condition, R... columns)
```

orderByAsc

```java
orderByAsc(R... columns)
orderByAsc(boolean condition, R... columns)
```

orderByDesc

```java
orderByDesc(R... columns)
orderByDesc(boolean condition, R... columns)
```

orderBy

```java
orderBy(boolean condition, boolean isAsc, R... columns)
```

having

```java
having(String sqlHaving, Object... params)
having(boolean condition, String sqlHaving, Object... params)
```

func

```java
func(Consumer<Children> consumer)
func(boolean condition, Consumer<Children> consumer)
```

or

```java
or()
or(boolean condition)
```

and

```java
and(Consumer<Param> consumer)
and(boolean condition, Consumer<Param> consumer)
```

nested

```java
nested(Consumer<Param> consumer)
nested(boolean condition, Consumer<Param> consumer)
```

apply

```java
apply(String applySql, Object... params)
apply(boolean condition, String applySql, Object... params)
```

last

```java
last(String lastSql)
last(boolean condition, String lastSql)
```

exists

```java
exists(String existsSql)
exists(boolean condition, String existsSql)
```

notExists

```java
notExists(String notExistsSql)
notExists(boolean condition, String notExistsSql)
```

## QueryWrapper

select

```
select(String... sqlSelect)
select(Predicate<TableFieldInfo> predicate)
select(Class<T> entityClass, Predicate<TableFieldInfo> predicate)
```

## UpdateWrapper

set

```java
set(String column, Object val)
set(boolean condition, String column, Object val)
```

setSql

```java
setSql(String sql)
```

lambda

```
获取 LambdaWrapper
在QueryWrapper中是获取LambdaQueryWrapper
在UpdateWrapper中是获取LambdaUpdateWrapper
```

