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

首先需要搞清楚的是，为什么需要自动装箱和自动拆箱，这个东西有什么用？我们知道，int，long等等这些是Java的基本类型，
这些类型的数据不能够调用Class的各种方法，而在Java中一切皆对象，我们怎么把这些个基本类型整成对象呢？解决方案来了，就是用这些个类型所对应的装箱的类。

|INDEX|基本类型|大小|数值范围|默认值|包装类型|
|:-------|:-------|:-------|:-------|:-------|:-------|
|1|boolean|---|true,false|false|Boolean|
|2|boolean|---|true,false|false|Boolean|
|3|boolean|---|true,false|false|Boolean|
|4|boolean|---|true,false|false|Boolean|
|5|boolean|---|true,false|false|Boolean|
|6|boolean|---|true,false|false|Boolean|
|7|boolean|---|true,false|false|Boolean|
|8|boolean|---|true,false|false|Boolean|
|9|boolean|---|true,false|false|Boolean|


#### 1. Integer的自动装箱和自动拆箱
```

```
