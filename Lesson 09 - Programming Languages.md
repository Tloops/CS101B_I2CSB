# Lesson 09 - Programming Languages and Compilers

> 介绍了现代高级语言出现的原因以及什么是编译器

## 汇编语言（Assembly Language）

学了上节课就知道，机器语言太离谱，一堆比特的堆叠，一点也不直观。

汇编语言使用一些助记符代表Op-code，用一些可命名的变量代表一些内存地址，于是变得更加可读啦！但是这个电脑读不懂，电脑只读得懂机器语言，所以我们需要一个翻译官：**Assembler**（汇编程序）。每次我们需要运行一些汇编语言的时候，我们就用它来帮我们把它变成机器语言。



## 高级语言（High-Level Languages）

改变了原语（primitives），提高了抽象程度的水平

高级语言：FORTRAN，COBOL，C，Pascal，Ada，Java...

### Compiler 编译器

一个程序，输入是高级语言的程序，输出的相应的机器语言代码

它可以将高级程序语言翻译为相应的机器语言，让计算机可以执行它

### Interpreter 解释器

不是一次性翻译完，读一条翻译一条执行一条

### Java

先翻译为Java bytecode，这个是用于给JVM（Java Virtual Machine）看的

JVM之后会编译或解释这些bytecode并执行它们

编写一次，就可到处运行



## 编程语言概念

- 分为三类：

  - 声明语句

  - 操作语句

  - 注释

- 变量（Variable）：存储数据，可以改变
- 数据类型（Data Type）：规定一个数据的存储的范围
- 常量（Constants）：不变的数据
- 直接量（Literal）：直接在程序中出现的量
- 表达式（expressions）：
  - 算数（Arithmetic）：`(a + b * c) / d - e`
  - 逻辑（Logic）：`a > b`
    - 关系操作符：`> < >= <= == != (or <> or /=)`

- 赋值（Assignment）：改变变量内的数据 （:=），如`Z := X + Y`

