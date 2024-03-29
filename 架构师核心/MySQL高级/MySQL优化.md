# MySQL索引优化
## 方案
1. 合理创建索引,对sql语句进行调优,让索引发挥最大效能
2. 合理调整MySQL配置参数,比如连接数,缓冲区的大小等
3. 根据实际需求合理选择存储引擎,比如操作中不涉及到事务就使用MyISAM作为存储引擎.
4. 合理设计表结构,比如多表关联查询时不要有多余的表
5. 对MySQL进行分库分表处理^[这里就涉及到了ShardingSphere的使用]
方案5详见[[ShardingSphere]]

网络的TCP/IP协议
## 性能分析
```
# explain + sql语句
# 执行之后，得到性能分析各个数据指标
explain select * from customer1

# 模拟优化器执行SQL查询语句
```

![[Pasted image 20240127103136.png|700]]
![[Pasted image 20240127103346.png|200]]
关于keyLen的计算方案
![[Pasted image 20240127111950.png]]
![[Pasted image 20240127103418.png|200]]
![[Pasted image 20240127103503.png|200]]
![[Pasted image 20240127103538.png|200]]
![[Pasted image 20240127103026.png|200]]
## 优化操作
### 数据准备
存储过程+自定义函数
### 单表索引查询优化
1. 计算,函数导致索引失效
2. LIKE以%开头导致索引失效
	- - **实际开发中，肯定会有这种情况 %abc%，**
	- **阿里巴巴开发手册规定：如果%abc%情况，使用搜索引擎工具**
3. 不等于(!= or <>)导致索引失效
4. IS NOT NULL 和 IS NULL
5. 类型转换导致索引失效
6. 全索引匹配效率最高
7. 违背了最佳左前缀法则
8. 索引中范围条件右边的列失效
### 多表关联查询优化
#### 左外连接
编写左外连接SQL语句,左表是驱动表,右表是被驱动表
#### 内连接
MySQL内,若编写内连接查询语句,MySQL会对查询语句自动进行优化
MySQL自动识别驱动和被驱动表,哪一个表的数据量少就作为驱动表
#### 子查询
尽量使用关联查询替代子查询
#### 其他优化
排序优化时,若索引生效,不会在key_len显示,因为优化幅度有限
groupBy时,优化和排序相同
### 微服务架构
![[Pasted image 20240129085703.png|300]]