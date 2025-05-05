# 实现原理
## 一、从JDK 1.7 和 JDK 1.8 版本区别回答
- 在 JDK 1.7 版本之前，HashMap 数据结构是数组和链表，通过 **哈希算法** 将元素的Key 映射到数组中的槽位（Bucket）。如果多个键映射到同一个槽位，则会以链表的形式存储在同一个槽位上，因为链表的查询时间是O(n)，所以冲突很严重，一个索引上的链表非常长，效率就很低了。
- 在JDK 1.8 版本优化，当链表长度超过8，弃用链表转而使用红黑树，查找时使用红黑树，时间复杂度O(log n)，数量小于6时，又会把红黑树转回链表。

## 二、HashMap的put(key,val)和get(key)过程
- 存储对象时，put方法得到K/V，然后调用hashCode计算hash从而得到bucket位置，进而存储； HashMap会根据当前bucket的占用情况自动调整容量(超过Load Facotr则resize为原来的2倍)
- 获取对象时，get方法得到Key，然后调用hashCode计算hash从而得到bucket位置，进而调用equals()方法确定键值对； 如果发生碰撞，Hashmap通过链表将产生碰撞冲突的元素组织起来，在Java 8默认情况下，当冲突元素个数>8 且 数组长度>=64，则使用红黑树来替换链表，如果数组长度 <64,则优先数组扩容

## HashMap一般用什么做Key，为什么
- string
- String对象是不可变的，一旦创建就不能被修改，这确保了Key的稳定性。如果Key是可变的，可能会导致hashCode和equals方法的不一致，进而影响HashMap的正确性。

## HashMap的扩容机制 / HashMap的大小为什么是2的n次方大小呢

### 扩容机制    

hashMap默认的负载因子是0.75，即如果hashmap中的元素个数超过了总容量75%，则会触发扩容。扩容分为两个步骤：
- 对哈希表长度的扩展（2倍）
- 将旧哈希表中的数据放到新的哈希表中
具体过程见[小林扩容机制](https://xiaolincoding.com/backend_interview/internet_medium/bilibili.html#hashmap%E7%9A%84%E6%89%A9%E5%AE%B9%E6%9C%BA%E5%88%B6)和[Java guide](https://javaguide.cn/java/collection/java-collection-questions-02.html#hashmap-%E7%9A%84%E9%95%BF%E5%BA%A6%E4%B8%BA%E4%BB%80%E4%B9%88%E6%98%AF-2-%E7%9A%84%E5%B9%82%E6%AC%A1%E6%96%B9)
### 为什么是2的n次方大小
浅看是适应扩容机制，但扩容机制又是适应：    
- 取余(%)操作中，如果除数是 2 的幂次则等价于与其除数减一的与(&)操作，即 如果 length 是 2 的 n 次方，则hash%length==hash&(length-1）
- 采用二进制位操作 & 相对于 % 能够提高运算效率
- 长度是 2 的幂次方，可以让 HashMap 在扩容的时候更均匀，原本存在 HashMap 中的元素，如果length=8扩容到16，那么其新的数组位置取决 hash 的倒数第4个二进制位