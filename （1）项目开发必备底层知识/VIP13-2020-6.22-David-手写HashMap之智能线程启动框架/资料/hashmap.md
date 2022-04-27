```
static final int tableSizeFor(int cap) {
    int n = cap - 1;
    n |= n >>> 1;
    n |= n >>> 2;
    n |= n >>> 4;
    n |= n >>> 8;
    n |= n >>> 16;
	return (n < 0) ? 1 : (n >= MAXIMUM_CAPACITY) ? MAXIMUM_CAPACITY : n + 1;
}
```

tableSizeFor(int cap)是hashMap中的一个Static函数，主要功能是返回一个比给定整数大且最接近的2的幂次方整数，如给定10，返回2的4次方16.
这个算法的原理是什么呢：
我们首先假定cap也就是给定数的的形式为

> #代表 任意数

0001 ####

第一次

0001 ####

0000 1###

结果  0001 1###

第二次

0001 1###

0000 11##

结果 : 0001  11#

最终  0001  1111

hash的初始长度是怎么计算   16   完了吗    默认实现

 



