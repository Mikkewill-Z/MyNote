由Netflix提供,基于Nacos与openFeign一起使用实现远程调用的过程^[不使用RestTemolate的方式]
## 使用
1.调用端引入OpenFeign依赖
2.调用端创建interface定义需要调用的接口的信息
![[Pasted image 20240117093329.png|400]]
3.在调用端Order模块启动类添加注解,开启远程调用
![[Pasted image 20240117093502.png]]
4.注入创建interface,调用方法进行实现
![[Pasted image 20240117093416.png]]
# 自定义配置
## 细节配置->配置文件
### 日志
![[Pasted image 20240117093934.png|300]]
![[Pasted image 20240117093952.png|350]]
### 超时
![[Pasted image 20240117094046.png|400]]
### 重试
调用端创建类实现重试接口
![[Pasted image 20240117094207.png|400]]
配置
![[Pasted image 20240117100055.png|400]]
## 配置类修改日志级别
![[Pasted image 20240117103219.png|500]]