通过配置实现分库分表,主从复制等功能
### 一:
使用ShardingSphere-JDBC进行配置,实现读写分离的功能
### 二:
### 实现垂直分库分表
shardingSphere通过配置自动识别库中的表
例如操作user表,就在user在的库中找到对应的表
不需要写程序的判断而去进行自动的寻找
#### 配置介绍
##### 垂直分片:
mode:
  type: Standalone
  repository:
    type: JDBC

dataSources:
  user_ds:
    dataSourceClassName: com.zaxxer.hikari.HikariDataSource
    driverClassName: com.mysql.cj.jdbc.Driver
    jdbcUrl: jdbc:mysql://192.168.6.128:3301/db_user
    username: root
    password: 123456
  order_ds:
    dataSourceClassName: com.zaxxer.hikari.HikariDataSource
    driverClassName: com.mysql.cj.jdbc.Driver
    jdbcUrl: jdbc:mysql://192.168.6.128:3302/db_order
    username: root
    password: 123456

这里配置的是上方对应的规则,操作哪个表,就从datasource配置里去对应的数据库中
rules:
  -!SHARDING
    tables:
      t_user:
        actualDataNodes: user_ds.t_user
      t_order:
        actualDataNodes: order_ds.t_order

props:
  sql-show: true

### 水平分片
![[Pasted image 20240131165344.png|470]]
![[Pasted image 20240131165359.png|470]]


## 关于分库分表时出现的问题

![[Pasted image 20240131104239.png|470]]