# Spring
## SpringMVC运行流程
### answer 1:
用户发起请求,servlet将请求拦截后转发给springMvc框架
其内的dispatchservlet核心控制器接收到请求后将请求转发给handlermapping
hadlermapping解析请求,根据请求信息和配置信息去寻找到合适的controller类
若有配置拦截器就会先执行拦截器内的prehandler方法
随后传递给controller并执行相应的controller内的方法
controller内的方法执行完成后会返回model and view ,包含视图名称以及模型数据
视图解析器会根据名称找到视图并将数据模型填充到视图中后渲染成html内容返回给客户端
### answer 2:
![[Pasted image 20231220155859.png]]
## Bean的加载过程
## ioc的原理
