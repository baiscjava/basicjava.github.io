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
(1). Channel有很多的实现:<br>
FileChannel,DatagramChannel,SocketChannel,ServerSocketChannel<br>
(2). Buffer的实现:<br>
ByteBuffer,CharBuffer,DoubleBuffer,FloatBuffer,IntBuffer,LongBuffer,ShortBuffer<br>
2. Selector<br>
![gras](/images/NIO/Selector.jpg)<br>

#### NIO与IO的区别<br>
IO在数据未获取前，一直等待到数据获取到。使用阻塞模式。
NIO不会等待，NIO会将数据读取到Buffer中，使用的时非阻塞模式。<br>

