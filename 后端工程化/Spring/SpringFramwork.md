## 技术体系

单一架构 : 一个项目，一个工程，导出为一个war包，在一个Tomcat上运行。
主要的应用计数框架为: Spring, springMVC,Mybatis
![[Pasted image 20231124193323.png|500]]

**分布式架构** : 一个项目（对应 IDEA 中的一个 project），拆分成很多个模块，每个模块是一个 IDEA 中的一个 module。
分布式架构的项目主要框架为SpringBoot  SpringCloud  中间件等
![[Pasted image 20231124200244.png|500]]

**框架**就是被继承好的大架子,我们在架子内完成一些功能.
框架=jar包+配置文件

## 介绍

**Spring技术栈** :泛指以Spring Framework为基础的Spring技术栈,Spring Framework、Spring MVC、SpringBoot、Spring Cloud、Spring Data、Spring Security 等，其中 Spring Framework 是其他子项目的基础

SpringFramework是技术栈内的基础框架,提供了很多功能如：
依赖注入（Dependency Injection）、
面向切面编程（AOP）、
声明式事务管理（TX）等。

|功能模块|功能介绍|
|---|---|
|Core Container|核心容器，控制反转和依赖注入|
|AOP&Aspects|面向切面编程|
|TX|声明式事务管理|
|Testing|快速整合测试环境|
|Data Access/Integration|提供了对数据访问/集成的功能。|
|Spring MVC|提供了面向Web应用程序的集成功能。|

## 总结

SpringFramework的优势有:
	丰富的生态系统
	模块化的设计
	简化java的开发
**_从Spring Framework 6.0开始，Spring 需要 Java 17+。_**
Spring核心功能   [[IOC]](控制反转)  AOP(面向切面)
## 组件

以常规的三层架构为例:
![[Pasted image 20231124200843.png|550]]
Spring框架可以帮助我们完成组件的管理
Spring框架代替了程序原有的new对象和对象属性赋值动作
具体的组件管理动作包括:
	组件对象实例化
	组件属性赋值
	组件对象之间的引用
	组件对象存活周期管理
我们要做的就是编写**配置文件**告知Spring管理哪些类组件和对这些组件的管理即可.^[组件是映射到应用程序中所有可重用组件的java对象,应该是可以复用的功能对象]

Spring 充当一个组件容器，创建、管理、存储组件，减少了我们的编码压力，让我们更加专注进行业务编写.充当的这个容器就是  [[IOC]]

