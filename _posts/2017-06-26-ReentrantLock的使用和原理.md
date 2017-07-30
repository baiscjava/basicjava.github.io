---
layout: post
title: ReentrantLock的使用和原理
comments: true
author: "Yin Haomin"
tags:
    - ReentrantLock
    - 使用
    - 原理
---

来看看ReentrantLock的使用。ReentrantLock的优势在于它比synchronized更灵活、更强大，增加了轮训、超时、中断等高级功能。<br>

#### 1. ReentrantLock的例子<br>
Github: [使用ReentrantLock例子](https://github.com/yinhaomin/common-test/tree/master/common-test-service/src/main/java/com/baidu/common/test/service/cocurrency)<br>

#### 2. ReentrantLock的原理<br>
ReentrantLock还是借助了AQS(AbstractQueuedSynchronizer)这个类，在ReentrantLock中声明了：<br>
```
abstract static class Sync extends AbstractQueuedSynchronizer
```
借助了AQS的state和线程打包成的Node的List，这两个超级重要的变量。这两个变量在我们分析CountDownLatch的时候，也用到了。<br>
(1).对于公平锁(FIFO的锁，严格按照先到先得进行获取的锁)<br>
lock操作<br>
![gras](/images/aqs/ReentrantLock_lock3.jpeg)<br>

(2).对于非公平锁<br>
lock操作<br>
![gras](/images/aqs/ReentrantLock_unfair_lock.jpeg)<br>

(3).释放锁<br>
![gras](/images/aqs/ReentrantLock_unlock.jpeg)<br>

#### 3. ReentrantLock和synchronized的比较
*(1). ReentrantLock比synchronized速度较快，因为ReentrantLock默认是非公平锁，而synchronized是公平锁.<br>
*(2). ReentrantLock的优势在于它比synchronized更灵活、更强大，增加了轮训、超时、中断等高级功能。<br>

#### 参考资料
1. JDK package java.util.concurrent.locks;下面的源码
2. [ReentrantLock使用场景和实例](http://blog.csdn.net/antony9118/article/details/52664125)
3. [分析ReentrantLock的实现原理](http://www.jianshu.com/p/fe027772e156)
