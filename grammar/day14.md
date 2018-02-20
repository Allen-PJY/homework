# day14 正则 HTTP协议

---
### 1. 正则

##### 1.1 获取到 abc123efg456hij 里的所有数字，并打印
```python
import re

my_str = 'abc123efg456hij'
ret = re.findall(r'\d+', my_str)
for i in ret:
    print(i)
```

##### 1.2 匹配合法的ip地址

```python
import re

source_ip = '192.168.1.1'
p = r'((1[0-9][0-9]\.)|(2[0-4][0-9]\.)|(25[0-5]\.)|([1-9][0-9]\.)|([0-9]\.))'
q = r'((1[0-9][0-9])|(2[0-4][0-9])|(25[0-5])|([1-9][0-9])|([0-9]))'
pattern = p + '{3}' + q + '$'
pattern = re.compile(pattern)
ret = re.match(pattern, source_ip)
if ret:
    print(ret.group(0))
```

##### 1.3 匹配所有合法的Python标识符
```python
import re

source = ''
pattern = r'[a-zA-Z_][a-zA-Z_0-9]*$'
ret = re.match(pattern, source)
if ret:
    print(ret.group(0))
```

### 2. HTTP协议

##### 2.1 HTTP 协议的请求头，第一行内容包含什么？

- `GET / HTTP/1.1`
- `请求方式` `路径` `协议及版本`

##### 2.2 HTTP 协议的响应头，第一行内容包含什么？

- `HTTP/1.1 200 OK`
- `协议及版本` `状态码` `状态说明`

##### 2.3 简单描述，处理 HTTP 的长连接有什么注意点

- 长连接可以省去很多的TCP的建立和关闭操作，节约网络资源和缩短响应时间
- 如果客户端频繁请求，那么使用长连接更好
- 长连接需要一些策略进行管理，如关闭长时间没有读写的客户端连接、限制每个客户端最大连接数
- 因此web网站的http服务可以使用短链接，来减少服务端的资源消耗。
- 即并发量大、无需频繁访问的情况下，使用短链接更好
