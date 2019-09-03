---
title: 从0到1开发Java高并发SSM项目（序）
date: 2019-06-21 17:29:03
tags: 
- Java 
- SSM框架学习 
- 电商项目开发
categories: 笔记
---


## 前排感谢wistbean老师，我是在他的指导下一步一步实现这个项目的开发的！！！

wistbean老师的github：https://github.com/wistbean

## 什么是从0到1

这里的从0到1不是通过我个人魅力把一个gay掰直了，而是通过开发一个电商网站，系统学习Java web开发和SSM框架的使用等知识。

<!-- more -->

## 什么是框架

我们在做java开发的时候，会发现很大一部分内容是被重复使用的，比如对数据库的增删改查操作、对实体类和常用接口的实现。

如果能把这部分被重复使用的“代码”加以整合，实现取之即用，将大大提高我们的开发效率。而这就框架的特点 --- 整个或部分系统的可重用设计


一个框架就是一个可复用的设计构件，它规定了应用的体系结构，阐明了整个设计、协作构件之间的依赖关系、责任分配和控制流程，表现为一组抽象类以及其实例之间协作的方法，它为构件复用提供了上下文(Context)关系。

框架是实现了某应用领域通用功能的底层服务。使用这种框架的编程人员可以在一个通用功能已经实现的基础上开始具体的系统开发。

通俗的说，框架是完成是某种应用的半成品，提供了一些常用的工具类和一些基础通用化的组件，可以供开发人员在此基础上，更便捷的完成各自特有的系统。



## 什么是SSM框架

SSM框架是Spring、SpringMVC、MyBatis的整合

## Spring带来了春天

Spring是一个开源的、轻量级JavaSE/JavaEE开发框架。它的出现。解决了企业应用开发的复杂性、简化了java开发。

Spring的特点：
* 轻量级（依赖资源和消耗资源少） + 最小侵入式 + 分层架构
* IOC控制翻转来解耦合
* AOP切面编程
* 可以集成其他优秀框架
* 方便测试

## SpringMVC来自Sring家族

* M：Model 模型
* V：View 视图
* C：Controller 控制器

## Mybatis

和数据库打交道的框架

---

## 闲话少叙，以下项目准备前瞻

### 技术选型
* Spring
* Spring MVC
* Mybatis
* redis 缓存
* solor 搜索服务
* EasyUI 
* UEditor
* JQuery
* Freemark 模板渲染引擎
* activMQ 消息队列
* httpClient
* MySQL


### 开发环境
* Intellij IDEA
* Maven
* Tomcat7
* JDK
* Nginx 
* Git
* postman
* sqlyog
* Windows10


### 关键内容
* 技术架构
* 工程搭建
* SSM框架整合
* Mybatis逆向工程
* 日志的添加与使用
* 拦截器
* 后端功能（系统开发，图片系统，数据等）
* 前端功能（商品浏览，下订单，购物车等）
* redis 使用及集群搭建
* solor 使用和集群搭建
* JMS 消息队列
* sso 单点登录
* restful服务
* 在Linux上部署

## 未完待续 ...