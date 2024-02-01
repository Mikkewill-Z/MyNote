## 介绍
MyBatis的增强工具
核心是mapper接口的是实现
![[Pasted image 20240130112906.png|470]]
如果是实现单表的curd操作,在mp内不需要编写sql语句,调用mp封装的方法就可以实现
如果是多表查询,或者复杂的查询语句,还是需要编写sql语句来实现
## 使用
1. 创建SpringBoot工程
2. 引入相关依赖(SpringBoot依赖,MyBatisPlus依赖,数据库依赖等)
3. 创建表,创建表对应实体类,指定实体类和表的对应关系
4. 创建Mapper接口,继承BaseMapper,调用Mapper封装的方法实现curd操作