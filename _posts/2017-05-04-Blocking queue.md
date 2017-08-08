---
layout: post
title: Blocking queue
comments: true
author: "Yin Haomin"
tags:
    - Blocking queue
    - 原理
---

谈谈对Blocking queue的理解。<br>
#### Blocking queue与普通的Queue的区别<br>
(1) Normal queue取不到数据不会一直等待到Queue中有数据，不会等到一有数据被通知线程继续取数据。<br>
Blocking queue，拿不到数据时，会一直等待到有数据进入。当有数据进入的时候，会立即唤醒等待线程取数据。<br>
(2) Normal queue插入数据时，当队列满时，则返回失败。<br>
Blocking queue插入数据时，当队列满时，会一直等待到队列可以插入后再插入。<br>

#### 上面的论述，体现了Blocking queue最重要的特性，那么怎么实现呢？<br>
答案是: 结合使用了ReentrantLock，Condition进行对Queue进行操作。<br>
这个东西太简单了，想想就明白了，不做更深入的研究了。<br>

