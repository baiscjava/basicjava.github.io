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

Thread的start和run都是其内部的方法<br>

#### Thread start
将程序启动起来，不等待程序完成，继续往下走。<br>
它的原理是:<br>
[]<br>
#### Thread run
将程序启动起来，等待程序完成，才继续往下走。调用run方法，可以认为是对重载的run的方法的调用。<br>
