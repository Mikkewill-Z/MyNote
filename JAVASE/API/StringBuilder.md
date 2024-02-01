# 介绍
1.概述:一个可变的字符序列。此类提供一个与 StringBuffer 兼容的 API，但不保证同步
2.作用:StringBuilder主要的作用是拼接字符串

3.问题:既然String就可以做字符串拼接,那为啥还要学StringBuilder呢?
  a.String每拼接一次,会产生一个新的串儿,就会在内存中**开辟新的空间**,比较耗费内存资源.  [[String#^bc7c90|String拼接]]
  b.StringBuilder底层自带***缓冲区***,所有的字符串拼接之后会保存到缓冲区中,所以拼接之后不会产生新的字符串对象,比较省内存资源
    
4.StringBuilder的特点:
  a.StringBuilder底层自带缓冲区,所有的字符串拼接之后会保存到缓冲区中,所以拼接之后不会产生新的字符串对象,比较省内存资源
  b.StringBuilder底层的缓冲区其实是一个长度为16的并且**没有被final修饰**的数组(jdk8为char数组,jdk8之后是byte数组)
  
  c.数组默认长度为16,如果长度超过了16,StringBuilder会自动扩容
    创建新数组,长度为指定长度,将老数组元素复制到新数组中,然后将新数组地址值赋值给老数组 #StringBuilder扩容机制
  d.扩容多少倍: 2倍+2 
# 使用
 1.构造:
   StringBuilder()
   StringBuilder(String str)   
## 常用方法
 StringBuilder append(任意类型数据) -> 字符串拼接,返回的是StingBuilder自己,不会返回新的StringBuilder对象
      
  StringBuilder reverse() -> 字符串翻转,返回的是StringBuilder自己
      
  String toString() -> 将StringBuilder转成String
                       使用StringBuilder是为了拼接字符串效率快一点,拼接完之后,我们需要处理拼接好的字符串,所以我们需要将StringBuilder转成String对象,才能调用String中的方法处理拼接好的字符串