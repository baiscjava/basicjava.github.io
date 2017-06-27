---
layout: post
title: ReentrantLock的使用
comments: true
author: "Yin Haomin"
tags:
    - ReentrantLock
    - 使用
---

来看看ReentrantLock的使用。ReentrantLock的优势在于它比synchronized更灵活、更强大，增加了轮训、超时、中断等高级功能。<br>

#### 1. ReentrantLock的例子
[使用ReentrantLock例子](https://github.com/yinhaomin/common-test/tree/master/common-test-service/src/main/java/com/baidu/common/test/service/cocurrency)<br>

#### 2. ReentrantLock的原理



#### 3. ReentrantLock和synchronized的比较
*(1). ReentrantLock比synchronized速度较快，因为ReentrantLock默认是非公平锁，而synchronized是公平锁.<br>
*(2). ReentrantLock的优势在于它比synchronized更灵活、更强大，增加了轮训、超时、中断等高级功能。<br>

#### 参考资料
1. [ReentrantLock使用场景和实例](http://blog.csdn.net/antony9118/article/details/52664125)
2. [分析ReentrantLock的实现原理](http://www.jianshu.com/p/fe027772e156)
