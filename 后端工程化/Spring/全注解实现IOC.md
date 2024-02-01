# 分析
基于XML实现IOC
基于+注解方式实现

注解需要替代  
	1. 指定配置文件
	2. 扫描ioc/di中的注解
	3. 引入外部文件
![[Pasted image 20231127111425.png|600]]
# 实现

![[Pasted image 20231127112547.png|500]]
### @Configuration
标志当前所标注的类为配置类
### @ComponentScan
扫描注解,其内属性 basepackage内写需要扫描的路径
会扫描该路径的包及其子包
### @PropertySource
指定属性文件
### @Import
引入其他配置文件

![[Pasted image 20231127140252.png|500]]

![[Pasted image 20231127141128.png|500]]
# 总结

1. 完全注解方式指的是去掉xml文件，使用配置类 + 注解实现
2. xml文件替换成使用@Configuration注解标记的类
3. 标记IoC注解：@Component,@Service,@Controller,@Repository
4. 标记DI^[属性注入]注解：@Autowired @Qualifier @Resource @Value
5. <context:component-scan标签指定注解范围使用@ComponentScan(basePackages = {"com.atguigu.components"})替代
6. <context:property-placeholder引入外部配置文件使用@PropertySource({"classpath:application.properties","classpath:jdbc.properties"})替代
7. <bean 标签使用@Bean注解和方法实现
8. IoC具体容器实现选择AnnotationConfigApplicationContext对象