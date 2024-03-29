## 概述
日志可以记录系统/软件运行过程中的所有操作
通过日志可以排查系统中的一些相关问题
缺点:
	进行日志操作会造成一定的性能问题
	每个操作都记录日志会造成日志文件过大,占用过大的磁盘空间
	在线上项目中,除非有特殊的需求,一般来讲比如在springBoot项目中,日志的级别为ERROR
### 分类
MySQL数据库内包含的多种类型日志默认情况都大部分都是没有开启的
1. 错误日志
	- 记录MySQL服务器启动,运行过程中发生的错误和异常情况^[启动错误,语法错误等]
2. 查询日志
	- 记录所有的查询语句;^[select,insert,update,delete等]可用于分析查询性能和调试问题,可能会对性能产生影响
3. 慢查询日志
	- 记录执行时间超过指定阈值的查询语句,慢查询日志可以帮助解决执行时间较长的查询语句,便于性能进行优化
4. 二进制日志
	- 记录所有对数据库的更改操作,包括数据修改,表结构变更等,二进制日志可用于数据恢复,主从复制
5. 事务日志   
	- 又称重做日志,记录正在进行的事务的更改操作
	- 用于保证数据库的ACID特性[[AOP事务管理#事务的特性]],支持崩溃修复
# 分类介绍
## 慢查询日志
### 概述
用于记录当前执行sql是否超过设置运行时间
MySQL默认的sql语句执行时间为10s,当执行时间超过10s就会将语句信息记录在慢查询日志里
默认的sql执行时间可以修改
MySQL数据库慢查询日志默认没有打开的,如果使用需要手动开启
### 场景
用于**排查线上项目**SQL问题
	线上项目出现运行缓慢的问题,首先排查物理因素^[网络带宽,服务器配置],如果不是物理因素,程序问题^[代码问题,sql语句问题]
使用慢查询日志排查SQL语句的问题
### 应用
- 开启慢查询日志
-![[Pasted image 20240129093544.png|470]]
- 设置SQL语句的执行时间(默认10s)
-![[Pasted image 20240129093628.png|470]]
- 通过日志查看慢查询SQL语句
- 查询到慢查询SQL语句,使用explain进行调优
- EXPLAIN即MySQL优化测试语句,通过修改调整语句达到性能的优化
## 事务日志
### 什么是事务
### 事务四个特性
原子性: 不可分割,要么都成功,一个失败都失败 
一致性: 操作前后总量不变,数据状态前后一致
隔离性: 并发场景下,多个事务操作,事务与事务之间相互独立
持久性: 事务提交后永久保存到数据库
### 不考虑隔离性产生的问题
1.脏读
	两个未提交的事务,互相读取到对方的数据
![[Pasted image 20240129142039.png|300]]
2.幻读
	没有提交的事务读取到了另外一个提交了的事务的提交/添加数据
3.不可重复读
	没有提交的事务读取到了另外一个提交了的事务的修改数据
4.丢失修改
	后提交的数据会覆盖掉之前的数据,乐观锁解决

可以通过设置事务隔离级别解决这些问题^[mysql默认隔离级别 Repeatable Read]
## 事务日志概述
redo日志 记录更新后的数据,保证事务提交的
undo日志 记录更新前的数据,保证事务回滚的
## redo日志
InnoDB存储引擎 写数据过程
![[Pasted image 20240129103540.png|500]]
加入 redo日志处理/存储 进行优化
MySQL的写操作并不是立刻更新到磁盘,而是先记录到日志上(这里的日志就是redo日志),然后在合适的时间再更新到磁盘上
![[Pasted image 20240129103927.png|500]]
缓冲区默认的大小为16M
其大小设置规则为 最大值4096M,最小值为1M
### redo log刷盘策略
即何时向日志写入内容
设置为0: 每1s写入一次日志.性能最佳,数据风险高
设置为1: 实时写入日志(默认值).数据安全性较高,性能较差
设置为2: 不自己设置,由操作系统决定什么时候写.性能较高,数据安全性较高
### 指标:
性能和安全性
安全和时间
## undo日志
redolog是事务持久性的保证(保证事务的提交)
undolog是事务原子性的保证(保证事务回滚)
在事务中更新数据的**前置操作**其实是要先写入一个undolog
![[Pasted image 20240129192715.png|470]]
undo log类型 
	insert undo log : 插入操作
	update undo log: 删除和修改操作
# MySQL锁机制
前置详见[[锁概述]]
## 锁概念
锁是计算机协调多个进程或线程并发访问某一个资源的机制
加锁肯定会造成性能的降低,为了减少性能的损失,锁的范围应该尽可能的小
![[Pasted image 20240129141354.png|470]]
可设置锁的范围

## 并发事务访问情况
### 读-读
读操作不去修改数据库表记录,读-读情况不会发生问题
### 写-写
造成丢失更新问题,最后提交把之前数据覆盖
解决方案: 加锁
	第一个线程操作的时候,加锁,其他的线程等待
### 读-写
即一个事务进行读取操作,另一个进行改动操作,这种情况下可能发生脏读,不可重复读,幻读的问题
解决方案: [[MVCC]]
	**读并发的,写独立的**

锁分类详见 [[锁概述#划分|锁的分类]]

## MyISAM表锁
加锁语句
![[Pasted image 20240129200929.png|470]]
加读锁是并发读的;
加写锁,阻塞其他线程读操作和写操作
## InnoDB行锁
**对于UPDATE、DELETE和INSERT语句，InnoDB会自动给涉及数据集加排他锁（写锁）；**
对于普通的select语句,InnoDB不会加任何锁
进行UPDATE,DELETE和INSERT语句操作的时候,如果索引失效,行锁就升级为表锁

- **间隙锁**  

-- 写操作时候，条件设置范围，比如 id<4

-- 如果添加数据id在小于4范围中，添加语句执行等待锁释放才能进行下去

**-- 做写操作时候，如果条件是范围，避免添加数据在范围中**