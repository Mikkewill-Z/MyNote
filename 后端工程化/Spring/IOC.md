# 介绍
SpringIOC即是容器,用来管理项目中组件也就是需要调用的对象.[[SpringFramwork#组件|组件]]
替代每层new对象的操作,改成由spring创建,分发给每层的属性
## Spring管理组件的优势
1. 降低了组件之间的耦合性
2. 提高了代码的可重用性和可维护性
3. 方便了配置和管理
4. 交给Spring管理的对象(组件)^[组件一定是对象,对象不一定是组件],方可享受Spring框架的其他功能(AOP,声明式事务管理)
## 容器
### 普通容器
只能用来存储,没有更多别的功能
例如:   
	- 数组
	- 集合: List
	- 集合: Set
### 复杂容器
 SpringIOC容器:
	 负责实例化,配置和组装bean(组件).
	 容器通过读取配置文件来获取有关要实例化,配置和组装组件的指令.
	 配置元数据以 **XML、Java 注释**或**Java 代码形式**表现。

## 控制反转ioc
将创建对象的权限交由spring框架.由Spring框架完成对象的创建和赋值.
IOC控制反转主要侧重于文件创建权限
DI主要是依赖的注入
# 框架搭建

在maven项目中导入依赖包  spring-context
创建xml-spring配置文件
在配置文件中使用标签创建对象^[其内属性id为对象名,class为类的完整路径]
在测试中[[获取容器的对象]],需要先[[加载spirng的配置文件]]

# 对象属性赋值
### 一
![[Pasted image 20231125101457.png|500]]

1.调取set方法赋值
	在bean标签内使用property标签进行赋值
		property底层其实是通过调用set方法进行赋值
2.调取构造方法进行赋值
		通过使用bean标签内的constructor-arg标签
		这个标签的属性来进行赋值
		可以通过name也可以通过type来指定给哪一个属性赋值
### 二
![[Pasted image 20231127201931.png|400]]
## 引入外部属性文件
### 使用命名空间,将属性文件等引入容器之中
![[Pasted image 20231127203443.png|500]]
如此便可实现外部属性文件的引入,读取属性文件,context命名空间
![[Pasted image 20231127203518.png|500]]
引入之后
![[Pasted image 20231127203655.png|500]]
# 工厂模式创建对象
实现FactoryBean方法将当前类设置为工厂类,用来生成对象
![[Pasted image 20231127205306.png|400]]
在配置文件中创建工厂类对象
![[Pasted image 20231127210223.png|400]]
## FactoryBean和BeanFactory区别
**FactoryBean**是 Spring 中一种特殊的 bean，可以在 getObject() 工厂方法自定义的逻辑创建Bean！是一种能够生产其他 Bean 的 Bean。FactoryBean 在容器启动时被创建，而在实际使用时则是通过调用 getObject() 方法来得到其所生产的 Bean。因此，FactoryBean 可以自定义任何所需的初始化逻辑，生产出一些定制化的 bean。

**BeanFactory** 是 Spring 框架的基础，其作为一个顶级接口定义了容器的基本行为，例如管理 bean 的生命周期、配置文件的加载和解析、bean 的装配和依赖注入等。

# spring-test
可以配置文件的导入,不需要通过class或者annotatin去进行
![[Pasted image 20231127160700.png|400]]
简化了获取容器中对象的方式
在测试类中声明该类型的对象属性+autowired
@SpringJunitConfig(location="配置文件 路径")
@SpringJunitConfig(vlaue=配置类 .class)