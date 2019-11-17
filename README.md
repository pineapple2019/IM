# 基于qt c++的一个即时通讯软件
-----
## 项目说明
这个软件是我大二学期的一个c++课设，ui方面是仿照着pc端的wechat,由于本人不太喜欢c++的语法，所以这个软件更新的速度会很慢。

>  新增文件上传下载功能(很狗屎)，由于考虑到自己的服务器真的不行，所以服务端部分直接新创建了一个程序来对文件进行上传下载。



## 开发说明

本人负责此软件的后端部分

前端部分则由这个[靓仔](<https://github.com/MarkZ37>)编写

## 文件说明

chat -> 程序客户端源代码

service -> 服务器处理代码

testFileServer -> 文件服务器服务端源代码

serverRealse -> 服务端编译后文件夹

FileServerRealse -> 文件服务器源代码

chatRealse -> 客户端可执行文件夹

## 项目启动说明
 服务端都需要在MinGw 32bit下编译运行  (由于笔者编程能力有限，其他环境下都会出现编译错误，具体原因未知)

> 注意，service如果出现编译后不能正常执行的情况，则应该添加32bit的Mysql动态执行文件lib与dll.

客户端则需要在MSCV 2017 64bit下编译

所有笔者编译后的文件则不会出现这种情况

## 项目功能

**账号方面**

* 账号注册

* 账号登陆

**好友方面**

* 添加好友
* 查询好友
* 请求好友通知

**消息方面**

* 离线消息通知
* 在线消息

## 项目展示

>客户端方面

* 软件首页

![](https://s2.ax1x.com/2019/05/26/VElPKO.png)


* 登陆界面

![](https://s2.ax1x.com/2019/05/26/VEluxf.png)

* 主页面

![](https://s2.ax1x.com/2019/05/26/VElGIs.png)


* 聊天界面

![](https://s2.ax1x.com/2019/05/26/VElUzV.png)



> 客户端方面


![](https://s2.ax1x.com/2019/05/26/VElgRx.png)

## 技术选型

开发语言： c++
基础框架: MVC
核心技术：多线程QTcpSocket +多线程QUdpSocket + 数据库连接池
数据库： mysql

## 数据库说明

数据库文件需要加载到名字为qq数据库中，默认账号密码 root 123

数据库只有服务端有连接，分别在mysql.cpp和threadmysql.cpp中有连接信息，并没有单独出丑来做一个资源文件，耦合度很高。

## 重要说明

服务器这边我打算采用的是mvc架构，但是在最后的时候测试bug的时候发现数据库这边不允许主线程和子线程同时访问，考虑到子线程访问次数比较少，所以直接新建了一个类去让子线程直接访问数据库，打破了mvc模式，以后应该会改的。。。大概。。

## 