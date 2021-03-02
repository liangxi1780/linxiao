 
	  
 

 
     
          
     
     
          
     
     
          
     
 

# mybatis-dsc-generator
完美集成lombok，swagger的代码生成工具，让你不再为繁琐的注释和简单的接口实现而烦恼：entity集成，格式校验，swagger; dao自动加@ mapper，service自动注释和依赖; 控制器实现单表的增副改查，并集成swagger实现api文档。如果有缘看见，期望得到你的star，very thx.
# 源码地址
- GitHub:https://github.com/flying-cattle/mybatis-dsc-generator
- 码云：https://gitee.com/flying-cattle/mybatis-dsc-generator

# MAVEN地址
2.1.0版本是未集成Mybatis-plus版本——源码分支master
``` xml
 
     com.github.flying-cattle 
     mybatis-dsc-generator 
     2.1.0.RELEASE 
 
```
3.0.0版本是集成了Mybatis-plus版本——源码分支mybatisPlus
``` xml
 
     com.github.flying-cattle 
     mybatis-dsc-generator 
     3.0.0.RELEASE 
 
```
# 数据表结构样式
``` sql
CREATE TABLE `user` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT COMMENT 'ID',
  `login_name` varchar(40) DEFAULT NULL COMMENT '登录名',
  `password` varchar(100) NOT NULL COMMENT '秘密',
  `nickname` varchar(50) NOT NULL COMMENT '昵称',
  `type` int(10) unsigned DEFAULT NULL COMMENT '类型',
  `state` int(10) unsigned NOT NULL DEFAULT '1' COMMENT '状态：-1失败，0等待,1成功',
  `note` varchar(255) DEFAULT NULL COMMENT '备注',
  `create_time` timestamp NULL DEFAULT CURRENT_TIMESTAMP COMMENT '创建时间',
  `update_time` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP COMMENT '更新时间',
  `update_uid` bigint(20) DEFAULT '0' COMMENT '修改人用户ID',
  `login_ip` varchar(50) DEFAULT NULL COMMENT '登录IP地址',
  `login_addr` varchar(100) DEFAULT NULL COMMENT '登录地址',
  PRIMARY KEY (`id`),
  UNIQUE KEY `login_name` (`login_name`)
) ENGINE=InnoDB AUTO_INCREMENT=13 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```
要求必须有表注释，要求必须有主键为id,所有字段必须有注释（便于生成java注释swagger等）。

# 生成的实体类
生成方法参考源码中的：https://github.com/flying-cattle/mybatis-dsc-generator/blob/mybatisPlus/src/main/java/com/github/mybatis/fl/test/TestMain.java

