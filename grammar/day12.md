# day12 UDP、TCP

---
#### 1. UDP 客户端

```python
from socket import *

# 1. 创建套接字
udp_socket = socket(AF_INET, SOCK_DGRAM)

# 2. 对方地址
dest_addr = ('127.0.0.1', 6666)

# 3. 发送内容
send_msg = input('请输入发送的数据：')
udp_socket.sendto(send_msg.encode('gbk'), dest_addr)

# 4. 关闭套接字
udp_socket.close()
```

#### 2. UDP 服务端

```python
from socket import *

# 1. 创建套接字
udp_socket = socket(AF_INET, SOCK_DGRAM)

# 2. 本地地址
local_addr = ('127.0.0.1', 9999)
udp_socket.bind(local_addr)

# 3. 接受内容
data, dest_addr = udp_socket.recvfrom(1024)  # 最大接受1024Bytes
print(data.decode('gbk'))
print(dest_addr)

# 4. 关闭套接字
udp_socket.close()
```

#### 3. TCP和UDP的区别

	- TCP 是**面向连接**的，双方必须三次握手后才能通信，结束时四次挥手，而UDP 是**面向广播**的，
	- TCP 传输是可靠的，采用
		- **发送应答机制** （SYN, ACK+SYN, ACK）
		- **超时重传**
		- **错误校验**  重发丢失，舍弃重复，保证无差错
		- **流量和阻塞控制**  有序数据传输

#### 4. TCP 客户端

```python
from socket import *

# 1. 创建套接字
tcp_client_socket = socket(AF_INET, SOCK_STREAM)

# 2. 服务器地址
server_addr = ('127.0.0.1', 6666)

# 3. 连接服务器
tcp_client_socket.connect(server_addr)

# 4. 发送内容
send_msg = input('请输入发送的数据：')
tcp_client_socket.send(send_msg.encode('gbk'))

# 5. 接受内容
recv_msg = tcp_client_socket.recv(1024).decode('gbk')
print(recv_msg)

# 6. 关闭套接字
tcp_client_socket.close()
```

#### 5. TCP 服务端

```python
from socket import *

# 1. 创建套接字
tcp_server_socket = socket(AF_INET, SOCK_STREAM)

# 2. 服务器地址
server_addr = ('127.0.0.1', 6666)

# 3. 绑定
tcp_server_socket.bind(server_addr)

# 4. 监听
tcp_server_socket.listen(128)

# 5. 生成客户端套接字
client_socket, client_addr = tcp_server_socket.accept()

# 6. 接受内容
recv_msg = client_socket.recv(1024).decode('gbk')
print(recv_msg)

# 7. 发送内容
send_msg = input('请输入发送的数据：')
client_socket.send(send_msg.encode('gbk'))

# 8. 关闭套接字
client_socket.close()
tcp_server_socket.close()
```

#### 6. TCP 通信过程
![TCP 三次握手和四次挥手](http://p4emt3ysm.bkt.clouddn.com/tcp.png)
