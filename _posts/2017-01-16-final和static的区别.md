---
layout: post
title: final和static的区别
comments: true
author: "Yin Haomin"
tags:
    - final
    - static
    - 区别
---

我们来区分一下final和static。<br>

#### 1. final
(1). final修饰可以变量，方法和Class<br>
final修饰基础变量时，，那么此变量不需要实例化Class即可调用，此变量之后不可被修改。<br>
final修饰方法时，此方法不可以再被复写。另外可以使此方法成为内联函数，加快执行。<br>
final修饰Class时，此Class不能再被继承.<br>

(2). static可以修饰变量，代码块，方法和内部类<br>
static修饰变量，那么此变量不需要实例化Class即可调用。<br>
static修饰代码块，代码块会在类实例化时，按照顺序执行。<br>
static修饰方法，此方法可以被直接调用。<br>
static修饰内部类，那么此Class可以像普通的类一样被调用。<br>
