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

### Number（数字）

- 定义：对值的一种表示方式，满足一系列的算数运算定律
- 进制（进位值）：
  - 多少进制（即**基数base**）就是满多少进一位
    - binary 二进制：0和1
    - octal 八进制：0到7
    - decimal 十进制：0到9
    - hexadecimal 十六进制：0到9，A到F（10到15）
  - 现代计算机最底层的硬件中所有的数据都是用0和1来存储的（还记得下节课要学的`flip-flop`吗），这恰好和二进制不谋而合，因此计算机里的数据和指令都是以**二进制**的形式存储的。
  - 之所以要把Number放在第一个讲，是因为其实任何一种形式的数据Text、Audio、Images and graphics还是Video，**归根结底都是以Number的形式存放在内存中的**。
- 有小数部分的base为R的数<img src="https://latex.codecogs.com/svg.image?\inline&space;(d_nd_{n-1}d_{n-2}...d_2d_1.d_{-1}d_{-2}...d_{-m})_R" title="\inline (d_nd_{n-1}d_{n-2}...d_2d_1.d_{-1}d_{-2}...d_{-m})_R" />，表示的数为<img src="https://latex.codecogs.com/svg.image?\inline&space;\sum_{i=1}^n&space;d_i&space;\cdot&space;R^{i-1}&space;&plus;&space;\sum_{i=1}^m&space;d_{-i}&space;\cdot&space;R^{-i}" title="\inline \sum_{i=1}^n d_i \cdot R^{i-1} + \sum_{i=1}^m d_{-i} \cdot R^{-i}" />
- bit（比特，binary digit的缩写，即二进制数字），即二进制系统中的一位数字，一个0或者一个1；
- 1 byte = 8 bits，一个字节是8个比特
- word，字，字长是计算机能一次性能处理的位数的长度（请看Lesson 08）
- 4个bit恰好可以和1位的十六进制数相对应，所以二进制数可以很方便的写成16进制数
- n个bit可以表示2的n次方个数。



### Two's Complement Notation Systems

当表示的数的数量确定的时候，为了能够表示负数，我们选取其中一半来表示负数，另一半来表示正数和零。

先从十进制出发，当使用两位十进制数表示数字时，我们可以使用0到49表示它们这个数本身，用50到99表示-50到-1，不难发现，这种表示依然可以满足大部分数之间的加法（无溢出的情况下）。出于使用加法表示减法的目的（见Lesson 08，Appendix C中的示例计算机只有加法操作），`a-b`可以看做`a+(-b)`，而表示`-b`的数需要用十进制补码来获得，在本例中表示`-b`的数就是`100-b`（即`b`的十进制补码）。从本质上看，找一个数的补码就是在找表示负的这个数的数字是什么。

由于计算机还是得使用二进制，所以我们同样使用一半来表示负数，另一半来表示正数和零。以及二进制补码：

<img src="https://latex.codecogs.com/svg.image?Negative(I)&space;=&space;2^k&space;-&space;I" title="Negative(I) = 2^k - I" />

此处**k**为表示一个数所用的二进制的位数，即k bit。

由于二进制的特殊性，这使有一个明显的性质：当且仅当一个数为负数时，这个数的**最高位为1**。

除此之外，还有另一种表示方式，我们可以把最高位当做符号位，剩下的位当做这个数的大小，比如1010(2)表示-2，0010表示2。



### Floating point representations（浮点数）

为了表示实数，可不能只表示整数。于是我们再次给表示一个数的位以不同的含义来表示小数：

1. **sign bit**：仅一位，表示符号

2. **exponent**：指数位，相当于表示了结果的数量级

3. **mantissa**：尾数位，表示了一个数的末位的数码，或者说是“精度”

其实跟科学计数法很像，科学计数法表示一个数：<img src="https://latex.codecogs.com/svg.image?\inline&space;6.626&space;\times&space;10^{-34}" title="\inline 6.626 \times 10^{-34}" />

- sign bit：0
- exponent：-34
- mantissa：6.626

而在计算机的世界里，咱们还是得用二进制：

<img src="https://latex.codecogs.com/svg.image?(-1)^s&space;\times&space;mantissa&space;\times&space;2^{exponent}" title="(-1)^s \times mantissa \times 2^{exponent}" />

s表示sign bit（0或1），mantissa是尾数部分，exponent就是指数部分

为了一些原因，实际上是这样表示的：

<img src="https://latex.codecogs.com/svg.image?(-1)^s&space;\times&space;(1&space;&plus;&space;mantissa)&space;\times&space;2^{expoment-bias}" title="(-1)^s \times (1 + mantissa) \times 2^{expoment-bias}" />


### Character（字符）

计算机本质上只能存储数字，为了存储字符，我们需要建立数字到字符的映射。

为了统一不同计算机的这种映射，**ASCII**标准诞生了，使用7 bits表示一个字符。

后来越来越多的国家有了计算机，越来越多的文字需要收录其中，但ASCII码最多只能表示128个不同的字符，于是就有了它的扩展：**Unicode**码。它使用16 bits表示一个字符，也就是说，它最多可以表示65536个不同的字符。



### Audio（音频）

音频实质上是要表示声波。声波通过传感器的高频采样，得到一个个时刻的声波幅值并以电压的形式被存储下来。

常见的音频文件扩展名：`.wav`, `.au`, `.aiff`, `.vqf`, `.mp3`等



### Images and Graphics（图片）

**颜色（color）**：人眼能识别的所有颜色都可以由三原色构成，于是计算机存储一种颜色就是记录了这种颜色三原色的贡献度，即RGB（red，green，blue）。这个贡献度就是数字，取值范围取决于我们用多少位去表示这个数，这个位数就是color depth。一般我们会使用8bits去表示。

**像素（pixel）**：放大手机或电脑图像，你会发现图像是由一块块的同种颜色的小方块组成的，这就是像素。

**分辨率（resolution）**：表示一个图像所需要的像素的数量叫做分辨率

两种存储方式：

1. **raster-graphics format（光栅图像格式）**，按像素存储，常见的图像文件扩展名：`.bmp`, `.gif`, `.jpeg`, `.png`等
2. **vector-graphics format（矢量图像格式）**，存储的是点、线、面的位置、方向、粗细和颜色信息，其图形可以任意放大缩小，一种在网上最常用的矢量图格式是Flash。



### Video（视频）

本质上是一系列静态图像的快速播放，帧率。

**Codec**：编码解码器，缩小视频大小的一种工具。基本所有的视频压缩方式都是在最小化人类观看体验的有损压缩。
