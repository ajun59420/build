# Agent主机
每个Agent主机为一个独立的服务器，用来向TeaWeb上报本服务器信息，以便于TeaWeb可以展示这些独立服务器的信息；运维人员也可以在TeaWeb上配置Agent相关信息，TeaWeb会自动同步到Agent。

## 结构
以下是一个简单的结构示例：
~~~
|-------------------|		   |------------------------|
|    				|   <-->   | Agent1(192.168.1.100)  | 
|					|		   |						|
|					|		   | App1, App2, ... 		|	   
|					| 		   |------------------------|
|					|
|					| 		   |------------------------|
|	Master(TeaWeb) 	|   <-->   | Agent2(192.168.1.101)  |
|   (192.168.1.2)	|		   |						|
|	     			|		   | App1, App2, ... 		|	   
|					| 		   |------------------------|
|					|
|					| 		   |------------------------|
|					|   <-->   |           ...          |
|-------------------| 		   |------------------------|
~~~

其中：
* `Master` - 主控制服务器，`TeaWeb`部署在此服务器上，用来接收`Agent`发送的数据、向`Agent`发送在`TeaWeb`平台上的配置；
* `Agent` - Agent主机，`TeaWeb Agent`部署在此类服务器上，接收`Master`发送的配置信息、向`Master`发送本机产生的数据。

一个`Master`可以添加多个`Agent`，实际部署时要考虑主服务器的性能，来决定最多添加多少个`Agent`。

## 本地主机
在`TeaWeb`启动时，会启动一个和`TeaWeb`同服务器的本地`Agent`，行为和一般的`Agent`一致。

## `Agent`主机信息
* 基本信息
  * `主机名` - 容易识别主机用途的名字
  * `主机地址` - 主机的IP地址
  * `ID` - 主机的ID，通常是系统随机生成
  * `密钥` - 连接Master所用的密钥
  * `允许所有的IP` - 是否限制主机程序必须在某个IP上运行，默认是不限制的
* `App（应用）` - 一个Agent上可以设置多个App，具体请看[App（应用）](App.md)。

## 安装Agent
请在这里查看[Agent安装文档](Install.md)。