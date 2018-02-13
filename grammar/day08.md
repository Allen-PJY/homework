# day08 魔法方法的使用

---
1. 定义一个 Person 类，在 __init__ 方法参数接受 name 和 age，并初始化对象的属性

2. 使用 Person 类创建 zhangsan 对象，并打印 zhangsan 的 name 和 age

3. 在 Person 类添加 __str__ 方法，在方法里返回字符串类似： %s 的年龄是 %d

4. 直接打印 zhangsan 对象，验证打印的数据是否是上一题定义的格式

5. 在 Person 类添加 __del__ 方法，验证对象是在什么时候被销毁

6. 修改 Person 类，使用 __new__ 方法实现单例模式，让 Person 类只能创建一个实例对象