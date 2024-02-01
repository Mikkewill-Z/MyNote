## nosql数据库
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695815973159-db6ada12-c4b8-4c65-aa39-63f8b2581d9f.png#averageHue=%23fcfcf8&clientId=u0387edb6-d060-4&from=paste&height=148&id=ue4670b1a&originHeight=204&originWidth=910&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=98678&status=done&style=none&taskId=ud9383a32-e943-405f-a384-aff234cd550&title=&width=661.8181818181819)
不支持事务(回滚)
比SQL性能高
#### 适用于
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695815985671-05baa049-57d4-4006-8539-0ca388f12fac.png#averageHue=%23f9f9f5&clientId=u0387edb6-d060-4&from=paste&height=99&id=uab305553&originHeight=136&originWidth=265&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=30544&status=done&style=none&taskId=uec96e505-118e-43bd-93c6-7ebf663a3d3&title=&width=192.72727272727272)
#### 不适用于
不适用需要事务支持的场景
不适用于基于sql的结构化查询存储,处理复杂的关系查询等场景
#### 常见NoSQL数据库
1.Memcached
不支持持久化

2.MongoDB
文档类型,用来存储据
##### 3.Redis
支持持久化,用作备份恢复
支持的类型较多
一般作**缓存数据库**辅助持久化数据库
## Reids基础
### Redis介绍安装
是NOSQL系统之一,是开源的,c编写的key-value存储系统
读写书都快
操作都是原子性
支持的数据结构有: string(字符串), list(列表), hash(哈希) ,set(集合) ,zset(有序集合)
支持集群部署
#### 适用
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695817018349-9611bd1d-7f6f-4b2a-bf39-2daedc4381c0.png#averageHue=%23fcfcf8&clientId=u0387edb6-d060-4&from=paste&height=209&id=u220a985f&originHeight=287&originWidth=581&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=69256&status=done&style=none&taskId=u1037c5a9-8b62-47bf-a8e7-9c99b062321&title=&width=422.54545454545456)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695816542935-9f5df16b-a0b3-4641-9df8-6892b78006e8.png#averageHue=%23fdfdf9&clientId=u0387edb6-d060-4&from=paste&height=377&id=ue999152b&originHeight=519&originWidth=1010&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=272867&status=done&style=none&taskId=ub4d86b1f-bae4-4528-8248-f3427118c62&title=&width=734.5454545454545)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695816550783-353c4aea-9f7a-44d6-9df8-7f2da515ec79.png#averageHue=%23fdfbf4&clientId=u0387edb6-d060-4&from=paste&height=295&id=udb93f983&originHeight=406&originWidth=971&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=227016&status=done&style=none&taskId=u45d01359-4d4b-42db-bebc-5dcce189076&title=&width=706.1818181818181)
实现session共享
原:
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695816617934-7d6cb718-158f-4077-a9b2-e347eede584c.png#averageHue=%23fbfbf8&clientId=u0387edb6-d060-4&from=paste&height=435&id=u79617c33&originHeight=598&originWidth=780&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=51166&status=done&style=none&taskId=ua3526388-9444-4383-bebe-245870e87ab&title=&width=567.2727272727273)
现:集群解决问题的方案
1.cookie解决(不安全)
2.session复制(太重复)
3.ip绑定,每次请求只向绑定服务器发送(安全问题)
4.redis(第一次请求发送的本地存一份session数据,且往redis服务器上也存一份session数据,当请求并非发送到原本服务器上时,在本地找不到就取redis寻找)
#### 安装调试
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695818067843-19ac8ec6-c25c-4faa-9892-dc17e262d470.png#averageHue=%23e9e8e5&clientId=u0387edb6-d060-4&from=paste&height=484&id=u59c10744&originHeight=666&originWidth=516&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=286967&status=done&style=none&taskId=uc97cd39e-9adb-41a8-9f94-3af0dfa0c8a&title=&width=375.27272727272725)
##### 安装总结
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695818868385-2bd98789-4b60-48bc-9652-8ea82190b2a8.png#averageHue=%23fbfbf8&clientId=u4de97740-16ce-4&from=paste&height=271&id=u455b41fd&originHeight=372&originWidth=343&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=69878&status=done&style=none&taskId=u48ad193b-4784-4df7-8e48-4ed9d7532ed&title=&width=249.45454545454547)
随后进入/usr/local/bin之中
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695819025367-9575d489-5072-4aaa-a1e7-f1b00f7998e0.png#averageHue=%23283b29&clientId=u4de97740-16ce-4&from=paste&height=218&id=u0b515a0d&originHeight=300&originWidth=830&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=368057&status=done&style=none&taskId=u57e735cd-a946-4cea-b3ad-a0afd111f4d&title=&width=603.6363636363636)

### Redis启动
#### 前置启动(不建议)
使用redis-server进行启动(在任何地方都可以启动)
因为redis-server本身就在环境变量中
无法恢复到命令窗口
#### 后置启动(建议)
redis-server应该通过配置文件进行启动
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695819701846-e54ee323-56d3-4019-ab7f-44ca83cf96a1.png#averageHue=%23232521&clientId=u4de97740-16ce-4&from=paste&height=295&id=ud2a8c5a3&originHeight=406&originWidth=941&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=428363&status=done&style=none&taskId=u6ed4fc7d-8e6e-432b-afb5-6816e217dc9&title=&width=684.3636363636364)
在redis的安装目录之下有一个redis.conf
若直接使用 redis-server时,默认使用redis.conf启动
最好通过复制的形式来修改配置文件
复制的命令为cp  复制到家目录下--->cp redis.conf /root
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695820159029-731f3483-79e7-4244-adf3-11dae397d8d4.png#averageHue=%23fbfbf7&clientId=u4de97740-16ce-4&from=paste&height=497&id=u2daa9094&originHeight=683&originWidth=657&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=270888&status=done&style=none&taskId=u97e96463-7324-4166-aa91-534d14aafd4&title=&width=477.8181818181818)


#### 连接
启动之后通过客户端对其进行连接
redis-cli -p 6379
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695820857800-778dcb2d-405c-4125-b3ad-193e478061b4.png#averageHue=%232d2e2a&clientId=u4de97740-16ce-4&from=paste&height=236&id=u685f595b&originHeight=324&originWidth=992&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=262318&status=done&style=none&taskId=ude17cc95-70fc-47e5-bfde-1984fac4400&title=&width=721.4545454545455)
表示连接成功
### Redis停止(停止服务)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695821208769-683ce250-878f-4ece-81dd-218d09379298.png#averageHue=%23fbfbf6&clientId=u4de97740-16ce-4&from=paste&height=215&id=ua46fecfa&originHeight=296&originWidth=628&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=92885&status=done&style=none&taskId=u53c4f419-aad8-4f55-ae2e-9918b52f1b0&title=&width=456.72727272727275)
处在linux系统中时,使用关闭redis服务的方式进行
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695860998337-b3411d46-428e-41f4-820b-fa696d27c157.png#averageHue=%2332332f&clientId=ue2724c9a-e08f-4&from=paste&height=110&id=u339990e7&originHeight=151&originWidth=920&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=176425&status=done&style=none&taskId=ua13e506f-a940-4808-9a20-784a109d551&title=&width=669.0909090909091)

重新启动且进入redis-cli之中,
直接使用shutdown关闭
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695861163348-e7a4b1fa-ec56-41b5-8bd7-f53625619bec.png#averageHue=%232c2e2a&clientId=ue2724c9a-e08f-4&from=paste&height=191&id=uafc1e28e&originHeight=263&originWidth=799&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=226242&status=done&style=none&taskId=uc425a4fd-d58d-4d60-bb66-f949375d202&title=&width=581.0909090909091)

