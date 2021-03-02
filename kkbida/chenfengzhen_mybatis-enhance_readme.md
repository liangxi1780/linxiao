# mybatis-enhance-actable-1.0.8.1.RELEASE

该项目是从之前写过的一个框架中抽取出来的，本身是对Mybatis做的增强功能，为了能够使习惯了hibernate框架的开发者能够快速的入手Mybatis，我给他取名叫做 “A.C.Table” 本意是自动建表的意思，A.C.Table是一个基于Spring和Mybatis的Maven项目，增强了Mybatis的功能，过配置model注解的方式来创建表，修改表结构，并且实现了共通的CUDR功能提升开发效率，目前仅支持Mysql，后续会扩展针对其他数据库的支持。

A.C.Table是采用了Spring、Mybatis技术的Maven结构，详细介绍如下：

 **######### mybatis增加功能自动创建表——A.C.Table版本说明################** 
1. 该版本修复了修改主键同时修改其类型引起的error(版本1.0.1)
2. 该版本修复了根据model创建时没有创建父类中的字段的问题（ps：目前只支持扫描一层继承）(版本1.0.1)
3. 该版本增加了对唯一约束的支持(版本1.0.1)
4. 从原有的框架中剥离出来，支持任意结构的spring+mybatis的框架使用(版本1.0.1)
5. 再次声明A.C.Table目前仅支持mysql数据库(版本1.0.1)
6. 修复了不同数据库中有相同表名时，启动报错的问题。(版本1.0.2)
7. 修复了model属性名与表字段名不一致时公共的查询方法查不出数据的问题。(版本1.0.2)
8. 增加了对公共的CUDR方法的优化，保存成功会返回id，query查询时可以设置参数进行分页查询（pageSize:int类型标识每页数量，currentPage:int类型标识当前第几页，start:int类型从第几条开始，orderField：string类型排序字段，sortStr：string类型排序方式(desc,asc)）(版本1.0.3)
9. 增加了对Mysql的longtext和mediumtext两种字段类型的支持，公共的CUDR方法的优化，原query方法更正为search，现query方法支持动态sql查询，原orderField字段只支持单个字段的排序，现修改为orderBy字段，支持数据类型为LinkedHashMap ，有序，key为字段名，value为排序方式(版本1.0.4)
10. 增加对mysql数据库（timestamp/time/date/float/bit）五种数据类型的支持(版本1.0.5)
11. 增加对springboot框架的支持(版本1.0.5)
12. 删除旧版本在@Colum中实现唯一约束的方式(版本1.0.6.RELEASE)
13. 增加了新的唯一约束实现方式@Unique，支持多字段聚合约束(版本1.0.6.RELEASE)
14. 增加了索引创建方式@Index，支持多字段聚合索引(版本1.0.6.RELEASE)
15. 修复query查询方法无法返回父类字段数据的bug(版本1.0.6.RELEASE)
16. 修复原本是主键，现在依然主键，修改该字段的其他信息时会报multiple primary key defined(例如id为int(11)，改为int(10)后，就可重现次bug)(版本1.0.7.RELEASE)
17. 增加对字段备注的支持，使用方式@Column的comment属性(版本1.0.7.RELEASE)
18. 修复issues/IZ6WQ：bit类型的默认值设置失败，默认值可以使用0、1、true、false(版本1.0.8.1.RELEASE)
19. 修复issues/IYTJ1：使用@Unique进行联合约束，启动项目自动创建表结构后，删除联合约束报错(版本1.0.8.1.RELEASE)
20. 新增功能issues/IYW9F:mybatis.model.pack支持多包扫描","或者";"隔开(版本1.0.8.1.RELEASE)

 **基本使用规范**
1. 需要依赖mybatis-enhance-actable-1.0.8.1.RELEASE.jar

```
         
	     com.gitee.sunchenbin.mybatis.actable 
	     mybatis-enhance-actable 
	     1.0.8.1.RELEASE 
	 
```

2. 需要配置对于actable支持的配置

```
	mybatis.table.auto=update
	mybatis.model.pack=com.sunchenbin.store.model
	mybatis.database.type=mysql
	
	本系统提供三种模式：

	2.1 当mybatis.table.auto=create时，系统启动后，会将所有的表删除掉，然后根据model中配置的结构重新建表，该操作会破坏原有数据。

	2.2 当mybatis.table.auto=update时，系统会自动判断哪些表是新建的，哪些字段要修改类型等，哪些字段要删除，哪些字段要新增，该操作不会破坏原有数据。
	
	2.3 当mybatis.table.auto=none时，系统不做任何处理。

	2.4 mybatis.model.pack这个配置是用来配置要扫描的用于创建表的对象的包名
        
	2.5 mybatis.database.type这个是用来区别数据库的，预计会支持这四种数据库mysql/oracle/sqlserver/postgresql，但目前仅支持mysql

```

3. 支持actable的mybatis配置

```
	 
	1. classpath*:com/gitee/sunchenbin/mybatis/actable/mapping/*/*.xml
	2. com.gitee.sunchenbin.mybatis.actable.dao.*
```



4. 扫描actable的包到spring容器中管理

```
        1. com.gitee.sunchenbin.mybatis.actable.manager.*
```

 **Springboot+Mybatis的项目使用步骤方法**

1. 首先pom文件依赖actable框架

```
         
	     com.gitee.sunchenbin.mybatis.actable 
	     mybatis-enhance-actable 
	     1.0.8.1.RELEASE 
	 
```
    
2. 项目的application.properties文件配置例如下面

```
	mybatis.table.auto=update
	mybatis.model.pack=com.sunchenbin.store.model
	mybatis.database.type=mysql
	mybatis.mapperLocations=classpath*:xxxxxx/*.xml,classpath*:com/gitee/sunchenbin/mybatis/actable/mapping/*/*.xml
```

