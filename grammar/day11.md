# day11 Shell基础

---
#### 使用 echo 和 重定向，保存文本 "hello world" 到文件 1.txt 里

```bash
echo hello world > 1.txt
```

#### 任意找一个文件夹，使用 ls 和 管道，把文件列表送到 more 进行查看

```bash
ls | more
```

#### 使用终端命令创建文件 11.txt 12.txt 13.txt 123.txt 223.txt 323.txt

```bash
touch 11.txt 12.txt 13.txt 123.txt 223.txt 323.txt
```

#### 使用终端命令创建文件夹 abc abd

```bash
mkdir abc abd
```

#### 使用终端命令查看所有 1 开头的文件

```bash
ls | grep ^1
```

#### 使用终端命令查看所有 3.txt 结尾的文件

```bash
ls | grep 3.txt$
```

#### 使用 find 查找桌面上包含 1 的文件

```bash
find ~/Desktop/ -name "*1*"
```