或者直接杀死进程id--->kill -9 进程id
### 简单命令
redis单线程+多路复用(多路指的是多个网络连接客户端,复用指的是复用同一个线程)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695861613778-f3322650-87f8-4690-a9ce-cf9edd1a8d10.png#averageHue=%23f3f3ef&clientId=ue2724c9a-e08f-4&from=paste&height=399&id=uc1a17c2e&originHeight=549&originWidth=1038&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=225183&status=done&style=none&taskId=u8afb3804-85e5-4152-9af5-fd9a0904119&title=&width=754.9090909090909)
#### keys *   查看其内数据
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695821041857-634c7df1-e6b7-4bd4-832f-1d863957b76e.png#averageHue=%232a2d27&clientId=u4de97740-16ce-4&from=paste&height=292&id=ubb25e153&originHeight=401&originWidth=395&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=171050&status=done&style=none&taskId=u20f333d7-f760-47ee-b0f9-9fc9819c3bb&title=&width=287.27272727272725)
存进去的都是key与value形式的键值对
可以使用get来得到数据
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695821059348-965242a5-9239-47f0-8c89-77ee1ef597d9.png#averageHue=%232c2f27&clientId=u4de97740-16ce-4&from=paste&height=129&id=u5a3d7af8&originHeight=178&originWidth=329&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=72414&status=done&style=none&taskId=ufd5c24dc-1421-4572-87c4-1fca386f1e2&title=&width=239.27272727272728)
## Redis常用命令与操作
### Redis数据类型命令
前提:开启redis服务并连接
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695864593569-ff936abc-1339-4cf3-a39e-f6d2b7873b86.png#averageHue=%23191c16&clientId=u53930a31-d1c5-4&from=paste&height=137&id=u55112797&originHeight=188&originWidth=591&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=174822&status=done&style=none&taskId=u78965c6f-3108-4ae0-9389-66b130de3bb&title=&width=429.8181818181818)
#### Key的操作
##### keys*  查看库内所有的key
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695864690817-5709add4-084e-463e-8dac-37e4fa6b70f6.png#averageHue=%23161712&clientId=u53930a31-d1c5-4&from=paste&height=156&id=u3b197679&originHeight=214&originWidth=351&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=81189&status=done&style=none&taskId=u6a246317-5580-4ef8-a2be-49a722c64a8&title=&width=255.27272727272728)
若要在key内存放list组
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695864780817-3ad6b2e4-1eed-4848-9095-03304677b706.png#averageHue=%23131511&clientId=u53930a31-d1c5-4&from=paste&height=123&id=u065d4a97&originHeight=169&originWidth=568&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=102507&status=done&style=none&taskId=ua6896349-6618-44e4-a98e-c60ae4c24cc&title=&width=413.09090909090907)
##### exists key  判断某个key存不存在
##### type key值  判断key值是什么类型
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695864729979-ee59a3ab-4cc2-4a4f-95fe-67b5d7689bdd.png#averageHue=%23141611&clientId=u53930a31-d1c5-4&from=paste&height=113&id=ude71d1c5&originHeight=155&originWidth=408&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=61151&status=done&style=none&taskId=ud04fc952-4427-46f7-9766-06eb177ed04&title=&width=296.72727272727275)
判断出来的就是list形式
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695864821767-9294dd3b-57fc-497e-9544-fc8b05b1e0d7.png#averageHue=%23151813&clientId=u53930a31-d1c5-4&from=paste&height=73&id=uaac9c849&originHeight=100&originWidth=371&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=36126&status=done&style=none&taskId=u68bcf850-e2ba-4946-85ac-a8a1a02d4d2&title=&width=269.8181818181818)
##### del k1 在库内删除k1的数据
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695864998364-a6cd2525-a172-47db-9a99-157c575f3d43.png#averageHue=%23161813&clientId=u53930a31-d1c5-4&from=paste&height=281&id=u01f22d69&originHeight=387&originWidth=317&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=126701&status=done&style=none&taskId=ufe449600-5184-4f4f-80d7-0e068ad1813&title=&width=230.54545454545453)
##### unlink k2 无阻塞删除
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695865120967-f2acad2f-b4f7-418d-a613-4a0887e38062.png#averageHue=%23161913&clientId=u53930a31-d1c5-4&from=paste&height=132&id=u3cdc457a&originHeight=182&originWidth=331&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=70813&status=done&style=none&taskId=ubde5ec93-9474-4ed8-bf2e-b7aa7dc1425&title=&width=240.72727272727272)
##### expire k 10 设置key过期时间为10秒
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695865202767-d7e937b2-f76b-4933-b8a8-b39031745cbc.png#averageHue=%23171914&clientId=u53930a31-d1c5-4&from=paste&height=238&id=r6cOg&originHeight=327&originWidth=349&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=136885&status=done&style=none&taskId=u82eb3819-b390-4561-afc6-519c30d277c&title=&width=253.8181818181818)
##### ttl key 10 查看key的过期时间
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695865202767-d7e937b2-f76b-4933-b8a8-b39031745cbc.png#averageHue=%23171914&clientId=u53930a31-d1c5-4&from=paste&height=238&id=u6f4b8154&originHeight=327&originWidth=349&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=136885&status=done&style=none&taskId=u82eb3819-b390-4561-afc6-519c30d277c&title=&width=253.8181818181818)
过程中可以使用ttl key来查看key的剩余时间,若过期了就会显示-2
未设置过期时间就是永不过期,查看时就会显示-1
##### select 命令切换数据库
redis为我们准备了16个数据库,从0开始到15标(默认处于0号库)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695865619378-a8284908-b95e-4c33-8c90-f8c836c12319.png#averageHue=%23151712&clientId=u53930a31-d1c5-4&from=paste&height=306&id=uf84bc5da&originHeight=421&originWidth=428&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=213576&status=done&style=none&taskId=u036e5d43-cfd0-40ea-94e2-5fd00edcec8&title=&width=311.27272727272725)
不同的库之间数据是不互通的,可以区分存储不同的数据
##### dbsize查看库中数据的个数
可以配合切换库select来使用
查看哪个库有哪些数据
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695865690299-a518f374-2745-4dd6-a985-6ec8a98281b5.png#averageHue=%23151812&clientId=u53930a31-d1c5-4&from=paste&height=135&id=u30ea4fb1&originHeight=185&originWidth=367&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=82102&status=done&style=none&taskId=uec9ff11e-f2d1-4683-b0eb-e9019f958ec&title=&width=266.90909090909093)
##### flushdb	清空当前库
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695865840061-946b9529-e631-42b2-8ccc-49f8cadcdcba.png#averageHue=%23151712&clientId=u53930a31-d1c5-4&from=paste&height=224&id=u1d916c9a&originHeight=308&originWidth=405&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=131387&status=done&style=none&taskId=u1c6e75c1-172f-4556-8157-8f71b9cfc19&title=&width=294.54545454545456)
##### flushall	清空所有库
flushall,不管在哪个库内执行此操作,都会把所有库内的数据全部清除
#### String类型的常用命令
考虑到我们对于json数据的使用十分广泛,因此String类型也是Redis最基本的类型
##### set&get
简单使用可以将 k与v 存入redis库中通过get k 来获取相应地key值
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695867392470-82d5d5ca-e194-42b5-a74a-5864aee1183b.png#averageHue=%23f4f3ef&clientId=u53930a31-d1c5-4&from=paste&height=156&id=ucf328bd1&originHeight=214&originWidth=1034&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=149064&status=done&style=none&taskId=uaaa5d863-40e0-45ca-9560-7119d210640&title=&width=752)
在set k2 v200 后跟 NX --->在k2的值存在时,显示执行失败[只有key值为空时才执行]
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695867625650-5635849b-efe4-46bb-916c-75237a14cae1.png#averageHue=%23141612&clientId=u53930a31-d1c5-4&from=paste&height=122&id=u415a91e5&originHeight=168&originWidth=414&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=56494&status=done&style=none&taskId=u655f1e6b-eaf7-467f-9d8c-6dc013ce038&title=&width=301.09090909090907)
set k2 v2000 XX  在k2值存在时才执行,会将原先的value值修改为v2000
set k3 v3 EX 10  直接在创建时将过期时间设置为10秒
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695868096218-4dc4573b-f5a2-42e2-9e99-c4cbf0277d76.png#averageHue=%23151712&clientId=u53930a31-d1c5-4&from=paste&height=173&id=u286d6672&originHeight=238&originWidth=425&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=96458&status=done&style=none&taskId=ud7b07bad-d64b-454a-bf9e-58874ae6be0&title=&width=309.09090909090907)
set k3 v3 px 10  创建时将过期时间设置为10毫秒
##### append key   追加内容
为已经存在的key的value值进行追加
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695868455574-2ec8054c-93a5-4c8d-946c-7d1e39411dc2.png#averageHue=%23161812&clientId=u53930a31-d1c5-4&from=paste&height=139&id=ub498b995&originHeight=191&originWidth=388&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=84710&status=done&style=none&taskId=ub6df2675-1cf1-4907-b216-b35086138ff&title=&width=282.1818181818182)
##### strlen key (可以获取key的value的长度)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695868605695-0d0aed27-4490-453b-8c28-7b69ec77c4b3.png#averageHue=%23141612&clientId=u53930a31-d1c5-4&from=paste&height=96&id=u692bfc35&originHeight=132&originWidth=313&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=41305&status=done&style=none&taskId=u8897e303-3288-498b-90e8-73b36fa612b&title=&width=227.63636363636363)
##### setnx  key  value&setex key {过期时间} value
与set key value nx[只新增,不修改] 和set key value ex 秒值 [设置过期时间]的效用相同
不推荐使用
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695869742906-2d86fd92-e061-4cd3-960b-e0e43a754346.png#averageHue=%23161813&clientId=u53930a31-d1c5-4&from=paste&height=170&id=uc83f4a59&originHeight=234&originWidth=391&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=108087&status=done&style=none&taskId=u1ec095c6-271f-4f4c-9ea4-e41dadc2c81&title=&width=284.3636363636364)
##### incr key  为key值对应的value进行自增
可以使用incrby num 5 进行一次自增指定数字
要求其value值为数字
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695868822197-1c4d792d-650b-4456-9187-8222f19f0dcb.png#averageHue=%23151812&clientId=u53930a31-d1c5-4&from=paste&height=129&id=u55b09f49&originHeight=177&originWidth=355&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=79647&status=done&style=none&taskId=ueefd1092-6604-449c-82b7-97b64554a9e&title=&width=258.1818181818182)
##### decr key  为key值对应的vlaue进行自减
可以使用decrby key 数字 进行一次自减指定数字
要求其value为数字
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695869232949-3298d6b6-a735-4e74-adaf-0e4c4aa64c86.png#averageHue=%23151813&clientId=u53930a31-d1c5-4&from=paste&height=116&id=uda3eaa9f&originHeight=159&originWidth=338&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=66468&status=done&style=none&taskId=u1396090e-56ef-477a-b895-c34ddf98528&title=&width=245.8181818181818)
##### mset进行一次连续设置
注意set的格式
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695869335522-ac5f82f6-59c0-4b72-b2d7-65b2d2764c93.png#averageHue=%23141411&clientId=u53930a31-d1c5-4&from=paste&height=245&id=u5375d7ca&originHeight=337&originWidth=498&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=103149&status=done&style=none&taskId=u76c85e23-bf1b-4a1e-aaef-174544df186&title=&width=362.1818181818182)
##### msetnx  只新增不修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695869482994-8743a261-fbc8-4a9d-ab7a-845ceaa14a80.png#averageHue=%23141411&clientId=u53930a31-d1c5-4&from=paste&height=253&id=ub56dbc71&originHeight=348&originWidth=541&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=122342&status=done&style=none&taskId=u8d020323-61cd-4498-a476-22401656d49&title=&width=393.45454545454544)
若有已经存在的key则会执行失败(全部失败)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695869455092-0109c419-ba01-488c-b608-715c693997d0.png#averageHue=%23141411&clientId=u53930a31-d1c5-4&from=paste&height=276&id=u17a632c5&originHeight=380&originWidth=555&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=137054&status=done&style=none&taskId=u1b7a313d-6acb-4b78-b0d8-ab720d8eb88&title=&width=403.6363636363636)
##### getrange key 起始位置  结束位置
会得到值根据从零开始的标来进行读取
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695869559171-e7aeb843-7e19-4b0a-8b1d-e20d54a12e41.png#averageHue=%23151511&clientId=u53930a31-d1c5-4&from=paste&height=321&id=ue5c00094&originHeight=441&originWidth=449&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=144321&status=done&style=none&taskId=uf30aa59b-939a-4ed5-97b9-a1e30c1d248&title=&width=326.54545454545456)
##### setrange key 起始位置  想要替换的值
可以将从起始位置开始的字符串修改为想要修改的值
有几个就替换几个
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695869703046-bea68aeb-e670-4ce4-927d-bae1d3d3380f.png#averageHue=%23161813&clientId=u53930a31-d1c5-4&from=paste&height=187&id=u6203b94c&originHeight=257&originWidth=400&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=111489&status=done&style=none&taskId=u6996d7bf-d255-4217-b660-ca3ad29fa9a&title=&width=290.90909090909093)
##### mget进行一次连续的读取

##### getset key value  以新换旧,但会返回旧值
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695869954213-e4ec8a03-2079-4b8e-8457-06dc6c85bac5.png#averageHue=%23141712&clientId=u53930a31-d1c5-4&from=paste&height=173&id=u4202084a&originHeight=238&originWidth=376&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=103961&status=done&style=none&taskId=u3359e7d4-5e62-4d7f-83c9-0da7804c824&title=&width=273.45454545454544)
##### String的数据结构![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695870040485-78d81f4c-ea9e-47f3-8812-a26119c02eeb.png#averageHue=%23f7f7f2&clientId=u53930a31-d1c5-4&from=paste&height=236&id=u3bfe14b5&originHeight=324&originWidth=1164&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=333396&status=done&style=none&taskId=u331e0720-8994-4637-bcad-5a46724710c&title=&width=846.5454545454545)
#### (Redis列表)List型
底层是一个双向链表
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695870214374-a1d0ecff-9335-49f4-a126-6edc3182b407.png#averageHue=%23f7f7f3&clientId=u53930a31-d1c5-4&from=paste&height=151&id=ud395e786&originHeight=208&originWidth=1215&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=255105&status=done&style=none&taskId=u622f471b-cc04-4b2f-bb18-2802f1c873a&title=&width=883.6363636363636)
切库,select 1 防止数据混乱
##### lpush  &  rpush
lpush为左边加
读数据的时候使用lrange key值  下标范围来进行读取
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695870625539-c2f8f281-120e-48c2-87bb-80e459aadfba.png#averageHue=%23737470&clientId=u53930a31-d1c5-4&from=paste&height=285&id=u582b548c&originHeight=392&originWidth=970&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=412536&status=done&style=none&taskId=u25dc21e6-ac9b-4575-a0f6-8eb133f0f43&title=&width=705.4545454545455)
rpush为右边加
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695870726391-7011f0d3-adc1-4f18-bab3-252b23183ecc.png#averageHue=%2370716c&clientId=u53930a31-d1c5-4&from=paste&height=300&id=u5126e4fe&originHeight=412&originWidth=915&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=419236&status=done&style=none&taskId=u1ee5c23c-1349-4732-be59-921c838642a&title=&width=665.4545454545455)
使用push加是同理,但是下标会继续排列(lrange)
反着来即使-8到-1
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695870852422-5068095b-61ac-4bd6-8e0b-62831a211320.png#averageHue=%23151511&clientId=u53930a31-d1c5-4&from=paste&height=183&id=u55e77e8e&originHeight=251&originWidth=396&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=78022&status=done&style=none&taskId=u0e3e6d17-c427-4c0c-9c8e-29c39107ed0&title=&width=288)
也可以使用此法
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695871643147-1e8a917d-2963-4638-a5dd-2a43614a85cf.png#averageHue=%23141411&clientId=u53930a31-d1c5-4&from=paste&height=157&id=uf67ca77b&originHeight=216&originWidth=451&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=63639&status=done&style=none&taskId=u4c8cf17d-58be-4103-936e-e1da2fa429e&title=&width=328)
##### lpop/rpop key   将 左/右 最外层的弹出
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695871717124-e807353d-6545-4d24-944c-da577b359250.png#averageHue=%23141511&clientId=u53930a31-d1c5-4&from=paste&height=319&id=u94932a04&originHeight=439&originWidth=416&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=145528&status=done&style=none&taskId=u548e6a7e-42d5-4169-b617-bef80c4c3cd&title=&width=302.54545454545456)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695871737719-d7224703-dfbb-4635-be23-fd7f0c7ed396.png#averageHue=%23141611&clientId=u53930a31-d1c5-4&from=paste&height=176&id=u38f1bf4f&originHeight=242&originWidth=403&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=86314&status=done&style=none&taskId=uc1a396fa-c5a7-49b7-af4a-ebd43d2f182&title=&width=293.09090909090907)

