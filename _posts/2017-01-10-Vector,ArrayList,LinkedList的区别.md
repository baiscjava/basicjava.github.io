---
layout: post
title: Vector,ArrayList,LinkedList的区别
comments: true
author: "Yin Haomin"
tags:
    - Vector
    - ArrayList
    - LinkedList
    - 区别
---

本文来总结下Vector,ArrayList,LinkedList的区别，这些List类型我们经常在开发中用到，我们来讨论一下什么时候该使用什么?<br>

#### 1. Vector
(1). 使用数组的方式存储。<br>
(2). Vector是线程安全的，因为其方法上加上了synchronized关键字。<br>
(3). 每次数组增大的时候，都要增大原来Size的一倍。<br>

#### 2. ArrayList
(1). 存储是一个Object[],每当有数据增加的时候，就会创建新的Object数组，并将数据写入进去。<br>
(2). 所以其随机访问速度就很快啦，随机删除或者插入数据会导致其后面的数据都往前移动一位。<br>
(3). 每次数组增大的时候，都要增大原来Size的一半。<br>

#### 3. Linkedlist
(1). 存储在内存中时是一个链表<br>
(2). 随机访问速度低，随机删除和添加效率较高<br>
