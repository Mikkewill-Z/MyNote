# 方式一
new 一个ClassPathXmlApplicaitonContext传递参数为配置文件名
返回的参数是ApplicationContext类型,是为应用程序上下文,是个容器
随后从容器中拿出其中的对象

![[Pasted image 20231125094426.png|500]]

![[Pasted image 20231125094449.png|500]]

# 方式二
直接new   ClassPathXmlApplicationContext
返回的类型也是 classpath~类型
使用setConfigLocatin为其添加配置文件位置
随后使用refresh进行强制刷新
最后使用getBean方法传递对象id获取出容器内的对象
![[Pasted image 20231125095401.png|500]]