##### rpooplpush  ki  kii
从ki的右边进行一次弹栈将弹出的元素加到kii的左边(进行push操作)
若填写的key相同则会
将key的右边的元素压栈到左边
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695872062022-18590160-cdf5-40f5-8646-d449d96bc102.png#averageHue=%23151612&clientId=u53930a31-d1c5-4&from=paste&height=178&id=uee1a0c4b&originHeight=245&originWidth=385&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=89732&status=done&style=none&taskId=uc4ab7aa7-43f6-4b91-a5c5-df6d581e86a&title=&width=280)
##### lindex key 下标
根据下表来取key中的对应的value
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695872132665-54dd3936-8225-4f66-a098-d62d6f81f3c6.png#averageHue=%23131511&clientId=u53930a31-d1c5-4&from=paste&height=209&id=u77b0f2e1&originHeight=287&originWidth=397&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=98652&status=done&style=none&taskId=u55a578c5-bf91-4c92-87b0-6ebf1e5fa73&title=&width=288.72727272727275)
##### llen key 显示此key的长度
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695872218227-e2f16c8a-9b24-417a-a01b-c930ba9798ac.png#averageHue=%23161913&clientId=u53930a31-d1c5-4&from=paste&height=80&id=u8269f371&originHeight=110&originWidth=324&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=40939&status=done&style=none&taskId=u2269181e-5bfb-4a37-af99-e5368480865&title=&width=235.63636363636363)
##### linsert key before/after  旧value 要加啥
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695872286710-a671ad92-e390-4c21-bc96-53d50a54cb40.png#averageHue=%23141511&clientId=u53930a31-d1c5-4&from=paste&height=226&id=udfe6f6e4&originHeight=311&originWidth=494&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=109675&status=done&style=none&taskId=u0d80ef05-ff78-40d9-9317-afaa104195d&title=&width=359.27272727272725)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695872356416-b02ef2f0-e195-4fbd-b566-1e01ef53cb43.png#averageHue=%23141511&clientId=u53930a31-d1c5-4&from=paste&height=218&id=u0583b90f&originHeight=300&originWidth=509&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=123228&status=done&style=none&taskId=u53e17736-a306-4f9d-83a4-63b387ebf1f&title=&width=370.1818181818182)
##### lrem key  删几个  删啥
删除ks中的十个k2,删除了几个,就返回几
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695872407369-e9f4c0fa-7910-42df-a7f2-5c4b157de2ae.png#averageHue=%23141512&clientId=u53930a31-d1c5-4&from=paste&height=102&id=ud0856158&originHeight=140&originWidth=423&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=45669&status=done&style=none&taskId=u14e5694d-ef1c-4291-b377-426aafcfc1d&title=&width=307.6363636363636)
删除时是从左往右进行删除
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695872489211-58e45897-ad9e-47e8-ab56-cadbe0743607.png#averageHue=%23141511&clientId=u53930a31-d1c5-4&from=paste&height=341&id=u2470a2e5&originHeight=469&originWidth=464&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=170194&status=done&style=none&taskId=uaa005b49-5a6e-4ebf-ae47-1bdc5697247&title=&width=337.45454545454544)
##### lset key 下表 替换值
会将指定key下的指定下标的内容进行替换
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695872618020-5b88d4e5-ae53-4306-85f2-fdc87f95ffb6.png#averageHue=%23141411&clientId=u53930a31-d1c5-4&from=paste&height=392&id=ubabcfc92&originHeight=539&originWidth=456&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=164387&status=done&style=none&taskId=u8e588a77-b73d-4900-bd40-1b54a5ba9ee&title=&width=331.6363636363636)
#### set类型(无序且不可重复)
切库
##### 总结:
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695882481090-2fe5e8c9-3021-44ca-8ffe-1e26b9e14c98.png#averageHue=%23f3f3ee&clientId=u53930a31-d1c5-4&from=paste&height=425&id=u74ce0c71&originHeight=584&originWidth=1167&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=473449&status=done&style=none&taskId=u4db9dd2b-4eba-4b78-be79-3826003d739&title=&width=848.7272727272727)
##### sadd names  values~~~
为names中增加一些value
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695873175497-9923c794-d1b4-4fef-a124-1e5b83359e3e.png#averageHue=%23151712&clientId=u53930a31-d1c5-4&from=paste&height=159&id=u4df63499&originHeight=219&originWidth=557&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=126330&status=done&style=none&taskId=u73c81492-bc4b-47f4-845b-0deaacf7a26&title=&width=405.09090909090907)
可以向key中重复进行增加,若有重复自动去重复
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695873274060-3991b104-f54c-4caa-89df-d30be2f98bb0.png#averageHue=%23151612&clientId=u53930a31-d1c5-4&from=paste&height=222&id=u6bd1821d&originHeight=305&originWidth=494&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=149779&status=done&style=none&taskId=ua19b7c6c-54de-49ef-9311-7349b26e214&title=&width=359.27272727272725)
##### sismember key value 判断key中有无value
若有返回1,若没有则返回0
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695873408133-ffddc13e-d249-48b2-b609-d3ab2f4191cd.png#averageHue=%23171a14&clientId=u53930a31-d1c5-4&from=paste&height=164&id=ue8347452&originHeight=225&originWidth=486&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=149183&status=done&style=none&taskId=u96e868ba-98e6-4099-80d9-8fae7a59609&title=&width=353.45454545454544)
##### scard key  查看其中value个数
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695873471179-f43b63c9-601c-4dc5-b6e0-20fe2299ac5e.png#averageHue=%231c2617&clientId=u53930a31-d1c5-4&from=paste&height=59&id=u373a5c9c&originHeight=81&originWidth=406&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=45969&status=done&style=none&taskId=u63aa12dd-8faa-4f8a-a50a-b7279fb2e96&title=&width=295.27272727272725)
##### srem key values~  移除
在指定的key中移除指定的vlaue
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695873587638-2c822127-2748-4881-9810-a2f82dbb5c66.png#averageHue=%23151712&clientId=u53930a31-d1c5-4&from=paste&height=164&id=ub64de21f&originHeight=226&originWidth=451&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=100295&status=done&style=none&taskId=u55fb20a8-a4eb-4e52-99f8-ae86b45ac11&title=&width=328)
##### spop key  从key中随机吐出一个数据
吐出数据后,此数据就会也从key中消失
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695881673099-6e3ab816-31c6-4061-88d6-4eceaa8712fe.png#averageHue=%23151712&clientId=u53930a31-d1c5-4&from=paste&height=151&id=u8d9a0917&originHeight=207&originWidth=421&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=78420&status=done&style=none&taskId=ue4e2e09c-81c7-425c-bd7f-c42bdcfbc91&title=&width=306.1818181818182)
加了数字就是随机吐出几个
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695881713117-f8e96612-bc8e-4d4b-bf8b-b2a3a396f0e2.png#averageHue=%23151612&clientId=u53930a31-d1c5-4&from=paste&height=91&id=u5a3d6ad7&originHeight=125&originWidth=445&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=52348&status=done&style=none&taskId=uf1987394-3b50-405e-80d2-60f98f9bd15&title=&width=323.6363636363636)
##### srandmember key n 
取出n个,不删除key中的
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695881804993-9becc5c9-aeae-4c2f-8bf7-f73d0dfbbb7f.png#averageHue=%23151612&clientId=u53930a31-d1c5-4&from=paste&height=209&id=u0f5d5e83&originHeight=288&originWidth=484&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=126191&status=done&style=none&taskId=u8bfd3cbd-a534-4ba7-b50d-4c93318f996&title=&width=352)
##### smove key1 key2  value  转移
把value从key1中移到key2里
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695881909207-c37454e0-7f75-4779-a773-a24fb1b224a9.png#averageHue=%23151612&clientId=u53930a31-d1c5-4&from=paste&height=257&id=ubd09128f&originHeight=353&originWidth=617&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=156636&status=done&style=none&taskId=uf37ac8b5-691a-4ea3-9e1d-6f8c9b4ab33&title=&width=448.72727272727275)

##### sinter 集合一 集合二  交集
两个集合都有的
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695882064167-da2c7166-d95b-4943-a985-aed3b872902e.png#averageHue=%231a1b15&clientId=u53930a31-d1c5-4&from=paste&height=35&id=ube8af5ab&originHeight=48&originWidth=484&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=26458&status=done&style=none&taskId=u3ea3a8b9-af1b-421c-944d-f2cc14d5e0c&title=&width=352)
##### sunion 集合一 集合二 并集
两个集合全部的
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695882085383-83a3de55-a3cc-4af5-9be4-6ca0dcd87090.png#averageHue=%23151612&clientId=u53930a31-d1c5-4&from=paste&height=150&id=uea5c3604&originHeight=206&originWidth=442&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=71645&status=done&style=none&taskId=u4387e9f7-d3bd-42ed-a457-1b191eacf8d&title=&width=321.45454545454544)
##### sdiff 集合一 集合二 差集
集合一中有而集合二中没有的
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695882112703-305338cf-292b-43fc-a73d-65f1cec33fbd.png#averageHue=%23151712&clientId=u53930a31-d1c5-4&from=paste&height=95&id=uc28edf99&originHeight=131&originWidth=455&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=63915&status=done&style=none&taskId=ua98bc6c3-cfca-4383-b1aa-59717c9482c&title=&width=330.90909090909093)

#### Redis 哈希 (hash)-->存放键值对的集合
##### 总结
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695882551425-57ba8680-544f-49bd-9afa-68306778eefb.png#averageHue=%23f3f3ee&clientId=u53930a31-d1c5-4&from=paste&height=249&id=u3c7b66cf&originHeight=342&originWidth=1039&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=266655&status=done&style=none&taskId=uf3242bb8-37b9-458d-a71e-58864ab9152&title=&width=755.6363636363636)

##### hset key field value & hget key1 field
给key集合的filed键赋值value
从key1集合field中取出value
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695882722338-04a268eb-dd9b-4b65-83aa-ba6f48b2797d.png#averageHue=%23151613&clientId=u53930a31-d1c5-4&from=paste&height=220&id=ue8d528dc&originHeight=302&originWidth=640&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=177045&status=done&style=none&taskId=u66d014d2-40b9-4e7d-8ab1-cea6d768341&title=&width=465.45454545454544)
##### hekys key 取出所有的key(field)值
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695882758641-56e9c27d-a34f-4973-83f8-092590fc029f.png#averageHue=%23181a13&clientId=u53930a31-d1c5-4&from=paste&height=79&id=ua3a4dd90&originHeight=109&originWidth=348&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=50210&status=done&style=none&taskId=ub60fe27f-7dcf-48f0-90dd-e4259b3fde7&title=&width=253.0909090909091)
##### hvals key 取出所有的value值
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695882812759-9a056cc7-b410-479c-a34b-d92200d35a8d.png#averageHue=%23191a14&clientId=u53930a31-d1c5-4&from=paste&height=139&id=u5088ff5f&originHeight=191&originWidth=365&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=79911&status=done&style=none&taskId=uc2dcba28-f975-4da9-8f5b-6b68d3bc7a6&title=&width=265.45454545454544)
##### hexists key field 查看是否存在此field
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695883043959-22a5def9-687e-45d0-a8b4-febdc3577d0c.png#averageHue=%23161913&clientId=u53930a31-d1c5-4&from=paste&height=143&id=u916cbd72&originHeight=196&originWidth=434&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=104303&status=done&style=none&taskId=uc6bef93c-7b60-4872-8de6-f63dd96f074&title=&width=315.6363636363636)
##### hincrby  key 属性(必须是数字)
自增
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695883110640-499c71d1-f82d-4fe3-bb7a-5453a1dc3bef.png#averageHue=%23161912&clientId=u53930a31-d1c5-4&from=paste&height=39&id=u15794a21&originHeight=54&originWidth=416&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=38124&status=done&style=none&taskId=u10ef07e9-442a-4703-81dc-e0c0f0af45c&title=&width=302.54545454545456)
#####  hsetnx key field value 
只新增不修改
如果是hset key field value 若field存在时是会进行修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695883236605-d22696a1-8cce-4e96-a877-ff7ac74a5eef.png#averageHue=%23151812&clientId=u53930a31-d1c5-4&from=paste&height=172&id=u0a8e1a37&originHeight=237&originWidth=464&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=152199&status=done&style=none&taskId=u54c57c50-e0d0-4846-8011-d590797adf7&title=&width=337.45454545454544)
#### Redis 有序集合Zset
与普通集合set相似.但是有序集合每个成员都管来奶了一个分数来进行集合中成员的排序
##### zadd key 分数1 value1  分数2 value2~ 添加
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695883543107-89790831-80e0-4678-9102-6de40aa18c29.png#averageHue=%23141512&clientId=u53930a31-d1c5-4&from=paste&height=215&id=u512d845d&originHeight=296&originWidth=614&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=146111&status=done&style=none&taskId=u36d699a6-647f-4781-808f-e56e5590d85&title=&width=446.54545454545456)
##### zrange key 起始位置 结束位置 withscores
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695883760756-ab282843-1a3c-43a7-a5ff-971f73916e20.png#averageHue=%23141511&clientId=u53930a31-d1c5-4&from=paste&height=322&id=uf45d88e9&originHeight=443&originWidth=627&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=249753&status=done&style=none&taskId=u9aa7f338-a2f2-4ee7-b88f-c7a73213808&title=&width=456)
默认从小到大排序,若想从大到小使用zervrange
##### zrevrange key 起始  结束  
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695883837794-8acadf2c-b7d7-40e7-81fd-3e6423123b93.png#averageHue=%23141411&clientId=u53930a31-d1c5-4&from=paste&height=153&id=u6ab59180&originHeight=210&originWidth=600&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=79831&status=done&style=none&taskId=u9286f334-f2b5-4da1-a594-9ea7ec095f7&title=&width=436.3636363636364)
##### zrangebyscore key 分数一  分数二
会取出分数一和分数二之间分数的value
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695883911425-37873a4e-d1ca-43ab-ab2a-8e6daf06a5f0.png#averageHue=%23161612&clientId=u53930a31-d1c5-4&from=paste&height=276&id=ua4daf2e1&originHeight=379&originWidth=608&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=180588&status=done&style=none&taskId=u315a04c5-4986-4237-94a9-15f6ec88ac0&title=&width=442.1818181818182)
反转数字  zrevrangebyscore  key 分数二 分数一
会将其间的结果按照从大到小的顺序进行一次排列显示
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695884025228-35a09f63-5ed8-4375-8983-9ff0e2519be5.png#averageHue=%23161713&clientId=u53930a31-d1c5-4&from=paste&height=191&id=u6753863c&originHeight=262&originWidth=649&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=125554&status=done&style=none&taskId=u085a5f3c-63b1-4101-9d7c-0619eaa66ce&title=&width=472)
##### zincrby key 数字 某value
为key某value的分数进行自增,自增的大小为'数字'
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695885134796-58061592-cc04-4b69-8faa-af9ed6856bb4.png#averageHue=%23151612&clientId=u53930a31-d1c5-4&from=paste&height=168&id=u4b4429ec&originHeight=231&originWidth=510&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=104139&status=done&style=none&taskId=u3e466670-0727-4b09-b31f-b1034160828&title=&width=370.90909090909093)
##### zcount key 分数一 分数二
对符合分数区间的value进行计数
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695885225938-fc8e6d02-e363-49e6-aa39-b35fb6c9f7f5.png#averageHue=%23171813&clientId=u53930a31-d1c5-4&from=paste&height=73&id=u9af19909&originHeight=101&originWidth=506&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=62862&status=done&style=none&taskId=u375588b0-cf52-455a-9678-aaf16d99e3f&title=&width=368)
##### zrank key value 返回排名
返回某该value在key中的排名(根据分数大小进行的排名)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695885357820-21968a6c-9f9f-4242-a585-57bf68465451.png#averageHue=%23151813&clientId=u53930a31-d1c5-4&from=paste&height=151&id=u08a5ff93&originHeight=207&originWidth=462&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=110309&status=done&style=none&taskId=u604e347d-d3f5-4cc8-b253-2e6bf0dc036&title=&width=336)
### Jedis操作redis数据库
#### jedis(java redis 融合使用)前置配置
取消本机保护
注释 bind 127.0.0.1
protected-mode的值设置为no
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695885672299-be6393ac-086c-45e3-a0f3-c5e883d8c284.png#averageHue=%231a1c18&clientId=u53930a31-d1c5-4&from=paste&height=129&id=u4d9a48a3&originHeight=178&originWidth=878&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=172691&status=done&style=none&taskId=u4e54d75d-66fd-4862-b828-adf0d9705d8&title=&width=638.5454545454545)
#### jedis操作
##### 1.新建maven模块,导入jar包
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695885810477-16af227d-67f2-4614-935c-30f50560c32b.png#averageHue=%23f2f2ec&clientId=u53930a31-d1c5-4&from=paste&height=245&id=uf6a6a07e&originHeight=337&originWidth=842&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=196413&status=done&style=none&taskId=u53c424b0-5819-4c2d-931a-6890158b3c4&title=&width=612.3636363636364)
其中jedis的jar包为我们提供jedis类
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695885865874-b775b6d9-cbbc-49a3-a976-c30f494608f0.png#averageHue=%2389c6f2&clientId=u53930a31-d1c5-4&from=paste&height=124&id=u69e4d564&originHeight=171&originWidth=451&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=108605&status=done&style=none&taskId=ub8a3ac09-02da-4625-8e7e-4e5ef1fef2b&title=&width=328)
##### 2.测试连接
在测试类中new出jedis之后还需要指定端口号和需要取连接的ip
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695885932667-85c83434-2404-4329-9d42-2184a502b957.png#averageHue=%23f8f8f2&clientId=u53930a31-d1c5-4&from=paste&height=169&id=u86c10b0f&originHeight=232&originWidth=808&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=69063&status=done&style=none&taskId=ue28f0868-e5e2-4f0b-9476-906345cf106&title=&width=587.6363636363636)
测试连接是否成功
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695885983252-b060389f-8ca6-4fca-bba2-bff10a129034.png#averageHue=%23f8f8f0&clientId=u53930a31-d1c5-4&from=paste&height=143&id=u1f930121&originHeight=197&originWidth=697&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=102389&status=done&style=none&taskId=u70bc0768-07e9-4079-96cc-b6fd289221b&title=&width=506.90909090909093)
连接成功
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695886020017-74617771-1404-44e4-8dff-e865e61d0574.png#averageHue=%23f1f2ec&clientId=u53930a31-d1c5-4&from=paste&height=98&id=udd33ea38&originHeight=135&originWidth=496&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=60061&status=done&style=none&taskId=ufb4256f6-0742-4712-8459-f4de35d5c65&title=&width=360.72727272727275)
最后记得将jedis关掉---->jedis.close();
##### 3.操作
在测试类中
首先写new jedis后填写端口号和连接地址

