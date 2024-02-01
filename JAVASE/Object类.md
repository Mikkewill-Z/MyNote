# 介绍
1.概述:Object是所有类的根类,所有的类都会直接或者间接继承Object

2.比如:+
  public class Person{} -> 此时Person的亲爹就是Object
     
  public class Animal{}   -> Animal的亲爹是Object  
  public class Dog extends Animal{} -> Dog的亲爹是Animal 

# Object类中的getClass()方法

1.方法:
   Class getClass()  -> 获取类的class对象
# Native方法
private static native void registerNatives();->将当前类中的native方法注册进来

 static {
        registerNatives();//注册本地方法
    }
方法作用:当该类被加载的时候，调用该方法完成对该类中本地方法的注册

在Object类中，除了有registerNatives这个本地方法之外，还有hashCode()、clone()等本地方法，而在Class类中有forName0()这样的本地方法等等。也就是说，凡是包含registerNatives()本地方法的类，同时也包含了其他本地方法。所以，显然，当包含registerNatives()方法的类被加载的时候，注册的方法就是该类所包含的除了registerNatives()方法以外的所有本地方法
registerNatives()注册当前类的本地方法

1.native:关键字->代表的本地方法
2.本地方法是有方法体的:c语言编写,本地方法的方法体源码没有对我们开源,所以我们看不到方法体,简单理解为本地方法就是对java语言的扩展,比如:后面io流部分,很多功能java本身没有,比如读写,那么就需要调用本地方法进进行读写
3.位置:在本地方法栈运行
4.意义:跟系统打交道

注: 1.本地方法:对java不能实现的功能进行扩充
 2.本地方法是由C语言编写,源码没有开源
 3.本地方法运行在本地方法栈中
# GC垃圾回收
运行垃圾回收器，JVM将从堆内存中清理对象，清理对象的同时会调用对象的finalize()方法，JVM的垃圾回收器是通过另一个线程开启的，因此程序中的效果并不明显。

方法: public static void gc()-->运行垃圾回收器
作用:主要用于回收堆内存中的数据
堆内存中的数据什么时候被清理:如果我们的对象没有用了,GC底层会有很多精妙的算法,会做判断,做回收,详建[[垃圾收集|垃圾回收机制]]

构造方法:new对象的
  析构函数:销毁对象,C语言中才有这个析构函数的概念
      
  Object中的finalize():相当于C语言中的析构函数,用于清理对象,在回收之前,会自动被调用;而且不是垃圾回收器直接调用的,而是垃圾回收器通知当前对象,自动调用此方法进行对象回收   
## 垃圾回收关键点
1.垃圾回收机制只回收JVM堆内存里的对象空间。
2.对其他物理连接，比如数据库连接(Connection)、输入流输出流(IO)、Socket连接(网络编程)无能为力
3.现在的JVM有多种垃圾回收实现算法，表现各异。
4.垃圾回收发生具有不可预知性，程序无法精确控制垃圾回收机制执行
5.可以将对象的引用变量设置为null，暗示垃圾回收机制可以回收该对象。-自动
6.程序员可以通过System.gc()或者Runtime.getRuntime().gc()来通知系统进行垃圾回收，会有一些效果，但是系统是否进行垃圾回收依然不确定。
7.垃圾回收机制回收任何对象之前，总会先调用它的finalize方法（如果覆盖该方法，让一个新的引用变量重新引用该对象，则会重新激活对象）。
8.永远不要主动调用某个对象的finalize方法，应该交给垃圾回收机制通知。

# Object中的toString
Object中的toString方法:
  a.源码:
    public String toString() {
        return getClass().getName() + "@" + Integer.toHexString(hashCode());
    }  
  b.作用:返回该对象的字符串表示形式 -> 类名@十六进制数 -> 俗称对象的地址值
注意:
  a.如果没有重写Object中的toString方法,直接输出对象名,会默认调用Object中的toString,会输出地址值
  b.如果重写了Object中的toString方法,直接输出对象名,再输出地址值重写就没有了意义,所以我们重写toString之后应该输出对象的内容 
![[Pasted image 20231122184027.png|500]]
# Object中的quals

Object中的equals方法源码:
  public boolean equals(Object obj) {
        return (this == obj);
  }
作用:
  比较的是两个对象的**地址值**是否相等
注意:
  a.针对于基本类型来说,比较的是值
	针对于引用类型来说,比较的是地址值
  b.如果没有重写equals,那么默认会调用Object中的equals方法,会比较对象的地址值
  b.如果重写了equals,那么调用equals方法之后,再比较对象地址值,重写就没意义了,所以我们重写equals之后可以比较对象的内容
![[Pasted image 20231122184352.png|500]]
