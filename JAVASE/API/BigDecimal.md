# 介绍
1.描述:之前我们说过不要用float或者double直接参与运算,否则会出现精度损失的问题,尤其是涉及到钱,绝对不能用float或者double直接计算
2.作用:BigDecimal可以解决float和double直接参与运算而产生的精度损失问题
3.构造:
  BigDecimal(String val) 
# 使用
 1.常用方法:
  BigDecimal add(BigDecimal val) 返回其值为 (this + val) 的 BigDecimal 
  BigDecimal subtract(BigDecimal val)  返回其值为 (this - val) 的 BigDecimal 
  BigDecimal multiply(BigDecimal val) 返回其值为 (this * val) 的 BigDecimal 
  BigDecimal divide(BigDecimal val)   返回其值为 (this / val) 的 BigDecimal  
      
 2.注意:
  如果除不尽会报错
## divide
BigDecimal divide(BigDecimal divisor, int scale, int roundingMode) -> 除完之后指定保留几位小数
            divisor: 除数
            scale:小数点保留的位数
            roundingMode:取舍方式
                         static int ROUND_UP :向上加1
                         static int ROUND_DOWN :直接舍去
                         static int ROUND_HALF_UP:四舍五入