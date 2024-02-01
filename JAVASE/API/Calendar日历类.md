# 介绍
日历类是一个抽象类
获取: static Calendar getInstance()
![[Pasted image 20231123094457.png|500]]
# 常用方法
常用方法:
  int get(int field) ->返回给定日历字段的值
  void set(int field, int value)  :将给定的日历字段设置为指定的值
  void add(int field, int amount) :根据日历的规则,为给定的日历字段添加或者减去指定的时间量
  Date getTime():将Calendar转成Date对象
      
field:代表的是日历字段-> 年 月 日 星期等,都是静态的    

## 扩展方法
void set(int year, int month, int date) -> 直接设置年月日