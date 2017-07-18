# MongoDB

> MongoDB 是一个基于分布式文件存储的数据库。由 C++ 语言编写。旨在为 WEB 应用提供可扩展的高性能数据存储解决方案。MongoDB 是一个介于关系数据库和非关系数据库之间的产品，是非关系数据库当中功能最丰富，最像关系数据库的。

## 关系型数据库
> 1. 数据库有行、列的概念，数据有关系，数据不是散的。
> 2. 数据库能够提供非常方便的接口，让增删改查操作变得简单
> 3. 数据库不能自己玩，要给向PHP、.net、jsp等语言提供接口

## NoSQL
> 没有行、列的概念。用JSON来存储数据。集合就相当于“表”，文档就相当于“行”。

## SQL和NOSQL的比较
NoSQL数据库在以下的这几种情况下比较适用：
1. 数据模型比较简单；
2. 需要灵活性更强的IT系统；
3. 对数据库性能要求较高；
4. 不需要高度的数据一致性；
5. 对于给定key，比较容易映射复杂值的环境。

> 有些系统，特别需要筛选。比如，筛选出所有女生大于20岁的。那么SQL型数据库，非常擅长！因为它有行、列的概念。但是，有些系统，真的不需要进行那么多的筛选，比如站内信。站内信只需要存储就好了。不需要筛选。那么NoSQL的。

## MongoDB 适应场景
1. 游戏场景，使用 MongoDB 存储游戏用户信息，用户的装备、积分等直接以内嵌文档的形式存储，方便查询、更新
2. 物流场景，使用 MongoDB 存储订单信息，订单状态在运送过程中会不断更新，以 MongoDB 内嵌数组的形式来存储，一次查询就能将订单所有的变更读取出来。
3. 社交场景，使用 MongoDB 存储存储用户信息，以及用户发表的朋友圈信息，通过地理位置索引实现附近的人、地点等功能
4. 物联网场景，使用 MongoDB 存储所有接入的智能设备信息，以及设备汇报的日志信息，并对这些信息进行多维度的分析
5. 视频直播，使用 MongoDB 存储用户信息、礼物信息等

### 场景一
> 1. 用在应用服务器的日志记录，查找起来比文本灵活，导出也很方便。也是给应用练手，从外围系统开始使用MongoDB。
> 2. 用在一些第三方信息的获取或者抓取，因为MongoDB的schema-less，所有格式灵活，不用为了各种格式不一样的信息专门设计统一的格式，极大的减少开发的工作。

### 场景二
> mongodb之前有用过，主要用来存储一些监控数据，No schema 对开发人员来说，真的很方便，增加字段不用改表结构，而且学习成本极低。

### 场景三
> 使用MongoDB做了O2O快递应用，·将送快递骑手、快递商家的信息（包含位置信息）存储在 MongoDB，然后通过 MongoDB 的地理位置查询，这样很方便的实现了查找附近的商家、骑手等功能，使得快递骑手能就近接单，目前在使用MongoDB 上没遇到啥大的问题，官网的文档比较详细，很给力。

## 下载MongoDB
[https://www.mongodb.com/download-center?jmp=nav#community](https://www.mongodb.com/download-center?jmp=nav#community)

## 安装环境
> Windows 7 64位

## 安装MongoDB
![](http://i.imgur.com/tXIe2rl.png)
> 如果你的系统是 Windows Server 2008 R2 or Windows 7 ，需要安装一个补丁<br>
> [https://support.microsoft.com/zh-cn/help/2731284/33-dos-error-code-when-memory-memory-mapped-files-are-cleaned-by-usin](https://support.microsoft.com/zh-cn/help/2731284/33-dos-error-code-when-memory-memory-mapped-files-are-cleaned-by-usin)

![](http://i.imgur.com/g3QPCl8.png)

## 加载环境变量
![](http://i.imgur.com/Vz7BWNI.png)
> 测试

![](http://i.imgur.com/G1xasUP.png)

> mongo   使用数据库<br>
> mongod  开机<br>
> mongoimport  导入数据

## 开启数据库
> mongod --dbpath D:\AppServ\Mongo<br>
> --dbpath就是选择数据库文档所在的文件夹<br>
> mongoDB中，真的有物理文件，对应一个个数据库。U盘可以拷走<br>
> 一定要保持，开机这个CMD不能动了，不能关，不能ctrl+c。 一旦这个cmd有问题了，数据库就自动关闭了。

![](http://i.imgur.com/nZxvOxA.png)

> 新开窗口，输出 `mongo` 连接数据库

![](http://i.imgur.com/GArOujF.png)