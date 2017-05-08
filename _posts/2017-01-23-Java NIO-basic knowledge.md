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
它是一块可以写入数据，并且可以从中读取数据的内存。这块内存被报转化过程和NIO Buffer对象，并提供了一组方法，用来方便的访问内存。<br>
![gras](/images/NIO/nio-buffer.jpg)<br>
Buffer有三个重要的属性: position, limit, capacity<br>
他们的关系是: 0<=position<=limit<=capacity<br>
-- position: 代表当前数据读取，或者写入所处的位置<br>
-- limit: 代表当前数据读取，或者写入能够到达的上线<br>
-- capacity: 代表当前Buffer数据的最大容量<br>

(1). Channel有很多的实现:<br>
FileChannel,DatagramChannel,SocketChannel,ServerSocketChannel<br>
Channel可以理解为就是和实体之间进行交互的一根管子，类似Stream，但是Stream是单向的管子。<br>
(2). Buffer的实现:<br>
ByteBuffer,CharBuffer,DoubleBuffer,FloatBuffer,IntBuffer,LongBuffer,ShortBuffer<br>
2. Selector<br>
![gras](/images/NIO/Selector.jpg)<br>

#### IO, NIO与AIO的区别<br>
IO在数据未获取前，一直等待到数据获取到。使用阻塞模式。<br>
NIO同步非阻塞，NIO会将数据读取到Buffer中，使用的时非阻塞模式。<br>
AIO异步非阻塞<br>


#### 参考资料<br>
1. [Java NIO教程](http://www.iteye.com/magazines/132-Java-NIO)
2. [攻破Java BIO](http://www.importnew.com/19816.html)
3. [[Java]读取文件方法大全](https://www.cnblogs.com/lovebread/archive/2009/11/23/1609122.html)
4. [Java NIO使用及原理分析 (一)](http://www.jianshu.com/p/6a2af505ca27)
5. [JDK7 AIO初体验](http://www.iteye.com/topic/1113611)
6. [Java BIO、NIO、AIO概念和适用场景](http://blog.sina.com.cn/s/blog_9eb067b50102wdur.html)
7. [生产者消费者模式和观察者模式的区别](http://www.tuicool.com/articles/UFFR32I)
