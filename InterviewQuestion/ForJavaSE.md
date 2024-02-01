### 问题: String s = new String("abc")->共创建了几个对象?
     1个或者2个
     a.如果new对象之前abc已经创建出来了,那么String s = new String("abc")就创建了一个
     b.如果new对象之前abc没有创建出来,那么String s = new String("abc")会创建2个