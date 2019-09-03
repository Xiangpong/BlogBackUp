---
title: SSM框架搭建-下
date: 2019-08-23 08:06:45
tags:
- Java
- SSM框架学习
- 电商项目开发
categories: 学习笔记
---

前边我们完成了SSM框架搭建的第一步：Spring和SpringMVC的整合。接下来实现将Mybatis整合到两者之间去，即实现与数据库的交互。

与数据库的交互无非是常用的“增删改查”等操作。这就是项目开发中重复且枯燥的部分，所以我们用到了Mybatis的逆向工程，来简化这一步骤。

### Mybatis的逆向工程

>MyBatis的一个主要的特点就是需要程序员自己编写sql，那么如果表太多的话，难免会很麻烦，所以mybatis官方提供了一个逆向工程，可以针对单表自动生成mybatis执行所需要的代码（包括mapper.xml、mapper.java、po..）。一般在开发中，常用的逆向工程方式是通过数据库的表生成代码。

<!-- more -->

这里我使用“generatorSqlmapCustom”逆向工程代码
来生成Mapper和Pojo文件，用于Spring、Mybatis、数据库的整合

github链接：https://github.com/Xiangpong/generatorSqlmapCustom

[![逆向工程.png](https://i.loli.net/2019/06/24/5d1079b7ca93e87590.png)](https://i.loli.net/2019/06/24/5d1079b7ca93e87590.png)

如上图

将mapper文件夹文件（UserMapper、UserMapper.xml）复制到SSM项目的manager模块的mapper文件夹 → src/main/java/com.pong.mapper 文件夹内

将pojo文件夹文件（User、UserExample）复制到SSM项目的manager模块的pojo文件夹  → src/main/java/com.pong.pojo  文件夹内

[![逆向工程2.png](https://i.loli.net/2019/06/24/5d1079b7bee4463907.png)](https://i.loli.net/2019/06/24/5d1079b7bee4463907.png)

[![逆向工程3.png](https://i.loli.net/2019/06/24/5d1079b7bef0071324.png)](https://i.loli.net/2019/06/24/5d1079b7bef0071324.png)

#### 引入jackson-databind依赖进行JSON和Java对象转换

### 写一个service Demo 来检测整合结果

关键代码：

UserServiceImpl → UserService接口的实现

```java
package com.pong.service.impl;

import com.pong.mapper.UserMapper;
import com.pong.pojo.User;
import com.pong.pojo.UserExample;
import com.pong.service.UserService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import java.util.List;
@Service
public class UserServiceImpl implements UserService {
    @Autowired
    UserMapper userMapper;

    @Override
    public User getUserById(Integer id) {
        UserExample userExample = new UserExample();
        UserExample.Criteria criteria = userExample.createCriteria();
        criteria.andIdEqualTo(id);

        List<User> userList = userMapper.selectByExample(userExample);

        if (userList != null) {
            return userList.get(0);
        }
        return null;
    }
}
```

UserController

```java
package com.pong.controller;

import com.pong.pojo.User;
import com.pong.service.UserService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.ResponseBody;

@Controller
public class UserController {

    @Autowired
    UserService userService;

    @RequestMapping("/user/{userid}")
    @ResponseBody
        public User getUserById(@PathVariable Integer userid){
            User user = userService.getUserById(userid);
            return  user;
    }
}
```



### 运行测试

[![测试结果2.png](https://i.loli.net/2019/06/24/5d1079b7ca3b728420.png)](https://i.loli.net/2019/06/24/5d1079b7ca3b728420.png)

### 过程中的问题

1. 未引入jackson-databind依赖 
2. 未给UserServiceimpl 添加@Service注解
3. 未给UserController 添加@Controller注解
4. org.apache.ibatis.binding.BindingException: Invalid bound statement (not found)

#### 第四点为关键错误，可以从两个方面排查：

* Mapper interface和xml文件的定义对应不上，需要检查包名，namespace，函数名称等能否对应上；因为是用逆向工程生成的文件，所以一般没有错误

* mapper没有自动复制到响应位置，也会出错；maven默认会把src/main/resources下的所有配置文件以及src/main/java下的所有java文件打包或发布到target\classes下面，但是现实我们可能会在src/main/java下面也放置一些配置文件如hibernate配置文件或mybatis mapper配置文件等，如果不做一些额外配置，那我们打包后的项目可能找不到这些必须的资源文件，因此在pom.xml中增加类似如下配置：

```xml
<build>
	<resources>
		<resource>
			<directory>src/main/java</directory>
			<includes>
				<include>**/*.xml</include>
			</includes>
		</resource>
		<resource>
			<directory>src/main/resources</directory>
		</resource>
	</resources>
</build>
```
### SSM框架整合完成

