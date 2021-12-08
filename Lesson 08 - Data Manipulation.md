# Lesson 08 - Data Manipulation in Computer Systems

> 介绍了计算机中数据是如何被操作的

## 计算机指令的分类

Three groups:

- **data transfer group**
  - LOAD and STORE
  - Input and Output (I/O)
- **arithmetic/logic group**
  - ADD(, SUB, MUL, ...)
  - AND, OR, XOR
  - SHIFT, ROTATE
- **control group**
  - JUMP
  - BRANCH



## 附录C的演示用计算机指令

16（16^1）个通用寄存器，容量都为**8 bits**；

256（16^2）个存储单元（cell）（因此是8位地址（为什么？）），容量也都为**8 bits**；

因此，通用寄存器用一位16进制数0到F标记，存储单元用两位16进制数00到FF标记（即为其地址）。

指令使用16 bits表示（即为4位的16进制数）：

- 前4位表示**Op-code操作码**（最多16种指令）
- 后12位表示**Operand操作数**

具体每条指令略

### 思考

1. 老师着重用一节课讲了示例程序中的问题：
   1. load/store到底load/store了几个bit？6C、6D、6E相邻，如果一次是16bit会有问题（但是我后来发现通用寄存器和存储单元容量都是8 bit，因此LOAD肯定只LOAD 8 bit，这个问题根本就不存在）
   2. overflow
2. 给一串机器码，问是哪一种循环（while, do-while, for?）
3. 把乘法用这个示例写出来练一练



## 算数、逻辑操作符的巧妙用处

**bit map**：位映射，用一些位（bit）表示一些东西的存在与否

- **AND**和**OR**用于掩码（masking）
  - AND可以取1（mask相应位为1）
  - OR可以取0（mask相应位为0）
- **XOR**用于计算一个数的相反（和全1的bit map进行XOR操作）

**移位操作**：

1. Simple shift：尾补零头舍去
2. Circular shift：头补到尾
3. Arithmetic shift：
   1. 右移：左不变右舍去
   2. 左移：左舍去右补零

**减法、乘法和除法**：

减法：被减数 + 负的减数（或加2的补数）

乘法：循环的加法

除法：循环的减法

