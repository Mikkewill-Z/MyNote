# 是什么?
通过注解或者一些简单的配置就能在SpringBoot的帮助下实现某块功能
或者说是springBoot定义了一套接口规范,这套规范规定springboot在启动时会扫描 外部引用jar包 中的META/INF/spring.factories文件,将文件中的配置的类型信息加载到spring容器,并执行类中定义的各种操作,对于外部jar来说,只需要按照SpringBoot定义的标准,就能将自己的功能装置进SpringBoot
# 如何实现的?
![[Pasted image 20231223203834.png]]
