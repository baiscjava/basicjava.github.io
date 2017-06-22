---
layout: post
title: Thread的start和run的区别
comments: true
author: "Yin Haomin"
tags:
    - Thread start
    - Thread run
    - 区别
---

Thread的start和run都是其内部的方法，我们来对比下其区别。<br>

#### Thread start
将程序启动起来，不等待程序完成，继续往下走。<br>
它的原理是:<br>
[]<br>
#### Thread run
将程序启动起来，等待程序完成，才继续往下走。它是是定义在Thread实现的Runnable接口中的方法。<br>
Runnable的实现，必须实现run方法。调用run方法，可以认为是对重载的run的方法的调用。<br>


#### 参考资料
1. [Thread的run（）与start（）的区别](http://blog.csdn.net/xuxurui007/article/details/7685076)<br>
2.<br>
