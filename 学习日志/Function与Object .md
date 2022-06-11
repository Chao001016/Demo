![1653980027630](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1653980027630.png)

f = new Function()

o = new Object()

##### 所有的构造函数都是Function的实例

因此 Object.getPrototypeOf(Object) === Function.prototype

##### 所有对象的都是Object的实例，Object的原型对象除外

Object.getPrototypeOf(o) === Object.prototype

Object.getPrototypeOf(Object.prototype) === null

##### 所有的构造函数都有原型对象