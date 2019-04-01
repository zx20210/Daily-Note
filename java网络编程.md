# java网络编程

网络编程重视数据的传输（服务器）
网页编程重视与用户的交互

## 概念
1.网络：将不同区域的计算机连接到一起，分为局域网，城域网，互联网
2.地址：ip地址，确定计算机在网络上的绝对位置
3.端口号：区分计算机上的进程，长度两个字节，0-65535，共65536个

   - 在同一个协议下，端口号不能重复，不同协议下可以重复

   - 1024以下的不要使用，如80->http,21->ftp等

4.资源定位：URL统一资源定位符，URI：统一资源
5.数据的传输

   - 协议：TCP和UDP协议
      - TCP(transfer controll protocol)：先连接再通信，三次握手，面向连接，安全可靠，效率低下
      - UDP(user datagram protocol)：短信，非面向连接，效率高
   - 传输

      － 先封装
      － 后拆封

---------------

java封装的类
1.InetAddress InetSocketAddress
2.URL
3.TCP: ServerSocket Socket(服务器和客户端)
4.UDP: DatagramSocket DatagramPacket(服务器和客户端)
5.IO

--------------------

## 地址及端口
###　1.InetAddress
封装IP和DNS
实例化：
```java
InetAddress.getLocalHost();
InetAddress.getByName("ip地址|域名");
```
方法：
```java
getHostAddress()//返回ip地址
getHostName()//返回域名|本机为计算机名|如果域名可以解析返回域名否则ip地址
```
InetAddress没有封装端口
###　２.InetSocketAddress
封装了端口