# Cpp-Study
C++ Study

1、输入输出速度
有人专门写了文章对比各种输入输出方法的速度：https://blog.csdn.net/u013445530/article/details/43381833
		文章主要是针对读入大量整数的需求。
		cin慢是有原因的，其实默认的时候，cin与stdin总是保持同步的，也就是说这两种方法可以混用，而不必担心文件指针混乱，同时cout和stdout也一样，两者混用不会输出顺序错乱。正因为这个兼容性的特性，导致cin有许多额外的开销，如何禁用这个特性呢？只需一个语句std::ios::sync_with_stdio(false);，这样就可以取消cin于stdin的同步，提高cin(cout)的速度，与scanf(printf)效率相差无几
		读入整个文件再处理的方法效率更高。用fread把整个文件读入一个字符串，再将字符串转化为数组。

