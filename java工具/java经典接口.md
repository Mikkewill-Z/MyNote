# java.lang.Comparable
Java给所有引用数据类型的大小比较，指定了一个标准接口，就是java.lang.Comparable接口
```
package java.lang;

public interface Comparable{
    int compareTo(Object obj);
}
```

使我们的某个类的对象可以比较大小

步骤一: 哪个类的对象要比较大小,哪个类就实现java.lang.Comparable接口并重写方法

步骤二: 对象比较大小时，通过对象调用compareTo方法，根据方法的返回值决定谁大谁小。

示例:
- this对象（调用compareTo方法的对象）大于指定对象（传入compareTo()的参数对象）返回正整数
    
- this对象（调用compareTo方法的对象）小于指定对象（传入compareTo()的参数对象）返回负整数
    
- this对象（调用compareTo方法的对象）等于指定对象（传入compareTo()的参数对象）返回零

# java.util.Comparator
不满足java规定好的实现comparable之中的比较方法
想使用别的方式比较某两个类的对象的大小
使用comparator接口
## 步骤
一: 编写一个类,我们称之为比较器类型,实现java.util.Comparator接口并重写方法
方法体就是 你要如何指定的两个对象的大小

二: 比较大小时，通过比较器类型的对象调用compare()方法，将要比较大小的两个对象作为compare方法的实参传入，根据方法的返回值决定谁大谁小。
- o1对象大于o2返回正整数
    
- o1对象小于o2返回负整数
    
- o1对象等于o2返回零

# java.lang.Cloneable

在java.lang.Object类中有一个方法
```
protected Object clone() throws CloneNotSupportedException
```
所有类型都可以重写这个方法，它是获取一个对象的克隆体对象用的，就是造一个和当前对象各种属性值一模一样的对象。当然地址肯定不同。
![[Pasted image 20231122192333.png|500]]![[Pasted image 20231122192512.png|500]]![[Pasted image 20231122192530.png|500]]
