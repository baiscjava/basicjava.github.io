---
layout: post
title: Autobox和Auto-unbox
comments: true
author: "Yin Haomin"
tags:
    - Autobox
    - Auto-unbox
---

我们来看看自动装箱和自动拆箱。

#### 1. 为什么要有自动装箱和自动拆箱

首先需要搞清楚的是，为什么需要自动装箱和自动拆箱，这个东西有什么用？我们知道，int，long等等这些是Java的基本类型，
这些类型的数据不能够调用Class的各种方法，而在Java中一切皆对象，我们怎么把这些个基本类型整成对象呢？解决方案来了，就是用这些个类型所对应的装箱的类。

|INDEX|基本类型|大小|数值范围|默认值|包装类型|
|:-------|:-------|:-------|:-------|:-------|:-------|
|1|boolean|---|true,false|false|Boolean|
|2|byte|8 bit|-2^7--2^7-1|0|Byte|
|3|char|16 bit|\u0000 - \uffff|\u0000|Character|
|4|short|16 bit|-2^15 -- 2^15-1|0|Short|
|5|int|32 bit|	-2^31 -- 2^31-1|0|Integer|
|6|long|64 bit|	-2^63 -- 2^63-1|0|Long|
|7|float|32 bit|IEEE 754|0.0f|Float|
|8|double|64bit|IEEE 754|0.0d|Double|
|9|void|---|---|---|Void|


#### 2. Integer的自动装箱和自动拆箱
```
      Integer integer1 = 100;
      Integer integer2 = 100;
      System.out.println("integer1==integer2: " + (integer1 == integer2));// true  自动装箱的两个缓存中的 Integer对象的引用比较
      System.out.println("integer1.equals(integer2): " + (integer1.equals(integer2)));// true
      System.out.println("integer1.compare(integer2): " + integer1.compareTo(integer2));// 0    
      Integer integer3 = 200;
      Integer integer4 = 200;
      System.out.println("integer3==integer4: " + (integer3 == integer4));// false 自动装箱的两个new Integer的引用比较
      System.out.println("integer3>integer4: " + (integer3 > integer4)); // false 将两个对象拆箱，再比较大小
      System.out.println("integer3.equals(integer4): " + (integer3.equals(integer4)));// true
      System.out.println("integer3.compare(integer4): " + integer3.compareTo(integer4));// 0   
      Integer integer5 = new Integer(100);
      Integer integer6 = new Integer(100);
      System.out.println("integer5==integer6: " + (integer5 == integer6)); // false 两个不同的Integer对象引用的比较
      System.out.println("integer5.equals(integer6): " + (integer5.equals(integer6)));// true
      System.out.println("integer5.compare(integer6): " + integer5.compareTo(integer6));// 0    
      int int1 = 100;
      System.out.println("integer1==int1: " + (integer1 == int1));// true  Integer缓存对象拆箱后与int比较
      System.out.println("integer1.equals(int1): " + (integer1.equals(int1)));// true
      System.out.println("integer1.compare(int1): " + integer1.compareTo(int1));// 0      
      int int2 = 200;
      System.out.println("integer3==int2: " + (integer3 == int2));// true  Integer对象拆箱后与int比较
      System.out.println("integer3.equals(int2): " + (integer3.equals(int2)));// true
      System.out.println("integer3.compare(int2): " + integer3.compareTo(int2));// 0 
```
从上面可以知道
1. JVM对于-128到127之间的数据，进行缓存，凡创建这个区间的数据，都不会开辟新的空间。
2. 对于这个范围以外的数据，都进行空间的开辟，而这个数据范围是可以调整的。
3. 使用"=="进行数据比对，比较的是两个数据的内存地址是否一样，也用来比较两个基本数据类型的变量值是否相等。而equals进行比对，则是比较的两个数据的对象的hash值是否相等。

#### 3. String的自动装箱和自动拆
```

```

#### 4. 总结


#### 5. 补充说明
```
```
