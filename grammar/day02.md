# day02 变量、if、while、函数、文件

---
### 1. 变量、输入输出、类型转换、算数运算符

##### 写一行代码，让用户输入自己的年龄

```python
input("请输入年龄：")
```

##### 写一行代码，打印上面获取的年龄，格式为 "年龄是 xxx"

```python
age = input("请输入年龄：")
print("年龄是{}".format(age))
```

### 2. if 语句

##### 判断下面的条件计算结果

* 1 > 2
	- False
* 2 == 2
	- True
* 2 >= 2
	- True

##### x = 1, y = 2, z = 3，判断下面的条件计算结果，

* x < y and y < z
	- True
* x > y or y < z
	- True

### 3. while 语句

##### 代码三种执行顺序是：顺序执行，选择执行，`循环执行`。

##### for 语句的完整语法是？

```python
for item in iterable:
	loop_body
```

##### 简述 for 语句的执行过程是怎样的？

- 通过`iter()`函数获取可迭代对象`iterable`的迭代器
- 对该迭代器不断调用`next()`方法，取出下一个值并赋值给`item`，然后执行`loop_body`
- 遇到`StopIteration`异常后退出

### 4. 函数

##### 函数使用参数有什么好处？

- 将其他代码块执行的结果作为参数传入，直接使用，可以减少重复代码，降低代码块之间的耦合度

##### 什么是形参，什么是实参？

- 简而言之，形参是函数定义时的参数，实参是函数调用时的参数。

### 5. 文件

##### 文件的四种操作是什么？

- `open`、 `close`、 `read`、 `write`