# 生成的实体类
``` java
/**
 * @filename:Order 2018年7月5日
 * @project deal-center  V1.0
 * Copyright(c) 2018 BianP Co. Ltd. 
 * All right reserved. 
 */
import com.baomidou.mybatisplus.annotation.IdType;
import com.baomidou.mybatisplus.annotation.TableId;
import com.baomidou.mybatisplus.extension.activerecord.Model;
import com.fasterxml.jackson.annotation.JsonFormat;
import io.swagger.annotations.ApiModelProperty;
import lombok.Data;
import lombok.EqualsAndHashCode;
import lombok.experimental.Accessors;
import java.util.Date;
import org.springframework.format.annotation.DateTimeFormat;
import java.io.Serializable;

/**   
 * Copyright: Copyright (c) 2019 
 * 
 *  说明： 用户实体类 
 * @version: V1.0
 * @author: BianPeng
 * 
 * Modification History:
 * Date         	Author          Version          Description
 *---------------------------------------------------------------*
 * 2019年4月9日      BianPeng    V1.0         initialize
 */
@Data
@EqualsAndHashCode(callSuper = false)
@Accessors(chain = true)
@Data
@EqualsAndHashCode(callSuper = false)
@Accessors(chain = true)
public class User extends Model  {

    private static final long serialVersionUID = 1L;
    @TableId(value = "id", type = IdType.AUTO)
    @ApiModelProperty(name = "id" , value = "用户ID")
    private Long id;

    @ApiModelProperty(name = "loginName" , value = "登录账户")
    private String loginName;

    @ApiModelProperty(name = "password" , value = "登录密码")
    private String password;

    @ApiModelProperty(name = "nickname" , value = "用户昵称")
    private String nickname;

    @ApiModelProperty(name = "type" , value = "用户类型")
    private Integer type;

    @ApiModelProperty(name = "state" , value = "用户状态")
    private Integer state;

    @ApiModelProperty(name = "note" , value = "备注")
    private String note;

    @DateTimeFormat(pattern = "yyyy-MM-dd HH:mm:ss")
    @JsonFormat(pattern="yyyy-MM-dd HH:mm:ss",timezone = "GMT+8")
    @ApiModelProperty(name = "createTime" , value = "用户创建时间")
    private Date createTime;

    @DateTimeFormat(pattern = "yyyy-MM-dd HH:mm:ss")
    @JsonFormat(pattern="yyyy-MM-dd HH:mm:ss",timezone = "GMT+8")
    @ApiModelProperty(name = "updateTime" , value = "修改时间")
    private Date updateTime;
	
    @ApiModelProperty(name = "updateUid" , value = "修改人用户ID")
    private Long updateUid;

    @ApiModelProperty(name = "loginIp" , value = "登录IP")
    private String loginIp;

    @ApiModelProperty(name = "loginIp" , value = "登录地址")
    private String loginAddr;
	
    @Override
    protected Serializable pkVal() {
        return this.id;
    }
}
```
# 生成的DAO
``` java
import com.baomidou.mybatisplus.core.mapper.BaseMapper;
import org.apache.ibatis.annotations.Mapper;
import com.xin.usercenter.entity.User;

/**   
 * Copyright: Copyright (c) 2019 
 * 
 *  说明： 用户数据访问层 
 * @version: V1.0
 * @author: BianPeng
 * 
 * Modification History:
 * Date         	Author          Version          Description
 *---------------------------------------------------------------*
 * 2019年4月9日      BianPeng    V1.0         initialize
 */
@Mapper
public interface UserDao extends BaseMapper  {
	
}

```
# 生成的XML
``` xml
 
 
 

	 
		 
		 
		 
		 
		 
		 
		 
		 
		 
		 
		 
		 
	 
	 
		id, login_name, password, nickname, type, state, note, create_time, update_time, update_uid, login_ip, login_addr
	 
 
```
# 生成的SERVICE
``` java
import com.xin.usercenter.entity.User;
import com.baomidou.mybatisplus.extension.service.IService;
/**   
 * Copyright: Copyright (c) 2019 
 * 
 *  说明： 用户服务层 
 * @version: V1.0
 * @author: BianPeng
 * 
 * Modification History:
 * Date         	Author          Version          Description
 *---------------------------------------------------------------*
 * 2019年4月9日      BianPeng    V1.0           initialize
 */
public interface UserService extends IService  {
	
}
```
# 生成的SERVICE_IMPL
``` java
import com.xin.usercenter.entity.User;
import com.xin.usercenter.dao.UserDao;
import com.xin.usercenter.service.UserService;
import org.springframework.stereotype.Service;
import com.baomidou.mybatisplus.extension.service.impl.ServiceImpl;

/**   
 * Copyright: Copyright (c) 2019 
 * 
 *  说明： 用户服务实现层 
 * @version: V1.0
 * @author: BianPeng
 * 
 * Modification History:
 * Date         	Author          Version          Description
 *---------------------------------------------------------------*
 * 2019年4月9日      BianPeng    V1.0           initialize
 */
@Service
public class UserServiceImpl  extends ServiceImpl  implements UserService  {
	
}
```
# 生成的CONTROLLER
``` java
import com.item.util.JsonResult;
import com.xin.usercenter.entity.User;
import com.xin.usercenter.service.UserService;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
import com.baomidou.mybatisplus.core.conditions.query.QueryWrapper;
import com.baomidou.mybatisplus.core.metadata.IPage;
import com.baomidou.mybatisplus.extension.plugins.pagination.Page;
import io.swagger.annotations.Api;
import io.swagger.annotations.ApiImplicitParam;
import io.swagger.annotations.ApiImplicitParams;
import io.swagger.annotations.ApiOperation;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.beans.factory.annotation.Autowired;

/**   
 * Copyright: Copyright (c) 2019 
 * 
 *  说明： 用户API接口层 
 * @version: V1.0
 * @author: BianPeng
 * 
 * Modification History:
 * Date         	Author          Version          Description
 *---------------------------------------------------------------*
 * 2019年4月9日      BianPeng    V1.0           initialize
 */
@Api(description = "用户",value="用户" )
@RestController
@RequestMapping("/user")
public class UserController {

    Logger logger = LoggerFactory.getLogger(this.getClass());
	
    @Autowired
    public UserService userServiceImpl;
	
    /**
    * @explain 查询用户对象   
    * @param   对象参数：id
    * @return  user
    * @author  BianPeng
    * @time    2019年4月9日
    */
    @GetMapping("/getUserById/{id}")
    @ApiOperation(value = "获取用户信息", notes = "获取用户信息[user]，作者：BianPeng")
    @ApiImplicitParam(paramType="path", name = "id", value = "用户id", required = true, dataType = "Long")
    public JsonResult  getUserById(@PathVariable("id")Long id){
    	JsonResult  result=new JsonResult ();
    	try {
    		User user=userServiceImpl.getById(id);
    		if (user!=null) {
    			result.setType("success");
    			result.setMessage("成功");
    			result.setData(user);
    		} else {
    			logger.error("获取用户失败ID："+id);
    			result.setType("fail");
    			result.setMessage("你获取的用户不存在");
    		}
    	} catch (Exception e) {
    		logger.error("获取用户执行异常："+e.getMessage());
    		result=new JsonResult (e);
    	}
    	return result;
    }
    /**
     * @explain 添加或者更新用户对象
     * @param   对象参数：user
     * @return  int
     * @author  BianPeng
     * @time    2019年4月9日
     */
    @PostMapping("/insertSelective")
    @ApiOperation(value = "添加用户", notes = "添加用户[user],作者：BianPeng")
    public JsonResult  insertSelective(User user){
    	JsonResult  result=new JsonResult ();
    	try {
    		boolean rg=userServiceImpl.saveOrUpdate(user);
    		if (rg) {
    			result.setType("success");
    			result.setMessage("成功");
	    		result.setData(user);
		    } else {
			    logger.error("添加用户执行失败："+user.toString());
			    result.setType("fail");
			    result.setMessage("执行失败，请稍后重试");
    		}
	    } catch (Exception e) {
	    	logger.error("添加用户执行异常："+e.getMessage());
	    	result=new JsonResult (e);
	    }
       return result;
    }
	
    /**
     * @explain 删除用户对象
     * @param   对象参数：id
     * @return  int
     * @author  BianPeng
     * @time    2019年4月9日
     */
    @PostMapping("/deleteByPrimaryKey")
    @ApiOperation(value = "删除用户", notes = "删除用户,作者：BianPeng")
    @ApiImplicitParam(paramType="query", name = "id", value = "用户id", required = true, dataType = "Long")
    public JsonResult  deleteByPrimaryKey(Long id){
    	JsonResult  result=new JsonResult ();
	    try {
	    	boolean reg=userServiceImpl.removeById(id);
	    	if (reg) {
    			result.setType("success");
    			result.setMessage("成功");
    			result.setData(id);
    		} else {
    			logger.error("删除用户失败ID："+id);
    			result.setType("fail");
    			result.setMessage("执行错误，请稍后重试");
    		}
    	} catch (Exception e) {
    		logger.error("删除用户执行异常："+e.getMessage());
    		result=new JsonResult (e);
    	}
    	return result;
	}
	
	/**
	 * @explain 分页条件查询用户   
	 * @param   对象参数：AppPage 
	 * @return  PageInfo 
	 * @author  BianPeng
	 * @time    2019年4月9日
	 */
	@GetMapping("/getUserPages")
	@ApiOperation(value = "分页查询", notes = "分页查询返回对象[IPage ],作者：边鹏")
	@ApiImplicitParams({
        @ApiImplicitParam(paramType="query", name = "pageNum", value = "当前页", required = true, dataType = "int"),
        @ApiImplicitParam(paramType="query", name = "pageSize", value = "页行数", required = true, dataType = "int")
    })
	public JsonResult  getUserPages(Integer pageNum,Integer pageSize){
	
		JsonResult  result=new JsonResult ();
		Page  page=new Page (pageNum,pageSize);
		QueryWrapper  queryWrapper =new QueryWrapper ();
		//分页数据
		try {
			//List  list=userServiceImpl.list(queryWrapper); 
			IPage  pageInfo=userServiceImpl.page(page, queryWrapper);
			result.setType("success");
			result.setMessage("成功");
			result.setData(pageInfo);
		} catch (Exception e) {
			logger.error("分页查询用户执行异常："+e.getMessage());
			result=new JsonResult (e);
		}
		return result;
	}
}
```

