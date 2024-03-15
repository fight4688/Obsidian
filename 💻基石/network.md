# mess
ways of wall:DNS污染，连接重置（ip黑名单）,端口阻断

最简单方式：连接国外服务器（中间人）
vpn：共享中间人（飞机和机场配套），只给出隧道
机场：只是服务器（独立机场），包配送服务
安全性和速度

v2ray软件：飞机
白名单是绕过大陆，黑名单是全局

vps：（通过容器实现）
vpn是通过隧道传递,特征明显,机场是本地加密打包
![](../asset🧰/Pasted%20image%2020240131193658.png)

1. **物理层（Physical Layer）：**
   - Ethernet
   - USB
   - HDMI
   - IEEE 802.11 Wi-Fi
   - RS-232
   - RS-485
2. **数据链路层（Data Link Layer）：**
   - Ethernet（IEEE 802.3）
   - Wi-Fi（IEEE 802.11）
   - PPP（Point-to-Point Protocol）
   - HDLC（High-Level Data Link Control）
   - ATM（Asynchronous Transfer Mode）
3. **网络层（Network Layer）：**
   - IP（Internet Protocol）
   - ICMP（Internet Control Message Protocol）
   - ARP（Address Resolution Protocol）
   - RARP（Reverse Address Resolution Protocol）
   - OSPF（Open Shortest Path First）
   - BGP（Border Gateway Protocol）
4. **传输层（Transport Layer）：**
   - TCP（Transmission Control Protocol）
   - UDP（User Datagram Protocol）
   - SCTP（Stream Control Transmission Protocol）
5. **会话层（Session Layer）：**
   - NetBIOS（Network Basic Input/Output System）
   - RPC（Remote Procedure Call）
6. **表示层（Presentation Layer）：**
   - ASCII（American Standard Code for Information Interchange）
   - JPEG（Joint Photographic Experts Group）
   - MPEG（Moving Picture Experts Group）
   - SSL/TLS（Secure Sockets Layer/Transport Layer Security）
7. **应用层（Application Layer）：**
   - HTTP（Hypertext Transfer Protocol）
   - HTTPS（HTTP Secure）
   - FTP（File Transfer Protocol）
   - SMTP（Simple Mail Transfer Protocol）
   - DNS（Domain Name System）
   - DHCP（Dynamic Host Configuration Protocol）
   - SNMP（Simple Network Management Protocol）
   - RTP (Real-time Transport Protocol)

****************

# 电路交换，分组交换，报文交换

![](../asset🧰/Pasted%20image%2020240312230438.png)
![](../asset🧰/Pasted%20image%2020240312230508.png)
计算机的信息传递是突发式的

# 计算机网络的定义和分类

（可编程硬件的集合）
![](../asset🧰/Pasted%20image%2020240312230533.png)

# 计算机网络性能指标

速率是设备发出数据的速率，带宽就是线路上的数据在单位时间上的数量

（线路速率）宽带和窄带比特速率一样，宽带比特流更密集

总时延=分组延迟+（n+1)传播延迟（可忽略）+n个路由器的发送延迟

主机速率、路由速率、带宽有时近似相等（单位一样）

![](../asset🧰/Pasted%20image%2020240312230743.png)

![](../asset🧰/Pasted%20image%2020240312230822.png)

# 计算机网络体系结构

## 常见体系结构

![](../asset🧰/Pasted%20image%2020240312231130.png)

![](../asset🧰/Pasted%20image%2020240312231123.png)

## 体系结构分层的必要性

![](../asset🧰/Pasted%20image%2020240312231201.png)

## 分层思想例子

在传输过程中剥离到ip包

在物理层以比特流形式传输

![](../asset🧰/Pasted%20image%2020240312231348.png)


## 体系结构专业术语

SDU是未经处理的，PDU是经过服务原语处理的

![](../asset🧰/Pasted%20image%2020240312231339.png)

![](../asset🧰/Pasted%20image%2020240312231329.png)

# 物理层

## 基本概念

物理层协议众多，只需掌握基本概念

![](../asset🧰/Pasted%20image%2020240312231430.png)

## 传输媒体

非导引型统称为电磁波

![](../asset🧰/Pasted%20image%2020240312231726.png)

## 传输方式

异步是字节间隔异步，不是比特间隔

![](../asset🧰/Pasted%20image%2020240312231719.png)

## 编码与调制

QAM16？

![](../asset🧰/Pasted%20image%2020240312231634.png)

## 信道容量与信道复用

码元包含比特数=log2（波形数）

传输速率=波特率*码元包含比特数

奈氏准则和香农公式分别是无噪声（理想情况）和有噪声情况的计算公式

波分复用是光传输

