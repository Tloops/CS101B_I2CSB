# Lesson 11 - System Software and Application Software

> 主要介绍了系统软件和应用软件



## Definitions

### System Software(系统软件)

- 控制并管理资源

- 与硬件层面进行交互
- 为计算机所有的用户和应用程序提供基本的服务

例子：汇编器、编译器、翻译器、操作系统、Editors、linkers、debuggers、storage-media formaters、network software……



### Application Software(应用软件)

- 每一种都有其特别的功能，仅为一部分用户服务

例子：CAD、**DBMS**（数据库管理系统）、calendar、word、ppt、chat、e-mail、browser、video player、games……



## Database System（数据库系统）

**DB**：数据库，逻辑相关的数据的集合（application-dependent）

**DBMS**：数据库管理系统，管理数据库的一种软件（application-independent）

**DBS**：数据库系统，DBS = DB + DBMS

**DB application**：数据库应用，会与数据库进行交互的程序

application-dependent：应用特有的，各应用会互不相同

application-independent：通用的，与应用本身无特殊联系



### File-based system

基于文件的系统：使用文件存放数据，使用程序读取文件来获取数据

#### 缺点：

- 数据冗余和不一致（Data redundancy and inconsistency）：一些数据发生重复，不同程序员也可能使用不同的格式存储相同的数据
- 数据被分离和孤立（Data separation and isolation）：数据以不同格式存放在不同的文件中，难以快捷地查询到
- 数据存在依赖性（Data dependence）：数据之间存在相关性，难以更改数据，因为每次都需要检查数据之间的联系是否合理
- 数据整体性（Integrity problems）：数据必须要有一定的约束，但这些约束会加在程序中
- 原子性问题（Atomicity problems）：断电导致操作未完成等问题
- 并发访问异常（Concurrent-access anomalies）：多个用户同时访问
- 安全问题（Security problems）：不同用户应该有不同的权限



而DBMS就可以解决这些问题，为大家提供高水平的数据访问接口。

### DBMS

- **DDL**（Data-Definition Language）：定义数据格式
- **DML**（Data Manipulation Language）：增删改查（insert、delete、update、retrieve）

#### 缺点：

复杂性高、规模大、费用高、硬件的额外费用、转化费用大、性能相对较低、故障带来的影响较大



## Database System Applications

- 企业经验数据管理
- 银行和金融
- 大学（学生、课程、成绩等等）
- 航空公司
- 通信（QQ、微信、微博等等）

数据库应用无处不在



## Data Abstraction

提供数据的抽象

展现给用户的并不是原初存放在数据库里的数据格式

讲了两页ppt就没讲了……