# BigInteger

## 1.有什么用：可以表示**大整数**，超出Long范围的那种

## 2.怎么用（构造方法）
```
//获取随机大整数，0~2的num次方-1，含边界
public BigInterger(int num, Random random)

//获取指定大整数，字符串中必须是整数，否则报错
public BigInterger(String val)

//获取指定进制（radix）的大整数，字符串必须是整数且符合进制要求，否则报错
public BigInterger(String val,int radix)

//静态方法获取BigInteger的对象，-16~16内部有优化，只能表示long范围的值
public BigInterger(long val)

```
## 3.有什么特点：对象一旦创建，内部记录的值无法改变

## 4.有什么常见API方法
```
//加减乘除
public BigInterger add(BigInteger val)
public BigInterger subtract(BigInteger val)
public BigInterger multiply(BigInteger val)
public BigInterger divide(BigInteger val)
//获取商和余数
public BigInterger[] divideAndRemainder(BigInteger val)
//次幂
public BigInterger pow(int exponent)
//返回较大值或较小值（不会创建新对象）
public BigInterger max/min(BigInteger val)
//转为int类型整数，注意超出范围会报错
public int intValue(BigInteger val)
public int longValue(BigInteger val)

//判断是否相同
public boolean equals(Object x)
```

## 5.底层存储方式
`
final int signum//正负符号，-1表示整数，0表示负数
`

`
final int[] mag//具体数值数据，大数拆成几段存储：先转成二进制，再从右往左拆，每段32bit
`

