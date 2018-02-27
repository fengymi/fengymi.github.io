---
title: java虚拟机内存模型
date: 2018-02-19 13:56:35
toc: true
tags: [java,jvm]
---

### 1、JVM内存模型
<font size=3>
<b>JVM运行时，从内存模型来看分为五大区域：</b>
   <font size=2>程序计数器（Program Counter Register）、堆（Heap）、虚拟机栈（VM Stack）、本地方法栈（Native Method Stack）、方法区（Method Area）</font>
</font>
    
如图所示：
<!--more-->    
![内存模型](/img/java/jvm/jvm-memory.png)

#### 1.1 程序计数器
程序计数器（program Counter Register）是一块较小的内存空间，它可以看作是当前线程所执行的字节码的行号指示器。此内存区域是唯一一个在Java虚拟机规范中没有规定任何OutOfMemoryError情况的区域。
   
#### 1.2 堆
堆是Java虚拟机所管理的内存中<b>最大</b>的一块数据区域，在虚拟机启动时创建并被所有<b>线程共享</b>。此内存区域唯一的目的就是存放<b>对象实例</b>，几乎所有的对象实例都在这里分配内存，例如对象实例和数组。但随着其他技术的成熟（如JIT），对象分配在堆上慢慢地变得又没那么“绝对”了。堆是[垃圾收集器](#垃圾收集器)管理的<b>主要区域</b>，由于现在的收集器基本都采用分代收集算法，所以Java堆中还可以细分为新生代和老年代。当前主流的虚拟机都是按照可扩展来实现的（[通过-Xmx和-Xms控制]()）。如果堆中没有内存完成实例分配，并且对也无法再扩展时，将会抛出OutOfMemoryError异常。

















