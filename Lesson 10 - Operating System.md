# Lesson 10 - Operating System

> 主要介绍了操作系统是如何让你如此方便地使用计算机的

## 操作系统（OS）是什么

- 一个控制电脑的所有功能的**软件系统**
- 是计算机硬件与用户之间的**接口**，能够管理程序的运行，以及硬件和软件资源的分配

一台裸机（无操作系统）是非常难用的，即使你会用，也不一定能将它安全地操作。而操作系统就可以帮助你管理电脑上的硬件资源和软件资源，让你能够更简单快捷的进行想要的操作。

现在大家可以如此方便地浏览这篇课件，同时开着QQ或着微信，亦或是同时开着Edge或chrome浏览器，双击就能看到一个文件的内容，这都离不开操作系统的帮助。

 

## 如何启动计算机

ROM中存储着叫做**Boot Loader**的程序，这就是启动计算机所必须的程序。

（ROM的数据是烧死在其中的，及时断电也能保持其物理内容）

Boot Loader最开始把硬盘里指定位置的**操作系统**核心程序加载到主存中，直到操作系统能够主动工作为止，将操作系统的首条指令的地址给到PC，开始运行操作系统。从此，操作系统开始控制计算机。



## OS的组成部分

1. 用户接口（User interface）

2. Memory manager 存储器管理

3. Process manager 进程管理

4. Device manager 设备管理

5. File manager 文件管理



### 用户接口（User Interface）

操作系统为完成用户操作而提供的接口。

- Shells：使用文字指令与计算机交互
- GUI（Graphical User Interface）：图形界面



### OS内核（Kernel）

提供了计算机的运行所需要的最基础的一些功能

1. File Manager：文件系统
   - directory（folder）：目录
2. Device Manager：设备驱动（device driver），让计算机能够与接入计算机的外围设备进行信息交互和控制。每种设备都有它独特的设备驱动，它们能翻译一些泛化的操作到更加底层的技术实现。
3. Memory Manager：程序使用的内存空间的保护、回收以及分配
4. Scheduler：调度程序，决定当前什么程序应该被执行
5. Dispatcher：分派程序， 决定一个活动要分配多久的运行时间



## 进程（Process）

我们把某一个程序在计算机里的一次**执行**看做一个进程。

程序和进程的区别：

- 程序是静态的指令的集合
- 进程是程序的执行，是在运行时的

**Process state**：进程的状态

**PCB**（Process Control Block）：存放着执行一个进程所需要的数据

Context Switch：上下文切换，将当前在执行的程序从CPU中取出，并将另一个程序载入CPU的过程，涉及到运行状态（寄存器数据）的保存。



### Process States and Transition：

<img src="./imgs/L10_1.png" alt="L10_1" style="zoom:67%;" />

这个是一个类似图灵机里面学过的状态机的一个图：

1. 先看状态：
   - New
   - Ready
   - Run
   - Wait
   - Exit

2. 再看转换过程：
   - 0 - Program loaded
   - 1 - Process initialized
   - 2 - Gets CPU time
   - 3 - Needs something
   - 4 - Got what it needed
   - 5 - Interrupted
   - 6 - Finished or aborted
   - 7 - Exits system



### 进程管理（Scheduler和Dispatcher）

Scheduler负责……

Dispatcher负责分时，决定CPU time



### 死锁（Deadlock）

哲学家进餐问题（Dining Philosophers Problem）

Starvation饥饿：指一个进程长时间无法被处理的情况（影射了哲学家长时间无法吃到饭的问题）

死锁发生的四个必要的条件：

1. **Mutual Exclusion**：一个资源只能一个进程使用
2. **Resource Holding**：拿到了资源就不放
3. **No Preemption**：无法重新分配资源
4. **Circular Waiting**：两个或多个进程等待的资源形成了一个环



## 内存管理 Memory Management





## 文件系统 File System





## 三种主要的操作系统

- Unix

- Mac OS X

- Windows：世界上最烂的操作系统（？）