3. springboot启动类需要做如下配置

```
        1. 通过注解@ComponentScan配置，扫描actable要注册到spring的包路径"com.gitee.sunchenbin.mybatis.actable.manager.*"
        2. 通过注解@MapperScan配置，扫描mybatis的mapper，路径为"com.gitee.sunchenbin.mybatis.actable.dao.*"
```

 **传统Spring+Mybatis的Web项目使用步骤方法** 
1. 首先pom文件依赖actable框架

```
         
	     com.gitee.sunchenbin.mybatis.actable 
	     mybatis-enhance-actable 
	     1.0.8.1.RELEASE 
	 
```

2. 在你的web项目上创建个目录比如config下面创建个文件autoCreateTable.properties文件的内容如下：

```
	mybatis.table.auto=update
	mybatis.model.pack=com.sunchenbin.store.model
	mybatis.database.type=mysql
```

3. spring的配置文件中需要做如下配置：
```
	 
	 
	
	 
	 
         
             
                 classpath*:config/autoCreateTable.properties 
             
         
     
     
         
     
	
	 
	1. classpath*:com/gitee/sunchenbin/mybatis/actable/mapping/*/*.xml
	2. com.gitee.sunchenbin.mybatis.actable.dao.*
	
	举例这两个配置配置的详细位置
	
	 
	 
		 
		 
		 
			 
               classpath*:com/sunchenbin/store/mapping/*/*.xml 
               classpath*:com/gitee/sunchenbin/mybatis/actable/mapping/*/*.xml 
          	 
		 
		 
		  -->
	 
	
	 
		 
		 
	 
```
	
**代码用途讲解** 

    1.SysMysqlColumns.java这个对象里面配置的是mysql的数据类型，这里配置的类型越多，意味着创建表时能使用的类型越多

    2.LengthCount.java是一个自定义的注解，用于标记在SysMysqlColumns.java里面配置的数据类型上的，标记该类型需要设置几个长度，如datetime/varchar(1)/decimal(5,2)，分别是需要设置0个1个2个

    3.Column.java也是一个自定义的注解，用于标记model中的字段上，作为创建表的依据如不标记，不会被扫描到，有几个属性用来设置字段名、字段类型、长度等属性的设置，详细请看代码上的注释

    4.Table.java也是一个自定义的注解，用于标记在model对象上，有一个属性name，用于设置该model生成表后的表名，如不设置该注解，则该model不会被扫描到
    
    5.Index.java是一个自定义注解，用于标记在model中的字段上，表示为该字段创建索引，有两个属性一个是设置索引名称，一个是设置索引字段，支持多字段联合索引，如果都不设置默认为当前字段创建索引

    6.Unique.java是一个自定义注解，用于标记在model中的字段上，表示为该字段创建唯一约束，有两个属性一个是设置约束名称，一个是设置约束字段，支持多字段联合约束，如果都不设置默认为当前字段创建唯一约束

    7.系统启动后会去自动调用SysMysqlCreateTableManagerImpl.java的createMysqlTable()方法，没错，这就是核心方法了，负责创建、删除、修改表。

 **model的写法例子**
```
@Table(name = "test")
public class Test extends BaseModel{

	private static final long serialVersionUID = 5199200306752426433L;

	@Column(name = "id",type = MySqlTypeConstant.INT,length = 11,isKey = true,isAutoIncrement = true)
	private Integer	id;

        @Index
        @Unique
	@Column(name = "name",type = MySqlTypeConstant.VARCHAR,length = 111)
	private String	name;

	@Column(name = "description",type = MySqlTypeConstant.TEXT)
	private String	description;

	@Column(name = "create_time",type = MySqlTypeConstant.DATETIME)
	private Date	create_time;

	@Column(name = "update_time",type = MySqlTypeConstant.DATETIME)
	private Date	update_time;

        @Index(name="idx_number_name",value={"number","name"})
	@Column(name = "number",type = MySqlTypeConstant.BIGINT,length = 5)
	private Long	number;

	@Column(name = "lifecycle",type = MySqlTypeConstant.CHAR,length = 1,isNull=false)
	private String	lifecycle;

	@Column(name = "dekes",type = MySqlTypeConstant.DOUBLE,length = 5,decimalLength = 2)
	private Double	dekes;
        
        // get和set方法这里就不例举了太多
}
```
 **共通的CUDR功能使用**

    1.使用方法很简单，大家在manager或者Controller中直接注入BaseMysqlCRUDManager这个接口就可以了

    2.注意：接口调用save、delete等方法时传入的对象必须是modle中用于创建表的对象
代码事例：
```
@Controller
public class TestController{
	
	@Autowired
	private TestManager testManager;
	
	@Autowired
	private BaseMysqlCRUDManager baseMysqlCRUDManager;
	
	/**
	 * 首页
	 */
	@RequestMapping("/testDate")
	@ResponseBody
	public String testDate(){
		Test2 test2 = new Test2();
		test2.setNumber(3L);
		baseMysqlCRUDManager.save(test2);
		
		Test test = new Test();
		test.setName("aaae333");
		test.setNumber(9L);
		test.setDescription("adfsdfe");
		
		baseMysqlCRUDManager.delete(test);
		baseMysqlCRUDManager.save(test);
		int count = testManager.findTestCount();
		System.out.println(count);
		List  search= baseMysqlCRUDManager.search(test);
                List > query1 = baseMysqlCRUDManager.query("select * from test");
                List  query2 = baseMysqlCRUDManager.query("select * from test", Test.class);
		String json = JsonUtil.format(query);
		return json;
	}
}
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)