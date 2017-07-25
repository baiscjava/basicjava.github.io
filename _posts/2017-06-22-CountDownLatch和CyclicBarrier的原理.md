---
layout: post
title: CountDownLatch和CyclicBarrier的原理
comments: true
author: "Yin Haomin"
tags:
    - CountDownLatch
    - CyclicBarrier
    - 区别
    - 原理
---

我们来看看CountDownLatch和CyclicBarrier的用法场景，区别和原理。<br>

#### CountDownLatch
CountDownLatch在多线程中应用于这种场景:<br>
需要所有的线程结束以后，才进行下面的操作。具体的写法如下:<br>
[CountDownLatch的Sample](https://github.com/yinhaomin/common-test/tree/master/common-test-service/src/main/java/com/baidu/common/test/service/cocurrency)

它的相关使用的逻辑:<br>
![gras](/images/aqs/CountDownLatch_usage2.jpeg)<br>

它的相关原理:<br>
1. 新建出来CountDownLatch并调用await后<br>
![gras](/images/aqs/CountDownLatch_await6.jpeg)<br>
2. CountDownLatch调用countDown以后<br>
![gras](/images/aqs/CountDownLatch_countDown2.jpeg)<br>

可以替代它的方案:<br>
1.根据我们对于这个原理的探知，写代码实现类似的逻辑<br>
2.当然下面的CyclicBarrier也可以替代CountDownLatch<br>

#### CyclicBarrier
CyclicBarrier在多线程中应用于这种场景:<br>
需要足够量的线程到达某一个状态，才进行下面的操作。具体的写法如下:<br>
[CyclicBarrier的Sample](https://github.com/yinhaomin/common-test/tree/master/common-test-service/src/main/java/com/baidu/common/test/service/cocurrency)

它的相关原理是:<br>
![gras](/images/aqs/CylicBarrier_theory2.jpeg)<br>

可以替代它的方案:<br>
1.根据其逻辑代码实现<br>
2.使用CountDownLatch也能实现类似的功能<br>

#### 两者的区别<br>
终于把原理搞清楚了，我们来讲讲两者的区别<br>
举个例子，CountDownLatch相当于，我们班打算组织出去旅游，大榕树下集，预先知道我们班总共50个人，几个老师等50个人到齐了。几个老师有些去组织学生玩游戏，有些去准备糖果。只要学生没到齐，老师啥都不干。<br>
CylicBarrier相当于，我们班打算组织出去旅游，大榕树下集合，到10个人，就出发，不管班里总共多少人。出发到达目的地后，学生就开始干他们预先定好的事情。

#### 参考资料
1.JDK源代码<br>
2.[java共享锁实现原理及CountDownLatch解析](http://blog.csdn.net/yanyan19880509/article/details/52349056)<br>
3.[分析CountDownLatch的实现原理](http://www.jianshu.com/p/fe027772e156)<br>
4.[ 源码分析-CyclicBarrier](http://blog.csdn.net/u011518120/article/details/55252951)
