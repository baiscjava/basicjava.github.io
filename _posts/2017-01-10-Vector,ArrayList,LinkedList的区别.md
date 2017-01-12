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

本文来总结下Vector,ArrayList,LinkedList的区别，这些List类型我们经常在开发中用到，我们来讨论一下什么时候该使用什么?

#### 1. Vector

#### 2. ArrayList
(1). 存储是一个Object[],每当有数据增加的时候，就会创建新的Object数组，并将数据写入进去。
(2). 所以其存取速度就很快啦，删除数据会导致其后面的数据都往前移动一位。

#### 3. Linkedlist

