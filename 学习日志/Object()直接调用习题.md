# 学习记录

![image-20220426182338518](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220426182338518.png)

Object是一个方法，返回一个对象。 Object(1)返回Number对象，相当于new Number(1)，Object(false)返回Boolean对象,相当于new Boolean(false)

构造函数的原型的constructor指向该构造函数

因此 Object(1.0).constructor就是Number构造函数