jedis.ttl("k1")是查看k1的剩余有效时间,显示的是-1,表示k1永久有效
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695886405085-9b6dadc5-aae6-43af-9a7a-f1771bdab195.png#averageHue=%23f7f8f2&clientId=u53930a31-d1c5-4&from=paste&height=400&id=u03b978e1&originHeight=550&originWidth=770&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=410977&status=done&style=none&taskId=u03ad2a98-c61c-4ee5-bc64-93aee8a8b59&title=&width=560)
写jedis的关闭

结果:
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695886585640-507ca2db-49c2-45ec-bd3a-9c41af0ede25.png#averageHue=%23f8f8f4&clientId=ud3ed83cb-404f-4&from=paste&height=156&id=u7445a17c&originHeight=214&originWidth=703&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=100992&status=done&style=none&taskId=u7e50a3bf-2093-4b8b-9081-1b3dec946d8&title=&width=511.27272727272725)


#### Spring整合redis
##### 1.创建工程导依赖
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695886938190-63633da1-e2e8-45dd-b57f-112c8d018cfd.png#averageHue=%23f2f2ed&clientId=ud3ed83cb-404f-4&from=paste&height=449&id=ud39c15ab&originHeight=618&originWidth=779&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=347357&status=done&style=none&taskId=u940fdcaf-a655-4178-9a26-2cacc351b54&title=&width=566.5454545454545)
##### 2.创建配置文件
写主机名和端口号,保证连接
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695887264311-2f516978-c9b2-46fd-a61c-bae3558465ec.png#averageHue=%23f3f4ee&clientId=ud3ed83cb-404f-4&from=paste&height=287&id=uedced0af&originHeight=394&originWidth=445&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=231099&status=done&style=none&taskId=ue2bd84e2-4e4f-4dbe-8e9b-6229f0e286a&title=&width=323.6363636363636)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695887650362-44e62a9b-f2d7-4df3-92a0-645e1b1686f1.png#averageHue=%23f7f7f0&clientId=ud3ed83cb-404f-4&from=paste&height=102&id=ud7b51eaa&originHeight=140&originWidth=371&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=35661&status=done&style=none&taskId=ud06622d8-24d4-45e9-accd-072aca2fe87&title=&width=269.8181818181818)
##### 3.创建启动类
springbooapplication注解标记启动类
##### 4.序列化定制
注意 序列化定制是写在配置文件中的
转化为json形式虽然没有一堆符号字母,但也会有   /* 数据 */
将泛型更改为string的话就不会出现奇怪的符号,数据就是数据的格式
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696320034950-94c30f57-43d6-4423-934c-3d2a74d1320e.png#averageHue=%231a1913&clientId=u321dbba4-2e83-4&from=paste&height=37&id=ua11fc2df&originHeight=51&originWidth=235&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=13456&status=done&style=none&taskId=u8e789397-7b2c-48a7-b5a2-78a7b857bfd&title=&width=170.9090909090909)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695887490295-16c13a32-bd89-4a6d-8c2a-ecc07d882e60.png#averageHue=%23f2f1ec&clientId=ud3ed83cb-404f-4&from=paste&height=333&id=u155d16d8&originHeight=458&originWidth=1062&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=325142&status=done&style=none&taskId=u8832d27d-c4a9-49d7-bc2a-ee62c2438c4&title=&width=772.3636363636364)
##### 5.编写测试方法
springboot与单元测试进行整合
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695887828152-b9542233-2b78-43c1-bdfe-6ca359a7b382.png#averageHue=%23f6f6ed&clientId=ud3ed83cb-404f-4&from=paste&height=151&id=ufc33548e&originHeight=207&originWidth=507&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=77037&status=done&style=none&taskId=ufc3ec176-66c3-4078-b77c-dbcd2c897e5&title=&width=368.72727272727275)
我们需要一个redistemplate对象
redistemplate有自带的一些方法用来操作redis
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695888085547-dd06fdd4-57cd-418e-9a84-4811f04ea8b4.png#averageHue=%23f0f0eb&clientId=ud3ed83cb-404f-4&from=paste&height=267&id=u99501d61&originHeight=367&originWidth=901&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=351209&status=done&style=none&taskId=u872747ae-035a-47bc-af8b-c7e3f93c0b6&title=&width=655.2727272727273)
###### 进行添加和查询
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695888256746-daac269d-9a3a-4537-bc79-431af8bf9d16.png#averageHue=%23f8f7f1&clientId=ud3ed83cb-404f-4&from=paste&height=289&id=u03e4d085&originHeight=398&originWidth=866&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=178716&status=done&style=none&taskId=ud800f6e0-aa0c-4732-b986-10a84822c30&title=&width=629.8181818181819)
结果为:
添加了,但结果如下
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695888276999-41520c05-6976-4fd6-b70e-8757fcef826a.png#averageHue=%23131411&clientId=ud3ed83cb-404f-4&from=paste&height=94&id=u61108433&originHeight=129&originWidth=510&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=56974&status=done&style=none&taskId=ubf095e81-3a3a-4259-a569-21475b686d3&title=&width=370.90909090909093)
查询和返回的k1=null
[由此可得,存入时存储的数据被处理过]
[k1通过手动增加没有经过处理,因此无法正常查询]
但是使用k200,却取到了v200
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695888350638-3fe45240-5b72-45b4-b12f-80fcaae8a782.png#averageHue=%23f5f5ee&clientId=ud3ed83cb-404f-4&from=paste&height=323&id=u6104f74a&originHeight=444&originWidth=1032&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=484641&status=done&style=none&taskId=u845fad2b-2ec1-4867-aaaa-12886a6a2c1&title=&width=750.5454545454545)
因此需要对此处理的过程进行修改
##### 6.处理的配置
[没有此配置不影响操作,但影响阅读性,因此对其修改]
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695888682528-6b63357c-90d4-4154-91a4-b86a87731050.png#averageHue=%23f1f1eb&clientId=ud3ed83cb-404f-4&from=paste&height=292&id=u4f666c6e&originHeight=401&originWidth=1057&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=275939&status=done&style=none&taskId=u731a37c2-12c8-4d17-acf2-0d35dfae92e&title=&width=768.7272727272727)
随后重新修改测试类进行测试
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695889278841-cf415414-512b-44c3-9471-9484251d51ec.png#averageHue=%23f6f6ef&clientId=ud3ed83cb-404f-4&from=paste&height=252&id=ub4995b5c&originHeight=346&originWidth=763&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=197078&status=done&style=none&taskId=ufc70db43-f071-4e3d-ab0a-3fad8940466&title=&width=554.9090909090909)
在redis的linux客户端查看库内数据时增加观感
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1695889296550-05c2665e-7934-4166-a93d-41648846f89d.png#averageHue=%23121310&clientId=ud3ed83cb-404f-4&from=paste&height=76&id=u58ab9ecb&originHeight=104&originWidth=316&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=35182&status=done&style=none&taskId=uc509a534-e974-488a-8296-70919cba9af&title=&width=229.8181818181818)

