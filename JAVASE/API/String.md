# String基础
## 概述
1.String 类代表字符串
2.特点:
  a.Java 程序中的所有字符串字面值（如 "abc" ）都作为此类的实例实现
    凡是带双引号的,都是String的对象
    String s = "abc" -> String是数据类型;s是对象名;"abc"是对象
  b.*字符串是常量,它们的值在创建之后不能更改* 
  c.String 对象是不可变的，所以可以共享 
## 实现原理

1.jdk8:String底层是一个被final修饰的**char数组**-> 一个char类型占内存2个字节
2.jdk9:String底层是一个被final修饰的**byte数组** -> 一个byte类型占内存1个字节
    
3.只要是定义字符串,都会自动将字符串每一个字符放到数组中,一个字符就是一个元素    

注意:String底层是一个final修饰的数组,地址值直接锁死
String被声明为[[final]],因此它不可被继承^[Integer等包装类也不能被继承]
## String创建
1.构造:
  a.String()-> 利用空参构造创建String对象,此时没有内容
  b.String(String str) -> 利用有参构造创建String对象,此时有内容
  c.String(char[] chars) -> 利用char数组创建String对象
  d.String(byte[] bytes) -> 根据平台默认编码创建String对象
      
2.简化方式创建String
  String 变量名 = ""
  
**扩展构造:**
  1.String(char[] value, int offset, int count)->将字符数组一部分转成String
           value:要转的数组
           offset:从数组的哪个索引开始转
           count:转多少个
          
  2.String(byte[] bytes, int offset, int length)->将字节数组一部分转成String
           bytes:要转的数组
           offset:从数组的哪个索引开始转
           length:转多少个
## 扩展:
	字符串拼接:
	1.等号右边如果是字符串字面值,不会产生新对象
	2.等号右边如果有变量参与拼接,会产生新对象
String不可变的好处
1.可以储存hash值
	因为 String 的 hash 值经常被使⽤，例如 String ⽤做 HashMap 的 key。不可变的特性可以使得 hash 值也 不可变，因此只需要进⾏⼀次计算。
2.StringPool的需要
	如果⼀个 String 对象已经被创建过了，那么就会从 String Pool 中取得引⽤。只有 String 是不可变的，才可 能使⽤ String Pool。
3.安全性
	String 经常作为参数，String 不可变性可以保证参数不可变。
4.线程安全
	String 不可变性天⽣具备线程安全，可以在多个线程中安全地使⽤。
	
# 字符串操作类的区别
用法一样,作用一样

1.可变性
	String 不可变   StringBuffer 和 [[StringBuilder]] 可变 

 2.线程安全 
 String 不可变，因此是线程安全的 
 StringBuilder 不是线程安全的 
 StringBuffer 是线程安全的，内部使⽤ synchronized 进⾏同步

拼接效率来说:  StringBuilder>StringBuffer>String

# String的方法
## 判断
boolean equals(Object anObject) -> 比较两个字符串的内容 
boolean equalsIgnoreCase(String anotherString)-> 比较两个字符串的内容,忽略大小写	
![[Pasted image 20231122194931.png]]
### 注意
我们应该将确定的字符串放到前面,将不确定字符串变量放到后面,防空指针
## 获取
public int length():返回 此字符串的长度
public String concat(String str):将指定的字符串**拼接**到老串的末尾
char charAt(int index)  :返回指定索引处的char值
int indexOf(String str)  :获取的是指定字符串在老串中第一次出现的索引位置
String substring(int beginIndex):返回一个子字符串,从beginIndex开始截取字符串到字符串末尾,老串不动
String substring(int beginIndex, int endIndex) :返回一个子字符串,从beginIndex到endIndex截取字符串,  含beginIndex,不含endIndex ^bc7c90
## 转换
char[] toCharArray()-> 将字符串转成char数组
byte[] getBytes() -> 将字符串转成byte数组

String replace(CharSequence c1,CharSequence c2)->替换
               CharSequence->是String的一个接口
    
**扩展:**
byte[] getBytes(String charsetName)-> 按照指定编码将字符串转成byte数组
## 分割
String[] split(String regex):按照指定规则分割字符串,返回String数组
# 扩展方法
 1.boolean contains(String s) -> 判断字符串中是否包含指定的串儿
 2.boolean endsWith(String s) -> 判断字符串是否以指定的串儿结尾
 3.boolean startsWith(String s) -> 判断字符串是否以指定的串儿开头
 4.String toLowerCase()-> 将字符串所有字符转成小写
 5.String toUpperCase() -> 将字符串所有字符转成大写
 6.String trim() -> 去掉字符串两端空格,但是字符串儿中间空格去不掉
 若想去掉中间的空格,可以使用.replace方法将空格替换为空字符串"" 