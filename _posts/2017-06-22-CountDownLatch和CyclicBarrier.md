---
layout: post
title: CountDownLatch和CyclicBarrier
comments: true
author: "Yin Haomin"
tags:
    - CountDownLatch
    - CyclicBarrier
    - 区别
---

我们来看看CountDownLatch和CyclicBarrier的区别，用法。</br>

#### CountDownLatch
CountDownLatch在多线程中应用于这种场景:<br>
需要所有的线程结束以后，才进行下面的操作。具体的写法如下:<br>

可以替代它的方案:<br>

它的相关原理是:<br>

#### CyclicBarrier
CyclicBarrier在多线程中应用于这种场景:<br>
需要足够量的线程到达某一个状态，才进行下面的操作。具体的写法如下:<br>
[CyclicBarrier的原理](https://github.com/yinhaomin/common-test/tree/master/common-test-service/src/main/java/com/baidu/common/test/service/cocurrency)

可以替代它的方案:<br>
[]

它的相关原理是:<br>
