## 优化方案
1. 合理创建索引,对sql语句进行调优,让索引发挥最大效能
2. 合理调整MySQL配置参数,比如连接数,缓冲区的大小等
3. 根据实际需求合理选择存储引擎,比如操作中不涉及到事务就使用MyISAM作为存储引擎.
4. 合理设计表结构,比如多表关联查询时不要有多余的表
5. 对MySQL进行分库分表处理
## 读写分离
![[Pasted image 20240130181944.png|470]]
## 数据库分片
单表行数500w或者容量达到2GB,考虑分库分表
### 垂直拆分
#### 垂直分库
将一个库中的多个表,存放到多个库中
![[Pasted image 20240130182053.png]]
#### 垂直分表
![[Pasted image 20240130182439.png|470]]
### 水平拆分

![[Pasted image 20240130183229.png|470]]