
# 1.	IEEE 802.11协议族成员
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625155359629.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
# 2.	频谱划分
WiFi总共有14个信道，如下图所示：![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625170702360.PNG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)

 - IEEE 802.11b/g标准工作在2.4G频段，频率范围为2.400—2.4835GHz，共83.5M带宽
 - 划分为14个子信道
 - 每个子信道宽度为22MHz
 - 相邻信道的中心频点间隔5MHz
 - 相邻的多个信道存在频率重叠(如1信道与2、3、4、5信道有频率重叠)
 - 整个频段内只有3个（1、6、11）互不干扰信道
# 3.	802.11网络的基本元素
## 3.1	BSS(Basic Service Set)
 - Stations (STA)：任何的无线终端设备 
 - AP （Access Point）：一种特殊的STA
 
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019062516094498.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)

## 3.2	DS(Distribution System,分布式系统)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625160954660.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
## 3.3	SSID(Service Set ID 服务集识别码)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625161005190.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
## 3.4	ESS(Extended Service Set,采用相同的SSID的多个BSS形成的更大规模的虚拟BSS)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625161013203.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
# 4.	802.11MAC层工作原理
802.11MAC层负责客户端与AP之间的通讯。主要功能包括：扫描、接入、认证、加密、漫游和同步。

 ## 4.1	802.11MAC 报文类型
 ### 4.1.1 数据帧
 用户的数据报文
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625165144569.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
 ### 4.1.2	控制帧
 协助发送数据帧的控制报文，例如：RTS、CTS、ACK等
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/2019062516520872.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
 RTS和CTS用于信道预约，CF-End+CF_ACK和ACK用于确认正确接收到帧。

 - ACK帧
 ![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625165320651.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)

 ### 4.1.3	管理帧
负责STA和AP之间的能力级的交互，认证、关联等管理工作。例如：Beacon、Probe、Association及Authentication等
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625165356446.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70) 
ATIM：Announcement Traffic Indication Message，ATIM仅在ATIM窗口期间传送，ATIM没有负载。
## 4.2	用户接入管理过程
STA (工作站）启动初始化、开始正式使用、AP 传送数据幀之前，要经过三个阶段才能接入:

 - 扫描(Scaning) 
 - 认证(Authentication) 
 - 关联(Association) 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625162140626.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
### 4.2.1	Scaning
802.11MAC 使用Scanning功能来完成Discovery
 - 寻找和加入一个网络
 - 当STA漫游时寻找一个新的AP

Scaning功能的两种方式

 - Passive Scanning
通过侦听AP定期发送的Beacon帧来发现网络。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625162920806.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
 - Active Scanning
在每个信道上发送Probe request报文，从Probe Response中获取BSS的基本信息。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625162931732.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
### 4.2.2	Authentication
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625163219723.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
### 4.2.3	Association
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625163230736.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
# 5.AP种类
FAT AP和FIT AP比较如下图所示：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625172454838.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
# 6.	802.11帧格式
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625163908258.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
## 6.0 OSI模型
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190626110953460.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
## 6.1	802.11 MAC Header（MAC头）
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019062611092168.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
### 6.1.1	Frame Control（帧控制域）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190626111511285.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNjE3ODY2OA==,size_16,color_FFFFFF,t_70)
 • Protocol Version（协议版本）：通常为0；
     • Type（类型域）和Subtype（子类型域）：共同指出帧的类型；
     • To DS：表明该帧是BSS向DS发送的帧；
     • From DS：表明该帧是DS向BSS发送的帧；
     • More Frag：用于说明长帧被分段的情况，是否还有其它的帧；
     • Retry（重传域）：用于帧的重传，接收STA利用该域消除重传帧；
     • Pwr Mgt（能量管理域）：1：STA处于power_save模式；0：处于active模式；
     • More Data（更多数据域）：1：至少还有一个数据帧要发送给STA ；
     • Protected Frame： 1：帧体部分包含被密钥套处理过的数据；否则：0；
     • Order（序号域）：1：长帧分段传送采用严格编号方式；否则：0。

### 6.1.2	Duration/ID（持续时间/标识）
表明该帧和它的确认帧将会占用信道多长时间；对于帧控制域子类型为：Power Save-Poll的帧，该域表示了STA的连接身份（AID, Association Indentification）。

### 6.1.3	Address（地址域）
Address（地址域）：源地址（SA）、目的地址（DA）、传输工作站地址（TA）、接收工作站地址（RA），SA与DA必不可少，后两个只对跨BSS的通信有用，而目的地址可以为单播地址（Unicast address）、多播地址（Multicast address）、广播地址（Broadcast address）。

### 6.1.4	Sequence Control（序列控制域）
Sequence Control（序列控制域）：由代表MSDU（MAC Server Data Unit）或者MMSDU（MAC Management Server Data Unit）的12位序列号（Sequence Number）和表示MSDU和MMSDU的每一个片段的编号的4位片段号组成（Fragment Number）。

## 6.2	Frame Body（帧体部分）
包含信息根据帧的类型有所不同，主要封装的是上层的数据单元，长度为0~2312个字节，可以推出，802.11帧最大长度为：2346个字节；

## 6.3	FCS（校验域）
包含32位循环冗余码。

## 6.4	地址格式
1) 方案一：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625164433790.png)
A和B 在同一个IBSS，A->B (Ad hoc无线自组网中的数据帧的地址格式)。

2) 方案二：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625164440231.png)
从AP发出的无线数据帧中的地址格式。

3) 方案三：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190625164447676.png)
发到AP的无线数据帧中的地址格式。

4) 方案四：
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019062516445744.png)
通过无线分布系统传输的无线数据帧中的地址格式。

# 7.	AP种类

FAT AP和FIT AP比较如下图所示：