##### 7.切换成jedis(只是将默认的工具切换为redis)
导入jedis的jar包
需要将他的默认的连接工具排除
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696249256767-9d24c013-b7f8-4d92-a1f5-c0f44af3a27f.png#averageHue=%23f9f9f4&clientId=u27f24fdc-ab56-4&from=paste&height=351&id=uc7fc4776&originHeight=483&originWidth=707&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=256617&status=done&style=none&taskId=u9958bfc7-573e-47cb-ae0d-4d84aec4697&title=&width=514.1818181818181)
在配置文件内设置jedis的信息
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696249324211-b351a578-2fba-4423-b9e6-ea5b59a3a105.png#averageHue=%23f8f8f3&clientId=u27f24fdc-ab56-4&from=paste&height=261&id=uecf68f3a&originHeight=359&originWidth=520&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=108507&status=done&style=none&taskId=uce28fd33-78d8-43ea-ac41-1a94aac0582&title=&width=378.1818181818182)
## Redis配置文件
### 网络配置
#### bind绑定连接ip
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313055078-8b68b307-2746-41c8-abc1-b50f4d8d94a7.png#averageHue=%23e5e5df&clientId=u321dbba4-2e83-4&from=paste&height=311&id=u81b02ebd&originHeight=428&originWidth=897&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=352171&status=done&style=none&taskId=ucdad9d2c-e0a3-4eeb-8ab3-21654c40f53&title=&width=652.3636363636364)
#### 端口号6379
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313108160-04764f3e-4ec4-4f16-ac3a-1a91770a3df0.png#averageHue=%23141512&clientId=u321dbba4-2e83-4&from=paste&height=85&id=ub578836a&originHeight=117&originWidth=460&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=57563&status=done&style=none&taskId=uac643208-13c8-45d6-bf4e-807f6f43e97&title=&width=334.54545454545456)
直接  /port 搜索即可
修改其端口号
#### tcp-backlog 连接队列
数字为连接队列的值(高并发需要调节)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313154315-eadcfd2f-7411-4432-aa3a-85a64cc8b4fb.png#averageHue=%23f2f2ed&clientId=u321dbba4-2e83-4&from=paste&height=250&id=u85a315f7&originHeight=344&originWidth=1069&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=474501&status=done&style=none&taskId=ufe7f615b-8732-406d-b691-81e1649a536&title=&width=777.4545454545455)
#### timeout连接超时
不操作才叫空闲
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313221431-d3180c7e-dc3d-4a49-a59a-fbbbae56e908.png#averageHue=%2310110f&clientId=u321dbba4-2e83-4&from=paste&height=153&id=u600b4f60&originHeight=210&originWidth=578&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=109262&status=done&style=none&taskId=u77ce37bb-f56e-4c37-b605-c7dbcf2f188&title=&width=420.3636363636364)
#### tcp-keepalive心跳检测
类似ping--->pong
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313302094-e8c6859a-c124-4de2-9cd5-7f497d7d3d16.png#averageHue=%23edede7&clientId=u321dbba4-2e83-4&from=paste&height=49&id=u347c39fe&originHeight=67&originWidth=561&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=54284&status=done&style=none&taskId=ubd2d1a02-c07c-4569-8f42-05a7b0accc0&title=&width=408)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313269895-521c4d43-64e0-4aac-a768-e30df27ad2be.png#averageHue=%23111210&clientId=u321dbba4-2e83-4&from=paste&height=121&id=u99f35a13&originHeight=167&originWidth=354&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=88478&status=done&style=none&taskId=u79ff8526-fa4b-4103-91c9-cbec0d6a824&title=&width=257.45454545454544)
### 通用配置
#### 单位
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313317316-1fbbaf16-d199-44ab-8a89-852bed19319e.png#averageHue=%230f110d&clientId=u321dbba4-2e83-4&from=paste&height=189&id=u9111458e&originHeight=260&originWidth=445&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=139629&status=done&style=none&taskId=u6e0e756a-5b51-4301-b7e7-4841c85ea29&title=&width=323.6363636363636)
#### include
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313371131-f323f4f6-e73a-436d-bb1a-c18205c34342.png#averageHue=%230f110d&clientId=u321dbba4-2e83-4&from=paste&height=103&id=u397bd190&originHeight=141&originWidth=548&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=75379&status=done&style=none&taskId=u440e73d3-687c-4714-b6a9-d5e35170f17&title=&width=398.54545454545456)
#### 后台进程
守护进程,后台启动
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313388930-b7eb0173-fc87-4bda-a5f4-c52efaa2515e.png#averageHue=%23f5f4ef&clientId=u321dbba4-2e83-4&from=paste&height=186&id=u1c6bebe5&originHeight=256&originWidth=982&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=235719&status=done&style=none&taskId=ub6662f6c-865c-4eee-8b75-6ce93cb91a2&title=&width=714.1818181818181)
#### pidfile进程ID文件
存放pid文件的位置
一切皆文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313464632-b9acecf5-4df5-40dd-bbb8-b255672ea2c5.png#averageHue=%2310130f&clientId=u321dbba4-2e83-4&from=paste&height=151&id=u2af10f9f&originHeight=208&originWidth=627&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=179249&status=done&style=none&taskId=u277560d6-5202-49e6-82ba-4b6b419d997&title=&width=456)
文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313486973-d63bc644-83bc-4cda-b137-6b95fc8615ba.png#averageHue=%23161812&clientId=u321dbba4-2e83-4&from=paste&height=93&id=udb0c7394&originHeight=128&originWidth=384&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=52726&status=done&style=none&taskId=u976fc6a3-2d9d-4c71-b8da-c4f4bd22770&title=&width=279.27272727272725)
内容(将进程id通过id的形式进行存储)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313519127-8f028e05-30e8-4e0a-a919-7921cdc97c6c.png#averageHue=%23181916&clientId=u321dbba4-2e83-4&from=paste&height=137&id=u495bc4d9&originHeight=189&originWidth=884&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=148351&status=done&style=none&taskId=u2a9cb7b9-5ce8-41e2-8746-18cd96562af&title=&width=642.9090909090909)
#### database16
redis的库,默认有16个
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313565444-f76caae9-53e8-4270-a62a-3629f777c7b2.png#averageHue=%23121210&clientId=u321dbba4-2e83-4&from=paste&height=173&id=uc0070761&originHeight=238&originWidth=438&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=148250&status=done&style=none&taskId=uab52c096-ca09-4652-b295-329f8e16727&title=&width=318.54545454545456)
### SECURITY安全配置
设置密码
#### ![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313675408-cba87b93-9ada-4b38-a09a-0a86bb2b8547.png#averageHue=%23c9c9c5&clientId=u321dbba4-2e83-4&from=paste&height=494&id=u07b0f888&originHeight=679&originWidth=935&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=415300&status=done&style=none&taskId=uf27c8434-4fb3-44af-957e-dab622dc3cd&title=&width=680)临时密码
重启(关闭服务后重新开启)后会消失
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313786332-48a9b6db-0a79-4422-8f09-7bd208b5dc4c.png#averageHue=%23131312&clientId=u321dbba4-2e83-4&from=paste&height=86&id=u9a0b6c2a&originHeight=118&originWidth=345&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=27757&status=done&style=none&taskId=ue96b8c1c-ac8d-4ff7-9c68-14cb1d3dd41&title=&width=250.9090909090909)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313765867-05b6be9a-07ae-4653-9ac5-1f3f841d2d73.png#averageHue=%23161713&clientId=u321dbba4-2e83-4&from=paste&height=229&id=ud2743ed0&originHeight=315&originWidth=651&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=177935&status=done&style=none&taskId=ue6ebc85c-e8ce-41be-81d9-093522998b4&title=&width=473.45454545454544)
#### 配置文件密码(配置文件)
修改redis.config配置文件
vim进入后进行搜索与修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313882995-f02ef4a8-3545-48d9-9774-41ccc77c6cff.png#averageHue=%23151512&clientId=u321dbba4-2e83-4&from=paste&height=107&id=u9b91bbc3&originHeight=147&originWidth=419&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=84584&status=done&style=none&taskId=u9e059447-a716-46c2-beea-12d2eebc5a5&title=&width=304.72727272727275)
还需要进行一次认证
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696313914094-6a692e1b-6207-42f6-ad21-0ec3ff31a42e.png#averageHue=%23171814&clientId=u321dbba4-2e83-4&from=paste&height=84&id=ufdc570e0&originHeight=116&originWidth=572&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=67344&status=done&style=none&taskId=u20d7b188-5f2e-472b-8f30-593d3beaebe&title=&width=416)
还需要auth进行抛出密码进行认证
密码   admin
通过jedis进行连接也需要auth进行抛出
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696314036254-88a22a6c-c6e7-46ad-9d4e-ca2e69d4c528.png#averageHue=%23f4f4ee&clientId=u321dbba4-2e83-4&from=paste&height=180&id=u721dde07&originHeight=247&originWidth=650&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=115332&status=done&style=none&taskId=u30b7bb88-541d-4161-9adf-bf8ad13dd7e&title=&width=472.72727272727275)
#### LIMIT限制
#### maxclients客户端最大连接数
默认为10000个客户端,达到限制后会拒绝新的连接请求.并发出回应
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696314122600-edfcf0a5-b7b0-4d66-9e8e-e5d8bb30d1f0.png#averageHue=%23f7f7f2&clientId=u321dbba4-2e83-4&from=paste&height=47&id=u4c7d4b18&originHeight=65&originWidth=278&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=17813&status=done&style=none&taskId=uca2db1e5-bc6b-40e6-b710-983003897b6&title=&width=202.1818181818182)
#### maxmemory最大占用内存
必须设置!!--->内存满后服务器会宕机

若达到设置的最大占用内容,redis会移除内部数据,根据maxmemory-policy的置换策略(如下)
#### maxmemory-policy置换策略
volatile-lru 使用lru算法移除key,只对设置了过期时间的键
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696314376728-d5935099-0100-4de9-bd68-6ca743bd2d39.png#averageHue=%23f4f4ee&clientId=u321dbba4-2e83-4&from=paste&height=174&id=u3729971d&originHeight=239&originWidth=707&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=218580&status=done&style=none&taskId=uf3c6d964-77a0-41d8-9a4d-d787c159828&title=&width=514.1818181818181)
lru算法需要设置样本数量,通过maxmemory-samples
#### maxmemory-samples
设置样本数量
lru和小ttl算法都是估算值算法
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696314528690-69485080-6cbc-4d7f-97a0-9035eb13a592.png#averageHue=%23f7f7f2&clientId=u321dbba4-2e83-4&from=paste&height=257&id=u88f1ed28&originHeight=353&originWidth=1140&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=329261&status=done&style=none&taskId=ufdb12183-3621-41cc-b872-7c181d24d76&title=&width=829.0909090909091)
## Redis事务锁机制和案例
### 事务
定义:  是单独的隔离操作,所有命令都会序列化,按顺序执行.
作用: 串联多个命令防止别的命令插队.
控制命令如下
#### multi
写在命令之前之前
multi -->开始组队  (将 命令 加到 队列 中)
加入到队列中去准备执行
#### exec
执行队列中的命令
#### discard
取消组队
#### 案例:
组件队列:
multi组队命令
exec执行队列的命令
discard取消队列
两种错误情况
组队期间存在语法错误
队列都不执行
运行期间存在运行错误
只有错误的命令是失败的,其他全部都正常执行
##### 未组队状况
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696315798588-f3ac496b-a517-4a3f-90e5-79acea7716ea.png#averageHue=%23151612&clientId=u321dbba4-2e83-4&from=paste&height=194&id=u3b23d16b&originHeight=267&originWidth=379&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=95868&status=done&style=none&taskId=u00dd9a61-edf1-4789-bb3e-5b3f8b25c87&title=&width=275.6363636363636)
##### 组队状况
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696315873018-771ec478-91af-4151-b376-7afb1be1f339.png#averageHue=%23161813&clientId=u321dbba4-2e83-4&from=paste&height=167&id=u64718a75&originHeight=229&originWidth=395&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=93987&status=done&style=none&taskId=u3d2b6cdb-ea2f-4f0c-a792-5e06390f647&title=&width=287.27272727272725)
开始队列与执行队列
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696315904376-4b84d257-df26-4bb2-b461-bbe8971bc658.png#averageHue=%23131511&clientId=u321dbba4-2e83-4&from=paste&height=236&id=u5f0ebc64&originHeight=325&originWidth=391&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=120504&status=done&style=none&taskId=u497cba9d-b4dc-4a91-b9ee-e10b0194c59&title=&width=284.3636363636364)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696315977387-d550c4bc-446d-4c6f-9639-7adea5b21d80.png#averageHue=%23141612&clientId=u321dbba4-2e83-4&from=paste&height=167&id=u1a2810da&originHeight=229&originWidth=401&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=93521&status=done&style=none&taskId=ucffda335-6821-4204-9066-c481d02be15&title=&width=291.6363636363636)
队列中出现语法错误时
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696316084482-5bd3313e-ab36-48ad-8d94-44ede6419ac4.png#averageHue=%23141512&clientId=u321dbba4-2e83-4&from=paste&height=260&id=u480d9959&originHeight=358&originWidth=787&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=208058&status=done&style=none&taskId=uc3e71836-ede4-40aa-a8cb-85051ca54fe&title=&width=572.3636363636364)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696316190842-e717c2ac-d35c-48f4-8844-ce683bc8c099.png#averageHue=%23131411&clientId=u321dbba4-2e83-4&from=paste&height=324&id=u371a9bee&originHeight=445&originWidth=706&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=201049&status=done&style=none&taskId=u748c88e8-8956-4d2a-bda1-b3a4a20fdce&title=&width=513.4545454545455)
### 锁
#### 锁介绍
##### 悲观锁
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696317726964-1378a5cc-ae27-46f2-b7fe-0ad69d8db10f.png#averageHue=%23eaebe5&clientId=u321dbba4-2e83-4&from=paste&height=43&id=u0b42a271&originHeight=59&originWidth=1115&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=129522&status=done&style=none&taskId=ue128e61b-52d1-4122-87d7-3924de11e1a&title=&width=810.9090909090909)
mysql.orcal
每次拿数据时都会上锁,防止数据被拿走,只等它执行完毕之后才放开数据允许别人去拿这个数据,安全但效率低 
##### 乐观锁
redis
不上锁但是cheak(检查-->检查版本) and set(设置-->设置版本),只查询不修改的状况之下效率极高,适合少改多查的状况
只有发生了修改,数据被更新的状况之下才会重新设置新的版本号
若发生了**修改**则版本也会发生改变,在另一个并发程序执行时会检查版本是否发生变动,若发生变动则不会执行,_即使条件满足,只要版本号发生变化,其也不会执行_
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696317262623-f921b6c2-4ea1-4554-9d0c-d8e6217d0bb6.png#averageHue=%23f9ead8&clientId=u321dbba4-2e83-4&from=paste&height=193&id=ude5826c3&originHeight=265&originWidth=740&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=151791&status=done&style=none&taskId=u1913ab2c-8143-49e3-8b31-33dd5115662&title=&width=538.1818181818181)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696317595971-6a93a9d7-7b33-444f-8099-fbf079384de7.png#averageHue=%23f9ebd9&clientId=u321dbba4-2e83-4&from=paste&height=184&id=u5b1ba841&originHeight=253&originWidth=805&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=156750&status=done&style=none&taskId=ub566e6e4-c9dd-4934-8dfd-50bf38302af&title=&width=585.4545454545455)
#### 监视和取消监视key
watch 就是开启的一个版本检查机制
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696317977581-29290769-0dc7-4f95-bf5e-5f00244c1347.png#averageHue=%23c5c5c0&clientId=u321dbba4-2e83-4&from=paste&height=253&id=u88c6f938&originHeight=348&originWidth=1130&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=300727&status=done&style=none&taskId=u95bb0bbf-d30d-4868-8ef7-34a393c7ab4&title=&width=821.8181818181819)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696318309617-ea53c46f-e868-4fc7-b497-9f9d71da2b2b.png#averageHue=%23131411&clientId=u321dbba4-2e83-4&from=paste&height=222&id=ua642728e&originHeight=305&originWidth=777&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=147412&status=done&style=none&taskId=ubaa7dc66-3ea9-4ee0-9efe-8d504e96065&title=&width=565.0909090909091)
### redis lua脚本
Lua脚本具有原子性,因此其不可被中断
具备原子性,可以将复杂多步的redis操作写为一个脚本,一次性提交给redis执行,检查反复连接redis的次数,
可以大概理解为 将redis的乐观锁机制转变为悲观锁机制
**如何使用的关键在于:redisTemplate里的excute方法**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696321616155-b093ce0f-1da3-4dc8-a87a-3cb13f6fc66f.png#averageHue=%23f9f9f3&clientId=u321dbba4-2e83-4&from=paste&height=135&id=u1cbd7acc&originHeight=186&originWidth=851&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=89550&status=done&style=none&taskId=uaa3d6b16-84af-4e9e-bb72-0be99afc7dd&title=&width=618.9090909090909)

