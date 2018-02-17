# day07 面向对象基础

---
1. 定义一个 Person 类，提供 eat 方法
```python
class Person(object):
    def eat(self):
        print("I'm eating.")
```

2. 使用上面的 Person 类创建一个 zhangsan 对象，并调用 eat 方法
```python
class Person(object):
    def eat(self):
        print("I'm eating.")


zhangsan = Person()
zhangsan.eat()
```

3. 为 zhangsan 对象添加 age 属性，值为 18。
```python
class Person(object):
    def eat(self):
        print("I'm eating.")


zhangsan = Person()
zhangsan.age = 18
```

4. 使用上面的 zhangsan 对象打印 age 的值
```python
class Person(object):
    def eat(self):
        print("I'm eating.")


zhangsan = Person()
zhangsan.age = 18
print(zhangsan.age)
```

5. 在 Person 类提供给 talk 方法，在方法里使用 self 获取 age 并打印： 我今年 %d 岁
```python
class Person(object):
    def eat(self):
        print("I'm eating.")

    def talk(self):
        print("我今年{}岁".format(self.age))
```

6. 使用 zhangsan 对象调用 talk 方法
```python
class Person(object):
    def eat(self):
        print("I'm eating.")

    def talk(self):
        print("我今年{}岁".format(self.age))


zhangsan = Person()
zhangsan.age = 18
zhangsan.talk()
```
