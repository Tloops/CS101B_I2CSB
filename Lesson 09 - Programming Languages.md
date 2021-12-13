# Lesson 09 - Programming Languages and Compilers

> 介绍了现代高级程序设计语言出现的原因以及什么是编译器

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

### 几种基本的语句

顺序执行、条件分支和循环

- 赋值（Assignment）：改变变量内的数据 （:=），如`Z := X + Y`
  - 左边是变量名，右边可以是一个数值，也可以是一个算术或逻辑表达式

- 顺序执行（Sequence）
- 判断（If statement）
  - ppt中的红字是**保留字**，这些单词不可以用作变量名

- 循环（While statement）

#### 重要的概念：

- 子程序（Subprograms）
  - Void subprograms (procedures) 过程
  - Value-returning subprograms (functions) 函数
  - Parameters 参数
    - Formal parameters：形式参数，子程序内进行操作时使用的变量
    - Actual parameters：实际参数，调用子程序时外部程序传入的变量
  - 数据传递方式
    - Calling (Passing) by value 传值
    - Calling (Passing) by reference 传引用地址



## 编译（Compilation）

定义：从一种表示语言转换为另一种表示语言的过程

三个阶段：

1. Lexical analysis 字句分析：断成一个个的词（token）
2. Parsing 翻译：得到parse tree （文法树）
3. Code generation 代码生成：根据parse tree生成代码



## Important Programming Languages

### C

- 第一个系统程序设计语言
- 最有效
- 最广泛被应用（Unix操作系统）
- 最容易掌握
- 最“不可靠”（因为有很多不安全的操作（直接操作内存））

### Ada

- Ada 83 世界上第一种编程语言
- boeing 777 99%的代码都是用Ada写的
- 以Ada Lovelace的名字命名，她是世界上第一个程序员

### C++

- C的后继，更加安全
- 引入了面向对象

### Java

- C++的后继
- 移除了一些C++的复杂的操作使其更加鲁棒

除此之外，还有LISP、Scheme和SPARK（Ada的子集）

### Python

- 简单、容易使用
