---
layout: post
title: String,StringBuilder和StringBuffer的区别
comments: true
author: "Yin Haomin"
tags:
    - String
    - StringBuilder
    - StringBuffer
    - 区别
---

#### 1. String
(1) String新建出来的数据是不可变化的，因为String是个final的类，并且String是基本类型，其数据在内存中创建出来后不能够被修改。

(2) 一般建议使用String，但是当涉及到需要concatenate(连接)字符串的时候，或者字符翻转的时候，推荐使用StringBuilder，或者StringBuffer

(3) String的+会被转化为StringBuilder或者StringBuffer的append()方法

#### 2. StringBuilder
(1) StringBuilder在内存中是char array

(2) append方法，当 原始大小X2+2 小于 目标大小 时，使用目标大小，创建出来新的array。 否则，capacity为：原始大小X2+2，使用这个capacity创建array

(3) StringBuilder因为上述的append或者insert的时候，扩充其大小的方法实现，导致了它是线程不安全的

(4) 在单线程中，可以使用StringBuilder，因为相较于StringBuffer，它有较高的效率，但是多线程时，建议使用StringBuilder，或者更改StringBuilder的时候，加synchronized关键字

#### 3. StringBuffer
(1) javadoc中的描述和StringBuilder中是类似的，区别在于它是线程安全的

(2) 其原因是因为StringBuffer的append和insert实现加上了synchronized的关键字

经过上面的比较，当进行大量的数据的concatenate的时候，如果使用String的"+"的话，虽然"+"每次都会被转化为StringBuilder的append方法，但是却使用不到StringBuilder的append方法增加capacity策略，这个策略会导致char数组的新建会大大的减少。而String的每一次"+"运算，都新建char数组，因而StringBuilder可以在append的时候，效率优于String的"+"

另外String的concat方法可以保证每一次String的concatenate，新建的char array都是目标大小的，所以，当我们已知仅仅会做一次concatenate的时候，用String的concat方法更加节省空间。

#### 参考资料:
1. Java document的搜索入口: [https://docs.oracle.com/javase/tutorial/search.html](https://docs.oracle.com/javase/tutorial/search.html)