#### 具体操作
##### 1.导入相关jar包
##### 2.创建配置文件
@bean注解就是将对象返回给ioc容器
简单序列化
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696320329823-db289554-bdfd-4ccf-b812-de0baa74fc36.png#averageHue=%23f7f6f0&clientId=u321dbba4-2e83-4&from=paste&height=285&id=uc5f4814a&originHeight=392&originWidth=907&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=323056&status=done&style=none&taskId=u63d88ab7-95dc-4742-a340-039ec7f46f4&title=&width=659.6363636363636)
加载lua脚本,设置返回值类型
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696320596779-c6df7f65-db8d-4823-9064-686d1fb115c4.png#averageHue=%23f8f8f2&clientId=u321dbba4-2e83-4&from=paste&height=151&id=u6e5ec824&originHeight=208&originWidth=763&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=127725&status=done&style=none&taskId=ua7b18a78-710a-481a-87a9-86b69034f85&title=&width=554.9090909090909)
##### 3.创建启动类
##### 4.准备lua脚本
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696319317552-b263911b-3a2f-4820-88f8-65df84e3110c.png#averageHue=%23f6f6eb&clientId=u321dbba4-2e83-4&from=paste&height=161&id=u1fe6ce49&originHeight=222&originWidth=542&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=89549&status=done&style=none&taskId=udee426c1-26ea-4021-a962-aa1cd0e8dde&title=&width=394.1818181818182)
##### 5.准备单元测试
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696319276319-adfac55d-a726-48fe-9a14-ddd22f7ebe6f.png#averageHue=%23f7f8f1&clientId=u321dbba4-2e83-4&from=paste&height=145&id=uf5abb8a8&originHeight=200&originWidth=332&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=48031&status=done&style=none&taskId=u9468728f-d302-46b9-b09f-0fdc3d1dc66&title=&width=241.45454545454547)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696319228455-0a1d4bc0-58e2-4889-a8ea-344c7364736e.png#averageHue=%23f5f5ef&clientId=u321dbba4-2e83-4&from=paste&height=178&id=uf6b97cf7&originHeight=245&originWidth=756&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=160925&status=done&style=none&taskId=ub41063bb-2975-45be-b462-6ea0d2d7b1d&title=&width=549.8181818181819)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696320681499-dee67501-3dd7-4bbb-9198-40084b1bedf1.png#averageHue=%23f8f8f1&clientId=u321dbba4-2e83-4&from=paste&height=222&id=uc54f26b5&originHeight=305&originWidth=584&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=100812&status=done&style=none&taskId=u04b625a3-0e9d-4580-be80-1515df05e79&title=&width=424.72727272727275)
redisTemplate的execute需要传递的有:
rediscript--->通过配置文件进行传递(类路径下的某文件)
list keys-->keys的一个数组(存key值)
Object...parms--->rediscript即lua脚本需要的附加参数
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696320872704-af887ccd-3d5f-4e5a-b464-c4336863fbe2.png#averageHue=%23f9f9f3&clientId=u321dbba4-2e83-4&from=paste&height=287&id=u0068ce32&originHeight=395&originWidth=691&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=119049&status=done&style=none&taskId=u0c77f47a-13ec-4013-9828-cf4924f8929&title=&width=502.54545454545456)
其最终执行后会返回一个布尔值

## 持久化
### 介绍
将数据写到磁盘中io操作
redis的主要功能是高速缓存
redis的持久化的主要目的是数据恢复(数据备份)
而客户机依然操作的是内存,持久化只是为数据上一份保险,防止意外状况发生数据丢失(达到持久化时机才会持久化)
### 类型 
#### rdb(数据存文件)
##### 介绍
默认开启状态
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696400282729-8f416946-67b0-49bf-89d1-5fd2e887767c.png#averageHue=%23f5f5f0&clientId=u543942c5-5d82-4&from=paste&height=47&id=u1bbd132f&originHeight=64&originWidth=1060&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=69216&status=done&style=none&taskId=ue1bf0aaf-7751-4d19-88c0-1950da20dc6&title=&width=770.9090909090909)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696497189697-59c35739-d8c3-4c61-a52b-2afaa3c92aef.png#averageHue=%23171815&clientId=ufa017544-5757-4&from=paste&height=433&id=u0d8a5b27&originHeight=596&originWidth=749&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=510126&status=done&style=none&taskId=ued461835-75a9-4a75-9935-1adc365d017&title=&width=544.7272727272727)
默认会在执行启动命令时读取当前目录下的rdb文件,可以启动redis但是读取不到rdb文件于是数据无法被获取,读取不到.
读取到数据的关键是rdb文件
##### 解决方案(修改redis.config目录下的rdb文件存读目录)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696595012732-cc665e5f-e25d-4120-bdc3-c8830bacc18c.png#averageHue=%2311120f&clientId=u89e7926b-8dc5-4&from=paste&height=160&id=u23a04c37&originHeight=220&originWidth=758&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=179459&status=done&style=none&taskId=u6531383b-3603-4d47-a19c-da8880fc2d7&title=&width=551.2727272727273)
将此处的配置修改(建议修改)
即 固定产生rdb文件的位置
此处配置的目录含义是  启动命令时创建的rdb文件所在的目录以及数据恢复自动读取rdb文件的目录
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696595056669-e54956a1-761d-4704-93ed-02c6452a1edd.png#averageHue=%23f6f6f1&clientId=u89e7926b-8dc5-4&from=paste&height=132&id=ua10f009a&originHeight=182&originWidth=708&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=106681&status=done&style=none&taskId=u6b08b0bf-55d7-4957-b91c-21a2c879a0e&title=&width=514.9090909090909)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696596621754-fd053615-8373-4974-8417-7872bdd91b34.png#averageHue=%2310130f&clientId=u89e7926b-8dc5-4&from=paste&height=135&id=u4facbb94&originHeight=185&originWidth=402&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=118959&status=done&style=none&taskId=uc0b92e14-e4ff-4cc6-8a72-98973fd98d4&title=&width=292.3636363636364)
此处的bdfilename是修改redis缓存文件的文件名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696596840240-88fa6fa0-4cf1-4edd-94ae-40d63d535c0b.png#averageHue=%23141612&clientId=u89e7926b-8dc5-4&from=paste&height=155&id=uf550088c&originHeight=213&originWidth=525&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=125267&status=done&style=none&taskId=u35e3a5fe-1564-4258-90b9-4314fcbe3b1&title=&width=381.8181818181818)
当正常退出的状态下会将其内的文件进行缓存(手动持久化)
##### 自动持久化
修改配置文件 修改的就是进行缓存的时间
可以自己写
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696597061057-9f90600c-6fd8-4225-b9c0-0180e0d46f23.png#averageHue=%23111410&clientId=u89e7926b-8dc5-4&from=paste&height=86&id=u87b283f5&originHeight=118&originWidth=270&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=56918&status=done&style=none&taskId=uf1213d41-58b9-411b-ab8d-147cb48fba6&title=&width=196.36363636363637)
60秒操作10次变化就会自动进行缓存
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696597018831-3f50ecad-1b97-4192-bb12-b0b399588d72.png#averageHue=%23111210&clientId=u89e7926b-8dc5-4&from=paste&height=190&id=u490396a2&originHeight=261&originWidth=829&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=250524&status=done&style=none&taskId=u31328ce3-23b7-4d2b-8cdd-2403ac266c7&title=&width=602.9090909090909)

##### RDB手动执行快照命令
###### save VS bgsave
建议使用bgsave
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696598001757-28cfe271-628d-462c-80eb-45b9be92a482.png#averageHue=%23eeede8&clientId=u89e7926b-8dc5-4&from=paste&height=244&id=ufc002b72&originHeight=335&originWidth=827&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=225204&status=done&style=none&taskId=u600b9b45-1d5c-4ab9-be49-ac807808de4&title=&width=601.4545454545455)

**_flushall(清空所有)--->也会进行持久化_**
##### 其他配置与操作
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696638676735-a641bec5-d6cc-4f99-9794-23bf5d2dbec0.png#averageHue=%23f6f6f1&clientId=u32fdc52e-01e7-4&from=paste&height=201&id=ucd385742&originHeight=276&originWidth=1019&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=255302&status=done&style=none&taskId=ude595529-078c-4faa-a00e-1aee2c6aa02&title=&width=741.0909090909091)
rdb采用了一些压缩机制使其比其余持久化更加节省内存
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696638896671-2a314be0-f548-48c7-b6b6-61a0e4696d67.png#averageHue=%23f7f7f2&clientId=u32fdc52e-01e7-4&from=paste&height=259&id=u85919f5d&originHeight=356&originWidth=1056&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=314398&status=done&style=none&taskId=u4697b429-2342-4d76-b4e4-9e7428df7e8&title=&width=768)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696638920395-cf2555e6-2356-4710-864d-21f5feb3754f.png#averageHue=%23f7f7f2&clientId=u32fdc52e-01e7-4&from=paste&height=203&id=u475312df&originHeight=279&originWidth=1059&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=246678&status=done&style=none&taskId=u6b169dcb-112c-41eb-a8ae-6f14d562496&title=&width=770.1818181818181)
rdb文件的备份
手动(复制--->cp)备份出一个附加了后缀的备份文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696639061824-9c8cf730-e954-477d-b83f-b9b6948f3d2c.png#averageHue=%23161814&clientId=u32fdc52e-01e7-4&from=paste&height=272&id=u0650af70&originHeight=374&originWidth=688&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=387932&status=done&style=none&taskId=u7d46be10-77d2-4885-aac4-52084d9cfeb&title=&width=500.3636363636364)

禁用 ---> save""
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696639187440-c4559d2f-a240-418a-b166-748418d712b2.png#averageHue=%23f6f6f1&clientId=u32fdc52e-01e7-4&from=paste&height=260&id=ueebfd651&originHeight=357&originWidth=764&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=152080&status=done&style=none&taskId=u3ba06ec1-7be5-428e-b92d-40146fd1674&title=&width=555.6363636363636)
##### 总结
流程
需要考虑内存占用问题
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696639562061-6633a896-7cc2-4f5e-9bb9-612fcfd2a110.png#averageHue=%23f4f4ee&clientId=u32fdc52e-01e7-4&from=paste&height=260&id=u7c8211d2&originHeight=357&originWidth=1140&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=513843&status=done&style=none&taskId=u5b700231-74c3-4c9c-a8d2-58383537a9d&title=&width=829.0909090909091)

