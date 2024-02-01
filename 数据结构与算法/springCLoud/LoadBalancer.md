负载均衡器,其是SpringCloud中负责客户端负载均衡的模块^[就是负载均衡算法由客户端提供]
# 执行流程
1.通过LoadBalancerInterceptor请求拦截器拦截restTemplate请求
2.获取请求的url,从中获取服务提供方的主机名
3.调用LoadBalancerClient中的execute方法,将服务提供方的名称传递过去
4.在client的choose方法中通过Reactive Load Balancer.Factory从Nacos注册 中心获取服务列表以及负载均衡算法实例对象
5.通过ReactiveLoadBalancer从服务列表中选择一个服务实例地址，然后发起远程调用
# 修改负载均衡策略
1. 创建类,new随机负载均衡策略,交给spring管理
2. ![[Pasted image 20240117085636.png|400]]
3. 在RestTemplate配置类上添加自定义策略
4. @LoadBalancerClients(value = {
        @LoadBalancerClient(name = "spzx-cloud-user" , configuration = CustomLoadBalancerConfiguration.class)      // 将负载均衡算法应用到指定的服务提供方中
})

