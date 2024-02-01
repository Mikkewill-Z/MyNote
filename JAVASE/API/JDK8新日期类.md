# LocalDate本地日期
1.概述:LocalDate是一个不可变的日期时间对象，表示日期，通常被视为年月日
2.获取:
  a.static LocalDate now()  从默认时区的系统时钟获取当前日期
  b.static LocalDate of(int year, int month, int dayOfMonth) -> 从一年，一个月和一天获得一个 LocalDate的实例   
## LocalDateTime
1.概述:LocalDateTime是一个不可变的日期时间对象，代表日期时间，通常被视为年 - 月 - 日 - 时 - 分 - 秒
2.获取:
 a.static LocalDateTime now()  从默认时区的系统时钟获取当前的日期时间
 b.static LocalDateTime of(int year, int month, int dayOfMonth, int hour, int minute, int second)   从年，月，日，小时，分钟和秒获得 LocalDateTime的实例 
## 获取日期字段,名字是get开头
int getYear()->获取年份
int getMonthValue()->获取月份
int getDayOfMonth()->获取月中的第几天
## 设置日期字段,名字是with开头
LocalDate withYear(int year):设置年份
LocalDate withMonth(int month):设置月份
LocalDate withDayOfMonth(int day):设置月中的天数
## 日期字段偏移
设置日期字段的偏移量,方法名plus开头,向后偏移
设置日期字段的偏移量,方法名minus开头,向前偏移
![[Pasted image 20231123104733.png|500]]
# Period和Duration类
## period计算日期之间的偏差
方法:
  static Period between(LocalDate d1,LocalDate d2):计算两个日期之间的差值
  
  getYears()->获取相差的年
  getMonths()->获取相差的月
  getDays()->获取相差的天
## Duration计算时间之间的偏差
1.static Duration between(Temporal startInclusive, Temporal endExclusive)  -> 计算时间差
2.Temporal是一个接口:
  实现类: LocalDate , LocalDateTime
      
3.参数需要传递Temporal的实现类,需要传递LocalDateTime
  因为Duration计算的是精确时间偏差,所以需要传递能操作精确时间的LocalDateTime
      
4.利用Duration获取相差的时分秒  -> to开头
  toDays():获取相差天数
  toHours():获取相差小时
  toMinutes():获取相差分钟
  toMillis():获取相差秒(毫秒)   
## DateTimeFormatter日期格式化类
1.概述:日期格式化类
2.获取:
  static DateTimeFormatter ofPattern(String pattern)  
                                     pattern:指定的格式
                                         
3.常用方法:
  String format(TemporalAccessor temporal)  ->将日期对象按照指定格式转成String
                TemporalAccessor是一个接口,是Temporal接口的子接口
                实现类有:LocalDate,LocalDateTime
                    
  TemporalAccessor parse(CharSequence text)  -> 将符合格式的字符串日期转成日期对象
                返回值:TemporalAccessor接口,实现类有:LocalDate LocalDateTime  
                    
  static LocalDateTime from(TemporalAccessor temporal)  -> 将 TemporalAccessor转成LocalDateTime    