#### aof(操作数据的命令放文件)
添加与修改的命令(存的是命令)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696639621579-26e3213b-3a12-400a-b43c-8bd4cb7a87f9.png#averageHue=%23f5f5f1&clientId=u32fdc52e-01e7-4&from=paste&height=451&id=ud82178f1&originHeight=620&originWidth=766&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=269041&status=done&style=none&taskId=u48c675c5-0390-4b82-860a-6bde8c2e929&title=&width=557.0909090909091)
默认关闭状态,需要去手动开启
##### 在配置文件中开启AOF
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696639808303-f088bdaf-3c1e-47a3-b4cb-1a7de3a07c76.png#averageHue=%23f7f7f2&clientId=u32fdc52e-01e7-4&from=paste&height=41&id=uc7a2c5b9&originHeight=56&originWidth=250&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=10163&status=done&style=none&taskId=u76fc0fe3-d199-4e2e-ba50-2359832d25f&title=&width=181.8181818181818)
##### 也会使用dir的配置
##### 指定文件名
redis6---->一个文件
redis7---->一个目录(三个文件)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696639962663-0eb71158-1442-4e4e-9dd9-06110f63a973.png#averageHue=%23121210&clientId=u32fdc52e-01e7-4&from=paste&height=124&id=u9ca17c44&originHeight=170&originWidth=817&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=125495&status=done&style=none&taskId=ud704e6c5-0d79-464c-bfbc-369dd7ef57f&title=&width=594.1818181818181)
首先是在incr文件之中进行存储命令,在将rdb文件的内容放入aof目录之下的base.rdb文件之后会对aof的.incr文件进行删除
##### 如果aof和rdb都开启了,恢复数据时会使用
进行验证
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696640404292-5b8a84a9-0b74-4dc9-84a6-8158e059b643.png#averageHue=%23151712&clientId=u32fdc52e-01e7-4&from=paste&height=138&id=u6ce24de0&originHeight=190&originWidth=787&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=226746&status=done&style=none&taskId=ud9c87115-357d-4411-84c1-971f351f8dd&title=&width=572.3636363636364)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696640443163-85e1d665-30d8-4ffe-8c23-964a45d30d1f.png#averageHue=%23151512&clientId=u32fdc52e-01e7-4&from=paste&height=220&id=u7efc3cb6&originHeight=303&originWidth=536&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=141860&status=done&style=none&taskId=u5241890a-7475-49e8-88d5-8c0dfd5cf67&title=&width=389.8181818181818)
证明,当aof和rdb持久化都进行时,使用aof进行数据恢复.因为aof对数据的存储更为全面.
##### 当aof的持久化文件被破坏之后
会直接导致redis无法启动
可以将其删除,就会采用rdb文件作为持久化文件进行数据读取
##### 可以使用修复工具进行尝试修复
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696640809443-10b05866-cb01-4e83-a45e-c6515d8147ec.png#averageHue=%23f8f8f3&clientId=u32fdc52e-01e7-4&from=paste&height=159&id=u3c7b7336&originHeight=218&originWidth=876&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=128582&status=done&style=none&taskId=uba5001cd-ceca-4ee2-af35-2ceb08e78d4&title=&width=637.0909090909091)
首先是进入某目录之下,然后执行修复命令--fix 后跟需要进行修复(恢复)的文件路径
/user/local/bin/redis-check-aof --fix  待修复文件路径
注意最后要跟的是文件路径不是文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696640920779-aa300881-9e8c-4815-9347-dd5340c001fc.png#averageHue=%23151512&clientId=u32fdc52e-01e7-4&from=paste&height=73&id=uace90084&originHeight=100&originWidth=962&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=67649&status=done&style=none&taskId=u8100dcba-d4d1-4c0f-be2a-4b031fce411&title=&width=699.6363636363636)
##### aof的策略
分别是 一直  每秒  永不
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696641135240-add59570-d120-472a-b2c5-15d670f3e214.png#averageHue=%23111210&clientId=u32fdc52e-01e7-4&from=paste&height=104&id=uec1c4cf9&originHeight=143&originWidth=400&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=70394&status=done&style=none&taskId=u40b5fb9b-fce6-47b9-9d13-1c821e5e774&title=&width=290.90909090909093)
##### aof的重写
将命令增量文件的内容删除,将rdb文件写入目录下的指定文件之中
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696641236202-14a683ca-742f-4e5a-af89-0d4d7db7efe8.png#averageHue=%231b1c19&clientId=u32fdc52e-01e7-4&from=paste&height=169&id=u7e63f96a&originHeight=232&originWidth=768&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=198838&status=done&style=none&taskId=uf5c5b3fe-befc-426c-a5e9-8893d163750&title=&width=558.5454545454545)
rdb持久化的存储快照命令是dbsave
使用命令bgrewrite命令来进行aof文件重写
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696641406989-c058e86f-6c95-477e-b994-c829d4dcf5cb.png#averageHue=%23f1f1eb&clientId=u32fdc52e-01e7-4&from=paste&height=89&id=u5af2eb89&originHeight=122&originWidth=871&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=112168&status=done&style=none&taskId=uca66a81c-6679-40f9-bd7b-ec1b019961c&title=&width=633.4545454545455)
重写的时机
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696641855078-931890f4-44f1-4263-9b70-9f258a212055.png#averageHue=%23edede7&clientId=u32fdc52e-01e7-4&from=paste&height=51&id=u1903ffdb&originHeight=70&originWidth=1089&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=114528&status=done&style=none&taskId=ud46fa67a-f680-4c9c-854d-df89bcd4316&title=&width=792)
重写相关配置
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696641916008-214b12ea-3957-4bef-a2fa-3b6df5e137a4.png#averageHue=%23f4f4ef&clientId=u32fdc52e-01e7-4&from=paste&height=105&id=ue6a6bf7c&originHeight=145&originWidth=602&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=109864&status=done&style=none&taskId=u0d96a66e-b73c-4857-a275-e3e1e94e813&title=&width=437.8181818181818)
重写流程
依旧使用写实复制技术fork
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696642059760-bd11468e-615d-415c-8393-908e7d25102a.png#averageHue=%23f5f5ef&clientId=u32fdc52e-01e7-4&from=paste&height=208&id=u5bf2720f&originHeight=286&originWidth=1108&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=329505&status=done&style=none&taskId=u2d95a4c6-efc6-4577-a001-7a0750fbcc5&title=&width=805.8181818181819)
##### 如何选择
根据需要处理的情况来进行选择
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696644415481-9e306b8b-9281-4f39-9ba4-6c637cf16931.png#averageHue=%23f5f5f0&clientId=u32fdc52e-01e7-4&from=paste&height=178&id=u92fe4d1b&originHeight=245&originWidth=555&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=137600&status=done&style=none&taskId=uc48d5df7-1033-4ba8-8d15-96668bb3dad&title=&width=403.6363636363636)
## 主从复制
### 介绍
#### 好处:
##### 读写分离
redis内存的数据是为了对读的场景才去存储的
读写分离,提高性能(主要是提高读的性能)
redis是内存存储(io操作),读的效率高
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696644657916-ae1aba61-641e-4479-9a9d-f3bacccf0341.png#averageHue=%23faf9f5&clientId=u32fdc52e-01e7-4&from=paste&height=423&id=u3f4f8121&originHeight=582&originWidth=1283&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=103422&status=done&style=none&taskId=u68787a2c-ebec-4ebb-9302-f769f4d436a&title=&width=933.0909090909091)
为了避免宕机问题导致数据文件受损,可以采用读写分离的方式来进行
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696645015270-d675cefe-59ec-4968-9936-eec4d61d029c.png#averageHue=%23f9f9f5&clientId=u32fdc52e-01e7-4&from=paste&height=354&id=u6033effc&originHeight=487&originWidth=1206&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=84933&status=done&style=none&taskId=u09845ad3-f64c-423c-aa7b-08ef5326d58&title=&width=877.0909090909091)
来读数据的时候会在从机中进行读取.两个从机的内容与主机完全相同,是主机经过服务器写入之后复制给它的从机的数据
##### 快速容灾(容灾快速恢复)
宕机情况发生时
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696645288073-5b07ddc7-3212-4623-a713-f7489517feca.png#averageHue=%23f7f7f3&clientId=u32fdc52e-01e7-4&from=paste&height=211&id=u9a15f938&originHeight=290&originWidth=443&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=31072&status=done&style=none&taskId=u46b6229d-534a-4f31-9288-adf4484a9bc&title=&width=322.1818181818182)
从机宕机影响不是很大
主机宕机选从机中的一个去当主机
压力分担
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696645336354-32254a90-b7e6-4da8-b1e7-099eeaa1dc64.png#averageHue=%23fafaf6&clientId=u32fdc52e-01e7-4&from=paste&height=231&id=ub2635546&originHeight=318&originWidth=503&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=146713&status=done&style=none&taskId=uf625f567-99f3-4837-9cb8-22c754ab324&title=&width=365.8181818181818)
#### 具体操作:
##### 准备
一个机器使用多个redis来进行 
使用include来进行配置文件的复制和修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696645785528-4a76c456-0017-44c0-86f2-119d68f48e72.png#averageHue=%23f7f6f1&clientId=u32fdc52e-01e7-4&from=paste&height=244&id=u66eacdf2&originHeight=335&originWidth=365&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=102932&status=done&style=none&taskId=u31e45072-a50a-40f9-9939-eca54fd3bff&title=&width=265.45454545454544)
关闭本机保护
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696645858114-14c74b26-2f8c-47de-8793-01c43ef23124.png#averageHue=%23131612&clientId=u32fdc52e-01e7-4&from=paste&height=73&id=u9eef65b1&originHeight=101&originWidth=268&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=42725&status=done&style=none&taskId=u3e47e022-fdee-43eb-80d3-b7ad6d71375&title=&width=194.9090909090909)
设置pid存储文件名称
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696645949981-99ca9e9b-9d7c-4018-b202-7f3af2d886ed.png#averageHue=%23131612&clientId=u32fdc52e-01e7-4&from=paste&height=70&id=uee461235&originHeight=96&originWidth=420&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=70319&status=done&style=none&taskId=u3a19ee21-cc9d-481a-9581-5ab607f7c1f&title=&width=305.45454545454544)
设置端口号
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696645978995-1a5e63bc-3076-43c0-abf3-10d3985e33d3.png#averageHue=%2311120f&clientId=u32fdc52e-01e7-4&from=paste&height=80&id=u1e1d7a6e&originHeight=110&originWidth=226&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=34607&status=done&style=none&taskId=uc67d6349-73ae-473f-b7c7-4de924808b0&title=&width=164.36363636363637)
设置rdb文件的名称
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696646000221-e00ad69b-88f1-46a2-af85-955fee5cacb5.png#averageHue=%230e120e&clientId=u32fdc52e-01e7-4&from=paste&height=104&id=ua2fb1010&originHeight=143&originWidth=389&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=82798&status=done&style=none&taskId=uc6711dc3-a630-4302-9652-b96a43ae54d&title=&width=282.90909090909093)
将此步骤在三个reids配置进行修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696646110005-bc4724fd-4483-4349-abd6-dd64f70f3626.png#averageHue=%23252823&clientId=u32fdc52e-01e7-4&from=paste&height=129&id=uc47c8956&originHeight=177&originWidth=348&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=119009&status=done&style=none&taskId=ub1f52da0-e73f-4ea6-9951-4e624294457&title=&width=253.0909090909091)
完成修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696646128524-ef4bbb1f-5811-4029-9751-8dbff8a39504.png#averageHue=%23161614&clientId=u32fdc52e-01e7-4&from=paste&height=89&id=ub49b1186&originHeight=122&originWidth=683&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=72809&status=done&style=none&taskId=uafe6df89-44d9-4e05-bb5a-237362933cb&title=&width=496.72727272727275)
进行全局替换
加/g会进行全部修改,不加就只是每行第一个进行修改
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696646176556-01661b30-61c3-4fd8-8844-96d765d178f4.png#averageHue=%23141412&clientId=u32fdc52e-01e7-4&from=paste&height=56&id=u03a3dad9&originHeight=77&originWidth=222&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=12159&status=done&style=none&taskId=u6f71bf26-3642-4c96-bcc8-7f845e20d70&title=&width=161.45454545454547)
##### 启动并连接
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696646410729-37bcb8c9-096a-4874-a763-ac45af63ebd4.png#averageHue=%23191b16&clientId=u32fdc52e-01e7-4&from=paste&height=180&id=ua7c836d9&originHeight=248&originWidth=827&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=248003&status=done&style=none&taskId=u1b3a57e6-0863-4dae-9442-29ac7a743de&title=&width=601.4545454545455)
连接时使用 -p 来标注端口号来进行连接不同的redis服务
### 一主二仆(使用较多)
**_特点:_**
**_主机能写能读_**
**_从机只能读不能写_**
**_缺点是:当读取压力大时就需要增加很多从机,而增加的从机又会导致主机的复制压力增大_**
**_解决方案(薪火相传-->压力分摊)_**
**_缺点:无法越级管理,宕机后风险较大_**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696647709876-5dcfb5d6-8781-4069-8659-659ee67ee34e.png#averageHue=%23f6f6f0&clientId=u32fdc52e-01e7-4&from=paste&height=175&id=ue821bbef&originHeight=240&originWidth=1047&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=248125&status=done&style=none&taskId=ub0bc1e13-d9bb-494c-a047-855f8e25851&title=&width=761.4545454545455)
#### 配从不配主:
使用info replication去查看主机之间的关系
原理 :   配从不配主
是让从机主动去找主机
使用 slaveof 192.168.6.100(即主机ip) 6379(即主机端口号)
配置
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696646935590-cc380f54-1592-43b2-a0c6-1ca18e89072c.png#averageHue=%23181a16&clientId=u32fdc52e-01e7-4&from=paste&height=172&id=u7c3ac59a&originHeight=237&originWidth=886&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=256976&status=done&style=none&taskId=u11bc4827-371f-469d-88a3-fbc63dbf9e9&title=&width=644.3636363636364)
主机
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696646962877-8952b541-ae8f-4165-85c5-9dee3bcdce33.png#averageHue=%23151613&clientId=u32fdc52e-01e7-4&from=paste&height=246&id=ucb9c3ef2&originHeight=338&originWidth=393&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=208926&status=done&style=none&taskId=uaa36bd0f-db15-4ca4-889c-c0b58acf246&title=&width=285.8181818181818)
从机
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696646973681-a272a3af-8df4-4363-80f8-c8aa24c6d60f.png#averageHue=%23161614&clientId=u32fdc52e-01e7-4&from=paste&height=274&id=ud9636cad&originHeight=377&originWidth=501&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=244175&status=done&style=none&taskId=ud8ac4d09-cc59-4204-8ea4-6cb1a2fce55&title=&width=364.3636363636364)
#### 如果出现意外状况:
##### 1.从机宕机
除了掉线的从机之外,其余依旧保持主机和从机的关系;正常对外提供服务.
当掉线的从机返回时,不会自动归队,还需要重新进行一次认主 (slaveof 主机ip 主机端口)
认主后从机会立刻将主机中的所有数据都拿到自己的库中,保持数据的同步
##### 2.主机宕机
从机依旧保持自己的角色,只能读不能写;
会去等待主机的上线
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696647527064-91ce79f7-2553-4fb6-af57-9c4dfe6887af.png#averageHue=%23151713&clientId=u32fdc52e-01e7-4&from=paste&height=167&id=u7ea780fb&originHeight=229&originWidth=416&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=163966&status=done&style=none&taskId=u94b14cdd-7823-4d62-b8c2-93ed6b9f4e1&title=&width=302.54545454545456)
### 薪火相传
特点
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696647792533-65b2e1f7-5287-4e82-a1c1-e9aa2404f8ec.png#averageHue=%23eeeee8&clientId=u32fdc52e-01e7-4&from=paste&height=71&id=uf7caec1d&originHeight=97&originWidth=1137&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=153967&status=done&style=none&taskId=u3b8545ed-11e2-4d5c-8e96-594fc434abb&title=&width=826.9090909090909)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696658721032-76432563-0e3e-4a0d-a891-90895d69497c.png#averageHue=%23f9f9f5&clientId=u32fdc52e-01e7-4&from=paste&height=103&id=ue31bd06a&originHeight=141&originWidth=616&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=72041&status=done&style=none&taskId=u61161862-f016-4c16-b341-5c20c62b9b0&title=&width=448)
藩镇割据,各为其主
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696658883449-38687e9d-54de-4f99-916b-aefbf0ae320d.png#averageHue=%23151714&clientId=u32fdc52e-01e7-4&from=paste&height=332&id=u7e7c120c&originHeight=457&originWidth=1198&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=872057&status=done&style=none&taskId=u2693dad0-d91e-4655-a832-96c79c1f3c7&title=&width=871.2727272727273)
只要角色是从机,就没有写的能力;
能够减轻主机的复制压力,因为首层从机同时也作为二层从机的主机
#### 意外状况(宕机时)
##### 主机宕机
主机宕机则从机等待,等待主机重新连接
##### 中间从机宕机
最底层从机死等
主机缺少了一个从机
若中间的从机宕机后恢复则其需要重新认主
注-->同步是需要时间的
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696659322421-89a192f1-87fe-4898-ad99-e63c75cf83fd.png#averageHue=%23131412&clientId=u32fdc52e-01e7-4&from=paste&height=155&id=u756ab45d&originHeight=213&originWidth=766&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=197878&status=done&style=none&taskId=u8e31934b-50f3-486e-80d7-87ce1abf7fb&title=&width=557.0909090909091)
##### 最底层从机宕机
不影响主从复制,能读能写,可以提供服务
少一个从机,若其恢复时需要重新认主
### 哨兵模式
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696661041373-8baca268-9b77-4848-b0df-714f0228c1bc.png#averageHue=%23e9e9e5&clientId=u32fdc52e-01e7-4&from=paste&height=241&id=uea53917d&originHeight=332&originWidth=764&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=176355&status=done&style=none&taskId=u90fd99e3-5eb7-4404-ba14-eeddfbe2b5a&title=&width=555.6363636363636)
#### 使用
##### 1.设置简单的一主二仆
##### 2.为哨兵模式准备配置文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696659754611-49943e22-7a5b-4299-9851-a85d3fbd648f.png#averageHue=%23f4f4ef&clientId=u32fdc52e-01e7-4&from=paste&height=121&id=u8251f8af&originHeight=167&originWidth=761&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=100519&status=done&style=none&taskId=uae0e3edd-152b-4868-8973-b433721dd59&title=&width=553.4545454545455)
##### 3.启动哨兵
启动哨兵需要通过bin内文件sentinel来启动sentinel.conf配置文件来实现
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696660081080-0d0bba74-8441-4ffe-9a8b-2bfb558f5cb8.png#averageHue=%23151613&clientId=u32fdc52e-01e7-4&from=paste&height=211&id=u81b7b520&originHeight=290&originWidth=617&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=219997&status=done&style=none&taskId=uc7afa5c1-6ef0-4527-8f13-903bf3200c8&title=&width=448.72727272727275)
当处于根目录下时,可以使用此命令来启动哨兵模式
/user/local/bin/redis-sentinel /root/sentinel.conf
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696660222572-7abd02d9-2476-4a07-ac00-5c908e2580fe.png#averageHue=%232a3329&clientId=u32fdc52e-01e7-4&from=paste&height=29&id=u9d062ebf&originHeight=40&originWidth=641&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=30406&status=done&style=none&taskId=uc6d9e3cc-1fee-440b-9d7d-84d52214ab8&title=&width=466.1818181818182)
因为哨兵是前置启动,因此会显示redis图标
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696660339444-12ab2e73-f60d-474c-b039-ae432de94125.png#averageHue=%23131311&clientId=u32fdc52e-01e7-4&from=paste&height=225&id=ud01de5b9&originHeight=309&originWidth=580&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=121144&status=done&style=none&taskId=uf1e3998d-1134-480c-bc46-614c5f46ddd&title=&width=421.8181818181818)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696660580765-92a1887c-f4e2-4308-aff4-9e47c9f631a6.png#averageHue=%23161714&clientId=u32fdc52e-01e7-4&from=paste&height=320&id=u58dfb288&originHeight=440&originWidth=1341&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=903273&status=done&style=none&taskId=u64e94e58-41ca-4e03-ad46-f5cc6a5a231&title=&width=975.2727272727273)
哨兵会推选一个从机当主机
1.优先级
2.数据量
3.随机
其他的从机会跟随新主人
当原来的主机重新恢复后
会成为新的主机的从机(俯首称臣)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696661019198-b2a2fe8c-0ecb-42c1-a601-679ac02f287b.png#averageHue=%23181815&clientId=u32fdc52e-01e7-4&from=paste&height=324&id=ua237c8ec&originHeight=445&originWidth=555&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=236163&status=done&style=none&taskId=ud65fb1d3-fe25-4167-b8e7-18c31c476fd&title=&width=403.6363636363636)
## 集群
### 介绍
#### 好处
容量的横向扩容
高并发写操作分摊压力
##### 无中心配置相对简单
有中心配置就是需要一个类似接线员角色的代理主机来处理各个主机之间的关系
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696668914784-88d005ca-8c2b-4686-a347-57f0217a063e.png#averageHue=%23e2e2dd&clientId=u32fdc52e-01e7-4&from=paste&height=308&id=u7b0d65d0&originHeight=423&originWidth=1502&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=631508&status=done&style=none&taskId=u2d557db0-523b-4a77-bbca-74e40d6a239&title=&width=1092.3636363636363)
无中心配置即集群模式下任意登录某个主机都可实现,需要换时自己会进行一个自动切换
#### 不足
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696669075426-2057973b-5cf6-40ce-a22e-36d671b6d425.png#averageHue=%23f6f6f1&clientId=u32fdc52e-01e7-4&from=paste&height=113&id=ub87a39d4&originHeight=155&originWidth=1124&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=143550&status=done&style=none&taskId=u4076bfbf-5a41-4c80-8c94-b22cc32a8c7&title=&width=817.4545454545455)
#### 分析
若选择使用主从复制的方式来提升缓存性能,就是想要用到主从复制的优点即--->**读写分离,快速容灾**
当容量不够的情况时可以使用**集群**,来解决主机写的压力
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696661983603-b0e1f0cd-95ca-4bf4-9bd2-4a95605d6130.png#averageHue=%23fafaf6&clientId=u32fdc52e-01e7-4&from=paste&height=274&id=uec210ee6&originHeight=377&originWidth=954&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=141724&status=done&style=none&taskId=u38cb5749-1c70-498f-8a10-9077e855ecd&title=&width=693.8181818181819)
### 搭建集群(伪)
#### 1.准备六个redies
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696662208167-6c12f294-b3ba-4a05-ada9-8cd309fc7b96.png#averageHue=%23f6f6f1&clientId=u32fdc52e-01e7-4&from=paste&height=171&id=ud5fcb9ca&originHeight=235&originWidth=433&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=93718&status=done&style=none&taskId=u4473541f-2bcb-42f5-aa87-f5ebfa14ef2&title=&width=314.90909090909093)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696663723096-49ab2796-21dc-4bf0-a086-f4d41286dd1a.png#averageHue=%23151512&clientId=u32fdc52e-01e7-4&from=paste&height=387&id=uc94e78b4&originHeight=532&originWidth=586&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=227245&status=done&style=none&taskId=u6e0243b2-89a0-4b4b-b59c-b859c44d35e&title=&width=426.1818181818182)
#### 2.写六个实例的配置文件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696662347736-7a586eb8-1685-48da-8f09-a5a756ca5826.png#averageHue=%23e5e9e3&clientId=u32fdc52e-01e7-4&from=paste&height=135&id=u51a14902&originHeight=186&originWidth=440&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=99181&status=done&style=none&taskId=u6938caad-a9ee-40a2-a81b-06b7ed056e5&title=&width=320)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696662396793-d7a0522f-5846-4b09-8ef2-99273c63f919.png#averageHue=%23efefe9&clientId=u32fdc52e-01e7-4&from=paste&height=140&id=u0d14ea3c&originHeight=193&originWidth=690&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=164568&status=done&style=none&taskId=uf0bdd829-8860-49c7-89d5-8f261c33662&title=&width=501.8181818181818)
#### 3.启动六个服务
#### 4.将六个服务合并为一个集群
需要在指定目录下进行启动
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696662513618-ba92de5c-a3ac-422f-b98f-f864f0ddf43a.png#averageHue=%23f3f3ee&clientId=u32fdc52e-01e7-4&from=paste&height=195&id=u09066d07&originHeight=268&originWidth=1074&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=219919&status=done&style=none&taskId=ub00c6ad9-b27f-4e0a-a653-4cd5557f18b&title=&width=781.0909090909091)
根据卡槽对应不同的数据
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696662571859-982fdcd0-5bb2-4e1d-91c9-6018c22cbb49.png#averageHue=%232b2d27&clientId=u32fdc52e-01e7-4&from=paste&height=361&id=uda642acf&originHeight=497&originWidth=778&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=588990&status=done&style=none&taskId=ub77a642b-c450-4ed3-a11b-e716b8720d4&title=&width=565.8181818181819)
#### 集群的登录
redis-cli -c -p 6379
登录指令添加 -c 代表以集群方式登录
当向集群中set数据时,需要先计算卡槽,根据计算的卡槽来确定存到哪个端口号下
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696662694171-e0919c9a-f382-4b48-813e-f02cbeeb6f17.png#averageHue=%232c211e&clientId=u32fdc52e-01e7-4&from=paste&height=127&id=u71032280&originHeight=174&originWidth=710&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=90667&status=done&style=none&taskId=u5591a55a-dd1d-4948-9c80-be48aa133a1&title=&width=516.3636363636364)
#### 登录后查看集群信息
操作数据时会根据自动计算的卡槽数去自动切换到符合的主机之下来进行相关操作
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696664649187-dbb80da3-3f4e-46ed-ae38-03e0b3789819.png#averageHue=%23151712&clientId=u32fdc52e-01e7-4&from=paste&height=181&id=u159eb2a8&originHeight=249&originWidth=592&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=157126&status=done&style=none&taskId=u0f1f20e1-05c7-4137-81ff-8ff1cab29f1&title=&width=430.54545454545456)
#### 查看节点信息
通过各自主机之下来执行命令 cluster nodes来进行
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696664957376-7bb81f40-20cb-491c-b098-673bb3f702be.png#averageHue=%23161713&clientId=u32fdc52e-01e7-4&from=paste&height=153&id=u27a96dea&originHeight=211&originWidth=1128&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=327053&status=done&style=none&taskId=ueaec3ced-b158-4cc7-bcd8-25ed615ad76&title=&width=820.3636363636364)
#### 集群录入取出
一个集群有16384个插槽,数据库中的每个键都属于16384个插槽中的一个
##### 集群中录入值
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696665998914-1cbc6514-10c0-44f1-843d-ac8fe6906d66.png#averageHue=%23b5b6b1&clientId=u32fdc52e-01e7-4&from=paste&height=167&id=uf9ae41ef&originHeight=229&originWidth=897&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=176906&status=done&style=none&taskId=ueda35a35-8073-41ae-9eef-23b7e338e7b&title=&width=652.3636363636364)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696665765695-7797ba1d-250c-4fba-a1ca-3c2fa7740bb1.png#averageHue=%23161713&clientId=u32fdc52e-01e7-4&from=paste&height=120&id=u6f627650&originHeight=165&originWidth=656&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=121126&status=done&style=none&taskId=u24da391d-6d07-433e-8adc-ac7f5235ab7&title=&width=477.09090909090907)
分组前后分别存入的k1和k2和{group}k1和{group}k2
没有关系,加了{group}则表明两个key值存入了
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696665797494-a1a8be99-8852-477e-87f1-2567d7fea9ea.png#averageHue=%23161813&clientId=u32fdc52e-01e7-4&from=paste&height=263&id=ufc3df3f1&originHeight=361&originWidth=540&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=227413&status=done&style=none&taskId=u19a8a6f5-06b5-48ef-86ca-8397cc88dc9&title=&width=392.72727272727275)
##### 集群中查找值
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696667082803-ce3617ea-afaf-45b4-ab4f-ffc36b289252.png#averageHue=%23ababa6&clientId=u32fdc52e-01e7-4&from=paste&height=214&id=u8ba12a44&originHeight=294&originWidth=894&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=210886&status=done&style=none&taskId=uea8aff71-0a70-4c48-81c2-a45e9b544d2&title=&width=650.1818181818181)
cluster keyslot key 计算key应该保存在哪个卡槽
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696667144206-dca85461-347f-4141-920f-3e8be4033dcf.png#averageHue=%23141712&clientId=u32fdc52e-01e7-4&from=paste&height=164&id=u5ecd7383&originHeight=226&originWidth=470&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=145268&status=done&style=none&taskId=u104a08eb-f42f-4d3e-8e0f-578764eaa13&title=&width=341.8181818181818)
计算某个插槽中保存的key的数量(必须要在此主机端口之下才可)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696667242246-7b8164ac-2bb7-46d3-88d4-fa63a5b35936.png#averageHue=%23141612&clientId=u32fdc52e-01e7-4&from=paste&height=205&id=u6a137960&originHeight=282&originWidth=619&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=178382&status=done&style=none&taskId=u7ec80afa-112f-4115-aed5-2bda9e304eb&title=&width=450.1818181818182)
CLUSTER GETKEYSINSLOPT 插槽 num
返回 num 个所填插槽中的键
#### 集群故障恢复
##### 主机宕机
其内默认有一个哨兵模式,有十五秒的超时时间
主机宕机时
从机上位
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696667911092-ada137fb-115a-4246-8eec-18e165f3201d.png#averageHue=%23161713&clientId=u32fdc52e-01e7-4&from=paste&height=272&id=ub84fccd5&originHeight=374&originWidth=1005&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=455533&status=done&style=none&taskId=u4ad5934b-6243-4a6c-a81d-43436fd138d&title=&width=730.9090909090909)
若原主机恢复,则成为新主机的从机
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696667946186-e0df2cd9-f0a4-453b-b834-a24a8779a37e.png#averageHue=%23171915&clientId=u32fdc52e-01e7-4&from=paste&height=169&id=u275d3f5f&originHeight=232&originWidth=1064&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=363539&status=done&style=none&taskId=u88b3f44b-6909-418e-9711-a503d086df4&title=&width=773.8181818181819)
##### 主机和从机都宕机
杀死进程来结束redis服务
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696668028364-48abc1dd-c5c8-44e0-8a34-9a5de10c8a2a.png#averageHue=%23181b15&clientId=u32fdc52e-01e7-4&from=paste&height=147&id=u8b28bfa9&originHeight=202&originWidth=610&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=194875&status=done&style=none&taskId=u9a355134-f032-4294-8a2c-bdf47fcd227&title=&width=443.6363636363636)
 则整个集群都无法执行服务(集群因为某插槽的主从节点都宕掉而整个集群挂掉).
