---
layout: post
title: Strong,Soft,Weak,Phantom Reference
comments: true
author: "Yin Haomin"
tags:
    - Reference
    - Strong
    - Soft
    - Weak
---

#### 区分一下Strong,Soft,Weak,Phantom Reference<br>
Strong Reference: Java 默认的Reference,强引用当引用存在时，object不会被回收；<br>
Soft Reference:当内存不得不需要释放的时候，软引用才会被释放，并不会在每一次GC都释放；
在内存紧张时可能会被回收，不过也可以通过-XX:SoftRefLRUPolicyMSPerMB参数控制回收的时机.<br>
Weak Reference：每一次GC都释放；<br>
Phantom Reference: 虚引用，没看懂<br>

#### 下面的英文资料讲的特别好，不翻译；<br>
Strong Reference:  We use Strong references in Java everywhere: we can create
an object and then assign it to a reference. Note that if the object has a
strong reference, this object is never be garbage collected.<br>
Example:<br>
```
HelloWorld hello = new HelloWorld();
Here hello is the strong reference to HelloWorld Object.
```
Soft Reference: If an object has no strong reference but has a soft reference,
then the garbage collector reclaims this object’s memory when GC needs to free
up some memory. To get Object from a soft reference, one can invoke the get()
method. If the object is not GCed, it returns the object, otherwise , it
returns null.All soft references to softly reachable objects are guaranteed to
have been cleared before the virtual machine throws an OutOfMemoryError.<br>

Weak Reference: If an object has no strong reference but has a weak reference
then GC reclaims this object’s memory in next run even though there is enough
memory.<br>

Phantom Reference: If an object does not have any of the above references then
it may have a phantom reference. Phantom references can’t be accessed
directly. When using a get() method it will always return null.<br>

Phantom Reference can be used in situations, where sometimes using finalize()
is not  sensible.This is a special reference which says that the object was
already finalized, and the garbage collector is ready to reclaim its memory.<br>

#### 参考资料<br>
1.[弱引用和软引用WeakReference,SoftReference,最简讲解，以及一个应用场景](https://blog.csdn.net/qq_36523667/article/details/78549874)<br>
2.[Different Types of References in Java](https://dzone.com/articles/java-different-types-of-references)<br>
