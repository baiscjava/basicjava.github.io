---
layout: post
title: Java数据类型的大小比对以及equals与hashcode
comments: true
author: "Yin Haomin"
tags:
    - 数据类型
    - 大小
    - 比对
    - equals
    - hashcode
---

在Java中，基本数据类型的比对，我们一般使用">,<,==,<=,>="和object.equals进行数据的比对，以及object还有一个hashcode方法，为了搞清楚这些东西，下面我们一一剖析下。

#### 1. 使用"=="对比数据值
使用"=="的时候，对比的是数据在内存中真实的值，而对于封装类型，"=="比对的是他们在内存中的指向地址是否相同。对于基本的数据类型，对比的是其数据值是否一样。

而对于String这种类型，当String直接赋值的时候，java会先去内存中寻找是否已经存在这个值，如果存在，则将此值赋给它，如果不存在则在内存中将其新建出来。而new String()方式新建String的时候，无论存不存在这个值，都会将String新建出来。

所以，直接新建String的时候，比对两个String，可能两个String指向同一内存，从而使用"=="对比返回true

#### 2. 使用equals对比数据
equals默认使用"=="对比数据，当然这个方法和hashcode一样可以在类中重写。一般的，我们重写equals的时候，需要重写hashcode，所以可能会导致如下的结果:

(1). 当两个Object equals的时候，hashcode一定相等

(2). 当两个Object不equals的时候，hashcode可能相等

(3). 当两个Object hashcode相等时，两个Object不一定equals

(4). 当两个Object hashcode不相等时，两个Object一定不equals

当我们将数据写入到HashSet或者跟HashMap的时候，先去判断hashcode是否相等，再去调用equals.
