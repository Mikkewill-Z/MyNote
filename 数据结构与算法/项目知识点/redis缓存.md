缓存分类数据
### 方式一: 原生方式
![[Pasted image 20240118142754.png]]
### 方式二 springCache框架
只需要添加注解就能实现缓存功能,极大简化我们在业务中操作缓存的代码
其底层可以切换不同的cache来进行实现,具体就是通过cacheManager接口来统一不同的缓存技术,CacheManager接口就是Spring提供的各种缓存技术的抽象接口
针对不同技术实现不同的CacheManager
![[Pasted image 20240118143530.png]]

### 常见缓存操作
|**注解**|**说明**|
|---|---|
|@EnableCaching|开启缓存注解功能|
|@Cacheable|在方法执行前spring先查看缓存中是否有数据，如果有数据，则直接返回缓存数据；若没有数据，调用方法并将方法返回值放到缓存中|
|@CachePut|将方法的返回值放到缓存中|
|@CacheEvict|将一条或多条数据从缓存中删除|
