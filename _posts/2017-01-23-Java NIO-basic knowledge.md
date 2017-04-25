---
layout: post
title: Java NIO-basic knowledge
comments: true
author: "Yin Haomin"
tags:
    - Java
    - NIO
    - basic knowledge
---

Let's talk about the basic knowledge of Java NIO.<br>
#### NIO的基本概念<br>
1. Channel & Buffer<br>
![gras](/images/NIO/ChannelBuffer.jpg)<br>
(1). Buffer的本质
它是一块可以写入数据，并且可以从中读取数据的内存。这块内存被报转化过程和NIO Buffer对象，并提供了一组方法，用来方便的访问内存。

(1). Channel有很多的实现:<br>
FileChannel,DatagramChannel,SocketChannel,ServerSocketChannel<br>
Channel可以理解为就是和实体之间进行交互的一根管子，类似Stream，但是Stream是单向的管子。<br>
(2). Buffer的实现:<br>
ByteBuffer,CharBuffer,DoubleBuffer,FloatBuffer,IntBuffer,LongBuffer,ShortBuffer<br>
2. Selector<br>
![gras](/images/NIO/Selector.jpg)<br>

#### NIO与IO的区别<br>
IO在数据未获取前，一直等待到数据获取到。使用阻塞模式。
NIO不会等待，NIO会将数据读取到Buffer中，使用的时非阻塞模式。<br>

#### 参考资料<br>
1. [Java NIO教程](http://www.iteye.com/magazines/132-Java-NIO)
2. [攻破Java BIO](http://www.importnew.com/19816.html)
3. [[Java]读取文件方法大全](https://www.cnblogs.com/lovebread/archive/2009/11/23/1609122.html)
4. [Java NIO使用及原理分析 (一)](http://www.jianshu.com/p/6a2af505ca27)
5. [JDK7 AIO初体验](http://www.iteye.com/topic/1113611)
