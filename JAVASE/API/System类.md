# 介绍
1.概述:
  System 类包含一些有用的类字段和方法。它不能被实例化
2.特点:
  a.构造私有,不能new对象
  b.方法都是静态的
3.使用:
  类名直接调用
  
|方法|说明|
|---|---|
|static void exit(int status)|终止当前正在运行的 Java 虚拟机|
|static void gc()|运行垃圾回收器|
|static long currentTimeMillis()|返回以毫秒为单位的当前时间,可以用来计算代码的效率|
|static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)|数组复制 src:源数组 srcPos:从源数组的哪个索引开始复制 dest:目标数组 destPos:从目标数组的哪个索引开始粘贴 length:复制多少个|