看到这里，大家应该能看出，这个代码生成只适合一些特定的项目，不过确实为了那些喜欢lombok，swagger的猿们减少了很多不必要的工作。
一些朋友在问我JsonResult类：
``` java
import java.io.Serializable;
import java.net.ConnectException;
import java.sql.SQLException;
import lombok.Data;
import lombok.extern.slf4j.Slf4j;


/**   
 * Copyright: Copyright (c) 2019 
 * 
 *  说明： 用户服务层 
 * @version: V1.0
 * @author: BianPeng
 * 
 * Modification History:
 * Date         Author         Version         Description
 *---------------------------------------------------------*
 * 2019/4/9 	flying-cattle  V1.0            initialize
 */
@Slf4j
@Data
public class JsonResult  implements Serializable{
	
	private static final long serialVersionUID = 1071681926787951549L;

	/**
     *  返回状态 
     */
    private Boolean isTrue=true;
    /**
     *  状态码 
     */
    private String code;
    /**
     *  业务码 
     */
    private String type;
    /**
     *  状态说明 
     */
    private String message;
    /**
     *  返回数据 
     */
    private T data;
   
	/**
     *  返回成功 
     * @param type 业务码
     * @param message 错误说明
     * @param data 数据
     */
    public JsonResult(String type, String message, T data) {
        this.isTrue=true;
        this.code ="0000";
        this.type=type;
        this.message = message;
        this.data=data;
    }
    public JsonResult() {
        this.isTrue=true;
        this.code ="0000";
    }
    public JsonResult(Throwable throwable) {
    	log.error(throwable+"tt");
        this.isTrue=false;
        if(throwable instanceof NullPointerException){
            this.code= "1001";
            this.message="空指针："+throwable;
        }else if(throwable instanceof ClassCastException ){
            this.code= "1002";
            this.message="类型强制转换异常："+throwable;
        }else if(throwable instanceof ConnectException){
            this.code= "1003";
            this.message="链接失败："+throwable;
        }else if(throwable instanceof IllegalArgumentException ){
            this.code= "1004";
            this.message="传递非法参数异常："+throwable;
        }else if(throwable instanceof NumberFormatException){
            this.code= "1005";
            this.message="数字格式异常："+throwable;
        }else if(throwable instanceof IndexOutOfBoundsException){
            this.code= "1006";
            this.message="下标越界异常："+throwable;
        }else if(throwable instanceof SecurityException){
            this.code= "1007";
            this.message="安全异常："+throwable;
        }else if(throwable instanceof SQLException){
            this.code= "1008";
            this.message="数据库异常："+throwable;
        }else if(throwable instanceof ArithmeticException){
            this.code= "1009";
            this.message="算术运算异常："+throwable;
        }else if(throwable instanceof RuntimeException){
            this.code= "1010";
            this.message="运行时异常："+throwable;
        }else if(throwable instanceof Exception){ 
        	log.error("未知异常："+throwable);
            this.code= "9999";
            this.message="未知异常"+throwable;
        }
    }
}
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)