![](../asset🧰/Pasted%20image%2020240312233226.png)

![](../asset🧰/Pasted%20image%2020240312233214.png)

# 数据链路层

![](../asset🧰/Pasted%20image%2020240312233200.png)

帧是数据链路层的协议数据单元(PDU)

## 三个重要问题

![](../asset🧰/Pasted%20image%2020240312233151.png)

### 封装成帧和透明传输

帧的首尾部实现帧定界

![](../asset🧰/Pasted%20image%2020240312233138.png)

![](../asset🧰/Pasted%20image%2020240312233115.png)

![](../asset🧰/Pasted%20image%2020240312233105.png)

### 差错检测

奇偶校验和循环冗余校验

若出现偶数个误码，则奇偶校验无法检错

![](../asset🧰/Pasted%20image%2020240312233047.png)

![](../asset🧰/Pasted%20image%2020240312233038.png)

### 可靠传输

无线链路必须实现可靠传输

![](../asset🧰/Pasted%20image%2020240312233030.png)

可靠传输并不局限于数据链路层

![](../asset🧰/Pasted%20image%2020240312233019.png)

停止-等待的实现：

1. 确认，否认和重传
2. 超时重传
3. 数据分组编号
4. 确认分组编号

![](../asset🧰/Pasted%20image%2020240312233009.png)

回退N帧使用了滑动窗口算法

发送窗口取值不能超过取值上限，否则会出现分组重复

![](../asset🧰/Pasted%20image%2020240312233001.png)

选择重传类似指针

![](../asset🧰/Pasted%20image%2020240312232950.png)

## 点对点协议(PPP)

用于串行传输

![](../asset🧰/Pasted%20image%2020240312232941.png)

![](../asset🧰/Pasted%20image%2020240312232931.png)

![](../asset🧰/Pasted%20image%2020240312232921.png)

## 以太网
分为共享式和交换式
### 网络适配器和MAC地址

网络适配器即网卡，需要网卡才能接入以太网

MAC：medium access control

![](../asset🧰/Pasted%20image%2020240312232906.png)

![](../asset🧰/Pasted%20image%2020240312232848.png)

![](../asset🧰/Pasted%20image%2020240312232839.png)

争用期，最小帧长和最大帧长

单程传播时延的两倍就是争用期（碰撞窗口）

最小帧长就是能在信道上传输的数据

![](../asset🧰/Pasted%20image%2020240312232824.png)

![](../asset🧰/Pasted%20image%2020240312232814.png)

![](../asset🧰/Pasted%20image%2020240312232742.png)

退避算法和信道利用率

![](../asset🧰/Pasted%20image%2020240312232730.png)

帧长度尽量大，信道长度尽量小，可以尽可能避免碰撞

### 使用集线器的共享式以太网

集线器工作在物理层，采用星型拓扑结构

### 在物理层拓展以太网

站点可以是一个办公室

由转发器到光纤调制解调器

区分集线器，转发器，光纤调制解调器

### 在数据链路层拓展以太网

网桥工作在数据链路层，能查找转发表
网桥通过原地址和端口号进行自学习
通过最小生成树避免环路
## 共享式以太网
不使用集线器，只使用交换机的以太网就是共享式以太网

![](../asset🧰/Pasted%20image%2020240312232716.png)

### 以太网交换机

交换机：高级保安，就是高级网桥（多接口网桥）

交换机可盲目或明确转发，集线器只能盲目转发

### 共享式和交换式以太网对比

交换式转发效率更高，且能避免碰撞

### 以太网的MAC帧格式

![](../asset🧰/Pasted%20image%2020240312232705.png)

## 虚拟局域网(VLAN)概述

是为了替代路由器隔离广播域，防止广播风暴

