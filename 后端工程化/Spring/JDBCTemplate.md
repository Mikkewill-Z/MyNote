## 添加依赖
spring-context^[spirng环境]
spring-jdbc^[数据库连接]
mysql-connector-java^[数据库]
druid^[数据库连接池]
spring-text^[测试]
junit-jupiter-api^[更方便的获取容器类对象]
lombok^[实体类的构造]
## 添加属性文件
.properties文件
数据库连接信息:
```
url=jdbc:mysql://localhost:3306/库名
driverclassname=com.mysql.cj.jdbc.Driver
uname=root
upass=iwefv
```
## 配置文件
使用标签创建命名空间指定外部属性文件将配置类数据引入到容器之中
随后创建Druid数据源
在标签bean内使用property标签根据key将属性值传递
创建操作数据库的工具类对象JDBCTemplte
方便再测试类中使用工具类来对数据库进行csud^[增删改查]操作
## 数据库操作
新增.删除.修改都使用update()进行
方法传参为 sql  语句中待传参值

单行查询
使用的方法为query->queryForObject(sql , 结果集对象 , 待传参值)
其中,结果集对象RowMapper是个接口
需要我们在方法传参集中自己new
```
Users users = jdbcTemplate.queryForObject(sql, 

			new RowMapper<Users>() {
			%% rs为我们查询到的结果 %%  
            public Users mapRow(ResultSet rs, int rowNum) throws SQLException {
                //new对象用来接收参数
                Users users = new Users();
                参数是从结果中获取到的
                users.setUid(rs.getInt("uid"));
                users.setUname(rs.getString("uname"));
                users.setUpass(rs.getString("upass"));
                //最终返回的结果是从这里得到的
                return users;
            }
        }
        
        , 4004);
```
单行单列查询,查询总数
使用工具类jdbctemplate的queryForObject传递参数为sql和想要的返回值的类型 
![[Pasted image 20231128191607.png|400]]
