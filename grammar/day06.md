# day06 变量、if、while、函数

---

### 1. 变量、输入输出、类型转换、算数运算符

##### 写一个程序，让用户输入姓名和年龄，然后打印出 "xxx 今年 xxx 岁"

```python
name = input("请输入姓名：")
age = input("请输入年龄：")
print('{}今年{}岁'.format(name, age))
```

##### 写一个程序，让用户输入两个数字，计算两个数之和，并打印

```python
first_num = input("Please enter the first number:")
second_num = input("Please enter the second number:")
print('The summation of this two numbers is {}'.format(int(first_num) + int(second_num)))
```

### 2. if 语句

##### 写一个程序，让用户输入自己的年龄，如果年龄大于 18 岁则打印可以上网，否则打印不能上网

```python
age = input("Please enter your age:")
age = int(age)
if age >= 18:
    print('Now you can go in and enjoy!')
else:
    print('Sorry, you are too young to surfing on the Internet.')
```

##### 剪刀石头布的猜拳游戏

* 用户出拳
* 电脑出拳
* 比较输赢并打印结果

```python
import random

option = {
    'a': '剪刀',
    'b': '石头',
    'c': '布',
}

result_msg = {
    'win': '你赢了',
    'draw': '平局',
    'lose': '你输了',
}


def mora(user_option):
    computer_option = random.choice(list(option.keys()))

    if user_option not in option:
        return

    if (computer_option == 'a' and user_option == 'b') or \
            (computer_option == 'b' and user_option == 'c') or \
            (computer_option == 'c' and user_option == 'a'):
        ret_option = 'win'
    elif computer_option == user_option:
        ret_option = 'draw'
    else:
        ret_option = 'lose'

    return {
        'computer_option': option.get(computer_option),
        'user_option': option.get(user_option),
        'result': result_msg.get(ret_option),
    }


if __name__ == '__main__':
    user = input("请出拳：【a】{a}，【b】{b}，【c】{c}：".format(**option))
    ret = mora(user)
    if not ret:
        print("不按套路出牌")
    else:
        print("电脑:{computer_option}\t玩家:{user_option}\n{result}".format(**ret))
```

### 3. while 语句

##### 计算数字 1-100 的累积和

```python
i = 1
sum = 0
while i <= 100:
    sum += i
    i += 1
print(sum)
```

### 4. 函数

##### 定义一个函数，要求：

* 接收两个数字作为形参
* 计算形参之和并作为函数返回值
* 调用函数，计算 11 和 22 之和

```python
def add2num(num1, num2):
    return num1 + num2

add2num(11, 22)
```

##### 定义一个函数，计算一个长方形的周长

* 接受两个参数作为长和宽
* 计算长方形的边长
* 把计算结果为函数返回值
* 调用函数，计算长为 10，宽为 5 的长方形周长，并打印

```python
def perimeter(width, height):
    return (width + height) * 2

result = perimeter(10, 5)
print(result)
```

##### 定义一个函数，计算多边形的总边长，要求

* 函数能接收任意个数的数字，作为多边形每个边的长度
* 计算所有边的总长，并作为函数返回值
* 调用函数，计算边长为 5，10，5，10，5 的五边形总边长
* 调用函数，计算边长为 10，10，10，10，5，5 的六边形总边长.

```python
def perimeter(*args):
    s = 0
    for arg in args:
        s += arg
    return s

poly5 = perimeter(5, 10, 5, 10, 5)
print(poly5)

poly6 = perimeter(10, 10, 10, 10, 5, 5)
print(poly6)
```