虚拟局域网不是网，是虚拟技术（容器？），一般通过端口实现(802.1Q帧）

## VLAN实现机制

![](../asset🧰/Pasted%20image%2020240312232653.png)

## 以太网的发展

![](../asset🧰/Pasted%20image%2020240312232642.png)

## 无线局域网的组成

有固定基础设施和无固定基础设施的自组织网络（需要使用网关）

![](../asset🧰/Pasted%20image%2020240312232630.png)

## 无线局域网的物理层

![](../asset🧰/Pasted%20image%2020240312232615.png)

## 无线局域网的数据链路层

由于隐蔽站问题，将碰撞检测改为碰撞避免

帧间间隔和短帧间间隔

![](../asset🧰/Pasted%20image%2020240312232554.png)

## 无线局域网的MAC帧

无线局域网有三种帧：数据，控制，管理（管理加入退出ap）

![](../asset🧰/Pasted%20image%2020240312232541.png)

# 网络层

分组转发和路由选择，更像是传输的过程

![](../asset🧰/Pasted%20image%2020240312232527.png)

## 网际协议ip

![](../asset🧰/Pasted%20image%2020240312232513.png)

## IPV4

![](../asset🧰/Pasted%20image%2020240312232501.png)

凑值法有时比除数取余法能更快将十进制数转化为二进制数

### 分类编址

由网络号和主机号组成，分为ABC三类

区分127.0.0.1和0.0.0.0

容易造成大量浪费

减去网络地址和广播地址

![](../asset🧰/Pasted%20image%2020240312232449.png)

### 划分子网

通过占用主机号进行主网划分

区分网络和主机

目前一般使用默认子网掩码

![](../asset🧰/Pasted%20image%2020240312232435.png)

### 无分类编址

使用网络前缀和主机号，地址掩码有时通过斜线记法表示

### 应用规划

![](../asset🧰/Pasted%20image%2020240312232422.png)

### 对比MAC帧

IP：新疆->天津

帧：新疆->宁夏->陕西->河北->天津

### 数据报首部格式

数据载荷必须是八字节，否则会造成数据报片偏移不是整数

![](../asset🧰/Pasted%20image%2020240312232408.png)

标志有MF（是否还有）和DF（可否再分）

区分首部和数据载荷

使用首部检验和来进行检验，在IPV6中被取消

## ARP协议
通过ip找到MAC地址（打电话询问地址并存储在ARP表中）
定期删除，不可跨网络
## IP数据报发送流程

网关工作在网络间，路由器工作在网络中（分练和配送中心）

不同网络通过路由器隔开

![](../asset🧰/Pasted%20image%2020240312232354.png)

## 静态路由配置

就是记录地址

默认路由类似于通配符

可以记录特定主机路由

## 路由选择协议

静态和动态

三个特点：自适应，分布式，分层次
![](../asset🧰/Pasted%20image%2020240312232335.png)

## 路由信息协议RIP

使用距离向量，相同可实现负载均衡，最大为16

![](../asset🧰/Pasted%20image%2020240312232257.png)
![](../asset🧰/Pasted%20image%2020240312232315.png)

## 开放最短路径有限OSPF

基于链路，使用Dijkstra算法
![](../asset🧰/Pasted%20image%2020240312232239.png)

通过分组建立数据库从而实现Dij算法

![](../asset🧰/Pasted%20image%2020240312232223.png)

## 边界网关协议BGP

不同AS代价不同，使用BGP找出较好路由

![](../asset🧰/Pasted%20image%2020240312232103.png)

## 路由器工作原理

![](../asset🧰/Pasted%20image%2020240312232046.png)

## 国际控制报文协议ICMP

ping的使用原理

除了地址展示以外的快递信息（异常？）

![](../asset🧰/Pasted%20image%2020240312232030.png)

## VPN和NAT

隐藏收货人姓名和货物

NAT：邮政编码

![](../asset🧰/Pasted%20image%2020240312232014.png)

NAT必须由内部网发起

## IP多播技术

多播：定向传递给多台主机

适合用于内容分发

![](../asset🧰/Pasted%20image%2020240312231955.png)

### 局域网硬件多播

通过MAC映射执行多播，可能造成重复，因此还需在网际层进行过滤

![](../asset🧰/Pasted%20image%2020240312231930.png)

### 因特网IP多播两种协议

IP多播数据包封装在以太网帧中
IGMP判断是否需要到达，多播路由选择协议构建最小树

![](../asset🧰/Pasted%20image%2020240312231832.png)

类似于快递社群
多播路由：基于源树和基于组共享树
## 移动IP技术
蜂窝网络
旅游时，请当地代送快递
![](../asset🧰/Pasted%20image%2020240312235755.png)
## IPV6
![](../asset🧰/Pasted%20image%2020240313124407.png)
### 基本首部
流可以保证==实时性和连续性==
![](../asset🧰/Pasted%20image%2020240313125715.png)
![](../asset🧰/Pasted%20image%2020240313125804.png)
扩展首部使得首部在纯属过程中不需要被路由器检查
### IPV6地址
==目的地址==有三种类型：单播,多播(广播是单播的特殊情况)，任播
数量足够多，不使用ARP协议
![](../asset🧰/Pasted%20image%2020240313135031.png)
### 过渡方法
双协议栈和隧道技术：翻译和附带
### ICMPv6
![](../asset🧰/Pasted%20image%2020240313135851.png)
ICMPv6报文需要封装在IPv6数据报中
### 软件定义网络SDN
可编程网络
![](../asset🧰/Pasted%20image%2020240313144816.png)
将地址信息从路由器==转为远程主机处理==，更加高效，路由器只需传送信息（转发分组）：将控制层面和数据层面分离

将路由器变为OpenFlow交换机
# 运输层
属于计算机内部的范畴，端到端服务
是==进程之间==的通信
## 两个重要协议
![](../asset🧰/Pasted%20image%2020240313154657.png)
![](../asset🧰/Pasted%20image%2020240313154632.png)
## 端口号，复用和分用
端口号只具有本地意义
端口号是外部，进程号是内部
端口：服务器入口，进程是服务器运行的程序

多个进程（通过端口号表示）通过运输层利用一个运输层协议发送数据称为复用，反之则称为分用
![](../asset🧰/Pasted%20image%2020240313165608.png)
## UDP和TCP
![](../asset🧰/Pasted%20image%2020240313170526.png)
## TCP
### 首部格式
![](../asset🧰/Pasted%20image%2020240313174959.png)
### 运输连接管理
>[!握手和挥手]
>
三次握手：去逛街；我准备好了；我也准备好了
==是为了防止失效的TCP请求报文段传送到了TCP服务器进程==
>
四次挥手：分手吧；好吧；我真的走了；走吧
防止客户端无法接受到TCP服务器的断开连接请求造成资源浪费

通过保活计时器防止出现故障时一直打开连接
### 流量控制
通过滑动窗口解决：接收方根据自己的接收能力控制发送方的发送速率。
非零窗口通知防止造成死锁
### TCP拥塞控制和网际层拥塞控制
堵车（死锁）
拥塞控制基本方法
+ 开环
+ 闭环
	+ 显示表示
	+ 隐示表示

接受窗口和拥塞窗口：接收方的承受能力和链路的承受能力
==发送窗口取堵塞窗口和接收窗口的较小值==
TCP的四种拥塞控制方法（ssthresh是慢开始门限）
1. 慢开始是指开始时数据少，而不是增长慢（指数增长）
2. 拥塞避免算法（线性增长），以==超时重传==作为重启点
3. 快重传，不要等待，继续发送以获得反馈
4. 快恢复：改为ssthresh的的一半并执行拥塞避免

![](../asset🧰/Pasted%20image%2020240313231510.png)
TCP和网际层的拥塞关系：路由器进行尾部丢弃（队列）
### 可靠传输
滑动窗口，累积确认
### 超时重传
![](../asset🧰/Pasted%20image%2020240314160720.png)
### 选择确认
并不需要累积确认
# 应用层
通过应用进程交互实现特定网络问题，是具体服务（信，托运，快递等）
![](../asset🧰/Pasted%20image%2020240314161505.png)
## 客户-服务器方式和对等方式
P2P更节约资源
![](../asset🧰/Pasted%20image%2020240314195618.png)
## 动态主机配置协议DHCP
==中心化思想==，通过单台高性能主机为多台主机提供服务（同DNS）
需要二手书；我这里有；现在过来拿；可以
不由主机自己分配，而是==由中心服务器分配==，省去了手动配置
![](../asset🧰/Pasted%20image%2020240314200609.png)
使用中继代理时，需要给路由器配置DHCP服务器的IP地址
## 域名系统DNS
![](../asset🧰/Pasted%20image%2020240314205049.png)
## 文件传输协议FTP
命令控制于数据传输分离
![](../asset🧰/Pasted%20image%2020240314211114.png)
## 电子邮件
传统邮件服务器并非运行在本地,本地只有用户代理,故暂时不能创建文件夹进行分类等操作(浏览器服务器基于http,可以操作）
![](../asset🧰/Pasted%20image%2020240314224110.png)
## 万维网
万维网不是网，是一种应用
传输的是特殊文本（超文本）
![](../asset🧰/Pasted%20image%2020240315000926.png)
# 网络安全
攻击分为被动攻击（监听数据）和主动攻击
![](../asset🧰/Pasted%20image%2020240315102851.png)
## 密码学
关注的是计算上安全而不是理论上不可破
### 对称密钥
1. DES
2. Triple DES
3. AES
![](../asset🧰/Pasted%20image%2020240315103833.png)
### 公钥
速度相对较慢，常用于==建立会话==，用于分发对称会话密钥
公钥不是钥，是一个包，只进不出（类似于邮箱）
### 报文摘要和鉴别码
![](../asset🧰/Pasted%20image%2020240315114327.png)
### 数字签名
![](../asset🧰/Pasted%20image%2020240315115915.png)
### 实体鉴别
密钥分发是实体鉴别的基础
实体鉴别后可进入网站，网站中存有session
### 密钥分发
KDC发布密钥，CA发布密钥证书
### 访问控制
首先进行身份鉴别（准许进入），然后进行访问控制（等级划分）
上写下读（上下指的是客体（被访问部分））
