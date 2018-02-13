# day04

---
### 练习1

变量、输入输出、类型转换、算数运算符

1. 如何把字符串 '123' 转换成数字

2. Python 计算 -7 // 3 的结果是多少

### 练习2

if 语句

1. 条件 (1 < 2) or ((2 == 3) and (4 == 4)) 的计算结果是 True 还是 False

2. 分析下面代码的执行结果
```Python
age = 10

if age >= 100:
    print("老人家，请受晚辈一拜")

print("程序结束")
```

### 练习3

while 语句

1. 分析下面代码的执行结果
```Python
name = 'zhang'

for x in name:
    if x == 'a':
        print('不能使用字母 a')
        break
    
    print('获取到字母 %s' % x)
```

2. 上面的 for 循环代码里，if 判断总共执行了多少次？

### 练习4

函数

2. 分析下面代码的执行结果
```Python
def func(tmp):
    tmp = 22
    print('tmp = %d' % tmp)

num = 11
func(num)
print('num = ' % num)
```
   
2. 分析下面代码的执行结果
```Python
def func(tmp):
    tmp.append(22)
    print('tmp = %s' % tmp)

ls = [11]
func(ls)
print('ls = ' % ls)
```

### 练习5

文件

1. 使用 w 模式打开文件的效果是什么
