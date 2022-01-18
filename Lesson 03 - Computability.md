# Lesson 03 - Computability

> 本节主要描述了什么是可计算性，它和图灵机又有着怎样的联系



## What is Computability

- 什么样的过程能计算，什么样的不能计算？
- 计算机可以做什么，不能做什么？

### 可计算性理论：

1. CS的理论基础
2. 将可解决的问题和不能解决的做了分类
3. 是很多后面的内容（略）的基础

### 为啥要学？

（好像和Computation的意义基本一样）

- 探索computation的本质
- 找到电脑能做的事情
- computation的限制
- computation的效力和效率



## 回到图灵机

### 图灵机的语言（the language of TM）

对于一个图灵机M，它所接受的字符串组成的集合则被称为**the language of M**或者说是**the language recognized by M**，这个集合可以用<img src="https://latex.codecogs.com/svg.image?L(M)" title="L(M)" />表示。它可以是一个无限的集合。任何一个图灵机仅接受一种语言。



### 图灵机三种可能的运行结果

1. accept
2. reject
3. infinite loop（does not halt）



### 针对语言的两种性质

首先我要明确一点：**语言不过是字符串构成的集合而已**

并且一下两种性质均针对语言而言的

#### 1. Turing-recognizable（recursively enumerable）

当一个语言有某种图灵机能**recognize**它，那么它就被称为是**Turing-recognizable**，否则被称为**Turing-unrecognizable**

#### 2. Turing-decidable（recursive）

**decider**：对于所有输入均会停机的图灵机

一个能够recognize一种语言的decider，也被说成是**decide**那一种语言。

重要：每个decider都是图灵机，而每个图灵机不一定都是decider

当一个语言有某种图灵机能**decide**它，那么它就被称为是**Turing-decidable**，否则被称为**Turing-undecidable**

#### 区别与联系：

区别：

- 对于Turing-recognizable的语言L(M)，M在接收到属于L(M)的字符串时候**必须accept并停机**，而不属于L(M)的字符串可以reject并停机或不停机都行。

- 而对于Turing-decidable的语言L(M)，M在接收到属于L(M)的字符串时候**必须accept并停机**，而不属于L(M)的字符串**必须reject并停机**。

联系：

- Turing-recognizable和Turing-decidable都是语言的一种**内在属性**
- Turing-decidable的语言构成的集合**包含于**Turing-recognizable的语言构成的集合，或说Turing-decidable的语言都是Turing-recognizable的



### A problem is computable if and only if it is Turing-decidable

这就是著名的邱奇-图灵论点（Church-Turing Thesis）。

这使得一个抽象的问题（可计算吗）变成了一个具体的问题（有图灵机能decide它吗）。

邱奇发明了**Lambda calculus**，也是一种计算模型。

课件例子：多项式丢番图方程（细节略）

#### 如何描述图灵机上的算法？

三层细节：

1. Formal description：最接近本质的，描述图灵机的状态、转移函数等等
2. Implementation description：用英语描述图灵机怎么移动读写头以及怎么读取数据等，不涉及具体的实现
3. High-level description：用英语描述算法，勾勒大体的思想，不管具体的硬件如何操作

但是图灵机只能输入字符串，为了能够输入别的东西，我们可以将其他的东西**编码**（encode）成字符串。一个对象O的编码成字符串可以表示为\<O\>

比如A同学编码为字符串可以用它的学号表示，\<A\> = “12210101”

课件例子：无向图的连通性判别的图灵机的描述方式（细节略）



### 不可计算的图灵机（Undecidable）

决定某一个输入字符串w在特定图灵机M上是否能够accept的问题是一个undecidable的问题，但它是Turing-recognizable的。

课件例子：波斯特对应问题PCP



### Turing-unrecognizable Languages

**countable set**（可数集）：有限集或可以和自然数集一一对应

结论1：对于任意的alphabet <img src="https://latex.codecogs.com/svg.image?\Sigma" title="\Sigma" />，其上所有字符串的集合<img src="https://latex.codecogs.com/svg.image?\Sigma^*" title="\Sigma^*" />是可数集

结论2：所有图灵机的集合是一个可数集

定理：实数集R是不可数集

**pigeonhole principle**（鸽巢原理）：当有n+1只鸽子而只有n个巢的时候，必定有一个巢至少有两只鸽子

由于实数集是不可数集，而实数集的任意子集也是一种语言，所以所有语言的集合也不可数。而图灵机是可数集，由鸽巢原理可知，一定存在Turing-unrecognizable的Languages。（课件97页有其证明）

<img src="https://latex.codecogs.com/svg.image?L^C" title="L^C" />，所有不在L符串构成的集合，其实就是L的在全集<img src="https://latex.codecogs.com/svg.image?\Sigma^*" title="\Sigma^*" />下的补集

结论：<img src="https://latex.codecogs.com/svg.image?L" title="L" />是decidable的 当且仅当<img src="https://latex.codecogs.com/svg.image?L^C" title="L^C" />和<img src="https://latex.codecogs.com/svg.image?L" title="L" />都为Turing-recognizable的。（课件98页有其证明）