通过更改配置文件中的一段配置来修改此状态.
将其修改为no则集群中的主机和从机都宕机之后,也只有其主机从机所在插槽不能使用而不会导致整个集群都挂掉.如下
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696668670088-875053c2-39e6-4c7b-a6f6-f58b7ffd4a34.png#averageHue=%23141511&clientId=u32fdc52e-01e7-4&from=paste&height=167&id=u7afb9b26&originHeight=229&originWidth=680&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=144706&status=done&style=none&taskId=u4a48f450-8706-4786-816f-cf3e6ada682&title=&width=494.54545454545456)
cluster-require-full-coverage 默认为yes
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696668230324-33094e6f-2f13-4c20-bbca-70045e179d48.png#averageHue=%23f5f5ef&clientId=u32fdc52e-01e7-4&from=paste&height=65&id=ub39d0043&originHeight=89&originWidth=823&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=82853&status=done&style=none&taskId=u3c9f8e04-9612-4201-90b8-e45a6ebb4b5&title=&width=598.5454545454545)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/838436/1696668327925-a6f83a91-d443-498f-8b01-616b158cc6ce.png#averageHue=%2311110f&clientId=u32fdc52e-01e7-4&from=paste&height=86&id=u4823a20f&originHeight=118&originWidth=437&originalType=binary&ratio=1.375&rotation=0&showTitle=false&size=73843&status=done&style=none&taskId=u782a7efa-969f-4f83-b4ca-0b93a10e621&title=&width=317.8181818181818)
