# day01

---	
### 练习1 变量、输入输出、类型转换、算数运算符

1. Python 里基本变量类型有哪些？
	- 数字(number)、字符串(str)、列表(list)、元组(tuple)、字典(dict)、集合(set)
	- 其中数字有，整型(int)、浮点型(float)、布尔型(bool)、py2中还包含长整型(long)

2. 说出 3 个 Python 里的关键字
	- `class`、 `def`、 `return`


### 练习2 if 语句

1. if 语句的三种格式是什么
	- `if else`
	- `if elif`
	- `if`

2. if 语句三种格式的执行过程是怎样的
	- `if else`
		- `条件1`成立执行`语句1`，不成立执行`语句2`
	- `if elif`
		- `条件1`成立，执行`语句1`，`条件2`成立，执行`语句2`
	- `if`
		- `条件1`成立执行`语句1`

### 练习3 while 语句

1. while 语句的格式是什么
```python
while condition:
	code block
```

2. while 语句的执行过程是怎样的
	- `condition`成立时执行`code block`
	- 执行完成再次判断`condition`, 如果成立仍然执行`code block`
	- 重复第二步，直到`condition`不再成立

### 练习4 函数

1. 定义函数的基本格式是什么
```python
def func():
	code block
	return result
```

2. 调用函数的基本格式是什么
```python
func()
```

### 练习5 文件

1. 简述文件有什么用
	- 把数据存储起来，程序再次执行的时候可以直接使用，不必重新制作一份
