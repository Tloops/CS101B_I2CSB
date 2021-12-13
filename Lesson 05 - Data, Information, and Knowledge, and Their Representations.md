# Lesson 05 - Data, Information, and Knowledge, and Their Representations

> 主要介绍了各种各样的数据是如何存储在计算机中的

## Data, Information and Knowledge

### data

定义1：是**记录事情的符号的集合**（a collection of symbols recorded things），仅当它被解释时才是有意义的

定义2：

- 基础的数值或事实（basic values or facts）
- 可能是无条理的且缺乏上下文的（can be unstructured and lack context）

### information

定义：被**组织或处理为某种形式**，并可以被用于解决一些问题的data

它可以帮助我们去回答问题

data和information的区别：

- data不需要接收者而information是需要接受者的
- information的意义取决于接受者，而data的意义取决于去解释它

### knowledge

我记得这个老师说在计导B中不重要，他也没有细讲，故略



## 数据的分类（Data Categories）

### Analog and Digital Data

- Analog data（模拟数据）：对数据的连续表示，模拟了data实际表示的方式
  - 一般是由传感器直接采集得到的连续变化的值，例如温度、声音的波形、图像等等
- Digital data（数字数据）：对数据的离散表示，将data打散成分散的几个基本部分
  - 一般是由模拟数据经量化之后得到的离散的数据

### Various Types of Data

- Numbers
- Text
- Audio
- Images and graphics
- Video



## 数据的表示（representation）

### Number

- 定义：对值的一种表示方式，满足一系列的算数运算定律
- 进制（进位值）：
  - 多少进制（即**基数base**）就是满多少进一位
    - binary 二进制：0和1
    - octal 八进制：0到7
    - decimal 十进制：0到9
    - hexadecimal 十六进制：0到9，A到F（10到15）
  - 现代计算机最底层的硬件中所有的数据都是用0和1来存储的（还记得下节课要学的`flip-flop`吗），这恰好和二进制不谋而合，因此计算机里的数据和指令都是以**二进制**的形式存储的。
  - 之所以要把Number放在第一个讲，是因为其实任何一种形式的数据Text、Audio、Images and graphics还是Video，**归根结底都是以Number的形式存放在内存中的**。
- 有小数部分的base为R的数$(d_nd_{n-1}d_{n-2}...d_2d_1.d_{-1}d_{-2}...d_{-m})_R$，表示的数为$\sum_{i=1}^n d_i \cdot R^{i-1} + \sum_{i=1}^m d_{-i} \cdot R^{-i}$
- bit（比特，binary digit的缩写，即二进制数字），即二进制系统中的一位数字，一个0或者一个1；
- 1 byte = 8 bits，一个字节是8个比特
- word，字，字长是计算机能一次性能处理的位数的长度（请看Lesson 08）
- 4个bit恰好可以和1位的十六进制数相对应，所以二进制数可以很方便的写成16进制数
- n个bit可以表示2的n次方个数。



### Two's Complement Notation Systems

当表示的数的数量确定的时候，为了能够表示负数，我们选取其中一半来表示负数，一半来表示正数和零。

先从十进制出发，当使用两位十进制数表示数字时，我们可以使用0到49表示它们这个数本身，用50到99表示-50到-1，不难发现，这种表示依然可以满足大部分数之间的加法（无溢出的情况下）。出于使用加法表示减法的目的（见Lesson 08，Appendix C中的示例计算机只有加法操作），`a-b`可以看做`a+(-b)`，而表示`-b`的数需要用十进制补码来获得，在本例中表示`-b`的数就是`100-b`。

