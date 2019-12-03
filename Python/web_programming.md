# 网络编程

## 基本概念

### IP地址

IP地址用来标记一台电脑，每台电脑的IP地址在本地局域网上是唯一的

> 每个IP地址包括网络地址和主机地址两部分<br>
> IP分为A类、B类、C类、D类、E类五种，其中D类地址用于多点广播，E类IP地址保留，仅作实验和开发用。

> **私有IP** 不能在公网使用，所以可以重复，不唯一，范围是：

> ```
> 10.0.0.0～10.255.255.255  
> 172.16.0.0～172.31.255.255  
> 192.168.0.0～192.168.255.255
> ```

> `127.0.0.1`~`127.255.255.255`用于 **回路测试**，例如`http://127.0.0.1`可以测试本机中配置的Web服务器

### IP类型

IP类型有`IPv4`和`IPv6`两种，`IPv4`为四个三位数字串，每一串从`0~255`共256个数字。

### 查看IP地址

  系统    | 命令
:-----: | --------
 MacOS  | ifconfig
 Linux  | ifconfig
Windows | ipconfig

`ifconfig`命令返回的内容中`inet`后面的数字串表示IP地址。

> `ifconfig`返回两个`inet`，其中`127.0.0.1`为回路测试地址

### ping测试

`ping`命令可以用来检测网络是否正常：

```sh
ping 192.168.1.1
```

### 端口

端口通过端口号来标记，只能是整数，范围为`0~65535`共`2^16`个。端口分为知名端口和动态端口，其中知名端口范围为`0~1023`其余为动态端口。

> 80端口分配给HTTP服务<br>
> 21端口分配给FTP服务

## socket

一台电脑上可以通过进程号`PID`唯一标识一个进程，网络层的IP地址可以唯一标识网络中的主机，传输层的"协议+端口"可以唯一标识主机中的进程(`TCP/IP`协议族)。<br>
`socket`（简称`套接字`）是进程间通信的一种方式，能实现不同主机的进程间通信。

### 创建socket

```python
import socket
socket.socket(AddressFamily, Type)
```

`AddressFamily`可以选择以下两种：

- `AF_INET`用于internet进程间通信（常用）
- `AF_UNIX`用于同一台机器进程间通信

`Type`可以选择以下两种：

- `SOCK_STREAM`流式套接字，主要用于`TCP`协议
- `SOCK_DGRAN`数据报套接字，主要用于`UDP`协议

创建一个`tcp socket`

```python
import socket

# 创建tcp的套接字
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# ...这里是使用套接字的功能（省略）...

# 不用的时候，关闭套接字
s.close()
```

创建一个`udp socket`

```python
import socket

# 创建udp的套接字
s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

# ...这里是使用套接字的功能（省略）...

# 不用的时候，关闭套接字
s.close()
```

## udp

### 发送数据

发送数据`sendto`

```python
udp_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

# 从键盘获取数据
send_data = input("请输入要发送的数据：")

# 接收地址
dest_addr = ("192.168.128.129", 8080)

# 使用套接字收发数据
udp_socket.sendto(send_data.encode("utf-8"), dest_addr)
```

### 接收数据

绑定端口号`bind`

```python
local_addr = ('', 7788)  # ip地址和端口号，ip一般不用写，表示本机的任何一个ip
udp_socket.bind(local_addr)
```

接收数据`recvfrom`

```python
recv_data = udp_socket.recvfrom(1024) #  1024表示本次接收的最大字节数
```

> `recvfrom`返回一个包含数据、IP和端口号的元祖`(b'xxxx', (192.168.128.1", 7788))`

> `windows`默认编码方式为`gbk`，`MacOS` `Linux`默认编码方式为`utf-8`

### socket流程

```python
# 1\. 创建套接字
udp_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
local_addr = ("", 7890)
udp_socket.bind(local_addr)

# 2\. 使用套接字收发数据
udp_socket.sendto("xxxx".encode("utf-8"),("192.168.128.129", 8080))
udp_socket.recvfrom(1024)

# 3\. 关闭套接字
udp_socket.close()
```

### 数据传输模式

**单工：** 只能发数据，不能收数据。<br>
**半双工：** 能发数据也能收数据，但是不能同时进行。<br>
**全双工：** 能同时收发数据。

> `socket`为全双工类型

## tcp客户端

### 基本概念

`TCP协议`传输控制协议（英语：Transmission Control Protocol，缩写为 TCP）是一种面向连接的、可靠的、基于字节流的传输层通信协议，由IETF的RFC 793定义。

`TCP协议`特点：

- 应答机制
- 超时重传
- 错误校验
- 流量控制和阻塞原理

> `UDP协议`无需建立连接，可以直接发送数据，可能丢失数据<br>
> `TCP协议`在建立连接后传输数据，不会丢失数据

### 客户端构建

## tcp下载文件
