# day13 多任务

---
#### 按照你的理解，描述进程、线程、协程的特点
- 进程
	- 占用资源最多，切换效率低，进程之间全局变量独立，是资源分配的单位，CPU核数多时可以是并行
- 线程
	- 占用资源中等，切换效率中，线程之间全局变量共享，是系统调度的单位，CPU核数多时可以是并行
- 协程
	- 占用资源最少，切换效率高，协程处在一个线程中，是并发

#### 使用进程实现两个函数同时运行

```python
from multiprocessing import Process
import time


def p_func():
    for i in range(5):
        print('p_func-{}'.format(i))
        time.sleep(1)


def m_func():
    for i in range(5):
        print('m_func-{}'.format(i))
        time.sleep(1)


if __name__ == '__main__':
    p = Process(target=p_func)
    p.start()
    m_func()
```

#### 使用线程实现两个函数同时运行

```python
from threading import Thread
import time


def t_func():
    for i in range(5):
        print('t_func-{}'.format(i))
        time.sleep(1)


def m_func():
    for i in range(5):
        print('m_func-{}'.format(i))
        time.sleep(1)


if __name__ == '__main__':
    t = Thread(target=t_func)
    t.start()
    m_func()
```

#### 使用 gevent 实现两个函数同时运行

```python
import gevent
from gevent import monkey
import time

monkey.patch_all()  # 程序执行到需要等待操作时，gevent自动切换


def g1_func():
    for i in range(5):
        print('g1_func-{}'.format(i))
        time.sleep(1)


def g2_func():
    for i in range(5):
        print('g2_func-{}'.format(i))
        time.sleep(1)


if __name__ == '__main__':
    gevent.joinall([
        gevent.spawn(g1_func),
        gevent.spawn(g2_func)
    ])
```

#### 使用 yield 函数实现斐波那契生成器， for 遍历能够生成 10 个斐波那契数字