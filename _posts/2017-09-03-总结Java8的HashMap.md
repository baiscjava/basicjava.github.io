---
layout: post
title: 总结Java8的HashMap
comments: true
author: "Yin Haomin"
tags:
    - HashMap
    - 总结
---

给自己挖一坑位，总结一下Java8的HashMap。<br>
红黑树是一种二分查找树，之所以设计这种树，就是为了一方面要快速查找，一方面又不希望在新的数据插入的时候，浪费很多时间空间来重新让树平衡。<br>


#### 参考资料<br>
1. [红黑树(一)之 原理和算法详细介绍](https://www.cnblogs.com/skywang12345/p/3245399.html)
2. [Java8系列之重新认识HashMap](http://www.importnew.com/20386.html)
