# day09 继承、重写、多态

---
1. 定义一个 Animal 类，具备 age 属性，和 eat 方法

2. 定义一个 Cat 类，继承 Animal，并在 Cat 类提供 dance 方法

3. 使用 Cat 类创建一个对象 xiaobai，并调用 dance 方法、eat 方法，并打印 age

4. 在 Cat 类也写一个 eat 方法，并打印和 Animal 不同的内容

5. 使用 xiaobai 调用 eat 方法，验证是执行 Cat 类还是 Animal 类的 eat 方法。
    (重写是指，子类和父类有同名方法，当子类对象调用被重写的方法，执行的是子类方法)

6. 创建 Dog 类，继承 Animal，在 Dog 重写 eat 方法，并打印和 Animal 不同的内容

7. 使用 Dog 类创建对象 wangcai，调用 eat 方法，验证执行效果

8. 创建 Person 类，提供 play_with_animal 方法，参数接收 animal 对象，并在方法里调用 eat 方法

9. 使用 Person 类创建对象 laowang，调用 play_with_animal 方法，分别传递 xiaobai 和 wangcai，查看执行效果
    (多态：只要是父类对象可以工作的地方，就可以使用子类对象，并且不同子类对象会产生不同的执行效果)