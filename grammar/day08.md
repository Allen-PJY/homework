# day08 魔法方法的使用

---
1. 定义一个 `Person` 类，在 `__init__` 方法参数接受 `name` 和 `age`，并初始化对象的属性

```python
class Person(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age
```

2. 使用 `Person` 类创建 `zhangsan` 对象，并打印 `zhangsan` 的 `name` 和 `age`

```python
class Person(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age


zhangsan = Person('zhangsan', 18)
print(zhangsan.name)
print(zhangsan.age)
```

3. 在 `Person` 类添加 `__str__` 方法，在方法里返回字符串类似： `%s 的年龄是 %d`

```python
class Person(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return '{}的年龄是{}'.format(self.name, self.age)
```


4. 直接打印 `zhangsan` 对象，验证打印的数据是否是上一题定义的格式

```python
class Person(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return '{}的年龄是{}'.format(self.name, self.age)


zhangsan = Person('zhangsan', 18)
print(zhangsan)
```

5. 在 `Person` 类添加 `__del__` 方法，验证对象是在什么时候被销毁

```python
class Person(object):
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return '{}的年龄是{}'.format(self.name, self.age)

    def __del__(self):
        print("Good bye!")


zhangsan = Person('zhangsan', 18)
print(zhangsan)
```

6. 修改 `Person` 类，使用 `__new__` 方法实现单例模式，让 `Person` 类只能创建一个实例对象
```python
class Person(object):
    _instance = None

    def __new__(cls, *args, **kwargs):
        if not cls._instance:
            cls._instance = super().__new__(cls)
        return cls._instance

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return '{}的年龄是{}'.format(self.name, self.age)


zhangsan = Person('zhangsan', 18)
print(zhangsan)
print(id(zhangsan))
lisi = Person('lisi', 20)
print(lisi)
print(id(lisi))
print(zhangsan)
print(id(zhangsan))
```