# 介绍
1.概述:数组工具类
2.特点:
  a.构造私有,不能new
  b.方法为静态的
3.使用:
  类名直接调用
# 方法

|方法|说明|
|---|---|
|static int binarySearch(int[] a, int key)|二分查找|
|static void sort(int[] a)|升序排序|
|static String toString(int[] a)|按照指定格式输出元素[元素1,元素2...]|
|static int[] copyOf(int[] original, int newLength)|数组扩容,返回新数组|