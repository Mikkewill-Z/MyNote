# 介绍
1.概述:日期格式化类
      SimpleDateFormat extends DateFormat
    
2.构造:
  SimpleDateFormat(String pattern) 
                   pattern:传递的是我们指定的日期格式
                           字母不能变,连接符可以改变
                   比如: yyyy-MM-dd HH:mm:ss
                       
3.方法:
  String format(Date date)->将Date对象按照指定的格式转成String  
  Date parse(String source) -> 将符合日期格式的字符串转成Date
  
|时间字母表示|说明|
|---|---|
|y|年|
|M|月|
|d|日|
|H|时|
|m|分|
|s|秒|

