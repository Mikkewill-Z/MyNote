通过注册中心可以对服务提供方和服务消费方进行解耦

nacos启动!!!^[需要在bin目录下]
![[Pasted image 20240117194205.png]]

## 流程说明
1. 服务提供方启动,向注册中心注册服务信息(ip,端口).
2. 注册中心会维护一张服务清单保存注册信息,以心跳方式监测清单中的服务是否可用
3. 服务消费方向注册中心咨询,获取所有服务清单,按照指定的[[LoadBalancer|负载均衡]]算法从服务清单中选择一个服务实例进行访问

# 注册中心
## Eureka
![[Pasted image 20240115211901.png]]
包含EurekaServer和EurekaClient
服务提供者在启动时通过EurekaClient向Eureka注册自己的服务信息,隔一段时间会发送心跳告诉Server仍存活.服务消费者通过Client从Server获取服务提供者列表,并对这些服务进行负载均衡和调用

### 优点
简单易用,高可用,动态扩展性,易于集成
### 不足
server在高并发场景下可能称为限制系统扩展的瓶颈
服务注册中心本身也需要高可用环境,一旦出现问题可能影响到整个微服务的正常运行
## Nacos
![[Pasted image 20240116104845.png|600]]
NacosServer 服务注册中心,是服务,服务的实例,元数据的数据库.服务实例在启动时将其注册到服务注册表,在关闭时注销,可能会调用服务实例健康监测API验证,需要独立的部署
NacosClient: 负责和server进行通讯完成服务的注册和服务的发现
NacosConsole 是nacos控制模块,提供了可视化的后台管理系统,便于实现服务管理操作
### 优点
高可用,动态扩展,易于集成,完备的功能支持

## 使用

### docker
//拉取 docker pull nacos/nacos-server:v2.2.2
//创建容器 docker run --name nacos -e MODE=standalone -p 8848:8848 -p 9848:9848 -d nacos/nacos-server:v2.2.2
### windows
下载解压
启动 startup.cmd-m standalone
访问界面 
## 服务注册
注册到nacos中
![[Pasted image 20240116111027.png|400]]
添加配置
![[Pasted image 20240116111118.png|400]]
order模块引入依赖loadbalancer
在order模块的rest Template配置类方法上添加@LoadBalanced注解
## 更改远程调用
注册成功之后
Nacos+[[LoadBalancer]]实现远程调用

![[Pasted image 20240116162900.png|700]]
也可使用[[OpenFeign]]来实现远程调用
## 负载均衡测试
### 轮询
![[Pasted image 20240116163120.png|400]]
简单创建集群->测试使用
![[Pasted image 20240116164023.png]]
可以取到配置文件之中的值->用于在测试中看到效果
启动所有userServer集群

在调用过程中会发现会遵循**轮询机制**,集群中所有模块按照服务注册时的顺序一个一个进行.

以下为Nacos作为配置中心的高级特性
## 跨集群访问
为保证每个服务的高可用,需要构建服务集群,通常会将多个服务分散部署到不同的机房,每一个机房的服务都可以看作是一个集群
![[Pasted image 20240116170836.png|500]]
特点:
	微服务互相访问时,尽可能访问同集群实例,因为本地访问的速度更快.
	本集群不可用时才访问其他的集群
始终要分清楚的是 服务的调用方和提供方之间的关系

### 服务集群
首先需要配置集群-->配置服务方
![[Pasted image 20240116212308.png|400]]
然后进行集群的访问-->配置请求方
![[Pasted image 20240116212240.png|400]]
## 权重配置
通过修改权重的方式实现不同性能的机器的服务量承占比
![[Pasted image 20240116212634.png|400]]

## 环境隔离
在nacos是通过namespace来实现多环境的隔离的

namespace+group才可以确定具体的微服务实例
默认所有service,group都在同一个namespace即public之下

我们可以创建新的名称空间,将不同的服务隔离到不同的环境下
![[Pasted image 20240116214408.png|400]]

## 实例类型:
nacos中的服务实例存在两种类型
临时实例.若实例宕机超过一定时间会从服务列表剔除,并且实例会定时上报自身的健康状态给注册中心^[此种属于默认的实例类型]
非临时实例: 若实例宕机,不会从服务列表剔除,nacos注册中心会主动询问实例的健康状态,也可以叫永久实例

![[Pasted image 20240116214706.png|500]]
ephemeral 临时的,短期的 默认是true,我们将其修改为非临时/永久实例