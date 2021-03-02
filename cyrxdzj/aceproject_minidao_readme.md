MiniDao
=======


MiniDao简介及特征

MiniDao是一种持久化解决方案，具备实体维护和SQL分离的两大优势，考虑了mybatis和hibernate的不足。 具有以下特征:

* 1.O/R mapping不用设置xml，零配置便于维护
* 2.不需要了解JDBC的知识
* 3.SQL语句和java代码的分离
* 4.可以自动生成SQL语句
* 5.接口和实现分离，不用写持久层代码，用户只需写接口，以及某些接口方法对应的sql 它会通过AOP自动生成实现类
* 6.支持自动事务处理和手动事务处理
* 7.支持与hibernate轻量级无缝集成
* 8.MiniDao吸收了Hibernate+mybatis的优势，支持实体维护和SQL分离
* 9.SQL支持脚本语言

※实体的增删改查不需要写sql,支持SQL自动生成




###接口和SQL文件对应目录
![github](http://www.jeecg.org/data/attachment/forum/201308/18/224051ey14ehqe000iegja.jpg "minidao")



### 接口定义[EmployeeDao.java]  
    @MiniDao
    public interface EmployeeDao {
     @Arguments("employee")
     public List  getAllEmployees(Employee employee);
    
     @Arguments("empno")
     Employee getEmployee(String empno);
    
     @Arguments({"empno","name"})
     Map getMap(String empno,String name);

     @Sql("SELECT count(*) FROM employee")
     Integer getCount();

     @Arguments("employee")
     int update(Employee employee);

     @Arguments("employee")
     void insert(Employee employee);
   }
    
    
    
### SQL文件[EmployeeDao_getAllEmployees.sql]
    SELECT * FROM employee where 1=1 
     
	and age = :employee.age
     
     
	and name = :employee.name
     
     
	and empno = :employee.empno
     

### MiniDao接口配置
         
	 
		 
			 
				 examples.dao.* 
			 
		 
	 

### 测试代码
    public class Client {
    public static void main(String args[]) {
		BeanFactory factory = new ClassPathXmlApplicationContext(
				"applicationContext.xml");
     		
		EmployeeDao employeeDao = (EmployeeDao) factory.getBean("employeeDao");
		Employee employee = new Employee();
		List  list =  employeeDao.getAllEmployees(employee);
		for(Map mp:list){
			System.out.println(mp.get("id"));
			System.out.println(mp.get("name"));
			System.out.println(mp.get("empno"));
			System.out.println(mp.get("age"));
			System.out.println(mp.get("birthday"));
			System.out.println(mp.get("salary"));
		}
	}
    }


技术交流
-----------------------------------
* 作  者：  张代浩
* 论  坛： [www.jeecg.org](http://www.jeecg.org)
* 邮  箱：  zhangdaiscott@163.com
* QQ交流群：106838471


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)