# BigDecimal

float：4个字节，32bit，23bit小数
double：8个字节，64bit，52bit小数

##  1.构造方法
```
public BigDecimal(double val)//传递double类型数值，不精确

public BigDecimal(String val)//传递字符串，精确

public BigDecimal valueOf（double val）//静态方法获取对象，0~10的对象已经提前准备好，其他的值则创建新对象，且值不能超出double
```

## 成员方法

```
//加减乘除
public BigDecimal add(BigDecimal val)

public BigDecimal subtract(BigDecimal val)

public BigDecimal multiply(BigDecimal val)

public BigDecimal divide(BigDecimal val)

public BigDecimal divide(BigDecimal val,int 精确几位,RoundingMode 舍入模式)//一般除不尽使用
//不记得参数是什么了可以ctrl + p 查看
//关于RoundingMode枚举类：在数轴上，UP代表远离零方向舍入，DOWN向零方向舍入，CEILING向正无穷大方向舍入，FLOOR向负无穷大方向舍入，HALF_UP四舍五入

```


## 底层存储方式
遍历得到字符串的每一个字符，获取字符对应ASCII数值，形成数组。
